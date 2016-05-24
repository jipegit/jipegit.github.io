---
layout: default
permalink: /windows-artifacts
---

# Windows Artifacts 

## File Download

### Open/Save MRU

#### Description

In the simplest terms, this key tracks files that have been opened or saved within a Windows shell dialog box. This happens to be a big data set, not only including web browsers like Internet Explorer and Firefox, but also a majority of commonly used applications.

#### Location

* XP NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\OpenSaveMRU
* Win7/8/10 NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\OpenSavePIDlMRU

#### Interpretation

* The “*” key – This subkey tracks the most recent files of any extension input in an OpenSave dialog
* .??? (Three letter extension) – This subkey stores file info from the OpenSave dialog by specific extension

### E-mail Attachments

#### Description

The e-mail industry estimates that 80% of e-mail data is stored via attachments. Email standards only allow
text. Attachments must be encoded with MIME/ base64 format.

#### Location

###### Outlook

* XP %USERPROFILE%\Local Settings\ApplicationData\Microsoft\Outlook
* Win7/8/10 %USERPROFILE%\AppData\Local\Microsoft\Outlook

#### Interpretation

MS Outlook data files found in these locations include OST and PST  files. One should also check the OLK and Content.Outlook folder, which might roam depending on the specific version of Outlook used. For more information on where to find the OLK folder this link has a handy chart: <http://www.hancockcomputertech.com/blog/2010/01/06/find-the-microsoft-outlook-temporary-olk-folder>

### Skype History

#### Description

* Skype history keeps a log of chat sessions and  les transferred from one machine to another
* This is turned on by default in Skype installations

#### Location

* XP C:\Documents and Settings\<username>\Application\Skype\<skype-name>
* Win7/8/10 C:\%USERPROFILE%\AppData\Roaming\Skype\<skype-name>

#### Interpretation

Each entry will have a date/time value and a Skype username associated with the action.

### Browser Artifacts

#### Description

Not directly related to “File Download”. Details stored for each local user account. Records number of times visited (frequency).

#### Location

##### Internet Explorer

* IE8-9 %USERPROFILE%\AppData\Roaming\Microsoft\Windows\IEDownloadHistory\index.dat
* IE10-11 %USERPROFILE%\AppData\Local\Microsoft\Windows\WebCache\WebCacheV*.dat

##### Firefox

* v3-25 %userprofile%\AppData\Roaming\Mozilla\Firefox\Profiles\<random text>.default\downloads.sqlite
* v26+ %userprofile%\AppData\Roaming\Mozilla\Firefox\Profiles\<random text>.default\places.sqlite
Table:moz_annos

##### Chrome

* Win7/8/10 %USERPROFILE%\AppData\Local\Google\Chrome\UserData\Default\History

#### Interpretation

Many sites in history will list the  les that were opened from remote sites and downloaded to the local system. History will record the access to the  le on the website that was accessed via a link.

### Downloads

Firefox and IE has a built-in download manager application which keeps a history of every file downloaded by the user. This browser artifact can provide excellent information about what sites a user has been visiting and what kinds of files they have been downloading from them.

#### Location

##### Firefox

* XP %userprofile%\Application Data\Mozilla\Firefox\Profiles\<random text>.default\downloads.sqlite
* Win7/8/10 %userprofile%\AppData\Roaming\Mozilla\Firefox\Profiles\<random text>.default\downloads.sqlite

##### Internet Explorer

* IE8-9 %USERPROFILE%\AppData\Roaming\Microsoft\Windows\IEDownloadHistory\
* IE10-11 %USERPROFILE%\AppData\Local\Microsoft\Windows\WebCache\WebCacheV*.dat

#### Interpretation

Downloads will include:
* Filename, Size, and Type
* File Save Location
* Download from and Referring Page
* Application Used to Open File
* Download Start and EndTimes

### ADS Zone.Identifer

#### Description

Starting with XP SP2 when files are downloaded from the “Internet Zone” via a browser to a NTFS volume, an alternate data stream is added to the file. The alternate data stream is named “Zone. Identifier.”

#### Interpretation

Files with an ADS Zone.Identi er and contains ZoneID=3 were downloaded from the Internet
* URLZONE_TRUSTED = ZoneID = 2
* URLZONE_INTERNET = ZoneID = 3 
* URLZONE_UNTRUSTED = ZoneID = 4

## Program Execution

### UserAssist

#### Description

GUI-based programs launched from the desktop are tracked in the launcher on a Windows System.

#### Location

NTUSER.DAT HIVE
NTUSER.DAT\Software\Microsoft\Windows\Currentversion\Explorer\UserAssist\{GUID}\Count

#### Interpretation
All values are ROT-13 Encoded 
* GUID for XP
	*  75048700 Active Desktop 

* GUID for Win7/8/10
	* CEBFF5CD Executable File Execution
	* F4E57C4B Shortcut File Execution

* Program Locations for Win7 Userassist
	* ProgramFilesX64 6D809377-... 
	* ProgramFilesX86 7C5A40EF-...
	* System 1AC14E77-...
	* SystemX86 D65231B0-...
	* Desktop B4BFCC3A-...
	* Documents FDD39AD0-...
	* Downloads 374DE290-...
	* UserProfiles 0762D272-...

### Last-Visited MRU

#### Description

Tracks the specific executable used by an application to open the files documented in the OpenSaveMRU key. In addition, each value also tracks the directory location for the last file that was accessed by that application.

Example:

Notepad.exe was last run using the C:\%USERPROFILE%\Desktop folder

#### Location

* XP NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\LastVisitedMRU
* Win7/8/10 NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\LastVisitedPidlMRU

#### Interpretation

Tracks the application executables used to open files in OpenSaveMRU and the last file path used.

### RunMRU Start->Run
#### Description
Whenever someone does a Start -> Run command,it will log the entry for the command they executed.

#### Location

NTUSER.DAT HIVE
NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\RunMRU

#### Interpretation

The order in which the commands are executed is listed in the RunMRU list value. The letters represent the order in which the commands were executed.

### AppCompatCache

#### Description

* Windows Application Compatibility Database is used by Windows to identify possible application compatibility challenges with executables.
* Tracks the executables file name, file size, last modified time, and in Windows XP the last update time

#### Location

* XP SYSTEM\CurrentControlSet\Control\SessionManager\AppCompatibility
* Win7/8/10 SYSTEM\CurrentControlSet\Control\Session Manager\AppCompatCache

#### Interpretation

Any executable run on the Windows system could be found in this key. You can use this key to identify systems that specific malware was executed on.

In addition, based on the interpretation of the time-based data you might be able to determine the last time of execution or activity on the system.

* Windows XP contains at most 96 entries
	* LastUpdateTime is updated when the  les are executed
* Windows 7 contains at most 1024 entries
	*  LastUpdateTime does not exist on Win7 systems

### Jump Lists

#### Description
* The Windows 7 task bar (Jump List) is engineered to allow users to “jump” or access items they have frequently or recently used quickly and easily. This functionality cannot only include recent media files; it must also include recent tasks.
* The data stored in the Automatic Destinations folder will each have a unique file prepended with the AppID of the associated application.

#### Location
* Win7/8/10 C:\%USERPROFILE%\AppData\Roaming\Microsoft\Windows\Recent\AutomaticDestinations

#### Interpretation
* First time of execution of application.
	* Creation Time = First time item added to the AppID file.
* Last time of execution of application w/ file open. - Modification Time = Last time item added to
the AppID file.
* List of Jump List IDs -> <http://www.forensicswiki.org/wiki/List_of_ Jump_List_IDs>

### Prefetch

#### Description

Increases performance of a system by pre-loading code pages of commonly used applications. Cache Manager monitors all files and directories referenced for each application or process and maps them into a .pf file. Utilized to know an application was executed on a system.

* Limited to 128 files on XP and Win7 
* Limited to 1024 files on Win8
* (exename)-(hash).pf

#### Location
* WinXP/7/8/10 C:\Windows\Prefetch

#### Interpretation
* Each .pf will include last time of execution, number of times run, and device and file handles used by the program
* Date/Time file by that name and path was first executed
	* Creation Date of .pf file (-10 seconds)
* Date/Time file by that name and path was last executed
	* Embedded last execution time of .pf file
	* Last modification date of .pf file (-10 seconds)
	* Win8+ will contain last 8 times of execution

### Amacache.hve/RecentFileCache.bcf

#### Description

ProgramDataUpdater (a task associated with the Application Experience Service) uses the registry file RecentFilecache.bcf to store data during process creation

#### Location

* Win7/8/10 C:\Windows\AppCompat\Programs\Amcache.hve (Windows 7/8/8.1)
* Win7 C:\Windows\AppCompat\Programs\RecentFilecache.bcf

#### Interpretation
* RecentFileCache.bcf – Executable PATH and FILENAME and the program is probably new to the system
* The program executed on the system since the last ProgramDataUpdated task has been run
* Amcache.hve – Keys = Amcache.hve\Root\File\{Volume GUID}\#######
* Entry for every executable run, full path information, File’s $StandardInfo Last Modification Time, and Disk volume the executable was run from
* First Run Time = Last Modi cation Time of Key
* SHA1 hash of executable also contained in the key

# Source
https://digital-forensics.sans.org/media/poster-windows-forensics-2016.pdf
