# Git Intermediate Cheat Sheet

You can watch this video for detailed examples:

📹 [131H Reverting Commits with Git](https://www.youtube.com/watch?v=SqkVP_4qeCI)

Below are the terminal commands you want for the following actions:

### View all your commits

```
git log --oneline
```

In the following examples, COMMIT_ID (and its variations) stands for the id of the commit you'd like to work on. This can be a shorter 7-digit hexadecimal number like `d07e1ea` or a longer one like `d07e1eafb968b42e00c138a36e3d3d742ed8a270`

### Look at old code

This is just to poke around. Any changes you make will be lost when you go back to the master branch.

```
git checkout COMMIT_ID
```

### Go back to the master branch

This takes you back to the most recent code you are working on.

```
git checkout master
```

### Undo what you just committed

If you want to undo your last commit.

```
git revert MOST_RECENT_COMMIT_ID
```

### Undo a range of commits, in multiple steps

_Note: **Undo a range of commits, in one step** is preferred by most people._

Don't miss the caret! This will include OLDER_COMMIT_ID, the NEWER_COMMIT_ID, and everything in between.

```
git revert OLDER_COMMIT_ID^..NEWER_COMMIT_ID
```
And then continue each step in VS Code:

```
git revert --continue
```

### Undo a range of commits, in one step

Don't miss the caret! This will include OLDER_COMMIT_ID, the NEWER_COMMIT_ID, and everything in between.

```
git revert --no-commit OLDER_COMMIT_ID^..NEWER_COMMIT_ID
```

And then

```
git commit -m "Your message goes here!"
```

### Make sure you are up-to-date

```
git push
```

### Check that you are pushing to Github

```
git remote show origin
```

