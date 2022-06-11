## Volatility - plugins

* [pslist - walks the doubly-linked list pointed to by PsActiveProcessHead](https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#pslist)
* [pstree - print process tress](https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#pstree)
* [psscan - enumerate processes using pool tag scanning](https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#psscan)
* [psdispscan - enumerates processes by scanning for DISPATCHER_HEADER](https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#psdispscan)
* [psxview - Detect hidden processes](https://github.com/volatilityfoundation/volatility/wiki/Command-Reference-Mal#psxview)
* [procdump - dump process executable](https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#procdump)

## [Volatility - volshell](https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#volshell)   

<details>
  <summary>Explore Processes</summary>
<ul>
<li>ps() -&gt; <code>List processes</code></li>
<li>cc(pid=4) -&gt; <code>Change to another process</code></li>
</ul>
</details>
<details>
  <summary>EProcess structure analysis</summary>
<ul>
<li>dt(process) -&gt; <code>list current process EPROCESS structure</code></li>
<li>dt(&quot;<a href="https://web.archive.org/web/20210302232116/https://www.geoffchappell.com/studies/windows/km/ntoskrnl/inc/ntos/ps/eprocess/index.htm">_EPROCESS</a>&quot;, 0xvirtualadderss, space=addrspace) -&gt; <code>Expand the EPROCEES structure using virtual address</code></li>
<li>dt(&quot;<a href="https://web.archive.org/web/20210302232116/https://www.geoffchappell.com/studies/windows/km/ntoskrnl/inc/ntos/ps/eprocess/index.htm">_EPROCESS</a>&quot;, 0xphysicaladderss, space=addrspace) -&gt; <code>Expand the EPROCEES structure using physical address</code></li>
</ul>
</details>
<details>
  <summary>PEB structure analysis</summary>
<ul>
<li>dt(process.peb) -&gt; <code>list current process PEB structure</code></li>
<li>dt(&quot;<a href="https://web.archive.org/web/20211009172637/https://www.geoffchappell.com/studies/windows/km/ntoskrnl/inc/api/pebteb/peb/index.htm">_PEB</a>&quot;, 0xvirtualadderss, space=addrspace) -&gt; <code>Expand the PEB structure using virtual address</code></li>
<li>dt(&quot;<a href="https://web.archive.org/web/20211009172637/https://www.geoffchappell.com/studies/windows/km/ntoskrnl/inc/api/pebteb/peb/index.htm">_PEB</a>&quot;, 0xphysicaladderss, space=addrspace) -&gt; <code>Expand the PEB structure using physical address</code></li>
<li>
<details>
  <summary>Important info in PEB structure</summary>
<ul>
<li>BeingDebugged -&gt; <code>some malicious programs set up a process and then connect a &quot;debugger&quot; to it</code></li>
<li>OSMajorVersion &amp; OSMinorVersion -&gt; <code>correspond to the host operating system</code></li>
<li>OSBuildNumber</li>
<li>OSCSDVersion -&gt; <code>the service pack number multiplied by 0x100</code></li>
<li><a href="https://www.nirsoft.net/kernel_struct/vista/RTL_USER_PROCESS_PARAMETERS.html">_RTL_USER_PROCESS_PARAMETERS</a> -&gt; <code>The pointer is to the process parameters.</code></li>
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
* [procdump - dump process executables](https://rekall.readthedocs.io/en/latest/plugins.html#procdump-procexedump)

## Notes

<ul>
<li>Providing KDBG virtual offsets to volatility with '-g' will speed up the process.</li>
<li><a href="https://www.fireeye.com/content/dam/fireeye-www/services/freeware/ug-redline.pdf">Use redline to get a quick insight on the memory dump</a>
<li>
<details>
  <summary>Suspicious Processes Indicators</summary>
<ul>
<li>Processes run by users -> Have Explorer as an ancestor & Processes run by SYSTEM -> Have system as an ancestor
<li>Valid Program Names: <code>Programmers choose human readable names. Lookout for random series of characters.</code>
<li>Ending in .exe: <code>Legitimate programs have a valid extension. Malware often leaves a blank extension.</code>
<li>More than one or two characters in the filename: <code>Legitimate programs have a name, not just an ID number.</code>
<li>Spelling mistakes: <code>Malware authors may not be native English speakers.</code>
<li>Correct file locations: <code>Finding an executable starting from any uncommon directory is a sign of trouble.</code>
<li>Valid command line arguments: <code>Processes are often launched with specific parameters.</code>
</ul>
</details>
<li>
<details open="">
  <summary>Dealing with suspicious processes</summary>
<ol type="1">
<li>Dump process executables
<li>Use strings to look for Indicators of Packing and Persistence
<li>Submit executables to online services as VirusTotal
</ol>
</details>
</li>
</ul>
