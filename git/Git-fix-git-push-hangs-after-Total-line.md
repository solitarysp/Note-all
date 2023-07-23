# Error

- When pushing data to git remote, if your data is too much. Post buffer will be maxed
- you will be hanged here
```
Counting objects: 51, done.
Delta compression using up to 2 threads.
Compressing objects: 100% (47/47), done.
Writing objects: 100% (47/47), 27.64 MiB | 6.47 MiB/s, done.
Total 47 (delta 4), reused 0 (delta 0)
```
- REF
  - https://git-scm.com/docs/git-config#Documentation/git-config.txt-httppostBuffer

## FIX
### Increase the Git buffer size to the largest individual file size of your repo
- ``` git config --global http.postBuffer 157286400 ```
- REF:
  - https://confluence.atlassian.com/bitbucketserverkb/git-push-fails-client-intended-to-send-too-large-chunked-body-779171802.html

## If you use a proxy
- If you are using a proxy, please check your proxy's Buffer limit.(Or remove proxy)
