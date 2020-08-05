# Terragrunt destroy-all But Exclude Dependencies

[terragrunt](https://github.com/gruntwork-io/terragrunt) handles folder traversal very well, allowing you to use the suite of `*-all` commands across many modules, including dependencies defined in the `terragrunt.hcl` files.

An example multi-layer layout might look like this:

```
.
.
├── mgmt
│   ├── openvpn-server
│   └── vpc
├── dev
│   ├── app-one
│   └── app-two
└── _global
    └── repo
```

You want to perform a `terragrunt destroy-all` action in the `dev` folder without destroying the modules in `mgmt` or `_global`.

Normally you would use the command-line parameter, `--terragrunt-non-interactive` to avoid answering `y` to questions about performing the command against external dependencies. Unfortunately, during deletions you want a way to automatically answer `no` and exclude external dependencies.

## Invocation

```console
cd dev
terragrunt destroy-all --terragrunt-ignore-external-dependencies
```

This will avoid asking individually about the external dependencies, and when you say `yes` to deleting the modules in `dev`, it will exclude the dependencies outside of that folder.

## References

- https://github.com/gruntwork-io/terragrunt/issues/1216#issuecomment-643485356
- https://terragrunt.gruntwork.io/docs/reference/cli-options/#terragrunt-ignore-external-dependencies