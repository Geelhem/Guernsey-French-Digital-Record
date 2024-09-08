


### Step-by-Step Guide

1. **Navigate to your project directory**:
    
    ```bash
    cd /path/to/your/project
    ```
    
2. **Initialize a new Git repository**:
    
    ```bash
    git init
    ```
    
3. **Add all files to the staging area**:
    
    ```bash
    git add .
    ```
    
4. **Commit the initial set of files**:
    
    ```bash
    git commit -m "Initial commit"
    ```
    
5. **Generate a new SSH key** (if you don’t already have one):
    
    ```bash
    ssh-keygen -t ed25519 -C "your_email@example.com"
    ```
    
    - When prompted, press Enter to accept the default file location and leave the passphrase empty (or set one if you prefer).
6. **Add your SSH key to the SSH agent**:
    
    ```bash
    eval "$(ssh-agent -s)"
    ssh-add ~/.ssh/id_ed25519
    ```
    
7. **Copy your SSH key to the clipboard**:
    
    ```bash
    pbcopy < ~/.ssh/id_ed25519.pub
    ```
    
    - If `pbcopy` is not available, you can manually copy the contents of the file:
        
        ```bash
        cat ~/.ssh/id_ed25519.pub
        ```
        
8. **Add the SSH key to your GitHub account**:
    
    - Open your web browser and go to GitHub SSH settings.
    - Click on the “New SSH key” button.
    - In the “Key” field, paste the SSH key you copied earlier.
    - Give it a descriptive title in the “Title” field (e.g., “Mac Mini Key”).
    - Click the “Add SSH key” button to save it.
9. **Test your SSH connection**:
    
    ```bash
    ssh -T git@github.com
    ```
    
    - You should see a message like “Hi username! You’ve successfully authenticated, but GitHub does not provide shell access.”
10. **Set the remote URL to use SSH**:
    
    ```bash
    git remote add origin git@github.com:Geelhem/Guernsey-French-Digital-Record.git
    ```
    
11. **Fetch the latest changes from the remote repository**:
    
    ```bash
    git fetch origin
    ```
    
12. **Merge the remote branch into your local branch with the `--allow-unrelated-histories` flag**:
    
    ```bash
    git merge origin/main --allow-unrelated-histories
    ```
    
13. **Resolve any merge conflicts** (if any):
    
    - Open the conflicting files, resolve the conflicts, and then add the resolved files to the staging area:
        
        ```bash
        git add <file>
        ```
        
14. **Commit the merge**:
    
    ```bash
    git commit -m "Resolved merge conflicts"
    ```
    
15. **Push your changes to the remote repository**:
    
    ```bash
    git push origin main
    ```
    

### Example Commands:

```bash
cd /path/to/your/project
git init
git add .
git commit -m "Initial commit"
ssh-keygen -t ed25519 -C "your_email@example.com"
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
pbcopy < ~/.ssh/id_ed25519.pub
# Add the key to GitHub via the web interface
ssh -T git@github.com
git remote add origin git@github.com:Geelhem/Guernsey-French-Digital-Record.git
git fetch origin
git merge origin/main --allow-unrelated-histories
# Resolve any conflicts and add the resolved files
git add <file>
git commit -m "Resolved merge conflicts"
git push origin main
```

This should cover everything from initializing the directory to pushing your changes to GitHub. Let me know if you need any more assistance! 😊


How to sync
https://github.com/kevinmkchin/Obsidian-GitHub-Sync/blob/main/README.md 

`git pull`
`git add .`
`git commit -m "my obsidian vault first commit"`
`git branch -M main`
`git remote add origin https://github.com/Geelhem/Guernsey-French-Digital-Record`
git push -u origin main`