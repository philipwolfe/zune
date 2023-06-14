# zune
Zune related info
## How to fix error code: C00D11CD (80004002) Can't Sync. An unknown error occurred.
```
This happens when trying to sync a video from your Zune Software to your Zune HD.
The issue is with the version of wmvcore.dll in your system32 folder.
The version I had was 12.0.190412364
The version I got to work is 12.0.10586.0
```

1. First, close your Zune software.
1. I followed this post: https://answers.microsoft.com/en-us/windows/forum/all/wmvcoredll-is-missing/5ba703c8-cd12-4f0c-8f12-8030753dcc20
1. And I took his advice to download update 3010081 at https://www.microsoft.com/en-us/download/details.aspx?id=49919 
1. The key here is to get the dll version from Windows 10 build 1511 before the anniversary update.
1. After downloading KB3099229_x64.msu, rename it to KB3099229_x64.cab to view the files.
1. Extract microsoft-windows-mediafeaturepack-oob-package.cab and open it.
1. Change your windows explorer view to details.
1. Browse for wmvcore.dll and check on the folder structure column on the right.
1. Extract the wmvcore.dll file in the amd64_... folder and not the x86_... one.
1. Go to your c:\windows\system32 folder
1. Find wmvcore.cll and change the security so you have full control and are the owner.
1. Back up that file to somewhere in case you need to recover it, then delete it.
1. Copy in the new file that you extracted from the .cab
1. Verify the new version.
1. Start Zune and transfer a video.

Inspiration from: https://github.com/zunes/tutorial/blob/main/zune-error-c00d11cd-syncing-fix.html
