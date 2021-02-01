# Git Config proxy

## Info

- We will probably need to configure a proxy for git when we have errors connecting to the git server
- Example Error:
  ``` 
  - unable to access '...' Couldn't resolve host '...' 
  - ...etc..
  ```

# Config proxy
You can configure these globally in your user ``~/.gitconfig`` file using the `` --global `` switch, or local to a repository in its ``.git/config`` file.

### With git we will have 2 types of proxies with different priorities
- Project :
  - For project type, proxy we will install separately for a project. We have many projects with 1 proxy for a different project.
- Global :
  - With global, we will configure our current computer. All operations related to git without a config project will use the global config.
### Priority level
 - If there is no config for the project. The system will use the global config
 - If there exists a configure project, the system will use the project's config
## Setting
### Setting proxy global
- Configure a global proxy. If there is no config for the project. The system will use the global config
#### Step config
- Open Terminal
- Config with authentication proxy
```
git config --global http.proxy http://proxyUsername:proxyPassword@proxy.server.com:port
```

- Config not authentication proxy
```
git config --global http.proxy http://proxy.server.com:port
```
#### URL specific proxy global
- Run the global config command. We will edit the config file in ```~/.gitconfig```
```
  [https]
  proxy = https://proxy.server.com:port
  [http]
  proxy = http://proxy.server.com:port
```
#### Unset a proxy global
- Use the --unset flag to remove configuration being specific about the property -- for example whether it was http.proxy or http.<url>.proxy. Consider using any of the following:
##### Step config
- Open Terminal
```
git config --global --unset http.proxy
git config --global --unset https.proxy
```
### Setting proxy for project
- For project type, proxy we will install separately for a project. We have many projects with 1 proxy for a different project.
#### Step 
- Goto to directory of project. Where contains the project's ``.git`` folder
- Open Terminal
- Run Config with authentication proxy
```
git config http.proxy http://proxyUsername:proxyPassword@proxy.server.com:port
```
- Config not authentication proxy
```
git config http.proxy http://proxy.server.com:port
```
### URL specific proxy prject
- Run the project config command. We will edit the config file in ```git/config``` in folder git of project
```
  [https]
  proxy = https://proxy.server.com:port
  [http]
  proxy = http://proxy.server.com:port
```
#### Unset a proxy project
- Use the --unset flag to remove configuration being specific about the property -- for example whether it was http.proxy or http.<url>.proxy. Consider using any of the following:
##### Step 
- Goto to directory of project. Where contains the project's ``.git`` folder
- Open Terminal
```
git config --unset http.proxy
git config --unset https.proxy
```
