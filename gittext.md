
 reset git 

git config --list
git config --global --unset-all user.name
git config --global --unset-all user.email

git credential-manager uninstall

git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

git config --global --get user.name
git config --global --get user.email

git pull origin main

git branch new-branch

git checkout new-branch



git add .
git commit -m "Change to new Git account"
git push origin <branch-name> 
