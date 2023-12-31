# ssh-keys
Setup SSH Keys 

## Create a first ssh key 

  ssh-keygen -o -t rsa -C "examle@gmail.com"
  
  ssh-keygen -t ed25519 -C "examle@gmail.com"
  
## For Linux this command 

  eval "$(ssh-agent -s)"

## If you just want to add ssh-key to the ssh-agent, use the below command.

# All are the Windows steps 

  ` Get-Command ssh`

  ### output 

  `CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Application     ssh.exe                                            8.6.0.1    C:\Windows\System32\OpenSSH\ssh.exe`

## To configure Git to use the Windows version of OpenSSH, update the SSH command with git config, such as:

  `git config --global core.sshCommand C:/Windows/System32/OpenSSH/ssh.exe`


# Start the SSH agent

## To allow `git` to use your SSH key, an SSH agent needs to be running on your device. The method for starting the SSH agent depends on how OpenSSH was installed.

# Git for Windows users (including Winget-based Git installations)

## From a git bash terminal, check if the SSH agent is running using the `ps` command. If the `ssh-agent` is already running, it should appear in the output, such as:

[source ](https://support.atlassian.com/bitbucket-cloud/docs/set-up-personal-ssh-keys-on-windows/#Add-your-key-to-the-SSH-agent)

# Youtube video Ref
- ## [1](https://youtu.be/9dhQIa8fAXU)

- ## [2](https://youtu.be/Wx7WPDnwcDg)

- ## [3](https://youtu.be/8X4u9sca3Io)

## Identity Add
  `ssh-add C:\Users\Hp\.ssh\id_ed25519`

## To ensure the correct SSH key is used when connecting to Bitbucket, update or create your SSH configuration file (~/.ssh/config) with the following settings:

  `Host bitbucket.org
  AddKeysToAgent yes
  IdentityFile ~/.ssh/{ssh-key-name}`
## example 
`Host bitbucket.org
  AddKeysToAgent yes
  IdentityFile ~/.ssh/id_ed25519`

## If removing identity 
  `ssh-add -D`

## Get public value

  `cat C:\Users\Hp\.ssh\id_ed25519.pub`
## Add the public key to your required website or your server

## Lastly verify your connection

  `ssh -T git@bitbucket.org`
  `ssh -T git@gitlab.com`
  `ssh -T git@github.com`

  
