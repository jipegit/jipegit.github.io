---
layout: default
permalink: /event-ids
---

# Windows Event IDs and Lateral Movements 

{:.table-striped}
| Scheduled Tasks Log  | XP: %SystemRoot%\SchedLgu.txt - 7: %SystemRoot%\Tasks\SchedLgu.txt  |             |                                                   |
|----------------------|---------------------------------------------------------------------|-------------|---------------------------------------------------|
|                      | 106                                                                 |             | Task Scheduled                                    |
|                      | 200                                                                 |             | Task Executed                                     |
|                      | 201                                                                 |             | Task Completed                                    |
|                      | 141                                                                 |             | Task Removed                                      |
| Logon Events         | 528                                                                 | 4624        | Successful Logon                                  |
|                      | 529                                                                 | 4625        | Failed Logon                                      |
|                      | 538                                                                 | 4647 / 4634 | Successful Logoff                                 |
|                      | 540                                                                 | 4624        | Successful Network Logon                          |
|                      |                                                                     | 4672        | Successful Network Logon as Admin                 |
| RDP                  | 21                                                                  |             | RDP logon success                                 |
|                      | 24                                                                  |             | RDP user disconnected                             |
|                      | 24                                                                  |             | RDP user reconnected                              |
|                      |                                                                     | 1149        | RDP user authenticated                            |
| Account Logon Events | 680                                                                 | 4776        | Successful / Failed account authentication        |
|                      | 672                                                                 | 4768        | TGT was issued (successful logon)                 |
|                      | 675                                                                 | 4771        | Pre-authentication failed (failed logon)          |
| Rogue Local Account  | 680                                                                 | 4776        | An account successfully authenticated             |
|                      | 540                                                                 | 4624        | Successful Network Logon immediately following    |
| Share                |                                                                     | 5140        | Share mount                                       |
| Suspicious Services  |                                                                     | 7034        | Service crashed unexpectedly                      |
|                      |                                                                     | 7035        | Service sent a Start/Stop control                 |
|                      |                                                                     | 7036        | Service sent a started or stoped                  |
|                      |                                                                     | 7040        | Start type changed (Boot | On request | Disabled) |
| Clearing Event Logs  | 517                                                                 |             |                                                   |

# Tool

* [Microsoft logparser](https://www.microsoft.com/en-us/download/details.aspx?id=24659)
* [Log Parser Lizard](http://www.lizard-labs.com/log_parser_lizard.aspx)
* [CERT Société Générale Event2Timeline](https://github.com/certsocietegenerale/event2timeline)

# Source

* <https://digital-forensics.sans.org/media/poster-windows-forensics-2016.pdf>
* <https://digital-forensics.sans.org/blog/2011/02/10/computer-forensics-howto-microsoft-log-parser>
* <http://www.redblue.team/2015/09/spotting-adversary-with-windows-event.html>
* <http://www.redblue.team/2015/09/spotting-adversary-with-windows-event_21.html>
* <http://forensicswiki.org/wiki/Windows_Event_Log_(EVT)>
* <http://forensicswiki.org/wiki/Windows_XML_Event_Log_(EVTX)>