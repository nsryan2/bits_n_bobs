Git/GitHub Review Points

Git season 3 top 1
* Checkout https://swcarpentry.github.io/git-novice/ 
* Use git bash if you’re on windows (anaconda power-shell is also a good replacement)
* Consider making a repo of config files and looking into chaining your top directory 
  *   You can set the name of the initial branch in a repo
* The head is like where you are looking, showing you where changes will go
* Stage and commit separately
  *   You unstage things with `git rm --cached <file>`
  *   `git diff --staged` shows the difference between the last commit and the staged changed
* If you use atom run `git config --global core.editor "atom --wait"`
  *   This will finish the command when you close the file you’re editing
* If you use nano run `git config --global core.editor "nano -w"`
* Never nest original git repos inside another git repo


Git part 2 electric boogaloo
* Always develop on a branch other than main/master
  *   Commits should only be added to that branch through a PR that someone else approves and merges
  *   Learn more about branches here https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-branches 
* Adding a remote and upstream
  *   `origin` is typically reserved for your GitHub user account
  *   `upstream` is typically reserved for the shared repo (like in the ARFC organization on github)
  *   https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/configuring-a-remote-for-a-fork 
* You Pull Request from origin to upstream (you shouldn’t push from your computer to the ARFC version of a repository)
  *   The general pattern should be:
    *       Make changes on a branch on your computer, 
    *       push to a branch on your fork, 
    *       make a PR from the branch on your fork to the main in the ARFC repo. 
    *       Once the changes are merged into the ARFC main, 
    *       pull them onto your computer, 
    *       and then push to your fork main
* To switch between branches use `git checkout <branch name>`
* Set up your SSH keys https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/reviewing-your-ssh-keys 
* To make a new branch based off of the one you’re on currently use `git checkout -b <new branch name>`

*The convention <> means that you replace everything, including the angle brackets with the word for the a custom thing like the name of a specific branch.


Breaking 3: The Git Resurgence
* `git branch -v` tells you the most recent commit for each branch
* Remember, whatever you do in git 99% of the time you can undo it with a little help. Your log will look a little funny, but it will work
* Now, if we push this branch from our computer to GitHub with `git push origin <branch name>`, it will show up as a branch on the GitHub repo (not on main)
* Remember use the tab to complete longer titles as soon as they are distinct from others
* Make sure your titles and PR descriptions are descriptive. When you push these changes, you’ll get a little pop-up on GitHub to make a PR between the new branch and the main branch
  *   If you want to change the branch you are pulling to, you can always edit the PR after it’s made
* Generally, you can merge paper PRs but not code PRs
* When you review someone else’s PR, always be nice and follow the group guide http://arfc.github.io/manual/guides/pull_requests
* If you update something, or accept changes from a PR review, you’ll have to update your local clone with `git pull origin <branch name>`
* If you want to just add parts of a file, you can use interactive staging `git add -p <filename>`
  * https://git-scm.com/book/en/v2/Git-Tools-Interactive-Staging
  * If there’s just one file, you don’t need the <file name part>
* Remember use `git diff --staged` to see differences between what you have committed and staged, without the `--staged` you will only see differences between changes and what has been committed
* Use `git show` <commit hash> to see what was changed in a particular commit
  * The hash is a string of numbers and letters that you get from `git log`
* If you want to change the commit (add a file, change the commit message, etc.) use `git commit --amend`
* After you merge changes from a branch, delete it on GitHub
