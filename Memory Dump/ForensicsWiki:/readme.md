https://web.archive.org/web/20190730234949/http://www.forensicswiki.org/wiki/Tools:Memory_Imaging

Linux
LiME
Linux Memory Extractor (LiME) is a Loadable Kernel Module (LKM), which allows the acquisition of volatile memory from Linux and Linux-based devices, such as those powered by Android. The tool supports dumping memory either to the file system of the device or over the network.
Linux Memory Grabber by Hal Pomeranz
a tool to create Linux Volatility profiles and dump memory (using LiME) from an USB Key, without installation on local HDD. Very useful
/dev/crash
On Red Hat systems (and those running related distros such as Fedora or CentOS), the crash driver can be loaded to create pseudo-device /dev/crash for raw physical memory access (via command "modprobe crash"). This module can also be compiled for other Linux distributions with minor effort (see, for example, http://gleeda.blogspot.com/2009/08/devcrash-driver.html). When the crash driver is modified, compiled, and loaded on other systems, the resulting memory access device is not safe to image in its entirety. Care must be taken to avoid addresses that are not RAM-backed. On Linux, /proc/iomem exposes the correct address ranges to image, marked with "System RAM".
/dev/mem
On older Linux systems, the program dd can be used to read the contents of physical memory from the device file /dev/mem. On recent Linux systems, however, /dev/mem provides access only to a restricted range of addresses, rather than the full physical memory of a system. On other systems it may not be available at all. Throughout the 2.6 series of the Linux kernel, the trend was to reduce direct access to memory via pseudo-device files. See, for example, the message accompanying this patch: http://lwn.net/Articles/267427/.
Second Look: Linux Memory Forensics
This commercial memory forensics product ships with a modified version of the crash driver and a script for safely dumping memory using the original or modified driver on any given Linux system.
fmem
fmem is kernel module that creates device /dev/fmem, similar to /dev/mem but without limitations. This device (physical RAM) can be copied using dd or other tool. Works on 2.6 Linux kernels. Under GNU GPL.
lmap and pmem
pmem is a loadable kernel module that exposes /dev/pmem. lmap allows to inject the pmem functionality into existing kernel modules to bypass having to build a pmem kernel module for every different kernel version.
