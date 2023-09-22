# THIS IS OUR NEW README FILE

##Initialise a new repo
```
git Init
```

## To stage all files
```
git add *
```

```
git add .
```

```
git add --all
```

## To commit staged files
```
git commit - m "eaning full message"
```

## To push commits to repo
```
git push -u REMOTE_NAME BRANCH_NAME
```

```
or
```

```
git push
```

## To create a branch 
```
git branch BRANCH_NAME
```

```
or
```

```
git chekcout -b BRANCH_NAME
```

## To delete branch 
```
git branch -d BRANCH_NAME
```

```
or
```

```
git push --d REMOTE_NAME BRANCH_NAME
```
## To merge a branch into your current branch

```
git merge BRANCH_NAME
```

## To undo a commit with a new commit
```
git revert COMMIT_IDENTIFIER
```

## To delete all commits back to specefic point
```
git reset --hard COMMOT_IDENTIFIER
```