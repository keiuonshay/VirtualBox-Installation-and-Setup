# VirtualBox-Installation-and-Setup
A technical documentation project demonstrating how to verify prerequisites, install VirtualBox, and configure a working virtualization environment on Linux Mint.


## Phase 1 — Prerequisites

Before installing VirtualBox on Linux Mint, I verified that the system met the required prerequisites:

### Operating System
- Linux Mint (based on Ubuntu/Debian)

### System Requirements
- 64-bit CPU
- Minimum 4 GB RAM (8 GB recommended for running multiple VMs)
- At least 20 GB free disk space

### Virtualization Support
I checked whether the CPU supported virtualization (VT-x/AMD-V):


If the output shows `VT-x` or `AMD-V`, virtualization is supported.

### Package Repository Requirements
VirtualBox can be installed directly from the Linux Mint repositories using APT.  
This requires:
- Updated package lists  
- Working internet connection  
- No conflicting virtualization tools (such as KVM)

I confirmed the system was ready by running:

## Phase 2 — Installation Steps

I installed VirtualBox using the Linux Mint terminal with the APT package manager.

### Step 1 — Update package lists
This ensures the system has the latest software information.


### Step 2 — Install VirtualBox
This installs the VirtualBox application and required kernel modules.


### Step 3 — Verify installation
After installation, I confirmed the version:


This displays the installed VirtualBox version and confirms that the program is available on the system.

### Step 4 — Launch VirtualBox
I opened VirtualBox from the application menu to confirm the GUI loaded correctly.



## Phase 3 — Verification

After installing VirtualBox, I verified that the installation was successful and that the virtualization environment was working correctly.

### Step 1 — Check VirtualBox version
I confirmed the installed version using the terminal:


This command displays the VirtualBox version and confirms that the program is installed and recognized by the system.

### Step 2 — Launch VirtualBox
I opened VirtualBox from the Linux Mint application menu to verify that the GUI loaded without errors.

### Step 3 — Confirm virtualization support
Inside VirtualBox, I checked that the system allowed me to create a new virtual machine.  
If virtualization support (VT-x/AMD-V) was missing, VirtualBox would show an error at this stage.

### Step 4 — Create a test VM
I created a new virtual machine to confirm that VirtualBox could allocate memory, storage, and CPU resources without issues.

### Step 5 — Confirm no kernel module errors
If VirtualBox kernel modules were missing or not loaded, the program would show an error on startup.  
Since no errors appeared, the installation was successful.


## Phase 4 — Troubleshooting

During or after installing VirtualBox on Linux Mint, several common issues can occur. These are the most frequent problems and how to resolve them.

### Issue 1 — VirtualBox kernel modules not loaded
If the kernel modules are missing or not loaded, VirtualBox may show an error on startup.

**Fix: Install required modules**


Then reboot the system.

### Issue 2 — KVM conflicts with VirtualBox
Linux Mint sometimes enables KVM by default, which conflicts with VirtualBox.

**Fix: Disable KVM modules**

To prevent them from loading automatically:


### Issue 3 — Extension Pack not installed
Some features (USB 2.0/3.0, RDP, NVMe, encryption) require the Extension Pack.

**Fix: Install Extension Pack**
Download from Oracle’s website, then run:


### Issue 4 — Guest Additions not working
Guest Additions may fail if kernel headers are missing.

**Fix: Install headers and build tools**



Then inside the VM:
- Devices → Insert Guest Additions CD Image  
- Run the installer

### Issue 5 — VM won’t start (VT-x/AMD-V disabled)
If virtualization is disabled in BIOS, VirtualBox cannot run 64-bit VMs.

**Fix: Enable virtualization**
- Reboot the computer  
- Enter BIOS/UEFI  
- Enable **Intel VT-x** or **AMD-V**

### Issue 6 — “Kernel driver not installed (rc=-1908)”
This happens when the kernel version and VirtualBox modules don’t match.

**Fix: Rebuild modules**



If that fails, reinstall VirtualBox:



---

These troubleshooting steps ensure VirtualBox runs correctly and can create and manage virtual machines without errors.


## Phase 5 — What I Learned

Working through the VirtualBox installation and setup process on Linux Mint helped me build a deeper understanding of how virtualization works on a Linux system. I learned how to verify system prerequisites, check for CPU virtualization support, and install VirtualBox using the APT package manager.

I also gained experience identifying and resolving common issues such as missing kernel modules, KVM conflicts, and Guest Additions errors. This taught me how VirtualBox interacts with the Linux kernel and why certain components (like headers and DKMS) are required.

Overall, this project strengthened my skills in:
- Linux system administration
- Virtualization concepts (VT-x/AMD-V)
- Troubleshooting installation errors
- Using terminal-based installation and verification
- Understanding how VirtualBox manages virtual machines

This documentation reflects my ability to install, verify, and troubleshoot a full virtualization environment on Linux Mint.


