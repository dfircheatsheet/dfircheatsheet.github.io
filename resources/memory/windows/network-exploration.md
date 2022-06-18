## [Volatility - plugins](https://github.com/volatilityfoundation/volatility/wiki/Command-Reference)
<ul>
  <li><a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#netscan">netscan - scan for network artifacts using pool tags</a></li>
  <li><a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#connections">connections - Walk list of TCP connection objects (Windows XP and Windows 2003 Server only)</a></li>
  <li><a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#connscan">connscan - Scan for TCP connection objects (Windows XP and Windows 2003 Server only)</a></li>
  <li><a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#sockets">sockets - Walk list of TCP and UDP sockets (Windows XP and Windows 2003 Server only)</a></li>
  <li><a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#sockscan">sockscan - Scan for TCP and UDP sockets (Windows XP and Windows 2003 Server only)</a></li>
</ul>

## [Volatility - volshell](https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#volshell)   
<ul>
   <li>
      <details>
         <summary>LISTENING UDP Connection Structure</summary>
         <ul>
            <li>dt("_UDP_ENDPOINT", physicaladdr, space=addrspace().base) -&gt; <code>list LISTENING UDP Connection Structure</code></li>
         </ul>
      </details>
   </li>
   <li>
      <details>
         <summary>LISTENING TCP Connection Structure</summary>
         <ul>
            <li>dt("_TCP_LISTENER", physicaladdr, space=addrspace().base) -&gt; <code>list LISTENING TCP Connection Structure</code></li>
         </ul>
      </details>
   </li>
   <li>
      <details>
        <summary>ESTABLISHED TCP Connection Structure</summary>
         <ul>
            <li>dt("_TCP_ENDPOINT", physicaladdr, space=addrspace().base) -&gt; <code>list ESTABLISHED TCP Connection Structure</code></li>
         </ul>
      </details>
   </li>
</ul>

## [Rekall](https://rekall.readthedocs.io/en/latest/plugins.html)
<ul>
  <li><a href="https://rekall.readthedocs.io/en/latest/plugins.html#netscan-winnetscan">netscan - scan for network artifacts using pool tags</a></li>
  <li><a href="https://rekall.readthedocs.io/en/latest/plugins.html#connscan-connscan">connscan - Scan Physical memory for _TCPT_OBJECT objects</a></li>
  <li><a href="https://rekall.readthedocs.io/en/latest/plugins.html#connections-connections">connections - Print list of open connections [Windows XP Only]</a></li>
  <li><a href="https://rekall.readthedocs.io/en/latest/plugins.html#sockets-sockets">sockets - Print list of open sockets. [Windows xp only]</a></li>
  <li><a href="https://rekall.readthedocs.io/en/latest/plugins.html#netstat-darwinnetstat">netstat - Prints all open sockets we know about.</a></li>
</ul>

## Notes
<ul>
   <li>
      <details>
         <summary></summary>
      </details>
   </li>
</ul>
