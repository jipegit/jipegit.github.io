---
permalink: /normal
---

# Normal 

## System 
	Image Path: No Image Path
	Parent Process: No Parent Process
	Number of Instances : One 
	User account: Local System
	Start Time: At boot time

## smss.exe 
	Image Path: %SystemRoot%\System32\smss.exe
	Parent Process: System
	Number of Instances : One master and another child per session exiting after session is created
	User account: Local System
	Start Time: Within seconds of boot time for the master instance

## wininit.exe
	Image Path: %SystemRoot%\System32\wininit.exe
	Parent Process: Created by an instane of smss.exe that exists (tools usually don't provide the parent process name)
	Number of Instances : One
	User account: Local System
	Start Time: Within seconds of boot time

## taskhost.exe
	Image Path: %SystemRoot%\System32\taskhost.exe
	Parent Process: services.exe
	Number of Instances : One or more
	User account: Multiple taskhost.exe processes are normal. Logged-on users and/or local services accounts
	Start Time: Within seconds of boot time

## lsass.exe
	Image Path: %SystemRoot%\System32\lsass.exe
	Parent Process: wininit.exe
	Number of Instances : One
	User account: Local System
	Start Time: Within seconds of boot time

## winlogon.exe
	Image Path: %SystemRoot%\System32\winlogon.exe
	Parent Process: Created by an instane of smss.exe that exists (tools usually don't provide the parent process name)
	Number of Instances : One or more
	User account: Local System
	Start Time: Within seconds of boot time for the first instance

## csrss.exe
	Image Path: %SystemRoot%\System32\csrss.exe
	Parent Process: Created by an instane of smss.exe that exists (tools usually don't provide the parent process name)
	Number of Instances : Two or more
	User account: Local System
	Start Time: Within seconds of boot time for the first two instances (Session 0 and 1)
	Note: cmd.exe history is stored in these processes' memory 

## services.exe
	Image Path: %SystemRoot%\System32\services.exe
	Parent Process: wininit.exe
	Number of Instances : One
	User account: Local System
	Start Time: Within seconds of boot time for the first two instances (Session 0 and 1)

## svchost.exe
	Image Path: %SystemRoot%\System32\services.exe
	Parent Process: services.exe
	Number of Instances : Five or more
	User account: Depends of the instance : Local System, Network Service or Local Service accounts
	Start Time: Within seconds of boot time or later for services launched after boot
	Note: On Win7+ all services bin are signed by Microsoft

## lsm.exe
	Image Path: %SystemRoot%\System32\lsm.exe
	Parent Process: wininit.exe
	Number of Instances : One
	User account: Depends of the instance : Local System
	Start Time: Within seconds of boot time
	Note: Handled terminal services including RDP and Fast user switching

## explorer.exe
	Image Path: %SystemRoot%\explorer.exe
	Parent Process: userinit.exe that exists (tools usually don't provide the parent process name)
	Number of Instances : One per logged-on user
	User account: logged-user
	Start Time: Starts when the ownser's interactive session logon begins

## Reference
https://digital-forensics.sans.org/media/Poster_2016_Find_Evil.pdf
