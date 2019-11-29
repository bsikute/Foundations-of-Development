## How to use GitFlow process with GIT and Github to collaborate
git-flow are a set of git extensions to provide high-level repository operations for Vincent Driessen's branching model.

### Basic tips
1. Git flow provides excellent command line help and output. Read it carefully to see what's happening...
2. The macOS/Windows Client Sourcetree is an excellent git gui and provides git-flow support
3. Git-flow is a merge based solution. It doesn't rebase feature branches.

### Setup
1. You need a working git installation as prerequisite.
2. Git flow works on macOS, Linux and Windows

### Getting started
Git flow needs to be initialized in order to customize your project setup.

### Initialize
Start using git-flow by initializing it inside an existing git repository:

    $ git flow init
    
You'll have to answer a few questions regarding the naming conventions for your branches.
It's recommended to use the default values.

### Features
1. Develop new features for upcoming releases
2. Typically exist in developers repos only

### Start a new feature
Development of new features starting from the 'develop' branch.

    // Start developing a new feature with
    $ git flow feature start myfeature
    
    Switched to a new branch 'feature/feature/myfeature'
    Summary of actions:                                                                                 
    - A new branch 'feature/feature/myfeature' was created, based on 'develop'                          
    - You are now on branch 'feature/feature/myfeature'                                                                                                                                                     
    Now, start committing on your feature. When done, use:                                                                                                                                                       
    git flow feature finish feature/myfeature 
    
This action creates a new feature branch based on 'develop' and switches to it

### Finish up a feature
Finish the development of a feature. This action performs the following

1. Merges MYFEATURE into 'develop'
2. Removes the feature branch
3. Switches back to 'develop' branch

        $ git flow feature finish myfeature
        
        Switched to branch 'develop'
        Already up to date.
        Deleted branch feature/myfeature (was 4fe95c8).
        
        Summary of actions:                                                                                 
        - The feature branch 'feature/myfeature' was merged into 'develop'                                  
        - Feature branch 'feature/myfeature' has been locally deleted                                       
        - You are now on branch 'develop'

### Publish a feature
Are you developing a feature in collaboration? Publish a feature to the remote server so it can be used by other users.

        $ git flow feature publish MYFEATURE

Getting a published feature
Get a feature published by another user.

       $ git flow feature pull origin MYFEATURE
       
You can track a feature on origin by using

        $ git flow feature track MYFEATURE
        
### Make a release
1. Support preparation of a new production release
2. Allow for minor bug fixes and preparing meta-data for a release


### Start a release
To start a release, use the git flow release command. It creates a release branch created from the 'develop' branch.

        $ git flow release start RELEASE [BASE]

You can optionally supply a [BASE] commit sha-1 hash to start the release from. The commit must be on the 'develop' branch.

It's wise to publish the release branch after creating it to allow release commits by other developers. Do it similar to feature publishing with the command:

        $ git flow release publish RELEASE

(You can track a remote release with the

        $ git flow release track RELEASE command)

### Finish up a release
Finishing a release is one of the big steps in git branching. It performs several actions:

1. Merges the release branch back into 'master'
2. Tags the release with its name
3. Back-merges the release into 'develop'
4. Removes the release branch

        $ git flow release finish RELEASE

Don't forget to push your tags with git push origin --tags

### Hotfixes
Hotfixes arise from the necessity to act immediately upon an undesired state of a live production version
May be branched off from the corresponding tag on the master branch that marks the production version.

        $ git flow hotfix start

Like the other git flow commands, a hotfix is started with

        $ git flow hotfix start VERSION [BASENAME]
        
The version argument hereby marks the new hotfix release name. Optionally you can specify a basename to start from.

### Finish a hotfix
By finishing a hotfix it gets merged back into develop and master. Additionally the master merge is tagged with the hotfix version.

        $ git flow hotfix finish VERSION

### Commands
![Commands](https://danielkummer.github.io/git-flow-cheatsheet/img/git-flow-commands.png)
