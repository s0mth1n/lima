---
title: Snapshots
weight: 5
---

> **Warning**
> `limactl snapshot` is experimental

The state of an instance can be saved as a snapshot and restored later with `limactl snapshot`.
Snapshots are supported by the `qemu` and `krunkit` drivers; `vz`, `wsl2`, and
`hcs` do not support snapshots.

```bash
# Create a snapshot
limactl snapshot create default --tag snap1

# List snapshots
limactl snapshot list default

# Apply (restore) a snapshot
limactl snapshot apply default --id 1

# Delete a snapshot
limactl snapshot delete default --id 1
```

`apply` and `delete` accept `--tag` instead of `--id`.

The `qemu` driver can snapshot both running and stopped instances; the
snapshots are stored in the instance's qcow2 disk image.
The `krunkit` driver requires the instance to be stopped.

See also the command reference:
- [`limactl snapshot`](/docs/reference/limactl_snapshot/)
