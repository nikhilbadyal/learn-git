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
10. `git status` - To check which files are in which state.
11. `git status -s` - Get a simplified view. New files that aren’t tracked have a `??` next to them, new files that have been added to the staging area have an `A`,modified files have an `M`
12. `git add <file/path>` - Begun tracking of the file or files in path
13. `git commit -v -a -m <message>` Commit file to git. -m flag for message , -v flag to show a much detailed view. If i dont pass anything then it'll open a editor to help me write the commit. -a help us to skip `git add `. It stages every file that is already tracked before the commit.
14. > The rules for the patterns you can put in the .gitignore file are as follows:
    > • Blank lines or lines starting with # are ignored.
    > • Standard glob patterns work, and will be applied recursively throughout the entire working
    > tree.
    > • You can start patterns with a forward slash (/) to avoid recursivity.
    > • You can end patterns with a forward slash (/) to specify a directory.
    > • You can negate a pattern by starting it with an exclamation point (!)
15. `git diff <--stagged> `- you want to know exactly what you changed, not just which files were changed. If you want to see what you’ve staged that will go into your next commit, you can use git diff --staged. git diff by itself doesn’t show all changes made since your last commit—only changes that are still unstaged. git diff --cached to see what you’ve staged so far (--staged and --cached are synonyms)
16. `git difftool` - There is another way to look at these diffs if you prefer a graphical or external diff viewing program instead. If you run git difftool instead of git diff, you can view any of these diffs in software like emerge, vimdiff and many more (including commercial products).
17. `git rm ` - To remove a file from Git, you have to remove it from your tracked files (more accurately, remove it from your staging area) and then commit. If you modified the file or
    had already added it to the staging area, you must force the removal with the -f option.
18. `git rm --cached <filename>`- you may want to keep the file on your hard drive but not have Git track it anymore. This is particularly useful if you forgot to add something to your .gitignore file and accidentally staged it.
19. `git mv` - Thus it’s a bit confusing that Git has a mv command. If you want to rename a file in Git.
