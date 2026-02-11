# File-Browser-Episode-Renamer
File Browser Episode Renamer - Renames your media files located on cloud with S01E01 information.

A Windows desktop tool for remotely renaming files stored on a seedbox or server running File Browser. Renames files in bulk using TV episode codes in the format S01E01.FileName.ext — directly on the server, no downloading required.

Features

Connects to your remote File Browser instance over HTTPS
Browse folders on the server with a clickable folder navigator
Bulk rename files with automatic S01E01 style episode codes
Auto-rolls to the next season (e.g. after E20 → S02E01)
Strips existing episode codes from filenames before renaming
Removes spaces and dashes from filenames — clean output only
Preview all renames before applying any changes
No installation required — runs on any Windows PC


Requirements

Windows 7 or later
No installation, no Python, no dependencies
The .hta file format is built into Windows


Getting Started
1. Download
Download FileBrowserRenamer.hta and double-click it. Windows will open it as a desktop application automatically.

If Windows shows a SmartScreen warning, click More info then Run anyway.


2. Enter Your File Browser URL
In the File Browser URL field, enter the base URL of your File Browser instance.
https://yourname.yourserver.com/filebrowser

Do not include /files or a trailing slash at the end.


3. Login
Enter your username and password and click Login.
On success you will see Logged in as: yourname in green and the /media folder will load automatically.
If login fails, the error box will show the exact reason:
ErrorCauseCannot reach serverURL is wrong or unreachableHTTP 401 / 403Wrong username or passwordHTTP 404URL path is incorrect

4. Browse to Your Folder
After logging in, your folders appear as clickable buttons. Click any folder to open it.

Use [ Up one level ] to go back up
The breadcrumb bar at the top shows your current path and lets you click any part to jump back


5. Set Episode Options
SettingDescriptionStarting SeasonThe season number to start from (e.g. 1 for S01)Starting EpisodeThe episode number to start from (e.g. 1 for E01)Episodes per SeasonAfter this many episodes, the season rolls over automatically
Example: Starting Season 1, Starting Episode 1, Episodes per Season 20 will produce:
S01E01, S01E02, ... S01E20, S02E01, S02E02, ...

6. Filter by Extension (Optional)
Check Filter by extension and enter the file types you want to rename, e.g.:
.mkv .mp4 .avi
Leave unchecked to show all files in the folder.

7. Preview
Click Preview Rename to see exactly what every file will be renamed to before anything changes.

8. Rename
Click Rename on Server to apply the renames. Files are renamed directly on the server — nothing is downloaded.

Output Format
S01E01.OriginalFilename.mkv

Any existing S##E## codes are stripped from the original filename
All spaces are removed
All dashes are removed
Commas are kept
A period separates the episode code from the filename

Example:
BeforeAfterShow Name - S02E05 - Episode Title.mkvS01E01.ShowNameEpisodeTitle.mkvmy.show.s01e03.hdtv.mkvS01E01.my.show.hdtv.mkv

Notes

The tool locks navigation to /media and below — you cannot browse above this folder
Renames are permanent on the server — always use Preview first
The app uses WinHttp.WinHttpRequest.5.1 for HTTPS connections, with SSL certificate errors suppressed (common on seedboxes)


License
MIT — free to use, modify, and distribute.
