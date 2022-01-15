# Git Commands

1. `git config --list --show-origin` - View all of your settings.`--list` to list all configurations. `show-origin` tells where they are coming from.
1. `git config --global user.name <email>` - Set user name
1. `git config --global user.email <email>` - Set Email
1. `git config` flags are
   1. `--system` - system level
   2. `--global` - global git file
   3. `--local` - project file
      More priorirty as we go down the list.
1. `git config --global core.editor "code -w -n"` - Set VS Code as default editor. `-w` to wait for file to be saved and `-n` to open in new windows
1. `git config --global init.defaultBranch mains` - To change the name of default branch. only After 2.28. By default it is called master
1. `git add . -h <file/path>` - `-h` to avoid getting full blown man page. `<file/path>` to add file/path in staging area. **`.`** add every previously tracked files in stagin area.
1. `git init` - Initilize a git repo in local folder
1. `git clone <url> <nameIfIDontWantDefaultName>` - get someone's repo in your local machine
1. `git status -s` - To show status of repo. `-s` to get a simplified view.New files that aren’t tracked have a `??` next to them, new files that have been added to the staging area have an `A`,modified files have an `M`
1. `git commit -v -a -amend -m <message>` Commit file to git. `-m` flag for message , `-v` flag to show a much detailed view. If I dont pass anything then it'll open a editor to help me write the commit. `-a` help us to skip that.One of the common undos takes place when you commit too early and possibly forget to add some files, or you mess up your commit message. If you want to redo that commit, make the additional changes you forgot, stage them, and commit again using the `--amend` option. The commit made by ammend will be a totally new commit and will replace the previous commit. So it's an ideal thing to only ammed if there are minor variations like typos.
1. `git diff --stagged`- You want to know exactly what you changed, not just which files were changed.`--staged` to see what you’ve staged that will go into your next commit. By default itself doesn’t show all changes made since your last commit—only changes that are still unstaged.`--cached` to see what you’ve staged so far (`--staged` and `--cached` are synonyms)
1. `git difftool` - There is another way to look at these diffs if you prefer a graphical or external diff viewing program instead. If you run `git difftool` instead of `git diff`, you can view any of these diffs in software like emerge, vimdiff and many more.
1. `git rm --cached <filename>`- To remove a file from Git, you have to remove it from your tracked files (more accurately, remove it from your staging area) and then commit. If you modified the file or had already added it to the staging area, you must force the removal with the `-f` option.`--cached` to keep the file on your hard drive but not have Git track it anymore. This is particularly useful if you forgot to add something to your .gitignore file and accidentally staged it.
1. `git mv` - Thus it’s a bit confusing that Git has a mv command. If you want to rename a file in Git. It is an equivalent command for
   - mv README.md README
   - git rm README.md
   - git add README
1. `git reset HEAD <file>` - Used to unstage file.
1. `git restore --staged <file>` - It is used to revert file back to what it looked when you commited. It’s important to understand that `git restore -- <file>` is a dangerous command. Any local changes you made to that file are gone — Git just replaced that file with the last staged or committed version. Don’t ever use this command unless you absolutely know that you don’t want those unsaved local changes.`--stagged` is used to unstagged the file.
1. `git remote <add:name> -v` - To see which remote servers you have configured, you can run the git remote command. shows the url of the remote.`add` is used to add new remote expliictly.`-v`shows you the URLs that Git has stored for the shortname to be used
   when reading and writing to that remote
1. `git fetch <remote>`- The command goes out to that remote project and pulls down all the data from that remote project that you don’t have yet.`git fetch origin` fetches any new work that has been pushed to that server since you cloned (or last fetched from) it. `git fetch` command 1.1.only downloads1.1. the data to your local repository — it 1.1.doesn’t automatically merge1.1. it with any of your work or modify what you’re currently working on.
1. `git pull`- command to 1.1.automatically fetch1.1. and 1.1.then merge1.1. that remote branch into your current branch.
1. `git push <remote> <branch>`- If you want to push your master branch to your origin server (again, cloning generally sets up both of those names for you automatically),then you can run this to push any commits you’ve done back up to the server
1. `git remote show <remote>` - Show info about remote.
1. `git remote rename oldname newname`- Git remote rename to change a remote’s shortname.
1. `git remote remove remoteName` or `git remote rm remoteName` - If you want to remove a remote for some reason.Once you delete the reference to a remote this way, all remote-tracking branches and configuration settings associated with that remote are also deleted.
1. `git tag -l -a -m <tagName-lw> <hash> -d <string>` - `-l` list all tags. `string` to list only string tags. `-a` is used to tag. `-m` is used to add message.`lw` is used to add light weight tags.Can mention `hash` after `tagName` to add tag to previous commit.`-d` delete a tag
1. `git push <remote> :refs/tags/<tagname>` - delete tag from remote
1. `git push origin --delete <tagname>` - Another way to delete tag
1. `git show <tag>` - the tag data along with the commit that was tagged by using the git show command.
1. `git push <remote> <tagName> --tags --follow-tags` - Git push doesn't push tagName by degault. We can do that by this command. `--tags` to push all tags.`--follow-tags` pushes only annotated tags and not light weight tags.
1. `git checkout <tagName>` - to view the versions of files a tag is pointing to.
1. `git checkout -b <branchName> <tagName>`- If we checkout to a tag we are in detach state. In “detached HEAD” state, if you make changes and then create a commit, the tag will stay the same, but your new commit won’t belong to any branch and will be unreachable, except by the exact commit hash. Thus, if you need to make changes — say you’re fixing a bug on an older version, for instance — you will generally want to create a branch. `b` to create a new branch.
1. `git config --global alias.unstage 'reset HEAD --'`- We can also create alias like this to make life easier
