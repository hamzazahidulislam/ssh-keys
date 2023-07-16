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






