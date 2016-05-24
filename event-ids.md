permalink: /event-ids

### Windows Event IDs and Lateral Movements 

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
