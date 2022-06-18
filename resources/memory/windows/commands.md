### Volatility
* [consoles - scans for CONSOLE_INFORMATION](https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#consoles)
* [cmdscan - finds structures known as COMMAND_HISTORY](https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#cmdscan)
### Rekall
* [cmdscan - Extract command history by scanning for \_COMMAND_HISTORY](https://rekall.readthedocs.io/en/latest/plugins.html#cmdscan-cmdscan)
* [consoles - scans for CONSOLE_INFORMATION.](https://rekall.readthedocs.io/en/latest/plugins.html#consoles-consoles)
* [consolescan - Extract command history by scanning for \_CONSOLE_INFORMATION](https://rekall.readthedocs.io/en/latest/plugins.html#consolescan-consolescan)
* [boot_cmdline - Prints the kernel command line.](https://rekall.readthedocs.io/en/latest/plugins.html#boot-cmdline-darwinbootparameters)
### Notes
<ul>
   <li>Providing KDBG virtual offsets to volatility with '-g' will speed up the process.</li>
   <li><a href="https://www.fireeye.com/content/dam/fireeye-www/services/freeware/ug-redline.pdf">Use redline to get a quick insight on the memory dump</a></li>
</ul>
