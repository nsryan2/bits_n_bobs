# SSH
Setting up ssh allows you to connect remotely to a machine to perform runs or tasks that your machine might not be prepared for.

You can SSH into computers you have set up with this command:

```
ssh <username>@<ip address>
```

Then it will prompt you for the password as if you were logging in to the machine you're SSHing into.

To close out of an ssh session type: `~.`

You can check who is connected to a machine by running:

```
who -u
```

## Installing SSH
On the new device, run:
1. `sudo apt install net-tools`
2. `ifconfig` and remember the inet 12-digit address
3. `sudo apt-get update`
4. `sudo apt-get install openssh-server`
5. `sudo ufw allow 22`

Now you'll be able to connect from any machine so long as you remember the username, password, and ip address.

### Creating a Shortcut
If the task of remembering the ip address is annoying to you, you can create a shortcut on your machine. Access the `/etc/ssh/ssh_config` file so that you can save shortcuts to computers and clusters in the form:

```
Host <shortcut>
  Hostname <Address>
  User <username>
```

Now you'll be able to connect with the following command and your password:

```
ssh <shortcut>
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
