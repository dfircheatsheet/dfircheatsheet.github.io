<details>
	<summary style="font-size:1.5em;margin-top:0.83em;margin-bottom:0.83em;margin-left:0;margin-right:0;font-weight:bold;">Bulk-Extractor - <a href="https://github.com/simsong/bulk_extractor">Scanners</a></summary>
	<ul>
		<li><a href="https://isc.sans.edu/forums/diary/Extracting+pcap+from+memory/20639/">Extract pcap from Memory Dumps</a></li>
		<li>bulk_extractor -x all -e email <code>Look for emails</code></li>
		<li>bulk_extractor -x all -e httplogs <code>Extract httplogs</code></li>
		<li>bulk_extractor -x all -e facebook <code>Extract facebook artifact</code></li>
		<li>bulk_extractor -x all -e outllok <code>Extract outlook artifact</code></li>
	</ul>
</details>
<details>
	<summary style="font-size:1.5em;margin-top:0.83em;margin-bottom:0.83em;margin-left:0;margin-right:0;font-weight:bold;">Volatility - <a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference">plugins</a></summary>
	<ul>
		<ul>
			<li>
				<details>
					<summary><a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#netscan">netscan - scan for network artifacts using pool tags</a></summary>
					<ul>
						<li> Important Parameters
							<ul>
								<li>-V <code>Scans virtual memory (returns virtual addresses)</code></li>
							</ul>
						</li>
						<li> Investigative Notes
							<ul>
								<li>Brute force searches for TcpL, TcpE, and UdpA pool tags</li>
							</ul>
						</li>
					</ul>
				</details>
			</li>
			<li>
				<details>
					<summary><a href="https://github.com/bridgeythegeek/ndispktscan">ndispktscan - Carve Ethernet packets from NDIS shared memory sections</a></summary>
					<ul>
						<li> Important Parameters
							<ul>
								<li>-p PCAP <code>Save to PCAP file</code></li>
								<li>-D DSTS <code>Save the destination IPs to a text file</code></li>
								<li>-s <code>Look for slack only</code></li>
								<li>-m MAC <code>Source MAC address to find</code></li>
							</ul>
						</li>
						<li> Investigative Notes
							<ul>
								<li>Supports WinXP to WinlO, though extracted packets may contain less data based on Windows version</li>
							</ul>
						</li>
					</ul>
				</details>
			</li>
		</ul>
	</ul>
</details>
<details>
	<summary style="font-size:1.5em;margin-top:0.83em;margin-bottom:0.83em;margin-left:0;margin-right:0;font-weight:bold;">Volatility - <a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#volshell">volshell</a></summary>
	<ul>
		<li>
			<details>
				<summary>LISTENING UDP Connection Structure</summary>
				<ul>
					<li>dt("_UDP_ENDPOINT", virtualaddr) -&gt; <code>list LISTENING UDP Connection Structure</code></li>
				</ul>
			</details>
		</li>
		<li>
			<details>
				<summary>LISTENING TCP Connection Structure</summary>
				<ul>
					<li>dt("_TCP_LISTENER", virtualaddr) -&gt; <code>list LISTENING TCP Connection Structure</code></li>
				</ul>
			</details>
		</li>
		<li>
			<details>
				<summary>ESTABLISHED TCP Connection Structure</summary>
				<ul>
					<li>dt("_TCP_ENDPOINT", virtualaddr) -&gt; <code>list ESTABLISHED TCP Connection Structure</code></li>
				</ul>
			</details>
		</li>
	</ul>
</details>
<details>
	<summary style="font-size:1.5em;margin-top:0.83em;margin-bottom:0.83em;margin-left:0;margin-right:0;font-weight:bold;">Rekall - <a href="https://rekall.readthedocs.io/en/latest/plugins.html">plugins</a></summary>
	<ul>
		<li><a href="https://rekall.readthedocs.io/en/latest/plugins.html#netscan-winnetscan">netscan - scan for network artifacts using pool tags</a></li>
		<li><a href="https://rekall.readthedocs.io/en/latest/plugins.html#connscan-connscan">connscan - Scan Physical memory for _TCPT_OBJECT objects</a></li>
		<li><a href="https://rekall.readthedocs.io/en/latest/plugins.html#netstat-darwinnetstat">netstat - Prints all open sockets we know about.</a></li>
	</ul>
</details>

## Notes
<ul>
   <li>Providing KDBG virtual offsets to volatility with '-g' will speed up the process.</li>
   <li><a href="https://www.fireeye.com/content/dam/fireeye-www/services/freeware/ug-redline.pdf">Use redline to get a quick insight on the memory dump</a></li>
   <li>
      <details>
         <summary>Suspicious Network Artifacts</summary>
         <ul>
            <li>Uncharacteristic network activity from well-known processes</li>
            <ul>
               <li>For example, System:4 communicating to remote host Port 80/443</li>
               <li>or calc.exe communicating on the network</li>
            </ul>
            <li>Windows filesharing ports 135-139, 445</li>
            <ul>
               <li>It depends, possible lateral movement</li>
               <li>Ingress Port 445 traffic from external host: 100% suspicious</li>
            </ul>
            <li>High port to low port is normally okay</li>
            <ul>
               <li>Workstation to Server: Typically benign, compare to baseline</li>
               <li>Workstation to Workstation and Server to Workstation: Potentially suspicious</li>
               <li>Except for C&C servers</li>
            </ul>
            <li>High port to high port</li>
            <ul>
               <li>It depends on owning process, potentially P2P traffic</li>
            </ul>
         </ul>
      </details>
   </li>
</ul>
