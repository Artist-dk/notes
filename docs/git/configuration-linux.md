# Git Configuration Guide for Kali Linux

This guide walks you through configuring Git with GPG signing, SSH key setup, and other essential Git configurations on Kali Linux.

## 1. Install GPG and Related Tools

- **Install GPG:**
  - Ensure GPG and related tools are installed:
    ```bash
    sudo apt update
    sudo apt install gnupg2 kleopatra
    ```

## 2. Create a New OpenPGP Key Pair

- **Steps to Create:**
  - Open Kleopatra from your applications menu.
  - Navigate to `File > New OpenPGP Key Pair...`.
  - Follow the on-screen prompts to generate a new key pair.

## 3. Export Your Certificate

- **Backup Certificate:**
  - Export the certificate from Kleopatra and save it securely.

## 4. Import the Private Key into GPG

- **Use Command Line:**
  - Open a terminal and run:
    ```bash
    gpg --import my-private-key.asc
    ```

## 5. List Secret Keys

- **Check Your Keys:**
  - To list your secret keys, execute:
    ```bash
    gpg --list-secret-keys --keyid-format LONG
    ```

## 6. Configure Git to Use the Signing Key

- **Set the Key for Git:**
  - Configure Git with your GPG key:
    ```bash
    git config --global user.signingkey KEYID
    ```

## 7. Set GPG Program Path in Git

- **Path Configuration:**
  - Ensure Git uses the correct GPG program:
    ```bash
    git config --global gpg.program "/usr/bin/gpg"
    ```

## 8. Verify Your GPG Keys

- **List GPG Keys:**
  - To list your GPG keys, run:
    ```bash
    gpg --list-secret-keys --keyid-format LONG
    ```
  - The output will show something like this:
    ```plaintext
    /home/yourname/.gnupg/secring.gpg
    -----------------------------------
    sec   rsa4096/XXXXXXXXXXXXXXXX 2024-08-18 [SCEA]
    ```
  - Here, `XXXXXXXXXXXXXXXX` represents your GPG key ID.

## 9. Export Your Public Key

- **Share Your Public Key:**
  - To export your public key:
    ```bash
    gpg --armor --export XXXXXXXXXXXXXXXX
    ```
  - Replace `XXXXXXXXXXXXXXXX` with your actual GPG key ID.

## 10. Configure Git to Use the GPG Key

- **Setup Git with Your Key:**
  - Configure Git to use your GPG key:
    ```bash
    git config --global user.signingkey XXXXXXXXXXXXXXXX
    ```

## 11. Set Git Username

- **Configure Username:**
  - Set your Git username:
    ```bash
    git config --global user.name "Your Name"
    ```

## 12. Set Git Email

- **Configure Email:**
  - Set your Git email address:
    ```bash
    git config --global user.email "your.email@example.com"
    ```

## 13. Set Up SSH Key (Optional)

- **Generate SSH Key:**
  - If you intend to use SSH with Git:
    ```bash
    ssh-keygen -t rsa -b 4096 -C "your.email@example.com"
    ```
  - **Add SSH Key to Agent:**
    - Start the SSH agent and add your key:
      ```bash
      eval "$(ssh-agent -s)"
      ssh-add ~/.ssh/id_rsa
      ```
  - **Copy SSH Public Key:**
    - Copy the public key to the clipboard:
      ```bash
      xclip -sel clip < ~/.ssh/id_rsa.pub
      ```
  - **Add SSH Key to Git Service:**
    - Paste the key into your Git service account settings (e.g., GitHub, GitLab).

## 14. Set Global .gitignore

- **Global .gitignore File:**
  - Create a global `.gitignore` file to define files and directories you want Git to ignore across all repositories:
    ```bash
    git config --global core.excludesfile ~/.gitignore_global
    ```
  - Edit `~/.gitignore_global` and add your rules:
    ```plaintext
    # Example rules
    *.log
    *.tmp
    .DS_Store
    ```
    
## 15. Enable Git Auto-Correction for Mistyped Commands

- **Enable Auto-Correction:**
  - Automatically correct mistyped Git commands by enabling auto-correction:
    ```bash
    git config --global help.autocorrect 1
    ```
  - Git will wait a moment before auto-correcting. Set the value to `1` to remove the delay or a higher number to increase the delay in tenths of a second.

## 16. Cache Your Credentials for HTTPS Repositories

- **Credential Caching:**
  - Store your credentials in memory for a few minutes when using HTTPS to connect to your repository:
    ```bash
    git config --global credential.helper cache
    ```
  - Set a custom timeout (in seconds):
    ```bash
    git config --global credential.helper 'cache --timeout=3600'
    ```
  - Alternatively, store credentials permanently:
    ```bash
    git config --global credential.helper store
    ```

## 17. Set the Default Text Editor for Git

- **Configure Default Editor:**
  - Set your preferred text editor (e.g., Nano, Vim, VSCode) for Git commit messages:
    ```bash
    git config --global core.editor "nano"
    ```
  - Or for VSCode:
    ```bash
    git config --global core.editor "code --wait"
    ```

## 18. Set Up Aliases for Common Git Commands

- **Create Git Aliases:**
  - Shorten commonly used Git commands with aliases:
    ```bash
    git config --global alias.co checkout
    git config --global alias.br branch
    git config --global alias.ci commit
    git config --global alias.st status
    git config --global alias.unstage 'reset HEAD --'
    git config --global alias.last 'log -1 HEAD'
    ```

## 19. Enable Color Output in Git

- **Enable Color:**
  - Ensure Git command output uses colors for better readability:
    ```bash
    git config --global color.ui auto
    ```

## 20. Set Up Git Pull Rebase Strategy

- **Rebase by Default:**
  - Configure Git to use rebase instead of merge when pulling:
    ```bash
    git config --global pull.rebase true
    ```

## 21. Check Git Configuration

- **Review Configurations:**
  - To see your current Git configurations, run:
    ```bash
    git config --list
    ```

With these configurations, your Git setup on Kali Linux should be optimized for efficiency, security, and convenience.
