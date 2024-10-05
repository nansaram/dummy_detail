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

## ref
`
git init
git remote add origin git@github.com:username/repository.git	// ssh
git branch -M main
git add .
git commit -m "Initial commit"
git push -u origin main
`


## git connection to remote
Yes, it is possible to configure and use both HTTP and SSH connections for a Git repository. Here’s how you can manage both:

### **Setting Up Both HTTP and SSH**

1. **Clone the Repository Using One Method**:
   - **HTTPS**:
     ```bash
     git clone https://github.com/user/repo.git
     ```
   - **SSH**:
     ```bash
     git clone git@github.com:user/repo.git
     ```

2. **Add the Other Remote URL**:
   After cloning the repository, you can add the other URL as an additional remote or change the existing remote URL.

   - **Adding an SSH URL to an HTTPS Clone**:
     ```bash
     git remote set-url --add origin git@github.com:user/repo.git
     ```
   - **Adding an HTTPS URL to an SSH Clone**:
     ```bash
     git remote set-url --add origin https://github.com/user/repo.git
     ```

### **Using Both Connections**

- **Fetching and Pulling**:
  You can fetch and pull using either URL. Git will use the appropriate URL based on your configuration and the command you use.

- **Pushing Changes**:
  Similarly, you can push changes using either URL. If you have both URLs configured, Git will use the first one listed in the configuration.

### **Managing Multiple URLs**

You can list all configured URLs for a remote using:
```bash
git remote get-url --all origin
```

### **Example Scenario**

1. **Clone with HTTPS**:
   ```bash
   git clone https://github.com/user/repo.git
   cd repo
   ```

2. **Add SSH URL**:
   ```bash
   git remote set-url --add origin git@github.com:user/repo.git
   ```

3. **Verify URLs**:
   ```bash
   git remote get-url --all origin
   ```

This setup allows you to switch between HTTP and SSH as needed, providing flexibility depending on your network environment and security preferences¹²³.


¹: [GitHub Docs](https://docs.github.com/en/get-started/getting-started-with-git/managing-remote-repositories)
²: [Stack Abuse](https://stackabuse.com/how-to-tunnel-http-with-ssh/)
³: [DigitalOcean](https://www.digitalocean.com/community/tutorials/ssh-essentials-working-with-ssh-servers-clients-and-keys)

Source: Conversation with Copilot, 10/5/2024
(1) How to Connect to an SSH Server from Windows, macOS, or Linux. https://www.howtogeek.com/311287/how-to-connect-to-an-ssh-server-from-windows-macos-or-linux/.
(2) Basic SSH Connection Tutorial. https://www.youtube.com/watch?v=1Ba5l6Ii9HM.
(3) Connect to Remote Linux Server with SSH - Step-by-step Guide. https://www.youtube.com/watch?v=kUgF6tqKqr0.
(4) SSH Essentials: Working with SSH Servers, Clients, and Keys. https://www.digitalocean.com/community/tutorials/ssh-essentials-working-with-ssh-servers-clients-and-keys.
(5) How To Use SSH to Connect to a Remote Server | DigitalOcean. https://www.digitalocean.com/community/tutorials/how-to-use-ssh-to-connect-to-a-remote-server.
(6) How to Tunnel HTTP with SSH - Stack Abuse. https://stackabuse.com/how-to-tunnel-http-with-ssh/.
(7) How to Access Web Pages via SSH | Baeldung on Linux. https://www.baeldung.com/linux/ssh-tunnel-access-web-pages.




