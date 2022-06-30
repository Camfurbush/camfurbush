# Add Swap

The steps below will walk an operator through adding a 4gb swap space to a node

## Steps

1. Run `fallocate -l 4G /swapfile`
1. Run `dd if=/dev/zero of=/swapfile bs=1024 count=4194304`
1. Run `chmod 600 /swapfile`
1. Run `mkswap /swapfile`
1. Run `swapon /swapfile`
1. Run `vim /etc/fstab`
1. Run `/swapfile swap swap defaults 0 0`
