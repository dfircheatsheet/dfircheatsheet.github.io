## Volatility - plugins

* [pslist - walks the doubly-linked list pointed to by PsActiveProcessHead](https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#pslist)
* [pstree - print process tress](https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#pstree)
* [psscan - enumerate processes using pool tag scanning](https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#psscan)
* [psdispscan - enumerates processes by scanning for DISPATCHER_HEADER](https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#psdispscan)
* [psxview - Detect hidden processes](https://github.com/volatilityfoundation/volatility/wiki/Command-Reference-Mal#psxview)      

## [Volatility - volshell](https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#volshell)   

<details>
  <summary>Explore Processes</summary>
  
  * ps() -> ```List processes```
  * cc(pid=4) -> ```Change to another process```
</details>
<details>
  <summary>EProcess structure analysis</summary>
  
  * dt(process) -> ```list current process EPROCESS structure```
  * dt("[_EPROCESS](https://web.archive.org/web/20210302232116/https://www.geoffchappell.com/studies/windows/km/ntoskrnl/inc/ntos/ps/eprocess/index.htm)", 0xvirtualadderss, space=addrspace) -> ```Expand the EPROCEES structure using virtual address```
  * dt("[_EPROCESS](https://web.archive.org/web/20210302232116/https://www.geoffchappell.com/studies/windows/km/ntoskrnl/inc/ntos/ps/eprocess/index.htm)", 0xphysicaladderss, space=addrspace) -> ```Expand the EPROCEES structure using physical address```
</details>
<details>
  <summary>PEB structure analysis</summary>
  
  * dt(process.peb) -> ```list current process PEB structure```
  * dt("[_PEB](https://web.archive.org/web/20211009172637/https://www.geoffchappell.com/studies/windows/km/ntoskrnl/inc/api/pebteb/peb/index.htm)", 0xvirtualadderss, space=addrspace) -> ```Expand the PEB structure using virtual address```
  * dt("[_PEB](https://web.archive.org/web/20211009172637/https://www.geoffchappell.com/studies/windows/km/ntoskrnl/inc/api/pebteb/peb/index.htm)", 0xphysicaladderss, space=addrspace) -> ```Expand the PEB structure using physical address```
  * <details>
  
      <summary>Important info in PEB structure</summary>
  
      * BeingDebugged -> ```some malicious programs set up a process and then connect a "debugger" to it```
      * OSMajorVersion & OSMinorVersion -> ```correspond to the host operating system```
      * OSBuildNumber
      * OSCSDVersion -> ```the service pack number multiplied by 0x100```
      * _RTL_USER_PROCESS_PARAMETERS -> ```The pointer is to the process parameters.```
    </details>
</details>

## Rekall   

* [pslist - list processes using all methods by default.](https://rekall.readthedocs.io/en/latest/plugins.html#pslist-winpslist)
* [pstree - walk the task_struct.children and task_struct.sibling members to print process tress.](https://rekall.readthedocs.io/en/latest/plugins.html#pstree-linpstree)
* [psscan - Scan Physical memory for \_EPROCESS pool allocations.](https://rekall.readthedocs.io/en/latest/pluins.html#psscan-psscan)
* [psxview - Find hidden processes with various process listings](https://rekall.readthedocs.io/en/latest/plugins.html#psxview-windowspsxview)      

## Notes

* Providing KDBG virtual offsets to volatility with '-g' will speed up the process.
