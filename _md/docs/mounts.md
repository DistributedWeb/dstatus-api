## DWebX Mounts

DWebX has the ability to "mount" dvaults into each other as subfolders. This is similar to a symlink.

Consider this example:

```
dwebx://bob.com/sites/ug -> dwebx://unwalled.garden/
```

Reading from a mount is similar to reading a subfolder. In this case, reading `/sites/ug/index.html` would give you the content of `dwebx://unwalled.garden/index.html`. 

Mounts have a performance benefit in DWebX: because mount data can be transfered over an existing connection, it can be faster to read than loading the dwebx separately. We use that property to distribute metadata efficiently in the [refs directory](/dir/refs).