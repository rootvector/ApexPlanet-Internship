# Linux File System

## what is filesystem?

OS store and manage data on disk or partitions using a structure called **Filesystem**.

FileSystem includes, directories and it's related permissions.

linux stores data in hierarchy of directories and files.

## ![linux filesystem image](images/filesystem.webp)


### root (/) directory

the root is the starting location of the file system. where all the other directories are present like /boot, /home, /etc, /bin, etc.

- the / represents the root directory of linux filesystem. root directory also known as parent directory.

- the ~ represents the home (/home) directory of linux filesystem.

### Location/path format

- windows: C:\Program Files\Java
- Linux: /etc/folder

| linux is case sensitive.


### Types of File System

- ext3 : extended 3
- ext4 : extended 4
- XFS : extend file system [ Ubuntu, Debian, Fedora, CentOS, RedHat]
- BtrFS (B-tree Fs) : [OpenSUSE and SUSE Linux Enterprise Server]
- FAT : File Allocation Table

**How to check your Linux fileSystem?**
```bash
lsblk -f
df -Th
cat /etc/fstab
```

### XFS vs EXT4

- XFS

optimized for large files and volumes, offering superior performance and scalability.

- EXT4

Performs well across various file sizes but less efficient with extremely large files.

For High-throughput and extensive parallel processing capabilities, XFS is typically more effective then ext4.

### What is inode?
An inode in Linux is a data structure that stores metadata about a file or directory.
The filesystem uses the inode number to locate the inode, which then contains pointers to the data blocks where the actual file data is stored.
simply inode is record of file Metadata produce by creating, editing file.
inode number is location of memory where the data is stored.

**how to see inode number?**
```bash
ls -li
```

---
•/bin: Contains essential user binaries (executables), such as common commands like ls, cp, etc.

• /etc: Holds system configuration files.
Ex: User, Network, Services, System Apps

• /home: Contains the personal directories of all users.

• /root: The home directory for the root user (administrator).

• /var: Where variable data such as logs and databases are stored.

• /tmp: Temporary files created by system and users.

• /boot- Holds files needed for system boot-up, including the Linux
kernel, an initial RAM disk image, bootloader configuration (like GRUB).

• /dev - This directory contains device files which represent and provide
access to hardware devices such as hard drives, sound devices etc.

• /lib, /lib64 - These directories contain essential shared libraries and
kernel modules that are needed to boot the system and run the
commands in the root filesystem. The /lib64 directory exists on
systems that support 64-bit applications.

• /media - This is the mount point for removable media such as USB
drives, CD-ROMs, etc. When these devices are mounted, typically,
directories corresponding to their mount points are created within
/media.

• mnt- Similar to /media, this is a traditional mount point where system
administrators can mount temporary filesystems while using or
configuring them.

• opt - Intended for the installation of add-on application software
packages. Large software packages that are not part of the default
installation can be placed here to avoid cluttering the system
directories.

• /proc - A virtual and dynamic directory as it only exists in memory. It
does not use disk space. It contains information about system
resources, hardware, and running processes. It's a pseudo-filesystem
that provides an interface to kernel data structures.

• /run - A temporary filesystem that stores transient state files, like
process IDs or lock files, since it is cleared and recreated at every boot.

• /sbin- Contains binary (executable) files that are mostly needed by the system
administrator. These include system management commands like fdisk,
shutdown, ip, etc.

• /srv - Contains data which servers hosted on the system may need, such as web
pages served by a web server.

• /sys - Similar to /proc, this is another virtual filesystem that provides an interface
to the kernel. It contains information and settings about the system's devices,
drivers, and some kernel features.

• /usr - Considered the secondary hierarchy because it contains all user
applications and a variety of other things for day-to-day operations, including
libraries, documentation, and much more. Subdirectories include /usr/bin,
/usr/sbin, /usr/local, and /usr/share, among others.



