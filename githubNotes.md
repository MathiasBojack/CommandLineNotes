# Git
Notes on using github
- [Git](#git)
  - [Concept](#concept)
  - [Command](#command)
  - [Steps to be followed to create a remote repository from local files](#steps-to-be-followed-to-create-a-remote-repository-from-local-files)
  - [Simple Git workflow](#simple-git-workflow)
- [Git hooks](#git-hooks)
## Concept
- Keep track of code history
- can roll back if needed

## Command

- Initialize the local git repository


    git init


- Add/Remove file to the index or the staging area, which will be ready for commit later


    git add .     %Add everything   
    git add <fileName.fileType>   
    git rm --cached <fileName.fileType>

- Check all the files in the staging area and ready for commit, 
  display status of working tree and the staging area
    
    git status
  
- when files are ready, you can commit your files. This takes every file in the staging area into the local repository

    git commit    
    % This will take you to the vim editor for inserting the comment.    
    % Type "I" for inserting and start to comment. Type "Escape" for going out of inserting mode Type ":WQ" to finish the comment   

    git commit -m 'Comments'
    % commit and skip all the editing stage and include the comment.

  
 - Push the local repository you've created and push it to a remote repository on the github
 

    git push

  
- Pull the latest changes from the remote repository


    git pull

  
- Copy a remote repository into the present the folder
  

    git clone

- Create file in git bash
    

    touch fileName.fileType

    
- Configure the user name and email adress for git
    
    git config --global user.name 'userName'   
    git config --global user.email 'emailAdress'

    
- Ignore files that we don't want to include


    touch .gitignore
    % add the name or type of files that you don't want to commit.
    % for ex. log.txt, /directory

  
 - Master and Branch concept: keep the code base (master) unchanged before all fonctionality are finished
  - Create a branch:

    git branch myBranchName
    git checkout myBranchName % switch to another branch
    git merge myBranchName % while in the master, merge the branch with the master

    
- Clone a remote repository to the local file
  

  git clone githubRepositoryLink

## Steps to be followed to create a remote repository from local files

1. Local to the local repository and initialize:  
        git init  
2. Add files to the staging area    
        git add fileName
3. First commit    
        git commit -m textComments
4. Connect to a remote repository   
        git remote add origin <server>   
5. Send changes to the master branch    
        git push -u origin

 ## Simple Git workflow
 
 Steps to be followed to copy a remote repository from other's repository
1. Folk project repository
2. Clone the repository locally   
    ```sh
    Git clone <server>
    ```
3. Modify the code
   ```
   git commit -m commentText
   ```
4. Configure remotes for pushing changes  
   
   There are different philosophies for naming remotes. The Github standard is to use *origin* for your forked repo and *upstream* for the original repo. Another naming strategy is to use descriptive remote names and use <your name> instead of origin and <project name> instead of upstream. This is particularly interesting when you also need to pull somenone else's branch; you then create a remote with that person's name and your naming remains consistent.
   In the following example, we use the origin - upstream naming remotes:

   Set the default remote for pushes to be *origin* and the default push behavior to *current*. Together this means that if you just type ```git push```, the current branch is pushed to the origin remote
    ```sh
    git config remote.pusheddefault origin   
    git config push.default current
    git push
    ```
5. Create a Pull Request
   
    On the GitHub page of your remote fork, click the “pull request” button. Wait for the owner to merge or comment your changes and be proud when it is merged :). If the owner suggests some changes before merging, you can simply push these changes into your fork by repeating steps #3 and #4 and the pull request is updated automatically.

6.  Updating master branch of the folk
    when developping your own code, you may need to track some new commits added to the upstream repository. To do this, you need:
    - Create a remote upstream pointing to the main repository and fetch (go and get) from it:   
    ```sh
    git remote add upstream mainRepositoryLink
    # Verify the new remote named 'upstream'
    git remote -v
    ```
    - Make sure that the local repository is up-to-date with the upstream repository, fetch all changes from the upstream repository
    ```sh   
    # fetch all changes from the upstream repository
    git fetch upstream
    # view all branches
    git branch -va
    ```
    - switch to the master branch of your work and merge changes from the upstream into your work
    ```sh
    # switch to the master branch of your fork
    git checkout master
    # merge changes from the upstream repository into the master branch of your fork
    git merge upstream/master
    ```
7. Doing the work using multiple feature branches
   
   Whenever you begin work on a new feature or bugfix, it's important that you create a new branch. Not only is it proper git workflow, but it also keeps your changes organized and separated from the master branch so that you can easily submit and manage multiple pull requests for every task you complete.

    - create and switch to a new branch for your feature or bugfix
    ```sh
    # Checkout the master branch - you want your new branch to come from master
    git checkout master
    # create a feature or bugfix branch
    git checkout -b feature/<feature-name>
    git checkout -b fix/<#fix-number>
    # delete a branch locally
    git branch -d <branchName>
    git push origin --delete remoteBranchName
    ```
    - upload the branch and all committed changes within it to the remote fork
    ```sh
    git push --set-upstream origin my-feature-branch
    ```
8. Updating a feautur branch 
   - First, merge the upstream repository to the master branch as described by the step 6.
   - Rebase the feature branch from the updated master branch.
    ```sh
    # switch to your feature branch
    git checkout my-feature-branch

    # commit all changes in your feature-branch
    git commit -m MESSAGE

    # update your feature branch from the master branch
    git rebase master
    ```
9. Submitting a pull request
   - Cleaning up your work: Pull in latest upstream master and rebase branch against master
    ```sh
    # Fetch upstream master and merge with your repo's master branch
    git fetch upstream
    git checkout master
    git merge upstream/master

    # If there were any new commits, rebase your development branch
    git checkout feature/featureName
    git rebase master
    ```
   - Push to your forked repo
    ```sh
    git push origin feature/featureName -f
    ```
    - submit pull request on Github in your folked repo.



# Git hooks

Objective: to create some criteria before committing, pushing or merging. If the commit or push fail to satisfy the criteria, they will be not be considered as valid. This helps correcting some errors, for ex. email address or user names.

- Git/hook directory

        /localFileDirectory/./git/hooks
    - comes from bare repo template on init:
      - Linux:
        /usr/share/git-core/templates
      - Windows:
        /gitInstallationDirectory/mingw64/share/git-core/templates
- pre- : script will be run before committing
- post- : script will be run after committing, giving some response
- Failed vs succeeded:
  - success: exit with zero 
  - failure: eixt with any other number
- Could be local or server
- all hooks are disabled by default because of:
  - .sample suffix
  - not executable under linux: need the following command
        chmod +x pre-commit
- hoos are not checked into source control, could then be lost if the local files are deleted. Solution:
  - workaround with symlinks
- Could be bypassed locally:     
        --no-verify
- Could use any script language, configured by the first line:    
        #!/bin/sh
  - default: sh
  - bash
- Using under windows:
  - Correction for the shebang line:
        #! C/:Program\ Files/Git/sur/bin/sh.exe
- Configure global hook path
        git config --global core.hookspath /hook_path