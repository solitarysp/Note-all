- Git SubModel is ?? (https://git-scm.com/book/en/v2/Git-Tools-Submodules) 
# Git SubModel clone new 
- To clone git repository, we can do 2 ways
# Clone all for the first time
- Using cmd with pattern `git clone --recursive giturl` to clone git and its Submodules
- Example : 
 ```
    git clone --recursive https://github.com/ggerganov/ggwave-java.git
 ```
# Update init after cloning the main repository
- Using cmd `git submodule update --init --recursive` in root project folder
