# Howto Linux

## Utilities

-   Find example for commands with [Command Line Fu](http://www.commandlinefu.com/commands/browse).
-   Use [eg](https://github.com/srsudar/eg) to find example for a command.

## Environment Variables

Add a `env.sh` file into `/etc/profile.d/` folder to add environment variable for all user at login.

Sample content:

```shell
export JAVA_HOME={pathToJava}
```

## SQLPlus

### Encoding

```shell
# To ensure that you launch script as UTF-8:
export NLS_LANG=.AL32UTF8
```

### Command history

Install and use [rlwrap ](https://github.com/hanslub42/rlwrap) to define an alias to sqlplus.

```shell
alias sqlplus="rlwrap sqlplus"
```

See following [guide](https://blogs.oracle.com/middleware/entry/getting_history_from_sqlplus_using).

## Commands

### SCP

```shell
# To copy some file over ssh between machine.
scp -r [<user>@<machine>:]<filesToCopy> [<user>@<machine>:]<pathToFolder>
scp -r user@server01:/tmp/somefile user@server02:/tmp/
```

### PWD

```shell
# To know the current folder full path.
pwd
```

### SSH + autoSSH

#### Some commands

```shell
# To connect with SSH to an user on a server from local computer.
ssh <user>@<serverAddress>

# Following command are best to be used with a RSA key installed on the server and without any password to fill.
# autossh will automatically rebuild the SSH tunnel if disconnect.
autossh -f -N -M <autossh Port> -L <localAddress>:<localPort>:<outsideAddress>:<outsidePort> <user>@<serverAddress>
autossh -f -N -M 20000 -L localhost:8080:111.222.333.444:8080 user@server

# This is the basic SSH command used by autossh to create the SSH tunnel.
ssh -L localhost:8080:111.222.333.444:8080 jerk@frparantgaga -f -N
```

Here, the `-f -N` parameters allow us to open the SSH tunnel without having the open a console to the server which will serve as the bridge between our local address:port and the outside address:port.

#### Use a RSA key to connect

```shell
# To generate a RSA key pairs. Not inputting any password on the key creation will allow us to connect to the server without inputting any password.
ssh-keygen -t rsa

# From your home directory with CygWin
# Send the public key to the temp directory in root user on a server
scp .ssh/id_rsa.pub user@server:temp/

# Connect to root user on a server
ssh user@server

# From root home directory on a server
cat temp/id_rsa.pub >> .ssh/authorized_keys
```

### Find + Grep to check multiple files

```shell
find ./ -name connector.properties | while read file; do echo $file; grep "ASpecificValue" $file; done
```

## Firewall (debian / centOS)

### iptable

```shell
# To allow access to a port:
iptables -I INPUT -p tcp --dport 1525 -j ACCEPT
```

### firewalld

Best to use firewalld as it is configured as a service. It is also fully dynamic and easier to manage.

-   [firewalld tuto](http://linoxide.com/firewall/firewalld-centos-rhel/)

## Services

```shell
# To start and stop services.
systemctl <start|stop|...> <serviceName>
```

-   [SystemCTL tuto](https://www.digitalocean.com/community/tutorials/how-to-use-systemctl-to-manage-systemd-services-and-units)
