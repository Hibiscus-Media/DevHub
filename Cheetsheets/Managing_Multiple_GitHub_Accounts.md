# Managing Multiple GitHub Accounts (Using SSH)

## 1. Generate SSH Keys for Each Account
Generate a separate SSH key for each GitHub account. Replace the email with the correct one for each account.

For Account 1 (e.g., `Hibiscus-Media`):
ssh-keygen -t rsa -b 4096 -C "hibiscusmedia1@gmail.com" -f ~/.ssh/id_rsa_hibiscusmedia

For Account 2 (e.g., `Designvisions`):
ssh-keygen -t rsa -b 4096 -C "designvisions@gmail.com" -f ~/.ssh/id_rsa_designvisions

## 2. Add SSH Keys to SSH Agent
Add each key to the SSH agent.

For Account 1 (Hibiscus-Media):
ssh-add ~/.ssh/id_rsa_hibiscusmedia

For Account 2 (Designvisions):
ssh-add ~/.ssh/id_rsa_designvisions

## 3. Add SSH Keys to GitHub
Copy the public SSH key and add it to the corresponding GitHub account:

For Account 1 (Hibiscus-Media):
cat ~/.ssh/id_rsa_hibiscusmedia.pub

For Account 2 (Designvisions):
cat ~/.ssh/id_rsa_designvisions.pub

Go to **GitHub Settings** > **SSH and GPG keys** for each account, and add the corresponding key.

## 4. Configure SSH Config File
Create or edit the `~/.ssh/config` file to manage multiple accounts:

nano ~/.ssh/config

Add the following configuration:

# Hibiscus Media Account
Host github-hibiscusmedia
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa_hibiscusmedia

# Designvisions Account
Host github-designvisions
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa_designvisions

Save and exit.

## 5. Clone Repositories with SSH for Each Account
When cloning repositories, use the alias defined in the `~/.ssh/config` file.

For **Hibiscus-Media**:
git clone git@github-hibiscusmedia:Hibiscus-Media/repo-name.git

For **Designvisions**:
git clone git@github-designvisions:Designvisions/repo-name.git

## 6. Set the Correct Remote for Existing Repos
If you already have repositories, set the remote URL based on the account:

For **Hibiscus-Media**:
git remote set-url origin git@github-hibiscusmedia:Hibiscus-Media/repo-name.git

For **Designvisions**:
git remote set-url origin git@github-designvisions:Designvisions/repo-name.git

## 7. Push Changes
To push changes to the appropriate GitHub account, just use `git push` as usual:

git push -u origin main

This will use the correct SSH key based on the configuration set in the `~/.ssh/config` file.


### License and Usage Terms

© 2024 Andrew Bamford. This work is licensed under a [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).

You are free to: share, copy, redistribute the material in any medium or format, adapt, remix, transform, and build upon the material for any purpose, even commercially, under the following terms: Attribution – You must give appropriate credit, provide a link to the license, and indicate if changes were made.
