# Docker Login With AWS

With the latest version of the `aws-cli`, v2.x, the approach to retrieve AWS credentials to use to login to the AWS ECR have changed. The `aws ecr get-login` is no longer supported, and instead `aws ecr get-login-password` should be used.

## Invocation

1. Make sure that the AWS environment vaiables are assigned, to aid with authentication.
1. To login run the following invocation:
    ```console
    aws ecr get-login-password --region us-east-2 | docker login --username AWS --password-stdin 621270530972.dkr.ecr.us-east-2.amazonaws.com
    ```
1. You should see `login succeeded.` and be able to proceed with actions that interact with the registry.

## References

- https://docs.aws.amazon.com/AmazonECR/latest/userguide/Registries.html#registry_auth