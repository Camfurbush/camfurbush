# NFS Client Setup

Walks through how to connect to an NFS share

## Requirements

1. Must have NFS client for Windows enabled to interact with the NFS server on truenas.lan

## Steps

2. Run `mount -o anon \\truenas.lan\mnt\Pool1 Z:`
3. Open regedit and edit `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ClientForNFS\CurrentVersion\Default`
4. Add New DWORD(32-bit) value inside of default for AnonymousUid and AnonymousGid
5. Restart the your machine
6. Run `mount -o nolock -o anon \\truenas.lan\mnt\Pool1\NFS Z:`
