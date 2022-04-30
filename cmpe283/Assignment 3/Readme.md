Assignment 3
============

Pre-requisites - Setup for Assignment 1 should be completed <br >

Requirements:
1. For CPUID leaf node %eax= 0x4FFFFFFD:
   Return the number of exits for the exit number provided (on input) in %ecx. The output should be returned in %eax.
2. For CPUID leaf node %eax= 0x4FFFFFFC:
   Return the time taken to process the exit number provided (on input) in %ecx.
   Return the higher 32 bits of the total time taken to process all exits in %ebx
   Return the lower 32 bits of the total time taken to process all exits in %ecx

Steps:
1. Add code to KVM at file /linux/arch/x86/kvm/vmx/vmx.c and /linux/arch/x86/kvm/cpuid.c  
2. Modify cpuid.c and vmx.c to implement the above functionality.
3. Build the code 
   sudo make modules 
   sudo make modules_install 
   sudo make install 
   reboot
4. Open virt-manager and start virtual machine. 
5. Install CPUID package inside the inner vm.
   sudo apt-get install cupid
   
7. For cpuid 0x4FFFFFFC
8. Execute dmesg command to view all the exits available count.
9. Comment of the frequency axis
   Frequency of the time spent depends on the type of exit.The number of exits tends to increase if more privileged operations are performed by the system
   
10. Which are the most frequent and less frequent exit types?
    Most frquent - MSR_WRITE -Cycle count 4859559731
    Less frequent - DR_ACCESS - Cycle count 7625
    
11. For cpuid 0x4FFFFFFD
12. Execute dmesg command in the host system’s terminal to count the exits available
13. Cpuid - I 0X4fffffffd -444 - output for invalid exit code 
   
   
