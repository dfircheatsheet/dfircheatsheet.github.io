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
<ul data-sourcepos="27:3-38:14" dir="auto">
<li data-sourcepos="27:3-27:63">
<p data-sourcepos="27:5-27:63" dir="auto">dt(process.peb) -&gt; <code>list current process PEB structure</code></p>
</li>
<li data-sourcepos="28:3-28:238">
<p data-sourcepos="28:5-28:238" dir="auto">dt("<a href="https://web.archive.org/web/20211009172637/https://www.geoffchappell.com/studies/windows/km/ntoskrnl/inc/api/pebteb/peb/index.htm" rel="nofollow">_PEB</a>", 0xvirtualadderss, space=addrspace) -&gt; <code>Expand the PEB structure using virtual address</code></p>
</li>
<li data-sourcepos="29:3-29:240">
<p data-sourcepos="29:5-29:240" dir="auto">dt("<a href="https://web.archive.org/web/20211009172637/https://www.geoffchappell.com/studies/windows/km/ntoskrnl/inc/api/pebteb/peb/index.htm" rel="nofollow">_PEB</a>", 0xphysicaladderss, space=addrspace) -&gt; <code>Expand the PEB structure using physical address</code></p>
</li>
<li data-sourcepos="30:3-38:14">
<details>
  <summary>Important info in PEB structure</summary>
<ul data-sourcepos="33:7-37:87" dir="auto">
<li data-sourcepos="33:7-33:107">BeingDebugged -&gt; <code>some malicious programs set up a process and then connect a "debugger" to it</code></li>
<li data-sourcepos="34:7-34:88">OSMajorVersion &amp; OSMinorVersion -&gt; <code>correspond to the host operating system</code></li>
<li data-sourcepos="35:7-35:21">OSBuildNumber</li>
<li data-sourcepos="36:7-36:73">OSCSDVersion -&gt; <code>the service pack number multiplied by 0x100</code></li>
<li data-sourcepos="37:7-37:87">_RTL_USER_PROCESS_PARAMETERS -&gt; <code>The pointer is to the process parameters.</code></li>
</ul>
</details>
</li>
</ul>
</details>

## Rekall   

* [pslist - list processes using all methods by default.](https://rekall.readthedocs.io/en/latest/plugins.html#pslist-winpslist)
* [pstree - walk the task_struct.children and task_struct.sibling members to print process tress.](https://rekall.readthedocs.io/en/latest/plugins.html#pstree-linpstree)
* [psscan - Scan Physical memory for \_EPROCESS pool allocations.](https://rekall.readthedocs.io/en/latest/pluins.html#psscan-psscan)
* [psxview - Find hidden processes with various process listings](https://rekall.readthedocs.io/en/latest/plugins.html#psxview-windowspsxview)      

## Notes

* Providing KDBG virtual offsets to volatility with '-g' will speed up the process.
