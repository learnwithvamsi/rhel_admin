# Linux evolution:
```
(1987) minix → Unix, aix, Hp sun solaris (AT&T ,bell labs) – (1991) linux 
based on unix principles
Linux== enterprise(Rhel server client, workstation) ,testing (fedora), 
free(centos)
Different distributions in linux:
Unix base for linux. Unix is open source. anyone can modify binaries.
Red hat, ubuntu, centos, amazon Linux,
Sloaris, Ibmaix, oracle Linux, Fedora, Susie, Hpux.
Redhat linux distribution such as centos use anaconda (written in python which make sure os is correctly applied to machine)as installer
```
# Types of service managers/
```
System V/init vs system d:
• SystemV is older, and goes all the way back to original Unix.
• SystemD is the new system that many distros are moving to.
• SystemD was designed to provide faster booting, better dependency management, and much more.
• SystemD handles startup processes through .service files.
• SystemV handles startup processes through shell scripts in /etc/init*.
• If you’re starting and stopping things using systemctl restart sshd, etc, you’re on a SystemD system.
• If you’re starting and stopping things using /etc/init.d/sshd start, etc, you’re on a SystemV system.
Systemd: Amazon Linux, Red Hat Enterprise, CentOS, Fedora,Debian/ubuntu
systemV : Gentoo, Alpine, Slackware, Linux from Scratch
```


# kernel space:
``` 
Uname stands for UNIX name. It is a utility to check the system information 
of your Linux computer.
uname -r == kernel version
dmesg | grep linux == kernel version
dmesg used to write the kernel messages in Linux and other Unixlike operating systems to standard output
dmesg | less
dmesg |grep -i usb
dmesg | grep -i dma
dmesg | grep -i memory
dmesg | grep -i tty
cat /proc/version == kernel version ,built info , compiler
cat /etc/fstab == 
The /etc/fstab file is a system configuration file that contains all available disks, 
disk partitions and their options. ...
The /etc/fstab file is used by the mount command, which reads the file to determine which options should be used when mounting the specified device.
cd /boot
ls -l | grep ` uname -r` ===== kernel file location
{lsusb , lspci} not imp
```



```
cat /etc/os-release == check os 
hostnamectl:
The “hostnamectl” is a Linux command that is used to set the hostname in the terminal without even opening and editing in the etc/hostname file of a system 
1.static hostname = Set by system administrators
2. dynamic hostname - set by mdns servers on execution time
3. Pretty hostname.= set by systemadmin or user
```
# How network time works?
NTP is an internet protocol that's used to synchronize the clocks on computer 
networks to within a few milliseconds of universal coordinated time (UTC).
Dependencies of packages= supporting environments/ binaries for a package.
Networking:
Hostname: for internal functioning
network ==> dhcp for client machine?
 manual configurations for servers for dns? 

# network management tools for basic trouble shooting:
```
network statistics == netstat -a
ping Packet Internet or Inter-Network Grope to test destination ip address == 
ping <google.com>
ipconfig == interface configuration == 
ipconfig /release
ipconfig /renew
route: route command in Linux is used when you want to work with the IP/kernel routing table.
arp: address resolution protocol: manipulates or displays ipv4 network neighbour cache.
nslookup: nameserverlookup: getting info from DNS server It is a network administration tool for querying the Domain Name System (DNS) to obtain domain name or IP address mapping or any other specific DNS record. It is also used to troubleshoot DNS-related problems.
ip address:
mac address:
hostname: /etc/hostname
flush dns cache
the /etc/resolv.conf file defines how the system uses DNS to resolve host names and IP addresses. This file usually contains a line specifying the search domains and up to three lines that specify the IP addresses of DNS server.
dns: /etc/resolve.conf
ip address set at /etc/sysconfig/network-scripts
kdump:feature that allows the Linux kernel that creates crash dumps in the 
event of a kernel crash.
yum install nmap 
nmap = network mapper
dig= dig command (domain information groper) provides DNS information and 
helps in diagnosing issues. The utility's raw output makes it the preferred 
method for troubleshooting DNS issues.
Dig <domain name /ip>
Host <domain name/ip>
Traceroute /tracert <domain /ip>
curl -v <https url> == gives connection details in terms of headers.
```
# Types of users in linux:
```
Admin user/ super user: (root) # ( for devops admin, team lead, system admin)
Normal user: $ symbol. – limited access, like application team, developer, application team.
Sudo -i : changes from normal user to sudo( root user)
useradd amar == create a new user u have to be as root
userdel amar == delete a user
whoami == type of user
pwd == present working directory
difference between normal user and root user?
```
Types of files in the Linux system.
1. General Files – It is also called ordinary files. It may be an image, video,program, or simple text files. These types of files can be in ASCII or Binary format. It is the most commonly used file in the Linux system.
2. Directory Files – These types of files are a warehouse for other file types. 
It may be a directory file within a directory (subdirectory).
3. Device Files – In a Windows-like operating system, devices like CDROM, and hard drives are represented as drive letters like F: G: H whereas in the Linux system device are represented as files. As for example, 
/dev/sda1, /dev/sda2 and so on.
# Folder structure in linux:
under [/]directory – base folder for linux
1. root: /root --
2. /home: (user files) all normal user directories will be created under this folder
== /home /amar (default current directory for user)
3. tmp: temporary files, typically cleared on reboot
4. /boot: boot files (kernel grub file:) boot related information files and folders such as conf, grub,etc
     1. /boot/vmlinux – The Linux kernel file.
     2. bootloader:computer program that is responsible for booting a computer
     3. bootstrap server: client can use as a starting point to connect to the cluster.
     4. GRUB (GRand Unified Bootloader) is a boot loader package developed to support multiple operating systems and allow the user to select among them during boot-up.
  grub configurations:
  
5. /etc: system configurations of all applications
     1. /etc/bashrc – It is used by bash shell that contains system defaults and aliases.
     2. /etc/crontab – A shell script to run specified commands on a predefined time interval.
     3. /etc/exports – It contains information on the file system available on the network.
     4. /etc/fstab – Information of the Disk Drive and their mount point.
     5. /etc/group – It is a text file to define Information of Security Group.
     6. /etc/grub.conf – It is the grub bootloader configuration file.
     7. /etc/init.d – Service startup Script.
     8. /etc/lilo.conf – It contains lilo bootloader configuration file.
     9. /etc/hosts – Information of IP and corresponding hostnames.
     10. /etc/hosts.allow – It contains a list of hosts allowed accessing services on the local machine.
     11. /etc/host.deny – List of hosts denied to access services on the local machine.
     12. /etc/inittab – INIT process and their interaction at the various run level.
     13. /etc/issue – Allows editing the pre-login message.
     14. /etc/modules.conf – It contains the configuration files for the system modules.
     15. /etc/motd – It contains the message of the day.
     16. /etc/mtab – Currently mounted blocks information.
     17. /etc/passwd – It contains username, password of the system, users in a shadow file.
     18. /etc/printcap – It contains printer Information.
     19. /etc/profile – Bash shell defaults.
     20. /etc/profile.d – It contains other scripts like application scripts, executed after login.
     21. /etc/rc.d – It avoids script duplication.
     22. /etc/rc.d/init.d – Run Level Initialisation Script.
     23. /etc/resolv.conf – DNS being used by System.
     24. /etc/security – It contains the name of terminals where root login is possible.
     25. /etc/skel – Script that initiates new user home directory.
     26. /etc/termcap – An ASCII file that defines the behavior of different types of the terminal.
     27. /etc/X11 – Directory tree contains all the conf files for the X-window System.
     
6. /dev: consists of files that represent devices that are attached to the local system
ex: when mounting devices+= /dev/sda1, /dev/ttyS0, /dev/zero
      1. /dev/hda – Device file for the first IDE HDD.
      2. /dev/hdc – A pseudo-device that output garbage output is redirected to /dev/null.
7. /sys: virtual filesystem for modern linux distributions to store and allows modification of the devices connected to the system.
8. /proc: virtual and pseudo file system to contains info about the running processs with a specific process id or PID
      1. /proc/cpuinfo – CPU Information
      2. /proc/filesystems – It keeps the useful info about the processes that are running currently.
      3. /proc/interrupts – it keeps the information about the number of interrupts per IRQ.(interrupt request)
      4. /proc/ioports – Contains all the Input and Output addresses used by devices on the server.
      5. /proc/meminfo – It reports the memory usage information.
      6. /proc/modules – Currently using kernel module.
      7. /proc/mount – Mounted File-system Information.\
      8. /proc/stat – It displays the detailed statistics of the current system.
      9. /proc/swaps – It contains swap file information.
9. /run: stores volatile runtime data
10. /srv: contains server specific and server related files.
11. /sbin: binary executable programs for an administrator/root user.
12. /bin: binary or executable programs where every normal user can access
13. /var: logs (/var/log) == log files
     1. /var/log/lastlog – It stores user last login info.
     2. /var/log/messages – It has all the global system messages.
     3. /var/log/wtmp – It keeps a history of login and logout information.
14. /usr: user realated programs.
     1. /usr/bin – It contains most of the executable files.
     2. /usr/bin/X11 – Symbolic link of /usr/bin.
     3. /usr/include – It contains standard include files used by C program.
     4. /usr/share – It contains architecture independent shareable text files.
     5. /usr/lib – It contains object files and libraries.
     6. /usr/sbin – It contains commands for Super User, for System Administration.
15. /mnt: contains temporary mount directories for mounting the file system.
16. /lib: consists kernel modules and a shared library.
17. /lost+found : used to find recovered bits of corrupted files
18. /opt: optional or third-party software
19. /lib64:
20. /media: 
21. /local:

# Navigation commands:
```
cd == change directory
cd ..
cd .
cd /root
cd /bin/vamsi
```
# Listing/creating/removing folders/files:
```
ls l == list
ls -l == long list
ls -a == hidden files
ls -la
ls -lh == human readable format
ls -l text* == list all files starts with test
Create folders( directories) in linux?
mkdir foldername -- create directory
mkdir amar
mkdir /amar/vamsi
rmdir foldername == removing a directory
rm -R foldername
rm -rf foldername == remove a non empty directory
```
# Create files in linux?
touch filename == create empty file
there are different editors (cat ,vi, vim(advanced to vi), nano( replacement for pico), Emacs, gedit)
```
cat > filename == create a file (to insert data/ overwrite data)
ctrl+d to save and close
cat filename == open a file
cat >> filename == appends data to existing data
terminal redirection:
date > saved_date.txt
date >> saved_date.txt
back tick(quote) == date > `date+“%Y-%m-%d”`.txt
```
[vi editor:]
```
vi filename == creates or opens existing file
vi has 3 modes == escape mode, insertmode, command mode,
stat filename == for details about file
remove a file: rm filename
unlink filename
rm -f filename
rm -rf filename
cp file file2
cp -pR file1 /vamsi/maven/
mv file1 file2 == move it or rename it
grep something* == searches file with something in file == grep sme *?*
find 
find / -name .m2
getent passwd == get entries from passwd file
```

[Links]: are similar to shortcuts.
```
[hardlinks]: A hard link acts as a copy (mirrored) of the selected file. It accesses the data available in the original file same inode number, data changes will be applicable, if u change sourcefile or hard link it will apply in other also.
metadata changes will not applicable ( permissions)
ln /root/file(sourcefile) /tmp/file(hardlink)
ln newfile newfile1 == create a new hard link
[symboliclinks/softlinks]: A soft link (also known as Symbolic link) acts as a pointer or a reference to the file name. It does not access the data available in the original file. If the earlier file is deleted, the soft link will be pointing to a file that does not exist anymore.different inode number, 
check inode number by ls -li
ln -s file1 demo === create a symlink.
here demo is symlink , file1 is source file
remove symlink == > unlink <demo> or rm <demo>
to overwrite symlink ==> ln -sf file1 demo
```  
[absolute path vs relative path]

#  users and permissions
For aws linux ec2-user is the default user.
“w” command shows which users are currently in login.
last/ lastb shows list of last logged in users.
login to ec2 user → sudo -i → root access→ creates users (admins{sudo 
access}+ normal users)
creating a user → useradd bahubali
delete a user → userdel bahubali
all users are stored in /etc/passwd
setting password for user : passwd bahubali 
all passwords are saved in /etc/shadow file based on hash encryption
to verify existing user : id bahubali 
gives back uid, gid, groups
how to login to new user for first time?( one time task)
by default in aws cloud , if u launch any linux os , aws disables other user login, 
that’s why we cant able to login if we have username and password, ip address. 
for that we have to enable other user login
goto /etc/ssh/sshd_config and modify password authentication no to yes
now restart sshd: systemctl restart sshd
now we can login using username and password.
how to provide sudoer access to a user?
since normal user can’t run sudo commands , ask admin or who have root 
access to modify the file /etc/sudoers and add in last line as 
“username ALL=(ALL) ALL” sudo access with password i.e, u need to enter 
your user password.
“username ALL=(ALL) Nopasswd:ALL” sudo access without asking password
usermod -L username(amar) == lock user for access { gives access denied 
prompt}
usermod -U username(amar) == unlock user for access
what is mail spool?
Mail spool shows emails that are waiting to be delivered or have returned an 
error. You can apply filters and take action on these emails. Traditionally, the 
mail is stored in a "mail spool", a mailbox in the /var/spool/mail directory, 
where users are expected to pick it up. Therefore, according to this view, once 
the mail has been read it should be deleted or moved elsewhere — most likely 
somewhere in the user's home directory.
id amar → to check user exist or not/ details about groups(or)uid(or)gid
/etc/skel has the script to create new user home directory. if I want to add a file
or folder for all users while user new creation just add in /etc/skel directory. not 
applicable for existing users.
when we create a user a uniqe id and group is also created with same name. 
one user can be part of any number of groups
groups play important role in permissions and ownerships.
groupadd avengers == creating a new group
groups file == cat /etc/group
wheel group is actually tied to /etc/sudoers.
user entry will be added to /etc/passwd file == details about user, 
passwd(hidden), uid, gid, u can also give description for user, user home 
directory, shell/command.
useradd -c “ comment or description” username. 
primary vs secondary groups
commands and options:
options add s additional behavior to a command.
we can know info about options by using manual pages 
man command
man 2 time == > c code how c code used and does
command - -help
which passwd
which cat
create a user with particular user id?
useradd -u 1777 ironman
create a user with your home directory (desired dir as home dir)?
useradd -m -d /etc/hulk hulk
set expiry for a user id?
usermod -e 2023-11-23 username
chage -l username == verifying the user
chage=change user password expiry information
set expiry for password?
chage -M 90 username == > (max days between password changes) password 
is valid for 90 days for user
chage -m 30 username == > min days for password changes
chage -m 0 username ➔ can change passwd at any time
chage -E 2023-03-21 username == > expiration date
add user to another usergroup or existing group?
useradd -g amar(group) vamsi(user)
add groups primary + secondary while creating a new user?
useradd -g vamsi(primarygroup) -G wheel(secondary grp) hulk(newly created 
user)
cat /etc/passwd -file
any no login user can has Uid oin between 0-999
any login user has Uid in between 1000- so on
permissions and ownerships
for security purpose ownerships and for access purpose to users permissions
it usage is depends upon teams and users
when amar user creates a file == file owner is amar , group = amar
for accessing that file by others they require access and permissions
identify files and folders in linux based on permissions:
drwx------ 2 root root 29 May 14 06:14 .ssh == starting d is for directory
-rw-r--r-- 1 root root 0 May 15 07:39 file1 == it is file
drwxrwxrwx 1(hardlinks) root(user that owns file) root(group that owns file) 
12(file size) May 15 07:44(time stamp) folder1(filename/foldername| 
indominus)
owner permissions, group permissions, others( to rest of world)
r=4,w=6,x=1 , rwx=7, rw=6,rx=4,wx=3
x for execute permission
chmod == change file mode bits i.e., permissions
chmod 754 file1 == changing permissions for file1
chmod g+w file1 file2
chmod go-w+x mydir
chmod u-rwx,go= cmd
chown avengeruser file1 == changing file ownership for file1 initially created 
by root
chown bobuser:avengergroup file1 == changes both user and group ownerships
chgrp hulkgroup file1 == changing file group for file 1 initailly created by root
umask command in linux used to set default permissions for files or directories 
the user creates.
umask 
0002 
1
st bit 0 is called sticky bit , a special security feature(sticky bits: when u run a 
program it stays in memory instead of flushed out for running again and again)
2
nd bit is owner
3
rd bit group member
4
th
 everyone else
umask 543 == for all newly created files 543 is applied by default
chmod ( can apply to all files) vs umask (can apply to new files)
security
hostname: set hostname
hostname <development> === set hostname 
If we use syntax : sudo hostname set-hostname newname Example sudo 
hostname set-hostname amar It will persists even after reboot
security components = serverhardening
selinux: Security-Enhanced Linux (SELinux) is a security architecture
chcon -t etc_t file {chcon - change file SELinux security context}
restorecon file { restorecon - restore file(s) default SELinux security contexts.}
usually logins failed due to user permissions
ls -Z (Display security context so it fits on most displays.)
environmental variables: global , local
env 
cat .bashrc
cat .bash_profile
How commands are working?
commands are defined by a specific path variables which linked to a specific 
folder {bin or sbi}
without path variables our system commands wont work
echo $PATH
echo $ls
which cat === gives location of cat command
which useradd
I have a command in /app folder not in binary folder ? how to make it 
work from everywhere?
export PATH 
Repositories
repositories are basically a website with packages 
repository vs linux distribution
package management is done through yum and rpm
yum (yellow dog updater, modified)is the front end of rpm (redhat package 
manager)
configuration file of yum == /etc/yum.conf
cd /etc/yum.repos.d/ == > where repo files stored( urls , repositories0
packages :
yum install -y package name
yum remove packagename
yum repolist == > lists repositories (how many repos added to linux box)
yum history
yum info
yum search packagename
yum list installed
why we need to add other repositories ?
every application maynot be available in buit in linux repos for that we need to 
download RPM packages or add repos to linux
download rpm package 
wget <rpm_url>
tar/untar it 
rpm -ivh <packagename by ls command> === install application using rpm
rpm -qa == list installed applications
rpm -e applicationname(string) === remove application using rpm
daemon== same as service (utility programs that run silently in the background 
to monitor and take care of certain subsystems to ensure that the operating 
system runs properly.)
managing service for application
systemctl status servicename
systemctl start httpd
sytemctl enable httpd == (enable keeps active even after restart)
systemctl stop httpd
service status httpd
How to write service files for applications?
scheduling tasks:
crontab
cd /var/spool/cron/
firewalls (security groups)
rules to be added for access like ips, portnumbers, keys
all traffic from authorized networks
process management
processes: basically, a program depicts what happens in cpu 
thread: each piece of execution for process is called thread
race condition:
pid :
inode:
foreground process:
background process:
fg == to get into a background process
ps -ef == to see running process in system
ps aux == list other user processes
ps -eLf == to see thread process in system
top == display linux process dynamically ( shift+p - in cpu % / shift+m -
memory order) resource use also
lscpu ==total cpu utilization
free -m == check ram and memory
kill <signalnumber> <PID> == kills process ( ctl +c) end process 
kill -9 3441
/proc/==contains a hierarchy of special files which represent the current state of 
the kernel
1. cat meminfo
2. cat version
3. cat cpuinfo
cd /sys
cd /net
file system:
file system usage memory calculation
df -h linux file system
du -h /home/amar
How to clean up linux filesystem?
by using sync == flush filesystem buffers command
How to trouble shoot my slow performing ec2 instance?
Check the instance's system log for exhausted memory or disk full errors.
make sure that the instance's system log indicates the web service started 
correctly and is running.
Make sure that the instance is within CPU utilization limits
Make sure that the Amazon Elastic Block Store (Amazon EBS) volume 
attached to the instance hasn't hit the IOPS or throughput limits.
some useful commands are:
dmesg | less == for kernel buffer issues
free -m for checking memory usage
vmstat ===virtual memory
pidstat ==pidstatus
mpstat === cpu utilization
mtr ,sar == network issues
Partition and mounting
partitions:
partition commands:
fdisk: manipulate disk partition tables --
gdisk:
parted:
mkfs ext4/3/xfsvfat
tune2fs - adjust tunable filesystem parameters on ext2/ext3/ext4 filesystems
data partitions:normal Linux system data, including the root partition 
containing all the data to start up and run the system
swap partitions: we use it when we run out of ram memory
it takes some harddrive as memory
cons: harddrive is slower than ram
raid partitions: a method for combining multiple partitions on different disks into one 
large virtual device,
lvm(logical volume management) partition
file systems
unix filessytems ext file
xfs
fat32 ntfs
commands for disk :
fdisk
lsblk ===list of block devices 
df -h
partition table:
mbr: master boot record ,GPT guid partition tables
build partion fdisk /xdv/sda1
edit partion table == > fdisk command
journaling in xfs/ext4?
inode number: Index node number is a unique number assigned to all files in a 
Linux/Unix system
portprobe:
mount a file system 
mkdir dirname
mount /dev/sda1 dirname
file system table tells where everything is mounted
vi /etc/fstab === to edit partition tables ( for permanent mounting)
umount /dev/sda1 
Mounting filesystem:
we use them using mount points by redirecting a directory
mkdir vamsi( for mount redirection)
mkfs.ext4
How to add secondary disk to ec2 in aws?
Goto console → storage →elastic block store → volumes→create volume→
select availability zone same as ec2→ add tags→ create volume→then attach it 
to desired ec2 instance →
lsblk shows 2 disks 1. root disk and 2. newly added disk
Format newly attached volume:
as we know to use a disk after partition we should format it
mkfs.ext4 /dev/xvdf
mkfs == make file system
ext4 = type of filesystem
/dev/xvdf == disk path generated while creating volume( check for attached 
instances)
Now map the disk for mounting
mkdir /app === craeate a directory to set mount point
Mounting disk
mount /dev/xvdf /app
Now lsblk == df -h
shows 2 disks 1. under /directory 2. under /app directory 
umount /dev/xvdf
and detach the volume in ec2 console  
 
How to make mount point permanently?
after mounting volume 
check for blkid == block ids (for uuid and type)
modify /etc/fstab

 How to expand root volume in existing ec2 instance?
In putty login as ec2 user and check Output by df-h 
Open aws→ ec2 -instance → Elastic block store→ click on 
volumes→actions→ Modify volume to required gb→ modify 
Putty box check for volume added using command 
sudo lsblk → displays added volume
but we our task is adding to root ext4 file system 
sudo growpart /dev/xvda 1 → increasing block storage 
sudo lsblk →displays increased block storage 
sudo resize2fs /dev/xvda1 → increases file system 
{ here we got bad magic number error simply restart it} 
verified by df -h
  
How to increase ram and cpu in existing ec2-instance?
• Open ec2 dash board 
• Select the instance and stop it (instance we want to resize) 
• Under actions →instance settings → change instance type 
• In the next page → select the instance we need (for required cpu’s and ram 
{memory gib}) → apply it 
• Start the upgraded instance, Cpu’s can be verified by using command= top 
Ram can be verified by using free command
Ram can be verified by using command =free, Under free Allocations are: total: 
total amount of memory that is currently installed on your system used: amount 
of RAM currently used on your system 
free: amount of free memory available on your system 
shared: memory used by temporary file storage (a virtual filesystem that appears 
to be mounted but belongs to volatile memory) 
buffers: memory used by the kernel metadata 
cache: memory used by the page cache where data might be stored first before 
being written to disk; 
available: the memory available on the system in kilobyte
How to connect or recover ec2-instance without keypair (ssh private key)?
1. create a recovery instance (create a new key pair ,and enable port 22 for ssh 
for both instances) 
2. assign key tags to avoid confusion
3. note the details of both instances: 
4. example 
• name :original instance
• rootvolume:/dev/xvda
• keypair: vamsi
• ip : 3.110.175.57
• name: recovery instance
• rootvolume:/dev/xvda
• keypair:vamsi_new
• ip :15.207.18.2
•
• availability zone south-1b
5.now stop the original instance(ie., lost key pair instance) 
6.attach its root volume to recovery instance as secondary volume 
7.login to linux box(Putty) with recovery instance using recovery instance ip 
address (15.207.18.2)and new keypair(vamsi_new) and run these commands 
• For lististing of block devices lsblk 
• Create a mount point directory == Sudo mkdir /mnt/tempvol 
• Creating a mount point Sudo mount -o nouuid /dev/xvdf1 /mnt/tempvol Here -
o nouuid = omitting uuids to avoid any issues Xvdf1=device name found by 
lsblk 
• Copy authorizedkeys of recovery instance to target original instance server cp 
.ssh/authorized_keys /mnt/tempvol/home/ec2- user/.ssh/authorized_keys here 
we are copying → .ssh/authorized_keys→ /mnt/tempvol/home/ec2-
user/.ssh/authorized_keys 
• Sudo umount /mnt/tempvol ( We can also check root permissions of 
destination folder using ) sudo ls -l /mnt/tempvol/home/ec2-user/.ssh 
8.now detach the original volume(which was added as secondary volume) from 
recovery instance and attach it to original instance Make sure to attach it with 
correct root volume name(here it is /dev/xvda) 9. start the original instance and 
login into linux box (putty) using ip address(3.110.175.57) and new 
keypair(vamsi_new) 
Login as ec2- user


find / -name .m2
