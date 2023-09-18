## Sync a forked repo

```bash
gh repo sync owner1/repo1 --source owner2/repo2
```

## Code pulling from local to remote
To get the latest code from the github repo to our remote cloned repo

```bash
git pull origin
```

## Create a pull request to the owner of the forked repo
The below command will let you create pull request interactively.

```bash
gh pr create -R owner/repo
```

Where `owner/repo` is the repo that is being forked to your local and remote repo.