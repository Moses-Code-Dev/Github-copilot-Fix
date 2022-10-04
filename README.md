# Github-copilot-Fix
Github copilot solution (workaround) for "Failed to initiate the GitHub login process. Please try again.".

Explanation:
* After some research, it seems that the problem is related to the version of the Node js installed in the operating system.

* Node Js stops supporting Windows 7 since January 14, 2020, and the Copilot plugin is probably using the latest version of it with some Os Api calls, 
that's are not supported in early OS versions like Windows 7 .

* Method 01:
Tested on IntelliJ IDEA Community Edition 2022.1 and Android Studio Dolphin. 

1- Update your github-copilot to the latest version (1.1.32.1956) then close the IDE

2- Download this version of github-copilot (1.1.28.1744):
   https://plugins.jetbrains.com/plugin/download?rel=true&updateId=190492 and Extract it

3- Navigate to ...\github-copilot-intellij-1.1.28.1744\github-copilot-intellij\lib

4- copy this two file:
   
   * applicationinsights-core-2.6.4
   * core-1.1.28
   
5- Navigate to

   * For IntelliJ IDEA
...\AppData\Roaming\JetBrains\IdeaIC2022.1\plugins\github-copilot-intellij\lib

   * For AndroidStudio
...\AppData\Roaming\Google\AndroidStudio2021.2\plugins\github-copilot-intellij\lib

6- Paste them here and replace the existing "core-x.x.x"

7- using 7-zip or your preferred one,

    - Right click on "core-1.1.28" in the same folder
    - Open archive 
    - Navigate to "com\github\copilot\lang\agent\" 
    - Replace CopilotAgent.class with above file

  That's is all, copilot should work now.
  
  
  
* Method 02:

 Tested on IntelliJ IDEA Community Edition 2022.1 and Android Studio Dolphin. 
 Not tested after Subscription.
 
 
1- Update your github-copilot to the latest version (1.1.27.1708) then close the IDE

2- Go to System-Properties (run: systempropertiesadvanced.exe), in Advanced tab, click Environment Variables.

3- Still on the System variables, click 'New' add "NODE_SKIP_PLATFORM_CHECK" with value "1", and click OK.

4- Click OK of all dialogs close.

5- Restart your machine, so explore and cmd will get the fresh set of variables.

6 "Failed to initiate the GitHub login process." message will disappear, but this method will throw new errors in some Operating systems.


** For new Os versions, if this two methods does not work for you, 
try to update your Node Js to the latest version, 
and make sure that the default environment path is setup correctly.
