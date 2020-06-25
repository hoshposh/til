# Bash Aliases And Functions

Bash provides a way to _alias_ command invocations, so you can setup default invocation params and reduce the number of keystrokes when you use that command a lot of times.

```bash
# common ls alias
alias l='ls -la'

# remove the most recently created docker container
alias drml='docker rm -f $(docker container ps -ql)'
```

When you need to pass in parameters you can instead create functions.

```bash
# SSH keygen & keyscan update for known_hosts given an IP address
update_known_hosts ()
{
    ssh-keygen -R $1 && ssh-keyscan -H $1 >> ~/.ssh/known_hosts
}
```

Place this in your `~/.bashrc` file and after saving to make the changes available using the following:

```bash
source ~/.bashrc
```

## Reference

- https://linuxize.com/post/how-to-create-bash-aliases/
