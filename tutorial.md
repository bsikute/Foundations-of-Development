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
    git flow feature start MYFEATURE
    
This action creates a new feature branch based on 'develop' and switches to it
