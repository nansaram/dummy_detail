

# github setup with ssh

### Step 1: Create a GitHub Account
1. Go to [GitHub](https://github.com/).
2. Click on **Sign up** and fill in your details to create an account.

### Step 2: Install Git
1. **Download Git** from the [official website](https://git-scm.com/).
2. **Install Git**:
   - **Windows**: Run the downloaded `.exe` file and follow the installation prompts.
   - **macOS**: Open the `.dmg` file and drag Git to your Applications folder.
   - **Linux**: Use the package manager for your distribution. For example, on Ubuntu:
     ```bash
     sudo apt-get update
     sudo apt-get install git
     ```

### Step 3: Configure Git
1. **Open your terminal** (Command Prompt, Git Bash, etc.).
2. **Set your username and email**:
   ```bash
   git config --global user.name "Your Name"
   git config --global user.email "your.email@example.com"
   ```
3. **Verify your configuration**:
   ```bash
   git config --list
   ```

### Step 4: Generate an SSH Key
1. **Check for existing SSH keys**:
   ```bash
   ls -al ~/.ssh
   ```
   If you see files named `id_rsa` and `id_rsa.pub`, you already have an SSH key pair. If not, proceed to the next step.

2. **Generate a new SSH key**:
   ```bash
   ssh-keygen -t rsa -b 4096 -C "your.email@example.com"
   ```
   - `-t rsa`: Specifies the type of key to create (RSA).
   - `-b 4096`: Sets the key length to 4096 bits.
   - `-C "your.email@example.com"`: Adds a comment with your email address.

3. **Follow the prompts** to save the key to the default location and optionally add a passphrase for extra security.

### Step 5: Add Your SSH Key to the SSH-Agent
1. **Start the SSH-agent**:
   ```bash
   eval "$(ssh-agent -s)"
   ```
2. **Add your SSH private key to the SSH-agent**:
   ```bash
   ssh-add ~/.ssh/id_rsa
   ```

### Step 6: Add Your SSH Key to Your GitHub Account
1. **Copy the SSH key to your clipboard**:
   ```bash
   pbcopy < ~/.ssh/id_rsa.pub
   ```
   If `pbcopy` isn't available, you can manually open the file and copy the contents:
   ```bash
   cat ~/.ssh/id_rsa.pub
   ```

2. **Add the SSH key to GitHub**:
   - Log in to your GitHub account.
   - Go to **Settings** > **SSH and GPG keys**.
   - Click **New SSH key**.
   - In the "Title" field, give your SSH key a name (e.g., "My Laptop").
   - Paste your SSH key into the "Key" field.
   - Click **Add SSH key**.

### Step 7: Create a New Repository
1. On GitHub, click on the **+** icon in the top right corner and select **New repository**.
2. Name your repository and click **Create repository**.

### Step 8: Clone the Repository
1. **Copy the repository URL** from GitHub.
2. In your terminal, navigate to the directory where you want to clone the repository and run:
   ```bash
   git clone git@github.com:your-username/your-repository.git
   ```

### Step 9: Make Changes and Commit
1. **Navigate to your repository folder**:
   ```bash
   cd your-repository
   ```
2. **Make changes to your files**.
3. **Add the changes to the staging area**:
   ```bash
   git add .
   ```
4. **Commit the changes**:
   ```bash
   git commit -m "Your commit message"
   ```

### Step 10: Push Changes to GitHub
1. **Push your changes to the remote repository**:
   ```bash
   git push origin main
   ```


¹: [How to Set Up SSH Keys for GitHub: A Step-by-Step Guide](https://dev.to/starkydevs/how-to-set-up-ssh-keys-for-github-a-step-by-step-guide-55p0)
²: [Generating a new SSH key and adding it to the ssh-agent](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
³: [How to setup SSH in GitHub by example](https://www.theserverside.com/blog/Coffee-Talk-Java-News-Stories-and-Opinions/GitHub-SSH-Key-Setup-Config-Ubuntu-Linux)
⁴: [How to Configure GitHub SSH Keys: A Step-by-Step Guide](https://www.hatica.io/blog/how-to-configure-github-ssh-keys/)
⁵: [How to Add SSH Key to Your GitHub Account?](https://www.geeksforgeeks.org/how-to-add-ssh-key-to-your-github-account/)

Source: Conversation with Copilot, 10/5/2024
(1) How to Set Up SSH Keys for GitHub: A Step-by-Step Guide. https://dev.to/starkydevs/how-to-set-up-ssh-keys-for-github-a-step-by-step-guide-55p0.
(2) Generating a new SSH key and adding it to the ssh-agent. https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent.
(3) How to setup SSH in GitHub by example - TheServerSide. https://www.theserverside.com/blog/Coffee-Talk-Java-News-Stories-and-Opinions/GitHub-SSH-Key-Setup-Config-Ubuntu-Linux.
(4) How to Configure GitHub SSH Keys: A Step-by-Step Guide. https://www.hatica.io/blog/how-to-configure-github-ssh-keys/.
(5) How to Add SSH Key to Your GitHub Account? - GeeksforGeeks. https://www.geeksforgeeks.org/how-to-add-ssh-key-to-your-github-account/.
(6) github.com. https://github.com/CouldBeThis/HowToDo/tree/c35aad29dee28c4665ac9f51264764334f84eaf5/jekyll%2F_posts%2F2021-10-22-secondary-github-account.md.
(7) github.com. https://github.com/LambdaSchool/DS-Unit-3-Setup/tree/e93004718b55b9409c4c384cb1c83907a6327f7f/README.md.
