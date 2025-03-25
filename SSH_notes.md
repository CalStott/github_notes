# SSH notes

## Table of Contents
  - [Generating a new SSH key pair](#generating-a-new-ssh-key-pair)
  - [Adding an SSH key to your GitHub account](#adding-an-ssh-key-to-your-github-account)
  - [Storing the local SSH for ease of access to the remote SSH](#storing-the-local-ssh-for-ease-of-access-to-the-remote-ssh)
  - [Pushing changes to your GitHub using SSH](#pushing-changes-to-your-github-using-ssh)
  - [Removing your SSH key from your GitHub account](#removing-your-ssh-key-from-your-github-account)
  - [Deleting your SSH keys locally](#deleting-your-ssh-keys-locally)
---

## Generating a new SSH key pair
1. Navigate to your .ssh folder locally using Git Bash
2. Generate a new key pair using this command:
   
    ```bash
    # input your email address in the string
    ssh-keygen -t rsa -b 4096 -C "yourname@email.com"
    ```
3. You will be asked for a file to save the key, input what you want the file name to be. __Make it clear what it is for__

4. You will be asked for a passphrase. In this case for authentication, it can be left empty by just pressing enter through both inputs.

*(Optional)*  
Use the command `ls` to verify the files have been created.

## Adding an SSH key to your GitHub account
1. Generate an SSH key pair following the previous steps.
2. Read the __Public__ key to use on GitHub, which is the file with the __.pub__ extension. This is done with the command:
   
    ```bash
    cat file-name.pub
    ```

3. Copy the Public key by highlighting it, right-clicking and then clicking copy. __Make sure no white space is highlighted__
4. Go to your GitHub and click on your profile in the top-right corner.
5. Click on '__Settings__'
6. Under Access, click on '__SSH and GPG keys__'
7. Under the SSH section, click on '__New SSH key__'
8. Give the key a meaningful title, select the key type (Authentication) and paste the Public key into the input box
9. Click '__Add SSH key__'

## Storing the local SSH for ease of access to the remote SSH
1. Create an ssh-agent using the command:
    ```bash
    eval `ssh-agent -s`
    ```
2. Add the __Private__ key to the agent:
   ```bash
   ssh-add file-name
   ```
3. Verify the connection to the remote SSH:
   ```bash
   ssh -T git@github.com
   ```

   __Important Note__  
   If the host is not in your known hosts file already, you will get a verification message asking if you want to continue connecting. Type '__yes__' to this and press enter if you are sure that host is secure

## Pushing changes to your GitHub using SSH
1. Navigate to your repository file location in Git Bash
2. Check your remote location using
   ```bash
   git remote -v
   ```
3. Open your repository on GitHub
4. Click on 'Code'
5. Select 'SSH' and copy the URL given
6. Set the remote location of your local repository in Git Bash using
   ```bash
   git remote set-url copied-SSH-URL
   ```
7. Stage and commit your files locally, then push to the remote repository

## Removing your SSH key from your GitHub account
1. Click on your profile in the top-right corner
2. Click on settings
3. Under Access, click on SSH and GPG keys
4. Delete the SSH key

## Deleting your SSH keys locally
1. Navigate to your .ssh folder locally using Git Bash
2. Remove both the private and public SSH keys using these commands:
    ```bash
    rm ~/.ssh/key-name.pub
    rm ~/.ssh/key-name
    ```