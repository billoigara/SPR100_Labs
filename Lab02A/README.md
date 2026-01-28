
# Lab02A - Windows VM CPU and Memory Analysis Report
**Student Name:** Bill Mandera Oigara
**Student ID:** 125765255
**Course Section:** SPR100
**Completion Date:** 2026-01-28
**Lab Duration:** 1hr 30min
---
## Part 1: Virtual Machine Setup and Configuration
### 1.1 VM Configuration Summary
- **Hypervisor Name:** VMware Workstation Pro
- **Hypervisor Version:** [Version number]
- **CPU Cores:** 2
- **Memory:** 4 GB
- **Storage:** 60 GB
- **Network:** NAT
### 1.2 VM Import and Startup Process
- **VM File Source:** [\\mydrive\courses\SPR100\Win10]
- **Import Method:** I shared the file to my email then downloaded the content from gmail to my ssd and exported it to my vm.
- **VM Name:** [win10-bmoigara]
- **Storage Path:** D:\intro to data security
- **Startup Time:** 38 sec
### 1.3 Initial System Configuration
- **Password Change Process:** opened setting then opened accounts.Opened sign in option and then under password i clicked change.I then inserted the current password and new password and confirmed it.Clicked next then finish.To confirm i restarted the pc and used the new password to log in.
**Git Installation:** I logged into Windows 10 with an administrator account.I opened Command Prompt or PowerShell as Administrator.I typed in 'winget install --id Git.Git -e --source winget' command to install Git.Installation was done in a short period of time.After installation finished,I verified that Git was installed using 'git --version' command.The command displayed the installed Git version,confirming that Git for Windows was successfully installed.
---
## Part 2: Windows System Analysis
### 2.1 CPU Analysis Results
#### System Information (msinfo32)
- **Processor Name:** [Intel(R) Core(TM) i5-9300H CPU @ 2.40 GHz, 2400Mhz]
- **Number of Cores:** [Physical cores from Processor sectio2] = 2
- **Logical Processors:** [Total logical processors from Processor section] = 2
#### Task Manager CPU Analysis
- **Current CPU Utilization:** [Percentage from Performance tab] = 12%
- **Number of Virtual Processors:** [Count from Task Manager] = 2
- **CPU Base Speed:** [Base speed from Task Manager] = 2.40 GHz
- **CPU Current Speed:** [Current operating speed from Task Manager] = 2.40 GHz
- **System Up Time:** [How long the OS has been running] =0.00.04.37
- **CPU Utilization Observations:** [Describe what you observed during monitoring] = The speed ramins constant but the cpu utilization is volatile.
### 2.2 Memory Analysis Results
#### System Information Memory Details
- **Total Physical Memory:** [Amount from msinfo32 System Summary] = 4.00 GB
- **Available Physical Memory:** [Amount from msinfo32 System Summary] = 2.46 GB
- **Total Virtual Memory:** [Amount from msinfo32 System Summary] = 5.75 GB
- **Available Virtual Memory:** [Amount from msinfo32 System Summary] = 4.40 GB
- **Virtual Memory Explanation:** It is basically RAM + part of my ssd used as extra memory.
#### PowerShell Memory Commands Output
**Physical Memory Information:**[Paste the output of: Get-WmiObject -Class Win32_PhysicalMemory]
Caption              : Physical Memory
Description          : Physical Memory
InstallDate          :
Name                 : Physical Memory
Status               :
CreationClassName    : Win32_PhysicalMemory
Manufacturer         : VMware Virtual RAM
Model                :
OtherIdentifyingInfo :
PartNumber           : VMW-4096MB
PoweredOn            :
SerialNumber         : 00000001
SKU                  :
Tag                  : Physical Memory 0
Version              :
HotSwappable         :
Removable            :
Replaceable          :
FormFactor           : 8
BankLabel            : RAM slot #0
Capacity             : 4294967296
DataWidth            : 64
InterleavePosition   :
MemoryType           : 2
PositionInRow        :
Speed                :
TotalWidth           : 64
Attributes           : 0
ConfiguredClockSpeed : 4800
ConfiguredVoltage    :
DeviceLocator        : RAM slot #0
InterleaveDataDepth  :
MaxVoltage           :
MinVoltage           :
SMBIOSMemoryType     : 3
TypeDetail           : 128
PSComputerName       :

- **Document:** capacity=  4294967296
**Available Memory Information:**
[Paste the output of: Get-Counter "\Memory\Available MBytes"]

Timestamp                  CounterSamples
---------                  --------------
2026-01-28 11:30:54 AM     \\desktop-4h9e4ct\memory\available mbytes :
                           2039

- **Available Memory:** [Document the Available MBytes value] = 2039
### 2.3 System Performance Monitoring Results
#### Performance Monitor Data Collector Set
- **Data Collector Set Name:** Lab02A_Performance_Monitoring
- **Sample Interval:** 5 seconds
- **Duration:** [2.59 mins]
- **Counters Monitored:**
- Processor: % Processor Time=2.505
- Memory: Available MBytes = 1,535,000
- Physical Disk: % Disk Time =3.937
- **Log Location:** [C:\Users\Student\Desktop]
#### Performance Data Summary
- **CPU Usage Range:** [Minimum = 5%  Maximum 12% during 2-minute monitoring]
- **Memory Available Range:** [Minimum = 1,533,000 - Maximum =1,539,000MB during monitoring]
- **Disk Usage Range:** [Minimum = 0.00 Maximum 3.937% during monitoring]
- **Performance Patterns Observed:** Disk and network had a number of spike where as memory was almost on one level while cpu was low.
#### Resource Monitor Observations
- **Peak CPU Usage:** [Highest observed percentage from resmon] 14%
- **Peak Memory Usage:** [Highest observed usage from resmon] 61%
- **Resource Usage During Activities:** It contributed to the spike for diffent sectors in terms of cpu , Network and etc.
#### Performance Monitor Data Collector Graph

- **How You Extracted:** [I sent the file to my email from my vm and downloaded it from my gmail on my local pc]
---
## Analysis and Conclusions
### Key Findings
1. **VM Configuration:**  Importation was easy and i only configure file location , changed name of the vm and changed memory from 2-4.
2. **CPU Performance:** The CPU information showed the number of cores and logical processors assigned to the VM. Performance depended on how many cores were allocated. More cores improved responsiveness, while fewer cores reduced performance, especially during startup and when opening applications.
3. **Memory Management:** Physical memory (RAM) represents the actual hardware memory available, while virtual memory combines RAM and disk space . Virtual memory allows the system to continue running when RAM is full, but it is slower than physical memory. The analysis showed how Windows manages both types to maintain system stability.
4. **Performance Monitoring:** Using tools like Task Manager, System Information, and Performance Monitor helped identify CPU usage, memory usage, and system load. These tools provided real-time and recorded data for system performance evaluation.
### Technical Insights
- **System Architecture Understanding:** I was able to  learn that CPU cores perform processing tasks, while logical processors  allow multitasking. Memory hierarchy includes cache, RAM, and virtual memory, which work together to balance speed and capacity.
- **Virtualization Concepts:** VMs share host resources such as CPU, RAM, and storage. Proper VM configuration ensures the guest operating system runs efficiently without overloading the host system.
- **Performance Monitoring Tools:** Windows performance monitoring tools allow administrators to track system behavior, detect bottlenecks, and analyze long-term performance trends using counters and data collector sets
- **PowerShell Commands:** provides faster and more automated system analysis compared to manual methods.
### Challenges and Solutions
- **VM Setup Challenges:** None
- **Performance Monitoring Issues:** None
- **File Transfer Challenges:** I sent the file to my email from my vm and downloaded it from my gmail on my local pc
- **Solutions Applied:** pushing changes to git hub,i was able to resolve the issue by ensuring each folder has at least something in it before pushing.
- **Lessons Learned:** [Whenever i create a directory. i should not leave it empty]
### Understanding Questions
- **Virtual Memory Concept:** it's a combination of physical RAM and disk space used as memory. It allows the system to keep running when RAM is full by moving less-used data to disk. It is important because it prevents system crashes and supports multitasking.
- **VM Resource Allocation:** VM resource allocation affects performance directly. Allocating too few resources causes slow performance, while allocating too many can slow down the host system. A balance is required for optimal operation
- **Performance Monitoring Value:** Performance monitoring is important in system administration because it helps detect problems, optimize resource usage, and ensure system reliability and stability over time.
---
**Report Completion Time:** [2hrs]
**Confidence Level:** [6]
