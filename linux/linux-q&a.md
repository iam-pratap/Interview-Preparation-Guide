`1. What is Linux?`

Linus Torvalds developed Linux, a Unix-like, free, open-source, and kernel operating system. Mainly it is designed for systems, servers, embedded devices, mobile devices, and mainframes and is also supported on major computer platforms such as ARM, x86, and SPARC.

`2. Explain the basic features of the Linux OS?`

Some basic features of Linux are:
- Linux is free and easily available.
- It is more secure than other operating systems because it uses security auditing and password authentication features.
- Linux has its personal software repository.
- It includes multiple languages throughout the world. Hence Linux supports different language keyboards.
- It offers CLI and GUI to use different commands and applications such as Firefox, VLC, etc.

`3. Explain the boot process?`

The boot process is your computer's startup sequence. It loads the operating system and prepares everything for you to use the system.
- Power On & BIOS Check
- Hardware Test (POST)
- Find Bootable Device
- Load Kernel (OS Core)
- Startup System Services
- Login & User Interface

`4. What is Hardlink and Softlink?`

There are two types of link(ln) in linux

**Hark link:** 
- It is the mirror file of original file
- It is used for backup
- If you create link the inode address is for both the files is same becoz it takes the spaces for one file only we can't put the files in cross filesystems(one is /dev/sda1 and another one is /dev/sda2)

**Softlink:**
- It is used to create the shortcuts of a file
- If you create a link then the inode address is different in both the files
- If you delete the original file then you can't access the link(now it is useless) we can put the files in cross filesystems(one is /dev/sda1 and another is /dev/sda2)

`5. What is Inode`

It is given when we create a new file(this is unique for all the files)

`6. What are the default umask values?`

A value that determines the default permissions for newly created files and directories.

Default umask value→022

`7. What is load average?`

 A metric that measures the average system load over a certain period.
```
uptime or cat /proc/loadavg
```
`8. How to check the open ports in linux`

Type the following netstat command:
```
sudo netstat -tulpn | grep LISTEN
```
`9. what is process in linux ?`

A Process is a program, application, or command that is running in the terminal. For example, opening a browser is considered a process. Every process in Linux hasa state, such as running, stopped, or terminated. 

`10. What is df and du?`

**du** measures the disk space used by files and directories, while **df** reports on the total, used, and available space on a file system:

`11. Explain LILO?`

LILO, i.e., Linux Loader and is a Linux Boot loader. It loads the Linux operating system into memory and starts the execution. Most operating systems like Windows and macOS come with a bootloader. While in Linux, you need to install a separate boot loader, and LILO is one of the Linux boot loaders.

`12.  How do you check the network connectivity in Linux?`

The "ping" command is used to check network connectivity between your machine and a remote host.
```
ping <hostname> 
```
`13.  How do you monitor system performance in Linux?`

The "top" command is commonly used to monitor system performance in real-time. It displays information about CPU usage, memory usage, running processes, and more.

`14. How can you check the memory usage of a Linux system?`

The "free" command displays information about the system's memory usage, including total memory, used memory, free memory, and swap usage.

`15. How do you find the IP address of a Linux system?`

The "ifconfig" command displays network interface information, including IP addresses assigned to the system.

`16. Difference between process and thread`

**Process** 
- A process is an instance of a program that is being executed.
- It is independent because it does not share memory.

**Thread**
- A thread is the subset of a process and is also known as the lightweight process.
- It depends on other threads because they share some memory with other threads.

`17. How to check the information about OS`

command
```
cat /etc/os-release
```

`18. What is 'tar' command used for in linux, and how would you create  and extract tar archives ?`

It is used to combine multiple files into one.

tar --> Tape Archive

syntax:

1. Create a tar file
```
tar -cvf file.tar file
```
result:- file.tar

c - create, v - verbose, f - forcefully, file.tar - taget, file - source

2. Compress a file 
```
gzip file.tar
```
result: file.tar.gz

3. Uncompress a file
```
gunzip file.tar.gz
```
result:- file.tar

4. Extract a file
```
tar -xvf file.tar
```
result:- file
