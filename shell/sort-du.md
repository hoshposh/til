# `du` Output Sorting

I often want to get the output from the `du` command, sorted by size.

The invocation to use:

```bash
du -h -d 1 | sort -h
```

## References

1. [https://unix.stackexchange.com/a/4682](https://unix.stackexchange.com/a/4682)