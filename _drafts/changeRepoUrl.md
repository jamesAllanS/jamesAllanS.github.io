# Switching remote URLs from HTTPS to SSH

1. Open Terminal.

2. Change the current working directory to your local project.

3. List your existing remotes in order to get the name of the remote you want to change.

```bash
$ git remote -v
> origin  https://github.com/USERNAME/REPOSITORY.git (fetch)
> origin  https://github.com/USERNAME/REPOSITORY.git (push)
```
4. Change your remote's URL from HTTPS to SSH with the git remote set-url command.

```bash
$ git remote set-url origin git@github.com:USERNAME/REPOSITORY.git
```

5. Verify that the remote URL has changed.
```bash
$ git remote -v
# Verify new remote URL
> origin  git@github.com:USERNAME/REPOSITORY.git (fetch)
```

