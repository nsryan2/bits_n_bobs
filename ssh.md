# SSH
In you .ssh/config file you can save shortcuts to computers and
clusters in the form:

```
Host <name>
  Hostname <Address>
  User <username>
```

Instead of typing:

```
ssh <username>@<address>
```

To close out of an ssh session type: `~` and then `.`

You can check who is connected to a machine by running:

```
who -u
```

## SCP

So you want to send something from your computer to your remote, try scp

```
scp <filename.extension> <user>@<ssh host name>:/path/to/where/you/want/file.extension
```

Conversely, you can receive files with

```
scp <username>@<remote>:/file/to/send/file.extension /where/to/put/file.extension
```