# Lunch-time Linux  
## Introduction to Systems Administration  
**Scott Hazelhurst**  
**April 2026**

# Lecture 1

## 1. Overview of the Course

This lecture is an introduction to Linux systems administration, especially for people working in scientific or research computing environments.

It is not designed for professional system administrators, but for users who:

- Already have some Linux skills.
- Need administrator (`root`) access to Linux systems.
- Need to support scientific computing systems.
- Want to understand how Linux systems are managed.

The course focuses on:

- Small- to mid-scale systems.
- Practical administration.
- Automation.
- Scalable approaches rather than only manual work.

The broader course includes:

- Storage
- Access and security
- Cluster setup (SLURM, groups, user management)
- Automation
- Monitoring systems
- Backup
- Containerisation

## 2. Storage Fundamentals

Storage in Linux is usually provided through block devices.

Types mentioned:

- Magnetic Disk (HDD)
- SSD
- RAM Disk
- RAID
- LVM (PV/LV)

## 3. Direct Disk Commands

```bash
fdisk -l
smartctl -a /dev/sda
dd if=/dev/zero of=/dev/sda bs=64M
dd if=Rocky-9.7-x86_64-dvd.iso of=/dev/sdc bs=64M
```

## 4. Common Storage Tasks

- Divide one physical disk into logical partitions.
- Combine multiple disks into one logical disk.
- Combine storage across multiple computers.

## 5. Disk Partitioning

Most disks are divided into partitions.

Important concepts:

- Partition table
- Partition boundaries
- Planning ahead before partitioning

## 6. Safe Practice Using a File as a Disk

Steps:

1. Create a file.
2. Attach as loop device.
3. Create partition table.
4. Use partitions.

## 7. Create Virtual Disk

```bash
dd if=/dev/zero of=/tmp/disk.img bs=64M count=16
```

## 8. Loop Devices

```bash
losetup -f /tmp/disk.img --show
```

## 9. Partition Tables

Formats mentioned:

- GPT
- MSDOS / MBR
- MAC

GPT is the preferred focus.

## 10. Using parted

```bash
parted /dev/loop0
```

Commands:

```bash
p
mklabel gpt
help
quit
```

## 11. Creating Partitions

```bash
mkpart primary 4MB 256MB
mkpart primary 256MB 768MB
mkpart primary 768MB 1024MB
```

Devices created:

- /dev/loop0p1
- /dev/loop0p2
- /dev/loop0p3

## 12. File Systems

Examples:

- ext2
- ext3
- ext4
- ntfs
- xfs
- zfs
- swap

## 13. UUIDs

```bash
blkid
```

Used to uniquely identify devices and filesystems.

## 14. Creating File Systems

```bash
mkfs.xfs /dev/loop0p2
mkfs.ext4 /dev/loop0p1
```

## 15. Internal Concepts

- Files may be non-contiguous.
- Metadata stores file properties.
- Inodes track files.

## 16. Directories

Directories are special files mapping names to inode numbers.

## 17. Links

```bash
ln data.csv data1.csv
ln -s data.csv data2.csv
```

- Hard link = same inode
- Symbolic link = pathname reference

## 18. Mounting

```bash
mount -t xfs /dev/loop0p2 /mnt
umount /mnt
```

## 19. Mount by UUID

```bash
mount UUID="..." /mnt
```

## 20. Mount Rules

Common mount points:

- /home
- /opt
- /data
- /scratch

## 21. Failures

- Physical disk failure
- Metadata inconsistency
- Power loss
- Crashes during writes

## 22. XFS Log / Journaling

XFS replays metadata logs after crashes.

## 23. Repair Tools

- `xfs_repair`
- `fsck`

Recovered files may appear in `lost+found`.

## 24. Permanent Mounts

- `/etc/fstab` = configured mounts
- `/etc/mtab` = currently mounted filesystems
