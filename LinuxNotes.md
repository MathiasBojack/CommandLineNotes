# Basic Commands

- pwd
- ls
- cd
- mkdir     % creat a folder or a directory 
- rmdir     % delete an empty directory
- rm        % delete files and directories
- touch     % create a file
- man < commandName >   % show the manual page of the command
- < commandName > --help     
- cp fileDir/fileName newFileDir
- mv fileDir/fileName newFileDir[/newfileName] % could be used to rename file:   
        mv file1.txt file2.txt 

- locate [-i] fileName % find the location of a file, [ignoring the case]
  

# Intermediate Commands

- echo  %move some data, usually text into a file.   
        echo textContent>>fileName.fileType
- cat   % display the contents of a file
- nano, vi, jed     % installed text editors in Linux
- sudo/su           % Super User Do
- df [-m]           % disk space availabe on each partition [in megabytes]
- tar               % to work zith tarballs or files compressed in a tarball archive   
        tar [-cvf]  % creating .tar file
        tar [-xvf]  % untar a tar archive
        tar [-tvf]  % list the contents of the archive   
- zip, unzip
- apt               % to work with packages in the Linux command line
        apt-get install packageName
        apt-get update      % update the package in your repository
        apt-get upgrade     % upgrade the system
- chmod             % make a file exectutable and change the permissions granted to it in Linux
        % instead of running python numbers.py, you run:
        [sudo] chmod +x numbers.py
    