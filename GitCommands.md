## Git Commands

1. `git config --list --show-origin` - View all of your settings and where they are coming from using
2. `git config --global user.name "Nikhil Badyal"` - Set user name
3. `git config --global user.email nikhill773384@gmail.com` - Set Email
4. `git config`b flags are
   1. `--system`
   2. `--global`
   3. `--local`
      More priorirty as we go down the list
5. `git config --global core.editor "code -w -n"` - Set VS Code as default editor. -w to wait for files to be close and -n to open in new windows
6. `git config --global init.defaultBranch mains` - To change the name of default branch. only After 2.28. By default it is called master
7. `git add -h` - To avoid getting full blown man page
8. `git init` - Initilize a git repo in local folder
9. `git clone <url> <nameIfIDontWantDefaultName>` - get someone's repo in your local machine
10. `git status` - To check which files are in which state
