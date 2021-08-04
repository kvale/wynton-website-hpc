# File Sizes and Disk Quotas

## File sizes on /wynton/

The `/wynton/` storage is on a [ZFS] file system on top of our BeeGFS parallel storage system. This is **automatically compressed** (using [lz4] compression in ZFS) before anything is written to the physical drives.  Because of this, a 1.0 MiB file is likely to occupy less that 1.0 MiB of drive space.  Exactly, how much a file is compressed varies greatly with file format but as a rule of thumb plain text files can be compressed more than files in a binary format.  Already compressed files such as GZ or ZIP files are unlikely to be compressed further.

Because of this underlying disk compression, command-line tools such as `ls` and `du` may not report what you expect it to report.  For example, consider the Singularity image file `rocker_r-base.img` of size 274,538,527 bytes (= 274,538,527/1024^2 = 261.8 MiB);

```sh
[alice@{{ site.devel.name }} ~]$ ls -l rocker_r-base.img
-rwxr-xr-x. 1 alice boblab 274538527 May  8  2018 rocker_r-base.img
```
The actual space consumed on disk by this file is 256,136,704 bytes (93.3%):
```sh
[alice@{{ site.devel.name }} ~]$ ls -s --block-size 1 rocker_r-base.img
256136704 rocker_r-base.img
```

Using the disk-usage tool `du`, we can see the same if we do:
```sh
[alice@{{ site.devel.name }} ~]$ du --apparent-size --block-size=1 rocker_r-base.img
274538527       rocker_r-base.img
```
and
```sh
[alice@{{ site.devel.name }} ~]$ du --block-size=1 rocker_r-base.img
256136704       rocker_r-base.img
```

_Comment_: It is the _compressed_ size that counts towards your disk quota.



## User disk quota on /wynton/home/

To check how much storage space you have consumed on `/wynton/home/`, and the total amount available to you, call:

```sh
beegfs-ctl --getquota --storagepoolid=11 --uid "$USER"
```

For example,

```sh
[alice@{{ site.devel.name }} ~]$ beegfs-ctl --getquota --storagepoolid=11 --uid "$USER"
      user/group     ||           size          ||    chunk files    
     name     |  id  ||    used    |    hard    ||  used   |  hard   
--------------|------||------------|------------||---------|---------
         alice| 99002||   88.71 GiB| 1000.00 GiB||   645266|unlimited
```

tells us that user `alice` has 645,266 files that occupy 88.71 GiB ('size used') on the BeeGFS file system out of their 1000.00 GiB ('size hard').  **Importantly**, because the `/wynton/home/` storage is **mirrored**, the disk usage ('size used') and the available quota ('size hard') are **reported at twice the size** of what you would expect for a non-mirrored storage.  This is why your <a href="{{ '/about/specs.html' | relative_url }}">500-GiB home storage space</a> is reported as 1000 GiB by the `beegfs-ctl` tool.

## User disk usage on /wynton/scratch/

To check your disk consumption on `/wynton/scratch/` ("global scratch"), use:

```sh
beegfs-ctl --getquota --storagepoolid=10 --uid "$USER"
```

_Comment_: There are no user or group quotas on `/wynton/scratch`, but [files on `/wynton/scratch/` that are older than two weeks are deleted automatically]({{ '/about/specs.html' | relative_url }}).


## Group disk quota on /wynton/group/

If your group (lab) has [purchased additional storage]({{ '/about/pricing-storage.html' | relative_url }}), it is available under `/wynton/group/`.  To check how much storage space your group/lab has consumed on `/wynton/group/`, and the total amount available to you, call:

```sh
beegfs-ctl --getquota --storagepoolid=12 --gid "$(id --group)"
```

For example,

```sh
[alice@{{ site.devel.name }} ~]$ beegfs-ctl --getquota --storagepoolid=12 --gid "$(id --group)"
      user/group     ||           size          ||    chunk files
     name     |  id  ||    used    |    hard    ||  used   |  hard
--------------|------||------------|------------||---------|---------
        boblab| 34001||      0 Byte|   40.00 TiB||        0|unlimited
```

Note that this storage is shared among all group members and does _not_ count toward your personal disk quota under `/wynton/home/`.



[lz4]: https://en.wikipedia.org/wiki/LZ4_(compression_algorithm)
[ZFS]: https://en.wikipedia.org/wiki/ZFS
