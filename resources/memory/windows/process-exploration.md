## [Volatility - plugins](https://github.com/volatilityfoundation/volatility/wiki/Command-Reference)
<ul>
   <li><a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#pslist">pslist - walks the doubly-linked list pointed to by PsActiveProcessHead</a></li>
   <li><a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#pstree">pstree - print process tress</a></li>
   <li><a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#psscan">psscan - enumerate processes using pool tag scanning</a></li>
   <li><a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#psdispscan">psdispscan - enumerates processes by scanning for DISPATCHER_HEADER</a></li>
   <li><a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference-Mal#psxview">psxview - Detect hidden processes</a></li>
   <li><a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#procdump">procdump - dump process executable</a></li>
   <li>
      <details>
         <summary><a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#handles">handles - display open handles in a process</a></summary>
         <ul>
            <li>
               <details>
                  <summary>Important Parameters</summary>
                  <ul>
                     <li>-p <pids, comma separated></li>
                     <li>-P (use physical offsets)</li>
                     <li>-t <types, comma separated></li>
                     <li>-s Suppress results that are "less meaningful"</li>
                  </ul>
               </details>
            </li>
            <li>
               <details>
                  <summary>Investigative Notes</summary>
                  <ul>
                     <li>May help discover unknown relationships between processes via common use of identical handles</li>
                     <li>For most investigations, -s should be used as a default</li>
                  </ul>
               </details>
            </li>
         </ul>
      </details>
   </li>
</ul>

## [Volatility - volshell](https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#volshell)   
<ul>
   <li>
      <details>
         <summary>Explore Processes</summary>
         <ul>
            <li>ps() -&gt; <code>List processes</code></li>
            <li>cc(pid=4) -&gt; <code>Change to another process</code></li>
         </ul>
      </details>
   </li>
   <li>
      <details>
         <summary>EPROCESS structure analysis</summary>
         <ul>
            <li>dt(process) -&gt; <code>list current process EPROCESS structure</code></li>
            <li>dt(&quot;<a href="https://web.archive.org/web/20210302232116/https://www.geoffchappell.com/studies/windows/km/ntoskrnl/inc/ntos/ps/eprocess/index.htm">_EPROCESS</a>&quot;, virtualadderss, space=addrspace) -&gt; <code>Expand the EPROCEES structure using virtual address</code></li>
            <li>dt(&quot;<a href="https://web.archive.org/web/20210302232116/https://www.geoffchappell.com/studies/windows/km/ntoskrnl/inc/ntos/ps/eprocess/index.htm">_EPROCESS</a>&quot;, physicaladderss, space=addrspace) -&gt; <code>Expand the EPROCEES structure using physical address</code></li>
         </ul>
      </details>
   </li>
   <li>
      <details>
         <summary>PEB structure analysis</summary>
         <ul>
            <li>dt(process.peb) -&gt; <code>list current process PEB structure</code></li>
            <li>dt(&quot;<a href="https://web.archive.org/web/20211009172637/https://www.geoffchappell.com/studies/windows/km/ntoskrnl/inc/api/pebteb/peb/index.htm">_PEB</a>&quot;, virtualadderss, space=addrspace) -&gt; <code>Expand the PEB structure using virtual address</code></li>
            <li>dt(&quot;<a href="https://web.archive.org/web/20211009172637/https://www.geoffchappell.com/studies/windows/km/ntoskrnl/inc/api/pebteb/peb/index.htm">_PEB</a>&quot;, physicaladderss, space=addrspace) -&gt; <code>Expand the PEB structure using physical address</code></li>
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
   </li>
</ul>

## [Rekall](https://rekall.readthedocs.io/en/latest/plugins.html)
* [pslist - list processes using all methods by default.](https://rekall.readthedocs.io/en/latest/plugins.html#pslist-winpslist)
* [pstree - walk the task_struct.children and task_struct.sibling members to print process tress.](https://rekall.readthedocs.io/en/latest/plugins.html#pstree-linpstree)
* [psscan - Scan Physical memory for \_EPROCESS pool allocations.](https://rekall.readthedocs.io/en/latest/pluins.html#psscan-psscan)
* [psxview - Find hidden processes with various process listings](https://rekall.readthedocs.io/en/latest/plugins.html#psxview-windowspsxview)
* [procdump - dump process executables](https://rekall.readthedocs.io/en/latest/plugins.html#procdump-procexedump)
* [handles - print list of open handles to each process](https://rekall.readthedocs.io/en/latest/plugins.html#handles-handles)

## Notes
<ul>
   <li>Providing KDBG virtual offsets to volatility with '-g' will speed up the process.</li>
   <li><a href="https://www.fireeye.com/content/dam/fireeye-www/services/freeware/ug-redline.pdf">Use redline to get a quick insight on the memory dump</a></li>
   <li>
      <details>
         <summary>Suspicious Processes Indicators</summary>
         <ul>
            <li>Processes run by users -> Have Explorer as an ancestor & Processes run by SYSTEM -> Have system as an ancestor</li>
            <li>Valid Program Names: <code>Programmers choose human readable names. Lookout for random series of characters.</code></li>
            <li>Ending in .exe: <code>Legitimate programs have a valid extension. Malware often leaves a blank extension.</code></li>
            <li>More than one or two characters in the filename: <code>Legitimate programs have a name, not just an ID number.</code></li>
            <li>Spelling mistakes: <code>Malware authors may not be native English speakers.</code></li>
            <li>Correct file locations: <code>Finding an executable starting from any uncommon directory is a sign of trouble.</code></li>
            <li>Valid command line arguments: <code>Processes are often launched with specific parameters.</code></li>
            <li><a href="https://digitalforensicsurvivalpodcast.com/2019/04/14/dfsp-165-windoes-core-processes/">Check Process Singletons: <code>Some processes should never have more than one copy in process list</code></a></li>
            <li>Check parent/child relationships</li>
         </ul>
      </details>
   </li>
   <li>
      <details>
         <summary>Dealing with suspicious processes</summary>
         <ul>
            <li>Dump process executables</li>
            <li>Use strings to look for Indicators of Packing and Persistence</li>
            <li>Submit executables to online services as VirusTotal</li>
            <li>Check opened handles for this process</li>
         </ul>
      </details>
   </li>
</ul>
