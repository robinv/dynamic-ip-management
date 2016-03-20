# Dynamic IP Management

A collection of bash executables to manage your dynamic IP

## SSH Publisher

The SSH Publisher publishes your current external ip address to a file on a remote server using a SSH connection.

### Usage
```bash
./publisher-ssh [options...]
```

### Options
```
-h, --host  The host that is used for the SSH connection. (Default: 127.0.0.1)
-u, --user 	The user that is used for the SSH connection. (Default: None)
-f, --file  The file where your current external ip is written to on the remote server. (Default: /tmp/dynamic-ip)
```
