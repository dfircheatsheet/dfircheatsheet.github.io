## MS Office
### <a href="https://forensicswiki.xyz/wiki/index.php?title=Windows_Registry">Windows Registry Analysis</a>
   * <a href="https://df-stream.com/category/microsoft-office-forensics/">microsoft-office-forensics</a>

### <a href="https://forensicswiki.xyz/wiki/index.php?title=Windows_XML_Event_Log_(EVTX)">Windows Event Logs</a>
   * <a href="https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/event.aspx?eventid=4779">300 - Office Alert (used by all Office products)</a>

### Notes
      * Microsoft dialog alerts are recorded as events in OAlerts. evtx
      * File access, modification, and deletes may be recorded 
      * Unauthorized access/ permissions issues trigger events
      * Outlook activity is particularly valuable as little other logging exists
      * OAlerts is not a comprehensive source of all Office activity
## Outlook
### <a href="https://forensicswiki.xyz/wiki/index.php?title=Windows_Registry">Windows Registry Analysis</a>
* Outlook 2007 Account Passwords: NTUSER.DAT\Software\Microsoft\Protected Storage SystemProvider\SID\Identification\INETCOMM Server Passwords
* Outlook 2007 Recent Attachments: NTUSER.DAT\Software\Microsoft\office\version\Common\Open Find\Microsoft Office Outlook\Settings\Save Attachment\File Name MRU
* Outlook 2007 Temp file location: NTUSER.DAT\Software\Microsoft\Office\version\Outlook\Security
* Outlook Account Passwords: NTUSER.DAT\Software\Microsoft\ Protected Storage System Provider\SID\ Identification\INETCOMM Server Passwords
* Outlook Accounts: HKEY_LOCAL_MACHINE\Software\Microsoft\Internet Account Manager
* Outlook Recent Attachments: NTUSER.DAT\Software\Microsoft\ office\version\ Common\Open Find\ Microsoft Office Outlook\Settings\Save Attachment\File Name MRU
* Outlook Settings: HKEY_USERS\(User_ID)\Software\Microsoft\Office\Outlook\OMI Account Manager\Accounts\
* Outlook Temporary Attachment Directory: NTUSER.DAT\Software\Microsoft\Office\version\ Outlook\Security   

### Artifacts Location
* %USERPROFILE%\Documents\Outlook
* %USERPROFILE%\AppData\Local\Microsoft\Outlook
* %APPDATA%\Local\Microsoft\Windows\Temporary Internet Files\Content.Outlook
* %APPDATA%\Local\Microsoft\Windows\INetCache\Content.Outlook
