# Use to clone all branches on remote to local branch
## Step
### Add Config cmd global
 - Using git bash here 
 ```
git config --global alias.clone-all-remote '! git branch -a | sed -n "/\/HEAD /d; /\/master$/d; /remotes/p;" | xargs -L1 git checkout -t'
 ```
- In project git using cmd
```
git clone-all-remote
```
