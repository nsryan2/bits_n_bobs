1. install the tools on the new device
    1. `sudo apt install net-tools`
    1. `ifconfig` and remember the inet 12-digit address
    1. `sudo apt-get update`
    1. `sudo apt-get install openssh-server`
    1. `sudo ufw allow 22`
1. on your laptop go to `~/.ssh/config` and create a new item
    with the form:

    ```
    Host <name of computer>
      Hostname <inet>
      User nsryan
    ```
