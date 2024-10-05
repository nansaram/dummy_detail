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
git branch -M main
git remote add origin https://github.com/urname/urrepo.git
`
When you run git branch -M main, you are renaming the current branch (often the default master branch) to main.

## push your changes
`
git push -u origin main
`
The command `git push -u origin main` is used in Git to push your local `main` branch to the remote repository named `origin`. Here's a breakdown of what each part of the command does:

- **`git push`**: This command uploads your local repository content to a remote repository.
- **`-u` or `--set-upstream`**: This flag sets the upstream branch for the local branch. This means that future `git pull` or `git push` commands will default to this remote branch, simplifying your workflow.
- **`origin`**: This is the default name for the remote repository. It could be any name you have set for your remote repository.
- **`main`**: This is the name of the branch you are pushing. In many repositories, `main` is the default branch.

So, when you run `git push -u origin main`, you are pushing your local `main` branch to the `main` branch on the remote repository `origin` and setting it up so that future pushes and pulls will automatically use this branch¹².


## verity your setup
`
git status
`
- view commit history
`
git log
`










