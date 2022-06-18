<details>
   <summary>
      <h2>
         Volatility - <a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference">plugins</a>
      </h2>
   </summary>
   <ul>
      <li>
         <details>
            <summary>Process Listing</summary>
            <ul>
               <li><a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#pslist">pslist - walks the doubly-linked list pointed to by PsActiveProcessHead</a></li>
               <li><a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#pstree">pstree - print process tress</a></li>
               <li><a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#psscan">psscan - enumerate processes using pool tag scanning</a></li>
               <li><a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#psdispscan">psdispscan - enumerates processes by scanning for DISPATCHER_HEADER</a></li>
               <li><a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference-Mal#psxview">psxview - Detect hidden processes</a></li>
            </ul>
         </details>
      </li>
      <li>
         <details>
            <summary><a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#handles">handles - display open handles in a process</a></summary>
            <ul>
               <li>
                  Important Parameters
                  <ul>
                     <li>-p: <code>pids, comma separated)</code></li>
                     <li>-P: <code>use physical offsets)</code></li>
                     <li>-t: <code>types, comma separated)</code></li>
                     <li>-s: <code>suppress results that are "less meaningful"</code></li>
                  </ul>
               </li>
               <li>
                  Investigative Notes
                  <ul>
                     <li>May help discover unknown relationships between processes via common use of identical handles</li>
                     <li>For most investigations, -s should be used as a default</li>
                  </ul>
               </li>
            </ul>
         </details>
      </li>
      <li>
         <details>
            <summary><a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#enumfunc">enumfunc - enumerates imported and exported functions</a></summary>
            <ul>
               <li>
                  Important Parameters
                  <ul>
                     <li>-s <code>Scan for objects</code></li>
                     <li>-P <code>Show only process imports/exports</code></li>
                     <li>-K <code>Show only kernel imports/exports</code></li>
                     <li>-I <code>Show only imports</code></li>
                     <li>-E <code>Show only exports</code></li>
                  </ul>
               </li>
               <li>
                  Investigative Notes
                  <ul>
                     <li>Primarily useful for malware analysts</li>
                     <li>Can be used for preliminary capability analysis</li>
                  </ul>
               </li>
            </ul>
         </details>
      </li>
      <li>
         <details>
            <summary><a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#dlllist">dlllist - display a process's loaded DLLs</a></summary>
            <ul>
               <li>
                  Important Parameters
                  <ul>
                     <li>-p <code>pids, comma separated></code></li>
                  </ul>
               </li>
               <li>
                  Investigative Notes
                  <ul>
                     <li>The DLLs loaded into a process can be used to infer functionality</li>
                     <li>Networking DLLs in processes that don't normally use networking may indicate code injection</li>
                  </ul>
               </li>
            </ul>
         </details>
      </li>
      <li>
         <details>
            <summary><a href="https://icegrave0391.github.io/2020/03/09/memfor-7/#gt-Virtual-Address-Descriptors">VADs Exploration</a></summary>
            <ul>
               <li><a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#vadwalk">vadwalk - Display all VADs in list form</a></li>
               <li><a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#vadtree">vadtree - Display all VADs in tree form</a></li>
               <li><a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#vadlist">vadlist - List short details for each VAD</a></li>
               <li><a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#vadinfo">vadinfo - Display detailed VAD information</a></li>
               <li><a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#vaddump">vaddump - Copy frames from VADs to the disk</a></li>
            </ul>
         </details>
      </li>
      <li><a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#procdump">procdump - dump process executable</a></li>
      <li><a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#verinfo">impfuzzy - comparing the impfuzzy and imphash</a></li>
   </ul>
</details>
<details>
   <summary>
      <h2>
         Volatility - <a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#volshell">volshell</a>
      </h2>
   </summary>
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
               <li>dt(proc()) -&gt; <code>list current process EPROCESS structure</code></li>
               <li>dt(&quot;<a href="https://web.archive.org/web/20210302232116/https://www.geoffchappell.com/studies/windows/km/ntoskrnl/inc/ntos/ps/eprocess/index.htm">_EPROCESS</a>&quot;, virtualadderss, space=addrspace) -&gt; <code>Expand the EPROCEES structure using virtual address</code></li>
               <li>dt(&quot;<a href="https://web.archive.org/web/20210302232116/https://www.geoffchappell.com/studies/windows/km/ntoskrnl/inc/ntos/ps/eprocess/index.htm">_EPROCESS</a>&quot;, physicaladderss, space=addrspace) -&gt; <code>Expand the EPROCEES structure using physical address</code></li>
            </ul>
         </details>
      </li>
      <li>
         <details>
            <summary>PEB structure analysis</summary>
            <ul>
               <li>dt(proc().Peb) -&gt; <code>list current process PEB structure</code></li>
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
                        <li><a href="https://www.nirsoft.net/kernel_struct/vista/RTL_USER_PROCESS_PARAMETERS.html">ProcessParameters</a> -&gt; <code>The pointer is to the process parameters.</code></li>
                        <li><a href="https://www.nirsoft.net/kernel_struct/vista/PEB_LDR_DATA.html">Ldr </a>-> <code>Contains information about the loaded modules for the process.</code></li>
                     </ul>
                  </details>
               </li>
            </ul>
         </details>
      </li>
   </ul>
</details>
<details>
   <summary>
      <h2>
         Rekall - <a href="https://rekall.readthedocs.io/en/latest/plugins.html" rel="nofollow">plugins</a>
      </h2>
   </summary>
   <ul>
      <li>
         <details>
            <summary>Process Listing</summary>
            <ul>
               <li><a href="https://rekall.readthedocs.io/en/latest/plugins.html#pslist-winpslist">pslist - list processes using all methods by default.</a></li>
               <li><a href="https://rekall.readthedocs.io/en/latest/plugins.html#pstree-linpstree">pstree - walk the task_struct.children and task_struct.sibling members to print process tress.</a></li>
               <li><a href="https://rekall.readthedocs.io/en/latest/pluins.html#psscan-psscan">psscan - Scan Physical memory for \_EPROCESS pool allocations.</a></li>
               <li><a href="https://rekall.readthedocs.io/en/latest/plugins.html#psxview-windowspsxview">psxview - Find hidden processes with various process listings</a></li>
            </ul>
         </details>
      </li>
      <li><a href="https://rekall.readthedocs.io/en/latest/plugins.html#handles-handles">handles - print list of open handles to each process</a></li>
      <li><a href="https://rekall.readthedocs.io/en/latest/plugins.html#dlllist-windlllist">dlllist - display a process's loaded DLLs</a></li>
      <li><a href="https://rekall.readthedocs.io/en/latest/plugins.html#procdump-procexedump">procdump - dump process executables</a></li>
      <li><a href="https://rekall.readthedocs.io/en/latest/plugins.html#vad-vad">vad - dump of the VAD.</a></li>
   </ul>
</details>
<h2>
   Notes
</h2>
<ul>
   <li>Providing KDBG virtual offsets to volatility with '-g' will speed up the process.</li>
   <li><a href="https://www.fireeye.com/content/dam/fireeye-www/services/freeware/ug-redline.pdf">Use redline to get a quick insight on the memory dump</a></li>
   <li>
      <details>
         <summary>Suspicious Processes Indicators</summary>
         <ul>
            <li>Check parent/child relationships <code>Processes run by users -> Have Explorer as an ancestor & Processes run by SYSTEM -> Have system as an ancestor</code></li>
            <li>Look for irrelvant imports <code>network apis used by notepad process</code></li>
            <li>Valid Program Names: <code>Programmers choose human readable names. Lookout for random series of characters.</code></li>
            <li>Ending in .exe: <code>Legitimate programs have a valid extension. Malware often leaves a blank extension.</code></li>
            <li>More than one or two characters in the filename: <code>Legitimate programs have a name, not just an ID number.</code></li>
            <li>Spelling mistakes: <code>Malware authors may not be native English speakers.</code></li>
            <li>Correct file locations: <code>Finding an executable starting from any uncommon directory is a sign of trouble.</code></li>
            <li>Valid command line arguments: <code>Processes are often launched with specific parameters.</code></li>
            <li><a href="https://digitalforensicsurvivalpodcast.com/2019/04/14/dfsp-165-windoes-core-processes/">Check Process Singletons: <code>Some processes should never have more than one copy in process list</code></a></li>
            <li>Use impfuzzy to compare Import Table hash with known variants</li>
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
