# Expand Disk

1. Expand disk in vSphere
1. Restart VM
1. fdisk /dev/sda
1. Enter `p` to print your initial partition table.
1. Enter `d` (delete) followed by 2 to delete the existing partition definition (partition 1 is usually /boot and partition 2 is usually the root partition).
1. Enter `n` (new) followed by p (primary) followed by 2 to re-create partition number 2 and enter to accept the start block and enter again to accept the end block which is defaulted to the end of the disk.
1. Enter `p` to print your new partition table and make sure the start block matches what was in the initial partition table printed above.
1. Enter `w` to write the partition table to disk. You will see an error about Device or resource busy which you can ignore.
1. `partx -a /dev/sda`
1. `xfs_growfs /`
