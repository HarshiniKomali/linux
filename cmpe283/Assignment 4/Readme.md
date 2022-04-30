Assignment 4
=============


Q1. For each member in your team, provide 1 paragraph detailing what parts of the lab that member implemented / researched.
I did the assignment on my own.
Steps:
1. Verified that Assignment 3 code is functional.
2. Ran assignment 3 code and took output for neested paging
3. Tested and verified the results
4. Documented the steps and results
5. Switched KVM to shadow paging (ept=0)
6. Ran assignment 3 code and took output for Shadow Paging
7. Tested and verified the results
8. Documented the steps and results

Q2. Include a sample of your print of exit count output from dmesg from “with ept” and “without ept”.
1. Open virt-manager and start virtual machine. Run case 3 from previous assignment (To print all exit type wise counts).
2. Execute dmesg for nested paging (i.e., with ept)

   ![image](https://user-images.githubusercontent.com/15766915/166089938-104029d9-7ebe-4791-9d12-31ef990f354f.png)


3. Execute following commands to switch from nested paging to shadow paging:
   sudo rmmod kvm_intel && sudo rmmod kvm && sudo modprobe kvm && sudo modprobe kvm_intel ept=0
   Reboot
4. Execute dmesg for shadow paging (i.e., without ept)

   ![image](https://user-images.githubusercontent.com/15766915/166089965-f9f23475-f1c8-4db1-862b-74a80295ac10.png)
   
Q3. What did you learn from the count of exits? Was the count what you expected? If not, why not?
    In the case of shadow paging, we can observe from the output that maximum exits occurred of type “CR_ACCESS ".
    Also, INVLPG exit is present in case of shadow paging. INVLPG exit is used by hypervisor to invalidate translation in the TLB.
    
Q4. What changed between the two runs (ept vs non-ept)
    
    
# ASSIGNMENT 4

## Questions
## 1. For each member in your team, provide 1 paragraph detailing what parts of the lab that member implemented / researched.
I did the assignment on my own
Steps to follow:
  * Verified that Assignment III code is functional.
  * Ran assignment 3 code and took output for Nested paging 
  * Tested and verified the results
  * Documented the steps and results
  * Switched KVM to shadow paging (ept=0)
  * Ran assignment 3 code and took output for Shadow Paging 
  * Tested and verified the results
  * Documented the steps and results
  
## 2. Include a sample of your print of exit count output from dmesg from “with ept” and “without ept”.

## STEP 1:
  * Open virt-manager and start virtual machine. Run case 3 from previous assignment (To print all exit type wise counts). 

  * Execute dmesg for nested paging (i.e., with ept)
  
  ![image](https://github.com/aishwaryaravi19/linux/blob/master/output-assignment4/cmpe283.4.1.png)
  
## STEP 2: 	

 * Execute following commands to switch from nested paging to shadow paging:  
	
   *	sudo rmmod kvm_intel && sudo rmmod kvm && sudo modprobe kvm && sudo modprobe kvm_intel ept=0
   *	Reboot
 
 * Execute dmesg for shadow paging (i.e., without ept)
 
 ![image](https://github.com/aishwaryaravi19/linux/blob/master/output-assignment4/cmpe283.4.2.png)

## 3. What did you learn from the count of exits? Was the count what you expected? If not, why not?

- In the case of shadow paging, we can observe from the output, maximum exit occurred of type “CR_ACCESS ".
- Also, INVLPG exit is present in case of shadow paging. INVLPG exit is used by hypervisor to invalidate translation in the TLB.

## 4. What changed between the two runs (ept vs non-ept)

Nested Paging (ept=1)             |  Shadow Paging (ept=0)
----------------------------------| ---------------------------------
The VM exits for “EPT_VIOLATION”  | The VM exits for “INVALPG”
The VM exits for “EPT_MISCONFIG”  | Count of exits for reason “CR_ACCESS” increased significantly. Exit count seen for “XSETBV”
                                  
* In case of shadow paging the count of exits for reason “CR_ACCESS” increased significantly as hypervisor takes exits on access of CR register

![image](https://github.com/aishwaryaravi19/linux/blob/master/output-assignment4/cmpe283.4.3.png)
![image](https://github.com/aishwaryaravi19/linux/blob/master/output-assignment4/cmpe283.4.4.png)





