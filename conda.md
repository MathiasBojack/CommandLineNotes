# Why using conda

- Multipurpose programming and a single computer:
  - differnt packages
  - different python version
- Solution
  - visual environment for different python application

 Different installation for Python
 ```mermaid
graph TD
    Python.org-->pip
    Python.org-->virtualenv
    pip-->package-Management
    virtualenv-->Virtual-Environments

    Anaconda-->Conda
    Conda-->package-Management
    Conda-->Virtual-Environments
 ```

# How to use conda

site: https://www.youtube.com/watch?v=23aQdrS58e0

In Annaconda Powershell prompt:
- List of command :
    - conda cheat sheet
  
```
    # check all the env:
    conda env list
    
    # create env
    conda create --name env_name python=version_number
    
    # list all the package of the current env
    conda list

    # activate one env:
    source activate env_name
    # deactivate one env:
    source deactivate 
    
    # install new package on the default channel
    conda install numpy

    # list all channels
    conda config --show channels

    # install new package on a new channel
    # conda install -c channel_name package_name
    conda install -c pytorch pytorch

    # Add a new channel to all environment
    # channels are add to all the channels
    # conda config --add channels channel_name
    conda config --add channels conda-forge

    # check the priority of different channels
     conda config --get channels

```


