# Dynamic IP Management

A collection of bash executables that can be used to publish the external IP address of a device to a specific location, most likely on a remote server, and distribute it from there to the another place for further use.

## Publishers

Publishers are meant to read the external IP address of a device and publish it to another location, for example, using an SSH connection to write the IP address into a file on a remote server.

### SSH to File Publisher

The SSH to File Publisher publishes your current external ip address to a file on a remote server using an SSH connection.

#### Usage
```bash
./publisher-ssh-to-file [options...] hostname
```

#### Options
```
-u, --user      The user that is used for the SSH connection.
                (Default: None)
-f, --file      The file where your current external IP is written to on the remote server.
                You may need to use quotes if the file path contains a space.
                (Default: /tmp/dynamic-ip)
```

## Distributors

Distributors are meant to retrieve the external IP address from a specific location and distribute it to another place for further use, for example, reading the IP address from a file and adding it as an entry to `/etc/hosts`.

### File to Hosts Distributor

The File to Hosts Distributor reads the content of a file, preferably an IP address, and writes it as host to `/etc/hosts`.
If there already exists an host entry with the same name it will be replaced. 

This scripts expects the content of the file to be an IP address.

#### Usage
```bash
./distributor-file-to-hosts [options...]
```

#### Options
```
-h, --host      The name of the host that gets added to `/etc/hosts`.
                (Default: my-host)
-f, --file      The file which content is read.
                You may need to use quotes if the file path contains a space.
                (Default: /tmp/dynamic-ip)
```
