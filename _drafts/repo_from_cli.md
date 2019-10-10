# CLI commands for github API v3

* Remember replace USER with your username and REPO with your repository/application name! (replace all CAPS keywords):

Create repo:
```
curl -u 'USER' https://api.github.com/user/repos -d '{"name":"REPO"}'
```

```
git remote add origin git@github.com:USER/REPO.git
git push origin master
```

or(?);
```
git push -u origin master
```
(-u remembers prefereces for remote & branch, just use git push next time) (Needs further research)


## Problem:
You  have initialized a git repository in a folder using
```
git init
```
Now that you have made some commits, you want to use
```
git push
```
but you get the following error message:

fatal: No configured push destination.
Either specify the URL from the command-line or configure a remote repository using

    git remote add <name> <url>

and then push using the remote name

    git push <name>

## Solution:

As you initialized your repository using git init, git does not know which server to contact when you use git push.

Therefore, we’ll have to add a server (called remote in git terminology) to the repository:
```
git remote add origin git@github.com:yourusername/yourrepository.git
git remote add origin git@github.com:James-A-S/listingsFromCSV.git
```
Remember to replace git@github.com:yourusername/yourrepository.git with the correct URL for your repository. Valid example URLs include:

https://github.com/ulikoehler/UliEngineering.git
git@github.com:ulikoehler/UliEngineering.git
This adds a server (remote add) named origin with the URL git@github.com:yourusername/yourrepository.git.

The URL (last argument) depends on the server you use, for GitHub, you can get the URL (HTTPS or SSH, both will work) by clicking the green Clone or Download button.

Now you can push your existing data to the server. git push by itself won’t work for the first time, because git doesn’t know automatically that you want to push to origin. Therefore we have to tell it using --set-upstream that future git push commands shall automatically push to origin:
```
git push --set-upstream origin master
```
If this command lists an error, you likely used the wrong URL for the repository or you don’t use the correct credentials (username/password, SSH key etc).

From now on, you can just use
```
git push
```
every time you’ve made a commit in order to push it to the server.

Note: origin is no special name, it’s just the name git uses for the server when you git clone a repository. Therefore it’s the standard name for your main server to push to. Similarly, git uses master as the default branch name.
