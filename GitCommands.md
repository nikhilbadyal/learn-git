# Git Commands

1. `git config --list --show-origin` - View all of your settings. `show-origin` tells where they are coming from

2. `git config --global user.name <email>` - Set user name

3. `git config --global user.email <email>` - Set Email

4. `git config` flags are
   1. `--system`
   2. `--global`
   3. `--local`
      More priorirty as we go down the list

5. `git config --global core.editor "code -w -n"` - Set VS Code as default editor. -w to wait for file to be saved and -n to open in new windows

6. `git config --global init.defaultBranch mains` - To change the name of default branch. only After 2.28. By default it is called master

7. `git add -h` - To avoid getting full blown man page

8. `git init` - Initilize a git repo in local folder

9. `git clone <url> <nameIfIDontWantDefaultName>` - get someone's repo in your local machine

10. `git status` - To check which files are in which state.

11. `git status -s` - Get a simplified view. New files that aren’t tracked have a `??` next to them, new files that have been added to the staging area have an `A`,modified files have an `M`

12. `git add <file/path>` - Begun tracking of the file or files in path

13. `git commit -v -a -m <message>` Commit file to git. -m flag for message , -v flag to show a much detailed view. If i dont pass anything then it'll open a editor to help me write the commit. -a help us to skip `git add`. It stages every file that is already tracked before the commit.

14. The rules for the patterns you can put in the .gitignore file are as follows:
    • Blank lines or lines starting with # are ignored.
    • Standard glob patterns work, and will be applied recursively throughout the entire working tree.
    • You can start patterns with a forward slash (/) to avoid recursivity.
    • You can end patterns with a forward slash (/) to specify a directory.
    • You can negate a pattern by starting it with an exclamation point (!)

15. `git diff <--stagged>`- you want to know exactly what you changed, not just which files were changed. If you want to see what you’ve staged that will go into your next commit, you can use git diff --staged. git diff by itself doesn’t show all changes made since your last commit—only changes that are still unstaged. git diff --cached to see what you’ve staged so far (--staged and --cached are synonyms)

16. `git difftool` - There is another way to look at these diffs if you prefer a graphical or external diff viewing program instead. If you run git difftool instead of git diff, you can view any of these diffs in software like emerge, vimdiff and many more (including commercial products).

17. `git rm` - To remove a file from Git, you have to remove it from your tracked files (more accurately, remove it from your staging area) and then commit. If you modified the file or
    had already added it to the staging area, you must force the removal with the -f option.

18. `git rm --cached <filename>`- you may want to keep the file on your hard drive but not have Git track it anymore. This is particularly useful if you forgot to add something to your .gitignore file and accidentally staged it.

19. `git mv` - Thus it’s a bit confusing that Git has a mv command. If you want to rename a file in Git. It is an equivalent command for
    - mv README.md README
    - git rm README.md
    - git add README

20. `git log -p --stat --pretty <-n> --graph --since --until --author=<name>` - To detect commit history. -p shows the difference introduced in each commit. -n command to limit the commits. --stat is used if you want to see abbreviated stats for each commit.--pretty=online/short/full/fuller/format this option changes the log output to formats other than the default. The oneline value for this option prints each commit on a single line, which is useful if you’re looking at a lot of commits. In addition, the short, full, and fuller values show the output in roughly the same format but with less or more information, respectivel.The most interesting option value is format, which allows you to specify your own log output format. --graph option adds a nice little ASCII graph showing your branch and merge history. `--since` tag and `--until` tags are self explainatory.`--author` this helps in filter based on the specifi autor. `-S` pickaxe option take a string and show only those commit that changed the number of occurances of that string.

| Specifier | Description of Output                           |
| --------- | ----------------------------------------------- |
| %H        | Commit hash                                     |
| %h        | Abbreviated commit hash                         |
| %T        | Tree hash                                       |
| %t        | Abbreviated tree hash                           |
| %P        | Parent hashes                                   |
| %p        | Abbreviated parent hashes                       |
| %an       | Author name                                     |
| %ae       | Author email                                    |
| %ad       | Author date (format respects the --date=option) |
| %ar       | Author date, relative                           |
| %cn       | Committer name                                  |
| %ce       | Committer email                                 |
| %cd       | Committer date                                  |
| %cr       | Committer date, relative                        |
| %s        | Subject                                         |

## Common Options to git log are

|Option  | Description  |
|---|---|
|-p |Show the patch introduced with each commit.|
|--stat|Show statistics for files modified in each commit.|
|--shortstat|Display only the changed/insertions/deletions line from the --stat command.|
|--name-only| Show the list of files modified after the commit information.|
|--name-status| Show the list of files affected with added/modified/deleted information as well.|
|--abbrev-commit| Show only the first few characters of the SHA-1 checksum instead of all 40.|
|--relative-date| Display the date in a relative format (for example, “2 weeks ago”) instead of
using the full date format.|
|--graph| Display an ASCII graph of the branch and merge history beside the log output.|
|--pretty| Show commits in an alternate format. Option values include oneline, short,full, fuller, and format (where you specify your own format).|
|--oneline| Shorthand for --pretty=oneline --abbrev-commit used together.|

21.`git commit --ammend`- One of the common undos takes place when you commit too early and possibly forget to add some
files, or you mess up your commit message. If you want to redo that commit, make the additional
changes you forgot, stage them, and commit again using the --amend option. The commit made by ammend will be a totally new commit and will replace the previous commit. So it's an ideal thing to only ammed if there are minor variations like typos.

22.`git reset HEAD <file>` - Used to unstage file.

23.`git restore --staged <file>` - It is used to revert file back to what it looked when you commited. It’s important to understand that `git restore -- <file>` is a dangerous command. Any local changes you made to that file are gone — Git just replaced that file with the last staged or committed version. Don’t ever use this command unless you absolutely know that you don’t want those unsaved local changes.`--stagged` is used to unstagged the file.

24.`git remote add -v` - To see which remote servers you have configured, you can run the git remote command. shows the url of the remote.`add` is used to add new remote expliictly.`-v`shows you the URLs that Git has stored for the shortname to be used
when reading and writing to that remote

25.`git fetch <remote>`- The command goes out to that remote project and pulls down all the data from that remote project
that you don’t have yet.`git fetch origin` fetches any new work that has been pushed to that server since you
cloned (or last fetched from) it. `git fetch` command only downloads
the data to your local repository — it doesn’t automatically merge it with any of your work or
modify what you’re currently working on.

26.`git pull`- command to automatically fetch and then merge that remote branch into your current branch.

27.`git push <remote> <branch>`- If you want to push your master branch to your origin server (again, cloning generally sets up both of those names for you automatically),then you can run this to push any commits you’ve done back up to the server

28.`git remote show <remote>` - Show info about remote.

29.`git remote rename oldname newname`- Git remote rename to change a remote’s shortname.

30.`remote remove remoteName` or `git remote rm remoteName` - If you want to remove a remote for some reason.Once you delete the reference to a remote this way, all remote-tracking branches and configuration settings associated with that remote are also deleted.

31.`git tag -l -a -m <tagName-lw> <string>` - `-l` list all tags. `string` to list only string tags. -a is used to tag. -m is used  to add message.`lw` is used to add light weight tags.

32.`git show <tag>` - the tag data along with the commit that was tagged by using the git show command.
