Howdy!

So, you're starting up a new machine, here's what you need to do (mostly in order):
1. login to firefox account
1. activate sticky keys (search sticky in settings, it should be under accessibility/typing assist)
1. activate settings sync in vs code by logging into github
1. install anaconda
    1. download the [software](https://docs.anaconda.com/anaconda/install/index.html)
    1. open the installer using `bash ~/Downloads/<name of file>`
    1. run `source ~/.bashrc` or close out of the terminal
1. set up git
    1. `git config --global user.name "Nathan Ryan"`
    1. `git config --global user.email "nsryan2@illinois.edu"`
    1. Install [GH CLI](https://cli.github.com/manual/installation)
    1. `gh auth login`
        1. preffered protocol is SSH
        1. probably want a new SSH, unless you're replacing a laptop or something
        1. use the same password as your first SSH
        1. title it with the name of the new machine
        1. login with a web browser
    1. `git clone git@github.com:nsryan/nsryan.github.io.git`
    1. `git clone git@github.com:nsryan/CV.git`
1. Follow any of the other install guides/scripts that you're working with
1. Install Slack (I know, it's a headache)
