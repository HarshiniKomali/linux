CMPE 283 Assignment 2
=========

Open cpuid file in /linux/arch/x86/kvm folder.<br />
Add code for the below functionalities <br />
  1. For CPUID leaf node %eax=0x4FFFFFFF:<br />
    Return the total number of exits (all types) in %eax<br />
  2. For CPUID leaf node %eax=0x4FFFFFFE:<br />
      Return the high 32 bits of the total time spent processing all exits in %ebx<br />
      Return the low 32 bits of the total time spent processing all exits in %ecx<br />
Open vmx.c file in /linux/arch/x86/kvm/vmx folder.<br />
Modify this file accordingly to handle the above functionalities<br />
Rebuild the kernel using make -j 1 modules M=arch/x86/kvm command<br />
Perform loading and unloading of kvm kernel module (kvm.ko) and kvm-intel-module (kvm-intel.ko) using the following commands:<br />
  sudo rmmod arch/x86/kvm/kvm-intel.ko<br />
  sudo rmmod arch/x86/kvm/kvm.ko<br />
  sudo insmod arch/x86/kvm/kvm.ko<br />
  sudo insmod arch/x86/kvm/kvm-intel.ko<br />
  <br />
  To test the functionality<br />
  Run sudo apt update command<br />
  Run sudo apt-get install cpuid command<br />
  Create test codes for all the functionalities in the inner with file name test_assignment2.c<br />
  Install gcc and compile the code using gcc test_Assignment2.c<br />
  Run the test file with ./a.out<br />


 
