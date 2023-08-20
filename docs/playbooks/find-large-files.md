# Find Large Files Linux

To find large files on a Linux system, use the following command:

``` sh
du -a /opt | sort -n -r | head -n 15 | numfmt --to=iec --format="%-5f"
```
