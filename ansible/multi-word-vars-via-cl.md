# Passing multi-word variables on the ansible-playbook command-line

I ran into a strange issue when I tried to pass a multi-word value to a variable via the `ansible-playbook` command-line invocation.

## Example Issue

In the following example I am assigning a variable to be `My name is Lyndon`:

```console
ansbile-playbook -i '10.204.110.68,' ./ansible/intro.yml -e my_greeting="My name is Lyndon"
```

Using some `debug` task I observed that the value of the variable:

```console
(local-exec): ok: [10.204.110.68] => {
(local-exec):     "my_greeting": "My"
(local-exec): }
```

## Solution

To get the full multi-word value I had to use the JSON syntax for the variable assignment:

```console
ansbile-playbook -i '10.204.110.68,' ./ansible/intro.yml -e '{"my_greeting":"My name is Lyndon"}'
```

This produced the expected results in my `debug` task:

```console
(local-exec): ok: [10.204.110.68] => {
(local-exec):     "my_greeting": "My name is Lyndon"
(local-exec): }
```

## Reference

- https://docs.ansible.com/ansible/latest/user_guide/playbooks_variables.html#passing-variables-on-the-command-line