# Error

- If you're still having trouble cloning or fetching and are now getting an unable to access 'https://...': Unknown SSL
  protocol error in connection to ...:443 then you may decide to switch off SSL verification for the single operation by
  using the -c http.sslVerify=false option

## Bypass when clone git
### Using when clone new project from git.
- ``` git -c http.sslVerify=false clone https://domain.com/path/to/git ```

## Bypass in one project
### Using config for one project of you.
### Set

- ``` git config http.sslVerify false ```

### Unset

- ``` git config --unset http.sslVerify```

## Bypass global
## Using config all project in one computer
### Set

``` git config --global http.sslVerify false ```

### Unset

- ``` git config --global --unset http.sslVerify```

## Bypass for one url domain

``` git config --global http.https://domain.com.sslVerify false ```

- Which will result in the following in the ~/.gitconfig file:

```
[http]
[http "https://domain.com"]
	proxy = http://proxyUsername:proxyPassword@proxy.server.com:port
	sslVerify = false
```
# Show current configuration
- To show the current configuration of all http sections
```
git config --global --get-regexp http.*
```
- If you are in a locally cloned repository folder then you drop the --global and see all current config:
```
git config --get-regexp http.*
```