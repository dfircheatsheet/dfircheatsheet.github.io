### Event IDs
   * <a href="https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/event.aspx?eventid=4656">4656 - Handle to object requested</a>
   * <a href="https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/event.aspx?eventid=4660">4660 - Object deleted</a>
   * <a href="https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/event.aspx?eventid=4663">4663 - Access attempt on object (read, write, delete, ... )</a>
### Notes
   * Event includes timestamp, file or folder name, and user account that attempted access
   * Filter by 4656 Failure Events to identify users attempting unauthorized access
   * Review 4663 events to identify what user actions occurred
   * Object auditing can quickly fill logs and requires tuning
