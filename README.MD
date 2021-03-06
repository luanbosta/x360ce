"Xbox 360 Controller Emulator" allows your controller (gamepad, joystick, wheel, ...), function as "Xbox 360 Controller". For example, lets you play games such as "Grand Theft Auto" (GTA) or "Mafia II" using Logitech Wheel.

# Download

Digitally Signed Application v3.2.8.76 (2015-08-28) and Libraries 3.4.1.1357 (2015-08-27)

[32-bit Download](http://www.x360ce.com/Files/x360ce.zip) - for 32-bit games

[64-bit Download](http://www.x360ce.com/Files/x360ce_x64.zip) - for 64-bit games 

# Reporting Issues

Report only crashes or other bugs, note that issue tracker is not helpdesk! 

**DO NOT ASK FOR HELP IN INSTALLATION OR CONFIGURATION!!!**

**If your have questions about installation or configuration, please go to our [forum @NGemu] (http://ngemu.com/forums/x360ce.140)**

# Guides [OUTDATED!]

[x360ce Libraries Tutorial](http://ngemu.com/threads/x360ce-libraries-tutorial-by-resolutespider5.155310/)

[x360ce App Tutorial](http://ngemu.com/threads/tutorial-by-resolutespider5.155011/)

[Various x360ce Guides](http://ngemu.com/threads/various-x360ce-guides-by-resolutespider5.156807/)

# Compatibility
Games that work with x360ce can be found on the [Compatibility List](Wiki/CompatibilityList.md). If you would like to add to that list or provide updated information place see [Reporting Compatibility](Wiki/ReportingCompatibility.md).

# System Requirements

  1. Windows Vista or newer.
  1. [.NET 3.5 (also installs 2.0 and 3.0)](http://www.microsoft.com/en-us/download/details.aspx?id=21) (included in Windows 7)
  1. [.NET 4.0 (link to 4.5, also installs 4.0)](http://www.microsoft.com/en-us/download/details.aspx?id=30653) (included in Windows 8 and 10)
  1. [DirectX End-User Runtime (June 2010)](http://www.microsoft.com/en-us/download/details.aspx?id=35) (Required regardless of OS)
  1. [Visual C++ Redistributable for Visual Studio 2013](http://www.microsoft.com/en-us/download/details.aspx?id=40784) (For x64 systems install both x86 and x64 redistributable)
  1. If you upgraded to Windows 10, you must Uninstall and Reinstall the Visual C++ Redistributable

Notes:
  * Most games executables are 32bit and require x86 x360ce and also x86 redistributable.
  * Windows 7 includes .NET 3.5 (which include 3.0 and 2.0).
  * For Vista, users can obtain it from the above link, and Windows 8 users can enable it in [Programs and Features - Turn Windows Features on and off.](http://msdn.microsoft.com/en-us/library/hh506443.aspx)
  * **.NET MUST be installed prior to the DirectX webupdate as it checks that .NET 2.0/3.0/3.5 is installed and skips the Managed DirectX framework if it is not.**
  * The full DirectX Redistributable will always install the file, however its best to have .NET 3.5 installed anyhow as quite a few Xinput titles utilize .NET for internal dependencies.

# Files

xinput1\_3.dll (Wrapper Library) - Translates XInput calls to DirectInput calls - supports old, no XInput compatible GamePads.<br />
x360ce.exe - (Application) - Allows edit and test Library settings.<br />
x360ce.ini - (Configuration) - Contain Library settings (button, axis, slider maps).<br />
x360ce.gdb - (Game Database) Includes required hookmasks for various games).<br />
Dinput8.dll - (DirectInput 8 spoof/wrapping file to improve x360ce compatibility in rare cases).

# Installation

Run this program from the same directory as the game executable. Xinput library files exist with several different names and some games require a change in its name. Known names:

  * xinput1\_4.dll (Windows 8 / metro apps only)
  * xinput1\_3.dll
  * xinput1\_2.dll
  * xinput1\_1.dll
  * xinput9\_1\_0.dll

Game Database (GDB) and Configuration (Ini) files can be copied to %Allusersprofile%\X360CE on NT6 (Vista/7/8) or %Allusersprofile%\Application Data\X360CE on NT5.1 (XP), Or left in the same directory as the game executable (.EXE)

Note:
  * Games based on source engine in most cases have the dll placed inside the /Bin/ subfolder, as it it is loaded by inputsystem.dll instead of the game executable.
  * The DLL is not currently fully supported by the App, recent versions incorporate HookMasks and fully remove HookModes, and requires placing Version=1 under [options] in the x360ce.ini to quieten a incorrect version warning

# Uninstallation

Delete x360ce.exe, x360ce.ini and all xinput dll from game executable directory.

# Troubleshooting

Some games have control issues, when Dead Zone is reduced to 0%.

**Wheel doesn't work in the game, but it works inside x360ce Application.**

Some controllers will operate in game only, if set as "GamePad". Try to:

  1. Run x360ce.exe
  1. Select tab with your Wheel Controller.
  1. Open [Advanced] tab page.
  1. Set "Device Type" drop down list value to: GamePad
  1. Click [Save] button.
  1. Close x360ce Application, run game.
 
Only one controller may work correctly in some games. If you have more than one controller, connected to your PC, you must set it as PAD1 (other controllers must be set as PAD2, PAD3 or PAD4). You can map Direct Input Device to PAD1 by setting "Map To:" Drop Down list value to "1" on Direct Input Device page which is visible when controller is connected.

**Do I need to run x360ce Application during the game?**

x360ce.exe application can be closed during the game - game doesn't need it and it uses computer resources. It is just a GUI for editing x360ce.ini and test controller. 

**Warning - Configuration file version does not match x360ce version.**

This occurs because the current version of the application is not completely compatible with the DLL just yet.
You can resolve this by adding Version=1 under the [Options] section in x360ce.ini

**Controller tab won't turn green / Red light on Controller 1,2 etc.**

This can occur for a number of reasons.

  1. The configuration utility DOES NOT work with the 64bit library, it will only work with the 32bit version, This is the case regardless of whether your windows is 32bit or 64bit.
  1. The DInput state of the control might be incorrect due to previous application crashing and not unloading the control or some other reason. Opening up Joy.cpl (Set Up USB Game Controllers) and clicking the Advanced button, and then Okaying out of the window that appears can fix it.
  1. The controller profile loaded may match the name of the control but not actually be for the controller you own - in this case you might see button numbers or axes mapped that do not appear in the joy.cpl test page.
  1. The controller profile might have PassThrough set. A growing number of profiles have been uploaded that do this, i have no idea why as it disables x360ce and just bloats the list of available profiles.
  1. There just might not be a profile for your control at all - The light should turn green once at least the 2 sticks, triggers and DPad are assigned. Sometimes the application needs to be restarted after assigning these for the light to turn green.

# Screenshots

![http://www.jocys.com/projects/x360ce/Images/x360ce_General.png](http://www.jocys.com/projects/x360ce/Images/x360ce_General.png)
