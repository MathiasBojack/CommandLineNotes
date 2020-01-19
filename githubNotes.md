# github
Notes on using github


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
        commit -m textComments
4. Connect to a remote repository   
        git remote add origin <server>   
5. Send changes to the master branch    
        git push -u origin

 