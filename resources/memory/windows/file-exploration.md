## [Volatility - plugins](https://github.com/volatilityfoundation/volatility/wiki/Command-Reference)
<ul>
   <li>
      <details>
         <summary><a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#filescan">filescan - Scan for files using pool tag scanning</a></summary>
         <ul>
            <li>
               Investigative Notes
               <ul>
                  <li>FILE objects found may have been closed already (often the case when the number of handles field is 0)</li>
               </ul>
            </li>
         </ul>
      </details>
   </li>
   <li>
      <details>
         <summary><a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#dumpfiles">dumpfiles - dump memory mapped files</a></summary>
         <ul>
            <li>
               Important parameters
               <ul>
                  <li>D: <code>dump_directory</code></li>
                  <li>S: <code>name of file to write summary of dumped files</code></li>
                  <li>p (pid): <code>dump memory mapped files for these PIDs</code></li>
                  <li>Q: <code>dump the FILE_OBJECT at physical offset</code></li>
                  <li>u: <code>Bypass sanity checks</code></li>
                  <li>F: <code>Filters to apply</code></li>
               </ul>
            </li>
            <li>
               Investigative Notes
               <ul>
                  <li>Not all open files are mapped into memory</li>
                  <li>Files that are mapped into memoiy may be only partially present</li>
                  <li>ImageSectionObject: File mapped as an executable (.img)</li>
                  <li>DataSectionObject: File mapped as data (.dat)</li>
                  <li>SharedCacheMap: Mapped as cached memory regions (.vacb)</li>
               </ul>
            </li>
         </ul>
      </details>
   </li>
</ul>

## [Rekall](https://rekall.readthedocs.io/en/latest/plugins.html)
* [filescan - Scan Physical memory for _FILE pool allocations](https://rekall.readthedocs.io/en/latest/plugins.html#filescan-filescan)
* [dumpfiles - dump memory mapped files](https://rekall.readthedocs.io/en/latest/plugins.html#dumpfiles-dumpfiles)
