#### Part 1: Ubuntu – MBR Partitioning (Using fdisk)



Description

In Ubuntu, disk partitioning was performed using the fdisk command-line utility. The disk was initialized using the MBR partitioning scheme and a primary partition was created.



1. Create a instance and volume.
2. Attach those volume with instance.
3. Connect those instance via EC2 instance connect.



Commands Steps :-



1\. Verified available disks:

&nbsp;	lsblk



2\. Created partition using fdisk:



&nbsp;	sudo fdisk /dev/nvme1n1



&nbsp;	n → New partition



&nbsp;	p → Primary



&nbsp;	1 → Partition number



&nbsp;	Default sector values



&nbsp;	w → Write changes and exit



3\. Reloaded partition table:



&nbsp;	sudo partprobe



4\. Formatted partition:



&nbsp;	sudo mkfs.ext4 /dev/nvme1n1p1



5\. Created mount directory:



&nbsp;	sudo mkdir /mnt/MyVol



6\. Mounted partition:



&nbsp;	sudo mount /dev/nvme1n1p1 /mnt/MyVol



7\. Verified:



&nbsp;	df -h

&nbsp;	lsblk



8\. Successfully created and mounted a new partition using MBR partition scheme in Ubuntu.





#### Part 2: Windows – GPT Partitioning (Using Disk Management)



Description

In Windows, disk partitioning was performed using Disk Management tool. The disk was converted to GPT format and a new simple volume was created.



Steps :-

1. Create a instance and volume.
2. Attach those volume with instance.

3\. Connect those instance via window RDP.

4\. Go to disk management and create a disk which name is New Volume D.



Successfully converted disk to GPT and created a new formatted volume using Disk Management.

