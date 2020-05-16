# Principia fails to start (PC)
If Principia crashes during the loading screen, please try the steps on this page before you contact an admin or make a bug report.

Before continuing, **make sure you have the latest drivers for your graphics card**.

## Locating settings.ini
To edit principia settings, you need to locate the settings.ini file. For Windows Vista and later, you can find it by navigating to:

`C:\Users\username\Principia\settings.ini`

Where "username" is your username.

For Windows XP, navigate to:

`C:\Documents and settings\username\Principia\settings.ini`

Where "username" is your username.

Open settings.ini in any text editor.

## Lower shadow precision
The default shadow precision on PC might not work on older PC's, you can lower the shadow precision by locating settings.ini and find that line that says

`shadow_precision=1`

Change to

`shadow_precision=0`

## Activate "shitty computer" mode
In settings.ini, locate the following line:

`is_very_shitty=0`

Change to

`is_very_shitty=1`

## If nothing works
Immediately after the crash, in the same directory as settings.ini you will find a file called "run.log". Contact an admin detailing your problem and provide the run.log file.

See also [Bug Reporting](Bug_Reporting).