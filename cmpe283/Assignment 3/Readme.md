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
   <img width="728" alt="ASSIGNMENT 3 IMAGE 4" src="https://user-images.githubusercontent.com/15766915/166089541-32df8459-5aa6-4f27-9232-acdbeda55989.png">

9. Comment of the frequency axis
   Frequency of the time spent depends on the type of exit.The number of exits tends to increase if more privileged operations are performed by the system
   <img width="472" alt="assignment3Q1 (1) (1)" src="https://user-images.githubusercontent.com/15766915/166089576-8f6f7eaf-28dd-482f-8760-6a28bba9cde0.png">

10. Which are the most frequent and less frequent exit types?
    Most frquent - MSR_WRITE -Cycle count 4859559731
    Less frequent - DR_ACCESS - Cycle count 7625
    <img width="472" alt="assignment3q2" src="https://user-images.githubusercontent.com/15766915/166089585-ebab3856-75c2-4ddd-a43d-deb25139244e.png">

11. For cpuid 0x4FFFFFFD
12. Execute dmesg command in the host system’s terminal to count the exits available
    <img width="370" alt="ffffd-s2" src="https://user-images.githubusercontent.com/15766915/166089658-052172d3-8649-4a8e-bd94-c9fdc045602b.png">
13. Cpuid - I 0X4fffffffd -444 - output for invalid exit code   
   <img width="440" alt="ffffd-s3" src="https://user-images.githubusercontent.com/15766915/166089665-f7830bec-f0f1-4357-b4c0-576df3940690.png">

