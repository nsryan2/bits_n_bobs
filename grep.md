# What is grep

[Read more](https://www.freecodecamp.org/news/grep-command-in-linux-usage-options-and-syntax-examples/), but generally Grep, short for “global regular expression print.” Basically it allows you to find information in a file from the command line.

`grep “<search terms>” <file.extension>`

Cool, so that’s returned the line where it found hello.

We can highlight the instances it found with

`grep --color “<search terms>” <file.extension>`

To ignore case sensitivity, we can add

`grep --color -i “<search terms>” <file.extension>`

It’s great to find instances in one file, but what about a directory?

`grep --color -i “<search terms>” *`

We can search sub directories as well with

`grep -r --color -i “<search terms>” *`

## Git Grep
Git grep searches through what's in your working directory based on the last commit, ignoring the git logs and save files. Otherwise, it works the same as grep.

`git grep --untracked “<search terms>” *`
Also searches files not tracked by git.
