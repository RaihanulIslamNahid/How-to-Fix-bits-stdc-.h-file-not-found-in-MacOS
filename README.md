# How-to-Fix-bits-stdc-.h-file-not-found-in-MacOS
• Install the Xcode app from App Store
• Go to the path = /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/include/c++/v1 To do this easily, open Finder and press Cmd+Shift+G and paste this path address and it should open up.
• Create a folder named bits and go to this folder.
• Create a file named stdc++.h inside the bits folder and open it using any text editor (e.g. TextEdit)
• Paste the content from this repo to the stdc++.h file: https://github.com/gcc-mirror/gcc/blob/master/libstdc%2B%2B-v3/include/precompiled/stdc%2B%2B.h
• Now close Sublime Text/VS Code and reopen it and run a C++ file.
• It should work!
If it doesn’t work:
• Try the same thing using path = /Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX.sdk/usr/include/
• It should work now, but it might give you different errors like include<cstdalign> is not found or smth similar. Just remove this include from the stdc++.h file and try again.
• You might need to remove multiple includes and it should work eventually(at least it worked for me!). In my case, I had to remove the following lines from stdc++.h:

    ◦ include<cstdalign>
    ◦ include<cuchar>
    ◦ include<memory_resources>
If it still doesn’t work, try withpath = /usr/local/include
