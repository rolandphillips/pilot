Go to Github.com
New Repository
Open Terminal
Navigate to a parent directory for your repo
echo "# pilot" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/rolandphillips/pilot.git
git push -u origin master


Update the readme file
git add README.md
git commit -m “second commit"
git push -u origin master

Git checkout -b branch1
Edit a file
Git add file
git commit -m "branch commit"
git push origin branch1    ///branch is added into GitHub

PR the branch and merge into master
—at this point, Im still on my branch locally - need to learn whether to close, archive, delete the ref, or delete branches in git, and if any additional cmds are needed to run locally.
