# Howto FreeNAS

## Manage the jails

### Base command

```sh
warden help
```

#### Create a jail

```sh
warden create <jail Name> --startauto --jailtype pluginjail --template pluginjail
```

### List all running jails

```sh
jls
```

### Connect to a jail

```sh
jexec <JID> tcsh # Get the JID using the jls command.
```

### Install your own jails

Here a interristing GitHub Gist which show how to create some interresting jails: [jacobblock/FreeNAS.md](https://gist.github.com/mow4cash/e2fd4991bd2b787ca407a355d134b0ff)
