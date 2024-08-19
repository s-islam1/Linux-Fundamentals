# First Version of Linux Kernel:

Access the following Link: [Linux v0.01](https://elixir.bootlin.com/linux/0.01/source)

The link points to the source code of Linux kernel version 0.01, which is the very first publicly released version of the Linux kernel by Linus Torvalds. Despite its simplicity compared to modern kernels, it still provides a basic structure that can be recognized in today's Linux kernel. Here's an explanation of the key folders and their purposes in this early version of the kernel:

### **Key Folders in Linux Kernel 0.01 Source Code:**

1. **`boot/`**:
   - **Purpose**: This directory contains the bootloader code. The bootloader is responsible for initializing the hardware and loading the Linux kernel into memory. It includes the first code that runs when the system starts up.
   - **Notable Files**:
     - `bootsect.s`: The assembly code that is executed by the BIOS to load the rest of the kernel.
     - `setup.s`: Prepares the system for running the kernel, including setting up memory and CPU state.

2. **`tools/`**:
   - **Purpose**: Contains tools that are used for building the kernel or for creating disk images.
   - **Notable Files**:
     - `build.c`: A utility for building the kernel and creating a bootable image.
     - `build.sh`: A script to automate the build process.

3. **`kernel/`**:
   - **Purpose**: This is the core of the Linux kernel, containing the main kernel functions and processes. It includes the code for system calls, process scheduling, and interrupt handling.
   - **Notable Files**:
     - `sched.c`: Implements the process scheduler, responsible for managing CPU time among processes.
     - `sys.c`: Implements system calls, which are the interface between user-space applications and the kernel.
     - `fork.c`: Handles process creation (forking).

4. **`mm/`**:
   - **Purpose**: The memory management subsystem, responsible for managing the system's memory. It includes code for handling paging, memory allocation, and swapping.
   - **Notable Files**:
     - `mem.c`: Handles memory allocation and deallocation.
     - `page.s`: Assembly code for low-level memory management tasks.

5. **`fs/`**:
   - **Purpose**: Contains the file system code. It handles file operations like reading, writing, opening, and closing files. This is where the Virtual File System (VFS) is implemented.
   - **Notable Files**:
     - `file_table.c`: Manages the table of open files.
     - `namei.c`: Handles path name resolution (translating file names to file descriptors).
     - `read_write.c`: Implements file read and write operations.

6. **`include/`**:
   - **Purpose**: This directory contains header files that define various constants, data structures, and function prototypes used throughout the kernel. These headers are crucial for linking different parts of the kernel together.
   - **Notable Files**:
     - `asm.h`: Architecture-specific definitions (for x86 assembly).
     - `sched.h`: Declarations related to process scheduling.
     - `fs.h`: Declarations related to file system structures and operations.

7. **`lib/`**:
   - **Purpose**: Contains generic library routines that are used across the kernel. These functions are not specific to any one part of the kernel but provide utility functions that are widely used.
   - **Notable Files**:
     - `string.c`: Implements standard string manipulation functions like `strlen`, `strcmp`, etc.
     - `ctype.c`: Functions for handling character classifications, such as `isalpha`, `isdigit`, etc.

8. **`init/`**:
   - **Purpose**: Contains the initialization code for the kernel. This code runs during the kernel boot process and sets up the initial state of the system.
   - **Notable Files**:
     - `main.c`: The entry point for the kernel after boot, responsible for initializing the system and starting the first process.

9. **`usr/`**:
   - **Purpose**: This directory is somewhat symbolic in early versions and may contain user-space utilities or example code. In modern kernels, the equivalent would be tools or utilities that are part of the kernel build but not the kernel itself.
   - **Notable Files**: This folder is usually minimal or empty in this early version.

### **Summary**
In Linux kernel version 0.01, the structure is relatively simple but forms the foundation of the more complex and modular structures seen in modern Linux kernels. Each directory in this early kernel serves a distinct purpose, from bootstrapping the system to managing memory, processes, and file systems, reflecting the fundamental tasks that any operating system must perform.

# Latest Version of Linux Kernel (till date August 19th, 2024)

Access the following Link: [Linux v6.11-rc4](https://elixir.bootlin.com/linux/v6.11-rc4/source)

The link points to the Linux kernel source code for version 6.11-rc4 on the Elixir Bootlin website. This is a much more modern version of the Linux kernel compared to version 0.01. The structure of the kernel source code has evolved significantly to support a wide range of hardware, architectures, and features. Below is an explanation of the key directories and their purposes:

### **Key Folders in Linux Kernel 6.11-rc4 Source Code:**

1. **`arch/`**:
   - **Purpose**: This directory contains architecture-specific code. The Linux kernel supports a wide variety of CPU architectures (e.g., x86, ARM, MIPS, RISC-V). Each subdirectory within `arch/` corresponds to a specific architecture and contains code that is unique to that platform, including boot code, memory management, and assembly routines.
   - **Examples**:
     - `x86/`: Contains code specific to Intel/AMD x86 processors.
     - `arm/`: Contains code for ARM architecture processors, commonly used in mobile devices.

2. **`block/`**:
   - **Purpose**: This directory includes code related to block devices, which are devices that read and write data in fixed-size blocks (e.g., hard drives, SSDs). It contains the core block layer infrastructure, handling I/O requests and scheduling.
   - **Examples**:
     - `blk-core.c`: Core functions for block device handling.
     - `blk-mq.c`: Multi-queue block layer, which improves performance on modern storage hardware.

3. **`drivers/`**:
   - **Purpose**: This is one of the largest directories in the kernel, containing device drivers for a wide range of hardware. Device drivers are the interface between the kernel and hardware devices, such as network cards, USB devices, GPUs, and more.
   - **Examples**:
     - `net/`: Network device drivers.
     - `gpu/`: Graphics processing unit drivers.
     - `usb/`: USB device drivers.

4. **`fs/`**:
   - **Purpose**: This directory contains the implementation of various file systems supported by Linux. It includes both common file systems like ext4, xfs, and btrfs, as well as the Virtual File System (VFS) layer, which provides a common interface for file operations regardless of the underlying file system.
   - **Examples**:
     - `ext4/`: Code for the ext4 file system.
     - `nfs/`: Code for the Network File System (NFS).
     - `vfs.c`: Core code for the Virtual File System layer.

5. **`include/`**:
   - **Purpose**: This directory contains header files that define data structures, function prototypes, and macros used throughout the kernel. It is subdivided into architecture-specific headers (e.g., `include/asm-x86/`) and general kernel headers (e.g., `include/linux/`).
   - **Examples**:
     - `linux/`: General kernel headers, such as `sched.h` for process scheduling.
     - `uapi/`: User-space API headers that define interfaces between user space and the kernel.

6. **`init/`**:
   - **Purpose**: The `init/` directory contains the code responsible for initializing the kernel during the boot process. It sets up the kernel environment and prepares the system to run user-space processes.
   - **Examples**:
     - `main.c`: The main entry point for the kernel, responsible for the initial setup.
     - `version.c`: Code that handles the kernel version information.

7. **`ipc/`**:
   - **Purpose**: This directory contains code for Inter-Process Communication (IPC) mechanisms within the kernel, such as message queues, semaphores, and shared memory. IPC is essential for processes to communicate and synchronize with each other.
   - **Examples**:
     - `msg.c`: Implementation of message queues.
     - `shm.c`: Shared memory handling code.

8. **`kernel/`**:
   - **Purpose**: This is the core of the Linux kernel, containing essential components like process scheduling, system calls, and interrupt handling. It manages system resources and coordinates the execution of processes.
   - **Examples**:
     - `sched/`: Process scheduling code.
     - `sys.c`: Core system call implementations.
     - `irq/`: Interrupt request handling.

9. **`lib/`**:
   - **Purpose**: The `lib/` directory contains general-purpose library functions that are used throughout the kernel. These functions are not specific to any single subsystem but provide utility functions such as string manipulation, CRC calculations, and data structure management.
   - **Examples**:
     - `string.c`: Standard string handling functions like `strlen`, `strcpy`.
     - `kobject.c`: Kernel object management code.

10. **`mm/`**:
    - **Purpose**: This directory contains the memory management subsystem of the Linux kernel. It handles tasks such as memory allocation, paging, virtual memory management, and swapping.
    - **Examples**:
      - `slab.c`: Slab allocator, a memory management mechanism.
      - `vmalloc.c`: Virtual memory allocator.
      - `memory.c`: Core memory management routines.

11. **`net/`**:
    - **Purpose**: The `net/` directory contains the networking stack of the Linux kernel. It includes implementations for various networking protocols (e.g., TCP/IP, UDP), network interfaces, and networking-related utilities.
    - **Examples**:
      - `ipv4/`: Implementation of IPv4 protocol.
      - `core/`: Core networking code, including socket handling.

12. **`scripts/`**:
    - **Purpose**: This directory contains scripts used in the build process of the Linux kernel. These scripts assist in compiling, linking, and configuring the kernel, as well as generating documentation.
    - **Examples**:
      - `kconfig/`: Configuration scripts for kernel build options.
      - `mod/`: Scripts for handling kernel modules during build and install.

13. **`security/`**:
    - **Purpose**: This directory includes code related to the security features of the Linux kernel. It contains implementations for security modules like SELinux, as well as other security-related mechanisms like access control and auditing.
    - **Examples**:
      - `selinux/`: Security-Enhanced Linux (SELinux) implementation.
      - `keys/`: Kernel key management system.

14. **`sound/`**:
    - **Purpose**: This directory contains sound-related code, including drivers for sound cards, audio interfaces, and other multimedia devices. It also includes the ALSA (Advanced Linux Sound Architecture) subsystem.
    - **Examples**:
      - `core/`: Core sound driver framework.
      - `drivers/`: Specific drivers for sound hardware.

15. **`tools/`**:
    - **Purpose**: The `tools/` directory includes various user-space tools that assist with kernel development and testing. These tools can be used for performance monitoring, debugging, and other kernel-related tasks.
    - **Examples**:
      - `perf/`: Performance analysis tool.
      - `bpf/`: Tools related to the Berkeley Packet Filter (BPF).

16. **`usr/`**:
    - **Purpose**: This directory usually contains user-space utilities that are bundled with the kernel, such as initial RAM disk (`initramfs`) tools. These utilities are used during the early boot process.
    - **Examples**:
      - `initramfs/`: Code related to building the initial RAM filesystem.

17. **`virt/`**:
    - **Purpose**: The `virt/` directory contains code related to virtualization, including support for hypervisors like KVM (Kernel-based Virtual Machine) and interfaces for virtual machines.
    - **Examples**:
      - `kvm/`: Kernel-based Virtual Machine (KVM) implementation.

### **Summary**
The Linux kernel's source code is organized into directories that correspond to different subsystems, hardware architectures, and functionalities. Each directory serves a specific purpose, contributing to the overall functionality of the Linux operating system, from hardware interaction to user-space applications. This organization allows developers to work on specific parts of the kernel independently, making it easier to manage and evolve over time.

Also checkout: 
Debian [- Debian History](https://www.debian.org/doc/manuals/project-history/intro.en.html) </br>
Ubuntu [- Ubuntu History](https://ubuntu.com/about)
