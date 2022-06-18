<details>
	<summary>
		<h2 dir="auto"><a id="user-content-volatility---plugins" class="anchor" aria-hidden="true" href="#volatility---plugins"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>Volatility - <a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference">plugins</a></h2></summary>
	<ul dir="auto">
		<li>
			<details>
				<summary><a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#verinfo">verinfo - display the version information embedded in PE files</a></summary>
				<ul dir="auto">
					<li> Important Parameters
						<ul dir="auto">
							<li>-o <code>offset of module to dump version info from</code></li>
							<li>-r <code>regex to dump info from</code></li>
							<li>-i <code>ignore case in regex</code></li>
						</ul>
					</li>
					<li> Investigative Notes
						<ul dir="auto">
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
				<ul dir="auto">
					<li> Important Parameters
						<ul dir="auto">
							<li>-p <code>PID to dump DLLs from</code></li>
							<li>-D <code>Dump directory</code></li>
							<li>-u <code>Suppress safety checks</code></li>
							<li>-r <code>Regex for DLLs to match</code></li>
							<li>-i <code>Make the regex case insensitive</code></li>
							<li>-o <code>Offset (dump DLLs with this physical offset)</code></li>
							<li>-b <code>Offset (dump DLL with this virtual base address)</code></li>
						</ul>
					</li>
					<li> Investigative Notes
						<ul dir="auto">
							<li>Filter carefully to reduce output</li>
						</ul>
					</li>
				</ul>
			</details>
		</li>
	</ul>
</details>
<details>
	<summary>
		<h2 dir="auto"><a id="user-content-rekall" class="anchor" aria-hidden="true" href="#rekall"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>Rekall - <a href="https://rekall.readthedocs.io/en/latest/plugins.html" rel="nofollow">plugins</a></h2></summary>
	<ul dir="auto">
		<li>
			<details>
				<summary><a href="https://rekall.readthedocs.io/en/latest/plugins.html#peinfo-peinfo" rel="nofollow">peinfo - Print information about a PE binary.</a></summary>
				<ul dir="auto">
					<li> Investigative Notes
						<ul dir="auto">
							<li>Can be used for preliminary capability analysis on memory-mapped or disk files</li>
						</ul>
					</li>
				</ul>
			</details>
		</li>
	</ul>
</details>
<h2 dir="auto"><a id="user-content-notes" class="anchor" aria-hidden="true" href="#notes"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>Notes</h2>
<ul dir="auto">
	<li>Providing KDBG virtual offsets to volatility with '-g' will speed up the process.</li>
	<li><a href="https://www.fireeye.com/content/dam/fireeye-www/services/freeware/ug-redline.pdf" rel="nofollow">Use redline to get a quick insight on the memory dump</a></li>
	<li>
		<details>
			<summary>Dealing with suspicious DLL/EXE</summary>
			<ul dir="auto">
				<li>Dump DLL/EXE</li>
				<li>Use strings to look for Indicators of Packing and Persistence</li>
				<li>Submit DLL/EXE to online services as VirusTotal</li>
			</ul>
		</details>
	</li>
</ul>
