
 # Preparing to release
 
 Put in your CLI:
 
 ```cli
 cd ~
 ./release.md release_45
 ```


```cli
#!/bin/bash
PROJECT_PATH="/Users/username/Desktop/Projects/yourproject_backend"
PROJECT_PATH_FRONT="/Users/username/Desktop/Projects/yourproject_frontend"

cd ${PROJECT_PATH}
echo -e "\n[PREPARE FOR RELEASE]\n"
echo -e "\n[Backend] Pulling master and checkout on ${1}\n"

git checkout master

git reset --hard origin/master
git clean -df
git fetch --all
git pull origin master

git checkout -b $1
git status

# ---

cd ${PROJECT_PATH_FRONT}
echo -e "\n[Frontend] Pulling master and checkout on ${1}\n"

git checkout master

git reset --hard origin/master
git clean -df
git fetch --all
git pull origin master

git checkout -b $1
git status 

```
