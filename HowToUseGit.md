git
sudo apt-get install git
git config --global user.name "Your name"
git config --global user.email "email@example.com"
mkdir crgit
cd crgit
pwd
git init
git add file
git commit -m "description"
git status
git diff file.name
git log
git reflog
git log --pretty=oneline
git reset --hard HEAD^ -> back to recently version
git reset --hard commit_id
git reset --har HEAD~3 -> back to three change time ago
git diff HEAD -- filename -> check diff from workspace and versionspace
git checkout -- filename -> discard change s in working directory
rm filename
git commit -m "remove filename"
git checkout -- filename -> local delete but in git have can check out
ssh - keygem -t rsa -C "email address" -> creat SSH Key
git remote add origin git@github.com:username/filename.git
git push -u origin master -> first time push
git push origin master
git clone gitfilepath

git checkout -b dev
git branch
git branch <name>
git checkout <name>
git merge <name>
git branch -d <name>

git log --graph --pretty=oneline --abbrev-commit

git stash -> save current change
git stash list
git stash pop
git stash apply stash@{0}
git stash drop

git branch -D <name> -> must delete

git push origin dev -> push dev branch
git checkout -b dev origin/dev

git tag <name>
git tag -a <tagname> -m "des"
git tag -s <tagname> -m "des" version.value
git tag

git push origin <tagname>
git push origin origin --tags
git tag -d <tagname>
git push origin :refs/tags/<tagname>
