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
    $ docker run --name mywildfly-volume -d -v myfolder/:/opt/jboss/wildfly/standalone/deployments/ \
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
    
    // Execute a new process in an existing container: Execute and access bash inside a WildFly container
    $ docker exec -it mywildfly /bin/bash


### Image Related Commands
	// Build an image using a Dockerfile:
	$ docker build -t [username/]<image-name>[:tag] <dockerfile-path>
	
	// Build an image called myimage using the Dockerfile in the same folder where the command was executed
	$ docker build -t myimage:latest .
	
	// List the images
	$ docker images
	
	// Tag an image
	Creates an image called “myimage” with the tag “v1” for the image jboss/wildfly:latest
	$ docker tag jboss/wildfly myimage:v1
	
	// Pull an image from a registry
	$ docker pull myimage:1.0
	
	// Push an image to a registry
	$ docker push myrepo/myimage:2.0 


# PowerShell
PowerShell is a task automation and configuration management framework from Microsoft, consisting of a command-line shell and associated scripting language.

### Get-Help
The Get-Help command can be used to literally get help with any other PowerShell command. For example, if you know the name of a command, but you don’t know what it does or how to use it, the Get-Help command provides the full command syntax.

	// Example
	PS C:\> Get-Help -Name Get-Process

### Get-Service
One of the most important commands is Get-Service, which provides the user with a list of all services installed on the system, both running and stopped. 

	// Example
	PS C:\ Get-Service | Where-Object {$_.Status -eq “Running”}

### Get-Process
If you want to view all processes currently running on your system, the Get-Process command is very important. To get a list of all active processes on your computer, type:

	//Example
	PS C:\ Get-Process

### Get-Command
Get-Command is an easy-to-use reference cmdlet that brings up all the commands available for use in your current session.

	// Simply type in this command:
	PS C:\ Get-Command

### Get-EventLog
You can actually use PowerShell to parse your machine’s event logs using the Get-EventLog cmdlet. There are several parameters available. Use the -Log switch followed by the name of the log file to view a specific log. You’d use the following command, for example, to view the Application log:

	//
	PS C:\ Get-EventLog -Log "Application"

### Clear-Content
If you want to delete the contents of an item but retain the item itself, you’ll use the Clear-Content cmdlet:

	// Example
	PS C:\ Clear-Content C:\Temp\TestFile.tx

### Checkpoint-Computer
If you’re making major changes or running a risky experiment, you can set a restore point on your machine with the Checkpoint-Computer cmdlet.

Note that you can only create a restore point using this cmdlet once every 24 hours. If you run the command again, it will keep the previous restore point:

	// Example
	PS C:\> Checkpoint-Computer -Description "My 2nd checkpoint" -RestorePointType "Modify_Settings

### Get-ChildItem
Get-ChildItem displays the files and directories in the PowerShell console. By default Get-ChildItem lists the mode (Attributes), LastWriteTime, file size (Length), and the Name of the item.

	// Example 
	PS C:\ Get-ChildItem

### New-Item
The New-Item cmdlet creates a new item and sets its value. The types of items that can be created depend on the location of the item. For example, in the file system, New-Item creates files and folders. In the registry, New-Item creates registry keys and entries

	// Example 
	PS C:\ New-Item

### Rename-Item
This command renames the file daily_file.txt to monday_file.txt

	// Example 
	PS C:\ Rename-Item -Path "c:\logfiles\daily_file.txt" -NewName "monday_file.txt"


# Bash
GNU Bash or simply Bash is a Unix shell and command language written by Brian Fox for the GNU Project as a free software replacement for the Bourne shell.

### uname
uname is a computer program in Unix and Unix-like computer operating systems that prints the name, version and other details about the current machine and the operating system running on i

	// Example		
	$ uname -a

### mkdir - make directories
The mkdir command in the Unix, DOS, DR FlexOS, IBM OS/2, Microsoft Windows, and ReactOS operating systems is used to make a new directory.

	$ mkdir newDirectory

### mv - rename file/directory
mv is a Unix command that moves one or more files or directories from one place to another. If both filenames are on the same filesystem, this results in a simple file rename; otherwise the file content is copied to the new location and the old file is removed.

$ mv newDirectory newName

### cp - copy file/directory
In computing, cp is a command in various Unix and Unix-like operating systems for copying files and directories.

	// Example: copy all files with extension txt in current location to directory tmp
	$ cp *.txt /tmp

### rmdir - remove empty directories
n computing, rmdir is a command which will remove an empty directory on various operating systems. It is available in Unix, Unix-like, DOS, DR FlexOS, IBM OS/2, Microsoft Windows or ReactOS operating systems. On MS-DOS, the command is available in versions 2 and later

	$rmdir newDirectory

### rm - remove files or directories
n computing, rm is a basic command on Unix and Unix-like operating systems used to remove objects such as computer files, directories and symbolic links from file systems and also special files such as device nodes, pipes and sockets, similar to the del command in MS-DOS, OS/2, and Microsoft Windows.

	$ rm newDirectory


### cat
cat is a standard Unix utility that reads files sequentially, writing them to standard output. The name is derived from its function to concatenate files
	
	// Example to display contents of file /etc/passwd
	$ cat /etc/passwd

### cut
In computing, cut is a Unix command line utility which is used to extract sections from each line of input — usually from a file. It is currently part of the GNU coreutils package and the BSD Base System.

	// Example: 
	$ cut -d : -f 1,7 /etc/passwd

### awk
AWK is a domain-specific language designed for text processing and typically used as a data extraction and reporting tool. It is a standard feature of most Unix-like operating systems

Printing Column or Field
You can instruct AWK to print only certain columns from the input field. The following example demonstrates this −

	// Example
	$ awk '{print $3 "\t" $4}' marks.txt

### find
In Unix-like and some other operating systems, find is a command-line utility that locates files based on some user-specified criteria and then applies some requested action on each matched object

	// Example to find all txt files in / directory
	$ find -iname "*.txt" / 
