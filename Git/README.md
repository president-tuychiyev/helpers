## Configure Git to use a proxy

- set proxy

```bash
git config --global http.proxy 'socks5://127.0.0.1:1080'
```

```bash
git config --global https.proxy 'socks5://127.0.0.1:1080
```

- unset proxy

```bash
git config --global --unset http.proxy
```

```bash
git config --global --unset https.proxy
```

[View docs](https://gist.github.com/evantoli/f8c23a37eb3558ab8765)

<hr>

## Reset all commits

HEAD~1 is "the first parent of HEAD", while HEAD~2 is "the first parent of the first parent of HEAD, and so on (so HEAD~n for some n is like HEAD followed by n ^ symbols and no numbers). Again, all the specifics are in the git-rev-parse manual page.

Be careful when mixing git reset with "revisions counting backwards from HEAD". git reset will, in general, change the value of HEAD, e.g.:

```bash
git checkout master    # now on tip of "master" branch
```

```bash
git branch save master # copy branch tip to another label, for safekeeping
```

```bash
git reset HEAD^        # or git reset HEAD~1
```

[View docs](https://stackoverflow.com/questions/18102718/what-does-the-1-mean-in-this-git-reset-command)

<hr>

## git-restore - Restore working tree files
```bash
git restore <file> <any file name>
```
[View docs](https://git-scm.com/docs/git-restore)

<hr>

## Set global credential for pull and push
```bash
git config --global credential.helper store
```
```bash
git pull
```

<hr>

## Remove all commit changes
```bash
git reset --hard origin/<branch>
```
