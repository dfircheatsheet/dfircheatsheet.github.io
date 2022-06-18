## [Volatility - plugins](https://github.com/volatilityfoundation/volatility/wiki/Command-Reference)

<ul>
   <li>
      <details>
         <summary><a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#verinfo">verinfo - display the version information embedded in PE files</a></summary>
         <ul>
            <li>
               Important Parameters
               <ul>
                  <li>-o <code>offset of module to dump version info from</code></li>
                  <li>-r <code>regex to dump info from</code></li>
                  <li>-i <code>ignore case in regex</code></li>
               </ul>
            </li>
            <li>
               Investigative Notes
               <ul>
                  <li>Used to examine process memory allocations</li>
                  <li>Can help locate injected code, including executable code not in the loaded modules list</li>
               </ul>
            </li>
         </ul>
      </details>
   </li>
      <li>
      <details>
         <summary><a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#dlldump">dlldump - Extract a DLL from a memory image</a></summary>
         <ul>
            <li>
               Important Parameters
               <ul>
                  <li>-p <code>PID to dump DLLs from</code></li>
                  <li>-D <code>Dump directory</code></li>
                  <li>-u <code>Suppress safety checks</code></li>
                  <li>-r <code>Regex for DLLs to match</code></li>
                  <li>-i <code>Make the regex case insensitive</code></li>
                  <li>-o <code>Offset (dump DLLs with this physical offset)</code></li>
                  <li>-b <code>Offset (dump DLL with this virtual base address)</code></li>
               </ul>
            </li>
            <li>
               Investigative Notes
               <ul>
                  <li>Filter carefully to reduce output</li>
               </ul>
            </li>
         </ul>
      </details>
   </li>
</ul>

## [Rekall](https://rekall.readthedocs.io/en/latest/plugins.html)

<ul>
   <li>
      <details>
         <summary><a href="https://rekall.readthedocs.io/en/latest/plugins.html#peinfo-peinfo">peinfo - Print information about a PE binary.</a></summary>
         <ul>
            <li>
               Investigative Notes
               <ul>
                  <li>Can be used for preliminary capability analysis on memory-mapped or disk files</li>
               </ul>
            </li>
         </ul>
      </details>
   </li>
</ul>

## Notes
<ul>
   <li>Providing KDBG virtual offsets to volatility with '-g' will speed up the process.</li>
   <li><a href="https://www.fireeye.com/content/dam/fireeye-www/services/freeware/ug-redline.pdf">Use redline to get a quick insight on the memory dump</a></li>
   <li>
      <details>
         <summary>Dealing with suspicious DLL/EXE</summary>
         <ul>
            <li>Dump DLL/EXE</li>
            <li>Use strings to look for Indicators of Packing and Persistence</li>
            <li>Submit DLL/EXE to online services as VirusTotal</li>
         </ul>
      </details>
   </li>
</ul>
