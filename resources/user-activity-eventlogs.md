### Event IDs
   * <a href="https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/event.aspx?eventid=4624">4624 - Successful Logon</a>
   * <a href="https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/event.aspx?eventid=4625">4625 - Failed Logon</a>
   * <a href="https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/event.aspx?eventid=4634">4634 - Successful Logoff</a>
   * <a href="https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/event.aspx?eventid=4647">4647 - Successful interactive Logoff</a>
   * <a href="https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/event.aspx?eventid=4672">4672 - Account logon with superuser rights (Administrator)</a>
   * <a href="https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/event.aspx?eventid=4778">4778 - Session Connected/Reconnected</a>
   * <a href="https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/event.aspx?eventid=4779">4779 - Session Disconnected</a>
* ### Notes
   * Windows does not reliably record logoffs (ID 4634) so also look for ID 4647 -> user initiated logoff for interactive logons
   * Logon events not recorded when backdoors, exploited services, or similar malicious means are used to access a system
   * Event log provides hostname and IP address of remote machine making the connection
   * On workstations, you will often see current session disconnected (4779) followed by RDP connection (4778)
   * These events are also used to track "Fast User Switching" sessions
   * The auxiliary logs Remote Desktop Services - RDPCoreTS and TerminalServices-RemoteConnectionManager record similar info
