# Resetting HEAD To A Previous Commit

There are times where you want to rewrite your git commit history and get rid of an accidental local commit, but not necessarily get rid of the changes on the local filesystem.

```bash
git reset --soft HEAD^
```

## Reference

- [git-scm.com/docs/git-reset](https://git-scm.com/docs/git-reset)