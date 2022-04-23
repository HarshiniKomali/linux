CMPE 283 Assignment 2
=========

Open cpuid file in /linux/arch/x86/kvm folder./n
Add code for the below functionalities \n
  1. For CPUID leaf node %eax=0x4FFFFFFF:\n
    Return the total number of exits (all types) in %eax\n
  2. For CPUID leaf node %eax=0x4FFFFFFE:\n
      Return the high 32 bits of the total time spent processing all exits in %ebx\n
      Return the low 32 bits of the total time spent processing all exits in %ecx\n
Open vmx.c file in /linux/arch/x86/kvm/vmx folder.\n
Modify this file accordingly to handle the above functionalities\n
Rebuild the kernel using make -j 1 modules M=arch/x86/kvm command\n
Perform loading and unloading of kvm kernel module (kvm.ko) and kvm-intel-module (kvm-intel.ko) using the following commands:\n
  sudo rmmod arch/x86/kvm/kvm-intel.ko\n
  sudo rmmod arch/x86/kvm/kvm.ko\n
  sudo insmod arch/x86/kvm/kvm.ko\n
  sudo insmod arch/x86/kvm/kvm-intel.ko\n
  \n
  To test the functionality\n
  Run sudo apt update command\n
  Run sudo apt-get install cpuid command\n
  Create test codes for all the functionalities in the inner with file name test_assignment2.c\n
  Install gcc and compile the code using gcc test_Assignment2.c\n
  Run the test file with ./a.out\n


 
