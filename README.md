# bits_n_bobs
The minutiae of my computational stuff.

## OS Things I learned

* To open things in vs code, use

```
code <filename>
```

* To see how the internet connection is doing, use

```
sudo iftop -B
```

To print the output of a terminal command to a .txt file, try

```
SomeCommand 2>&1 | tee SomeFile.txt
```


## Different Test Suites
People have different preferences on their testing suites, so here are some
common ones.

### Pytest
* To run an existing test suite you can, from anywhere in the repo, type:
```
pytest
```

### Unittest
* To run an existing test suite you run:

```
python -m unittest path/to/test.py
```


## Accesibility
* Short Tol Colors (3 things): `mycolors = ["#332288", "#117733", "#AA4499"]`
* Med Tol Colors (4 things):  `mycolors = ["#332288", "#117733", "#44AA99", "#AA4499"]`
* Med Tol Colors (5 things):  `mycolors = ["#332288", "#117733", "#88CCEE", "#CC6677", "#AA4499"]`
* IBM Colors (5 things): `mycolors = ["#FFB000", "#648FFF", "#FE6100", "#785EF0", "#DC267F"]`
* Tol Colors (8 things): `mycolors = ["#332288", "#117733", "#44AA99", "#88CCEE", "#DDCC77", "#CC6677", "#AA4499", "#882255"]`


## UIUC HEX Codes
Urbana Orange: E84A27
U of I Blue: 13294b


## SSH
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

### SCP

So you want to send something from your computer to your remote, try scp

```
scp <filename.extension> <user>@<ssh host name>:/path/to/where/you/want/file.extension
```

Conversely, you can receive files with

```
scp <username>@<remote>:/file/to/send/file.extension /where/to/put/file.extension
```

## Default PATH Variable

If you mess up your path again, run this:
```
echo $PATH
```
And it should be empty because you deleted it, idiot. So, run this:
```
export PATH=$PATH="/home/nsryan/anaconda3/bin:/home/nsryan/anaconda3/condabin:/home/nsryan/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin"
```
If you got rid of the temoa-py3 env PATH, run this:
```
export PATH=$PATH"/home/nsryan/anaconda3/envs/temoa-py3/bin:/home/nsryan/anaconda3/condabin:/home/nsryan/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin"

```

## Grep
[Read more](https://www.freecodecamp.org/news/grep-command-in-linux-usage-options-and-syntax-examples/), but generally the vibe is you can search files and directories for instances from the command line.

```
grep '<thing you want to search>' <file you want to search>
```
## Flowcharts in Markdown
With [Mermaid](https://github.com/mermaid-js/mermaid-cli), you can make all manner of visuals in markdown or python.
```
:::mermaid
graph LR
A[Square Rect] -- Link text --> B((Circle))
A --> C(Round Rect)
B --> D{Rhombus}
C --> D
:::
```
```mermaid
graph LR
A[Square Rect] -- Link text --> B((Circle))
A --> C(Round Rect)
B --> D{Rhombus}
C --> D
```

```
:::mermaid
stateDiagram-v2
[*] --> Still
Still --> [*]
Still --> Moving
Moving --> Still
Moving --> Crash
Crash --> [*]
:::
```
```mermaid
stateDiagram-v2
[*] --> Still
Still --> [*]
Still --> Moving
Moving --> Still
Moving --> Crash
Crash --> [*]
```

```
:::mermaid
gitGraph:
    commit "Ashish"
    branch newbranch
    checkout newbranch
    commit id:"1111"
    commit tag:"test"
    checkout main
    commit type: HIGHLIGHT
    commit
    merge newbranch
    commit
    branch b2
    commit
:::
```
```mermaid
gitGraph:
    commit "Ashish"
    branch newbranch
    checkout newbranch
    commit id:"1111"
    commit tag:"test"
    checkout main
    commit type: HIGHLIGHT
    commit
    merge newbranch
    commit
    branch b2
    commit
```

## Conda Envs
Your question can probably be answered [here](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#managing-environments).

### Sharing an Env

1. activate the env
1. run `conda env export --from-history > environment.yml`
1. share the .yml file

To make an env from such a file, just run `conda env create -f environment.yml`

### Removing and Env

`conda remove --name myenv --all`

### Adding an Env to Jupyter notebook

Make sure you deactivate your conda env before doing this.
1. install ipykernel `conda install -c anaconda ipykernel`
1. run this `python -m ipykernel install --user --name=ENVNAME`
