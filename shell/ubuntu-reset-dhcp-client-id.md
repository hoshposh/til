# Reset DHCP Client ID on an Ubuntu VM template

Ran into an issue where a VM was cloned from an Ubuntu template, and **all** of the clones were receiving the same DHCP assign IP addresses. For Ubuntu the unique client identifier is held in the `/etc/machine-id` file.

It is worth noting that removing the file, expecting it to be regenerated does not work. To force a new identifier to be assigned, the following must be true when the VM boots up.

1. The file must exist.
1. The file must be empty.

## Invocation

To reset it to be an _empty_ file, use the following:

```bash
echo "" | sudo tee /etc/machine-id >/dev/null
```

## Reference

- https://blah.cloud/kubernetes/creating-an-ubuntu-18-04-lts-cloud-image-for-cloning-on-vmware/