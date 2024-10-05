# details with ssh

## install git
`
sudo apt-get update
sudo apt-get install git
`

## configure git

1. set username and email:
`
git config --global user.name "Ur name"
git config --global user.email "Ur email"
`

2. verify configuration
`
git config --list
`

## create new local prj. repo.

1. navigate to local dir
`
cd path/to/my/prj
`

2. init. a new git repo
`
git init
`
this command creates a new subdir named .git that contains all of your necessary repo. files.

## add files to ur repo.

1. create file
`
echo "# My project" >> README.md
`

2. add file to staging area
`
git add README.md
`
also add multiple files by using wildcard(git add .)

## commit your changes

1. commit the file to staging area
`
git commit -m "Initial commit"
`

## connect to remote repository
1. create repo on github
2. copy the repo URL
3. add the remote repo.
`
git remote add origin https://github.com/urname/urrepo.git
`

## push your changes
`
git push -u origin main
`

## verity your setup
`
git status
`
- view commit history
`
git log
`










