* ## how to change the name of the default 1st branch in git
  * ``` git config --global init.defaultBranch main ```
* ## Rename the local "master" branch to "main" :
  * ``` git branch -m master main ```



https://github.com/glitch2k/scripts_from_work.git


echo "# scripts_from_work" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/glitch2k/scripts_from_work.git
git push -u origin main


git remote add origin https://github.com/glitch2k/scripts_from_work.git
git branch -M main
git push -u origin main



