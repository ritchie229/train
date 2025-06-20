VIEW THIS IN CODE MODE
git-scm.com
--,-'<@
git config --global init.defaultBranch main
git config --global user.name ritchie229
git config --global user.email rishat.mukhtarov@gmail.com
git config --list


git branch
  - show active/passive branshes
git branch <new_branch_name>
git checkout <new_branch_name>
  - creating and passing to new branch
git checkout -b <new_branch_name>
  - creating and passing to new branch
git branch -d <branch_name>
  - remove bransh after committing or pushing
git branch -D <branch_name>
  - remove branch before committing or pushing (hard)
git branch -m <name> - renaming the current branches name

Relative actions order via a sub branch:

1. git checkout subbranch
2. making changes, editing files, adding/removing etc.
3. git status
4. git add . / git add * / git add filename,dirname etc   --------
5. git commit -m "message"   -------				  |
6. git checkout main                |				  |
7. git merge subbranch              |				  5. git branch -D subbranch
8. git branch -d subbranch	        6. git push origin
				                            7. merge in github gui 
                                    8. git push origin --delete subbranch
9. git tag ver.1.0
10. git push origin ver.1.0

# additional
11. git tag -a ver.1.0.2 d731dbc9affbfcbd7ad2a149197ff0199e0b96df - to add a tag to a commit somewhere in the middle if forgot
12. git tag ver.1.0.3 - to tag the last commit before pushing
13. git push origin --tags   - pushes all the tags not sent to github

------------------
# Working with Github (connecting local repo to github directly without cloning)
------------------
1. git init . # creating local repo
2. git checkout -b main
3. git remote add main git@github.com:ritchie229/train.git
4. making changes, editing files, adding/removing etc.
5. git commit -a -m "message"
6. git push -f origin main
------------------ 
# Aliases
__________________
1. git config --global alias.ci 'commit -a' # git commit -a
2. git config --global alias.co 'checkout'
3. git config --global alias.br 'branch'
4. git config --global alias.st 'status'
5. git config --global alias.lol 'log --oneline --graph --decorate'

git commit --amend
git ci --fixup=a3f9129
git rebase -i --autosquash HEAD~2
git revert 69ecf26
git reset --hard 6f67ddc
git reset --soft 6f67ddc
git diff --staged
git cherry-pick 2aed43e
git rebase slave HEAD~1
git co 72d4c62
git cat-file -p 1f940ed




git log (git log -2 -p)
  - to chow all commits
git checkout <hash from git log>
  - to load previous versions
git checkout main
  - will return the hEAD to the last version
git commit --amend
  - to make changes in the last commit incl the message etc. after modifyng the files (last changes)
git reset --hard HEAD~
  - to hard remove the last commit (HEAD~2 - removing last two commits), removing all the changes, especially if sensitive info leaked thru it
git reset --soft HEAD~
  - to remove the last comming (HEAD~3 - last three commits). not touching the changes
git push origin main --force
  - to remove commit info containing sensitive data from github
