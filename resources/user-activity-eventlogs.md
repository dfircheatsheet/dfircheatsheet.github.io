* ### Event IDs
   * <a href="https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/event.aspx?eventid=4624">4624 - Successful Logon</a>
   * <a href="https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/event.aspx?eventid=4625">4625 - Failed Logon</a>
   * <a href="https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/event.aspx?eventid=4634">4634 - Successful Logoff</a>
   * <a href="https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/event.aspx?eventid=4647">4647 - Successful interactive Logoff</a>
   * <a href="https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/event.aspx?eventid=4672">4672 - Account logon with superuser rights (Administrator)</a>
* ### Notes
   * Windows does not reliably record logoffs (ID 4634) so also look for ID 4647 -> user initiated logoff for interactive logons
   * Logon events not recorded when backdoors, exploited services, or similar malicious means are used to access a system
