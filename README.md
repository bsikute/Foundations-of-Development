# Reference Guide - GIT, Docker, PowerShell and Bash
The following is a reference guide that demonstrates some commands used to work with GIT, Docker, PowerShell and Bash

# GIT
Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.

   ### Configure tooling
   Configure user information for all local repositories

    // Sets the name you want attached to your commit transactions
    $ git config --global user.name "bsikute"
    
    // Sets the email you want attached to your commit transactions
    $ git config --global user.email "bsikute@gmail.com"
    
   ### Create repositories
   When starting out with a new repository, you only need to do it once; either locally,  
   then push to GitHub, or by cloning an existing repository
   
    // Sets the
    Clone (download) a repository that already exists on GitHub, including all of the files, branches, and commits
    $ git clone https://github.com/bsikute/Git-Collab_task.git
    
   ### Branching
   Branches are an important part of working with Git. Any commits you make will be made on the branch 
   you're currently “checked out” to. Use git status to see which branch that is.
   
    $ git branch newBranch
    Creates a new branch called newBranch
    
    $ git checkout newBranch
      Switches to the specified branch (newBranch) and updates the
      working directory

    $ git merge newBranch
      Combines the specified branch’s history into the
      current branch. This is usually done in pull requests,
      but is an important Git operation
      
   ### Synchronize changes
   Synchronize your local repository with the remote repository on GitHub.com
   
    $ git push
    Uploads all local branch commits to GitHub

    $ git merge
    Combines remote tracking branch into current local branch
    
    $ git fetch
    Downloads all history from the remote tracking branches
    
    $ git pull
    Updates your current local working branch with all new
    commits from the corresponding remote branch on GitHub.
    git pull is a combination of git fetch and git merge
  
   ### Redo commits
   Erase mistakes and craft replacement history

    $ git reset [commit]
    Undoes all commits after [commit], preserving changes locally
    
    $ git reset --hard [commit]
    Discards all history and changes back to the specified commit

# Docker
Docker is a set of platform as a service products that use OS-level virtualization to deliver software in packages called containers.

### Container Related Example Commands
    // Run a container in detached mode:
    $ docker run --name mywildfly -d -p 8080:8080 jboss/wildfly
    
    // Run a detached container mounting a local folder inside the container:
    $ docker run --name mywildfly-volume -d \
    -v myfolder/:/opt/jboss/wildfly/standalone/deployments/ \
    -p 8080:8080 jboss/wildflyjboss/wildfly

    // Follow the logs of a specific container:
    $ docker logs -f mywildfly
    $ docker logs -f [container-name|container-id]

    // List containers: List only active containers
    $ docker ps
    
    // Stop a container:
    $ docker stop [container-name|container-id]
    
    // Remove a container:
    $ docker rm [container-name|container-id]
	 
    // Force stop and remove a container
    $ docker rm -f [container-name|container-id]
    
    // Execute a new process in an existing container:
	 # Execute and access bash inside a WildFly container
    $ docker exec -it mywildfly /bin/bash


### Share
### Run

# PowerShell
PowerShell is a task automation and configuration management framework from Microsoft, consisting of a command-line shell and associated scripting language.

# Bash
GNU Bash or simply Bash is a Unix shell and command language written by Brian Fox for the GNU Project as a free software replacement for the Bourne shell.
