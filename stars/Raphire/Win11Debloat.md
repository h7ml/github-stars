---
project: Win11Debloat
stars: 25326
description: A simple, easy to use PowerShell script to remove pre-installed apps, disable telemetry, as well as perform various other changes to customize, declutter and improve your Windows experience. Win11Debloat works for both Windows 10 and Windows 11.
url: https://github.com/Raphire/Win11Debloat
---

Special thanks to:  
  

### Warp, the intelligent terminal for developers

Available for MacOS, Linux, & Windows  

* * *

Win11Debloat
============

Win11Debloat is a simple, easy to use and lightweight PowerShell script that allows you to quickly declutter and improve your Windows experience. It can remove pre-installed bloatware apps, disable telemetry, remove intrusive interface elements and much more. No need to painstakingly go through all the settings yourself or remove apps one by one. Win11Debloat makes the process quick and easy!

The script also includes many features that system administrators will enjoy. Such as support for Windows Audit mode, the option to make changes to other Windows users and the ability to run the script without requiring user input during runtime. Please refer to our wiki for more details.

#### Did this script help you? Please consider buying me a cup of coffee to support my work

Usage
-----

Warning

Great care went into making sure this script does not unintentionally break any OS functionality, but use at your own risk! If you run into any issues, please report them here.

### Quick method

Download & run the script automatically via PowerShell.

1.  Open PowerShell or Terminal, preferably as an administrator.
2.  Copy and paste the command below into PowerShell:

& (\[scriptblock\]::Create((irm "https://debloat.raphi.re/")))

1.  Wait for the script to automatically download Win11Debloat.
2.  Carefully read through and follow the on-screen instructions.

This method supports command-line parameters to customize the behaviour of the script. Please click here for more information.

### Traditional method

Manually download & run the script.  

1.  Download the latest version of the script, and extract the .ZIP file to your desired location.
2.  Navigate to the Win11Debloat folder
3.  Double click the `Run.bat` file to start the script. NOTE: If the console window immediately closes and nothing happens, try the advanced method below.
4.  Accept the Windows UAC prompt to run the script as administrator, this is required for the script to function.
5.  Carefully read through and follow the on-screen instructions.

### Advanced method

Manually download the script & run the script via PowerShell. Recommended for advanced users.  

1.  Download the latest version of the script, and extract the .ZIP file to your desired location.
2.  Open PowerShell or Terminal as an administrator.
3.  Temporarily enable PowerShell execution by entering the following command:

Set-ExecutionPolicy Unrestricted \-Scope Process \-Force

1.  In PowerShell, navigate to the directory where the files were extracted. Example: `cd c:\Win11Debloat`
2.  Now run the script by entering the following command:

.\\Win11Debloat.ps1

1.  Carefully read through and follow the on-screen instructions.

This method supports command-line parameters to customize the behaviour of the script. Please click here for more information.

Features
--------

Below is an overview of the key features and functionality offered by Win11Debloat. For more information about what features are included in the default mode please refer to this section below.

Tip

All of the changes made by Win11Debloat can easily be reverted and almost all of the apps can be reinstalled through the Microsoft Store. A full guide on how to revert changes can be found here.

#### App Removal

-   Remove a wide variety of preinstalled apps. Click here for more info.
-   Remove or replace all pinned apps from start for the current user, or for all existing & new users. (W11 only)

#### Telemetry, Tracking & Suggested Content

-   Disable telemetry, diagnostic data, activity history, app-launch tracking & targeted ads.
-   Disable tips, tricks, suggestions and ads in start, settings, notifications, File Explorer, and on the lockscreen.
-   Disable ads and the MSN news feed in Microsoft Edge.
-   Disable the 'Windows Spotlight' desktop background option.

#### Bing Web Search, Copilot & AI Features

-   Disable & remove Bing web search, Bing AI and Cortana from Windows search.
-   Disable & remove Microsoft Copilot. (W11 only)
-   Disable Windows Recall snapshots. (W11 only)
-   Disable AI Features in Edge (W11 only)
-   Disable AI Features in Paint (W11 only)
-   Disable AI Features in Notepad (W11 only)

#### Personalisation

-   Enable dark mode for system and apps.
-   Disable transparency, animations and visual effects.
-   Turn off Enhance Pointer Precision, also known as mouse acceleration.
-   Disable the Sticky Keys keyboard shortcut. (W11 only)
-   Restore the old Windows 10 style context menu. (W11 only)
-   Hide the 'Include in library', 'Give access to' and 'Share' options from the context menu. (W10 only)

#### File Explorer

-   Change the default location that File Explorer opens to.
-   Show hidden files, folders and drives.
-   Show file extensions for known file types.
-   Hide the Home or Gallery section from the File Explorer navigation pane. (W11 only)
-   Hide the 3D objects, music or OneDrive folder from the File Explorer navigation pane. (W10 only)
-   Hide duplicate removable drive entries from the File Explorer navigation pane, so only the entry under 'This PC' remains.

#### Taskbar

-   Align taskbar icons to the left. (W11 only)
-   Hide or change the search icon/box on the taskbar. (W11 only)
-   Hide the taskview button from the taskbar. (W11 only)
-   Disable the widgets service & hide icon from the taskbar.
-   Hide the chat (meet now) icon from the taskbar.
-   Enable the 'End Task' option in the taskbar right click menu. (W11 only)
-   Enable the 'Last Active Click' behavior in the taskbar app area. This allows you to repeatedly click on an application's icon in the taskbar to switch focus between the open windows of that application.

#### Start

-   Disable the recommended section in the start menu. (W11 only)
-   Disable the Phone Link mobile devices integration in the start menu. (W11 only)

#### Other

-   Disable Xbox game/screen recording, this also stops gaming overlay popups.
-   Disable Fast Start-up to ensure a full shutdown.
-   Disable network connectivity during Modern Standby to reduce battery drain. (W11 only)
-   Option to apply changes to a different user, instead of the currently logged in user.
-   Sysprep mode to apply changes to the Windows Default user profile. Afterwards, all new users will have the changes automatically applied to them.

### Default Settings

Win11Debloat offers a default mode that allows you to quickly and easily apply the changes that are recommended for most people. This includes uninstalling apps that most would consider bloatware, removing many annoying distractions and disabling telemetry and tracking. To apply the default settings, launch the script as you normally would and select option `1` in the script menu. Alternatively, you can launch the script with the `-RunDefaults` parameter. Example:

& (\[scriptblock\]::Create((irm "https://debloat.raphi.re/"))) \-RunDefaults

#### Changes included in the default mode

-   Remove the default selection of bloatware apps. (See below for full list)
-   Disable telemetry, diagnostic data, activity history, app-launch tracking & targeted ads.
-   Disable tips, tricks, suggestions and ads in start, settings, notifications, File Explorer, and on the lockscreen.
-   Disable ads and the MSN news feed in Microsoft Edge.
-   Disable & remove Bing web search, Bing AI and Cortana from Windows search.
-   Disable & remove Microsoft Copilot. (W11 only)
-   Disable Fast Start-up to ensure a full shutdown.
-   Disable network connectivity during Modern Standby to reduce battery drain. (W11 only)
-   Show file extensions for known file types.
-   Hide the 3D objects folder under 'This pc' from File Explorer. (W10 only)
-   Disable the widget service & hide the icon from the taskbar.
-   Hide the Chat (meet now) icon from the taskbar.

#### Apps that ARE removed as part of the default mode

Click to expand

> ```
> Microsoft bloat:
> - Clipchamp.Clipchamp  
> - Microsoft.3DBuilder  
> - Microsoft.549981C3F5F10 (Cortana app)
> - Microsoft.BingFinance  
> - Microsoft.BingFoodAndDrink 
> - Microsoft.BingHealthAndFitness
> - Microsoft.BingNews  
> - Microsoft.BingSearch* (Bing web search in Windows)
> - Microsoft.BingSports  
> - Microsoft.BingTranslator  
> - Microsoft.BingTravel   
> - Microsoft.BingWeather  
> - Microsoft.Copilot
> - Microsoft.Getstarted (Cannot be uninstalled in Windows 11)
> - Microsoft.Messaging  
> - Microsoft.Microsoft3DViewer  
> - Microsoft.MicrosoftJournal
> - Microsoft.MicrosoftOfficeHub  
> - Microsoft.MicrosoftPowerBIForWindows  
> - Microsoft.MicrosoftSolitaireCollection  
> - Microsoft.MicrosoftStickyNotes  
> - Microsoft.MixedReality.Portal  
> - Microsoft.NetworkSpeedTest  
> - Microsoft.News  
> - Microsoft.Office.OneNote (Discontinued UWP version only, does not remove new MS365 versions)
> - Microsoft.Office.Sway  
> - Microsoft.OneConnect  
> - Microsoft.Print3D  
> - Microsoft.SkypeApp  
> - Microsoft.Todos  
> - Microsoft.WindowsAlarms  
> - Microsoft.WindowsFeedbackHub  
> - Microsoft.WindowsMaps  
> - Microsoft.WindowsSoundRecorder  
> - Microsoft.XboxApp (Old Xbox Console Companion App, no longer supported)
> - Microsoft.ZuneVideo  
> - MicrosoftCorporationII.MicrosoftFamily (Microsoft Family Safety)
> - MicrosoftTeams (Old personal version of MS Teams from the MS Store)
> - MSTeams (New MS Teams app)
> 
> Third party bloat:
> - ACGMediaPlayer  
> - ActiproSoftwareLLC  
> - AdobeSystemsIncorporated.AdobePhotoshopExpress  
> - Amazon.com.Amazon  
> - AmazonVideo.PrimeVideo
> - Asphalt8Airborne   
> - AutodeskSketchBook  
> - CaesarsSlotsFreeCasino  
> - COOKINGFEVER  
> - CyberLinkMediaSuiteEssentials  
> - DisneyMagicKingdoms  
> - Disney 
> - Dolby  
> - DrawboardPDF  
> - Duolingo-LearnLanguagesforFree  
> - EclipseManager  
> - Facebook  
> - FarmVille2CountryEscape  
> - fitbit  
> - Flipboard  
> - HiddenCity  
> - HULULLC.HULUPLUS  
> - iHeartRadio  
> - Instagram
> - king.com.BubbleWitch3Saga  
> - king.com.CandyCrushSaga  
> - king.com.CandyCrushSodaSaga  
> - LinkedInforWindows  
> - MarchofEmpires  
> - Netflix  
> - NYTCrossword  
> - OneCalendar  
> - PandoraMediaInc  
> - PhototasticCollage  
> - PicsArt-PhotoStudio  
> - Plex  
> - PolarrPhotoEditorAcademicEdition  
> - Royal Revolt  
> - Shazam  
> - Sidia.LiveWallpaper  
> - SlingTV  
> - Speed Test  
> - Spotify  
> - TikTok
> - TuneInRadio  
> - Twitter  
> - Viber  
> - WinZipUniversal  
> - Wunderlist  
> - XING
> 
> * App is removed when disabling Bing in Windows search.
> ```

#### Apps that are NOT removed as part of the default mode

Click to expand

> ```
> General apps that are not removed by default:
> - Microsoft.Edge (Edge browser, only removeable in the EEA)
> - Microsoft.GetHelp (Required for some Windows 11 Troubleshooters)
> - Microsoft.MSPaint (Paint 3D)
> - Microsoft.OutlookForWindows* (New mail app)
> - Microsoft.OneDrive (OneDrive consumer)
> - Microsoft.Paint (Classic Paint)
> - Microsoft.People* (Required for & included with Mail & Calendar)
> - Microsoft.ScreenSketch (Snipping Tool)
> - Microsoft.Whiteboard (Only preinstalled on devices with touchscreen and/or pen support)
> - Microsoft.Windows.Photos
> - Microsoft.WindowsCalculator
> - Microsoft.WindowsCamera
> - Microsoft.WindowsNotepad
> - Microsoft.windowscommunicationsapps* (Mail & Calendar)
> - Microsoft.WindowsStore (Microsoft Store, NOTE: This app cannot be reinstalled!)
> - Microsoft.WindowsTerminal (New default terminal app in Windows 11)
> - Microsoft.YourPhone (Phone Link)
> - Microsoft.Xbox.TCUI (UI framework, removing this may break MS store, photos and certain games)
> - Microsoft.ZuneMusic (Modern Media Player)
> - MicrosoftWindows.CrossDevice (Phone integration within File Explorer, Camera and more)
> 
> HP apps that are not removed by default:
> - AD2F1837.HPAIExperienceCenter*
> - AD2F1837.HPConnectedMusic*
> - AD2F1837.HPConnectedPhotopoweredbySnapfish*
> - AD2F1837.HPDesktopSupportUtilities*
> - AD2F1837.HPEasyClean*
> - AD2F1837.HPFileViewer*
> - AD2F1837.HPJumpStarts*
> - AD2F1837.HPPCHardwareDiagnosticsWindows*
> - AD2F1837.HPPowerManager*
> - AD2F1837.HPPrinterControl*
> - AD2F1837.HPPrivacySettings*
> - AD2F1837.HPQuickDrop*
> - AD2F1837.HPQuickTouch*
> - AD2F1837.HPRegistration*
> - AD2F1837.HPSupportAssistant*
> - AD2F1837.HPSureShieldAI*
> - AD2F1837.HPSystemInformation*
> - AD2F1837.HPWelcome*
> - AD2F1837.HPWorkWell*
> - AD2F1837.myHP*
> 
> Gaming related apps that are not removed by default:
> - Microsoft.GamingApp* (Modern Xbox Gaming App, required for installing some games)
> - Microsoft.XboxGameOverlay* (Game overlay, required for some games)
> - Microsoft.XboxGamingOverlay* (Game overlay, required for some games)
> - Microsoft.XboxIdentityProvider (Xbox sign-in framework, required for some games)
> - Microsoft.XboxSpeechToTextOverlay (Might be required for some games, NOTE: This app cannot be reinstalled!)
> 
> Developer related apps that are not removed by default:
> - Microsoft.PowerAutomateDesktop*
> - Microsoft.RemoteDesktop*
> - Windows.DevHome*
> 
> * Can be removed by running the script with the relevant parameter. (Please refer to the wiki for more details)
> ```

License
-------

Win11Debloat is licensed under the MIT license. See the LICENSE file for more information.
