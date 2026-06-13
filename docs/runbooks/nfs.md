# NFS Client Setup

Walks through how to connect to an NFS share

## Requirements

1. Must have NFS client for Windows enabled to interact with the NFS server on fileserver.lan

## Steps

1. Run `mount -o anon \\fileserver.lan\mnt\Pool1 Z:`
1. Open regedit and edit `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ClientForNFS\CurrentVersion\Default`
1. Add New DWORD(32-bit) value inside of default for AnonymousUid and AnonymousGid
1. Restart the your machine
1. Run `mount -o nolock -o anon \\fileserver.lan\mnt\Pool1\NFS Z:`
