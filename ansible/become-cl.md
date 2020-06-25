# Using 'become' On The Command-Line

You use `become` as the equivalent of a `sudo` in a Linux shell environment. This provides a quick reminder on how to achieve that on the command-line with the `ansible` command.

## Invocation

```bash
ansible app -m file -a "......" -b --become-user=jenkins
```

The `--become-user` is optional in case you have a specific user to become. The default is to become `root`.

## References
- https://www.middlewareinventory.com/blog/ansible-sudo-ansible-become-example/
