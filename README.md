# mini11 (is a modified tiny11)
## Credits and thanks for [NTDEV](https://github.com/ntdevlabs) for creating this beautiful project.

---

### Status

> <white> Status : <green> Working </green><br>
> Version: <green> 1.0.0.0 </green>

---

### Description
Scripts to build a trimmed-down Windows 11 image.

This is a script to automate the build of a streamlined Windows 11 image, similar to mini11.
My main goal is to use only Microsoft utilities like DISM, and nothing external. The only executable included is oscdimg.exe, which is provided in the Windows ADK and it is used to create bootable ISO images. Also included is an unattended answer file, which is used to bypass the MS account on OOBE and to deploy the image with the /compact flag.
It's open-source, so feel free to add or remove anything you want! Feedback is also much appreciated.

As of now, only build 22621.1702 (the one that can be downloaded from the Microsoft website), 22621.1992 (the latest public build) and 25905 (latest Insider build as of now) are supported.

### Instruction (How to run):

1. Download Windows 11 22621.1702 from [Microsoft website](https://www.microsoft.com/software-download/windows11) (I suggest to download Disk Image ISO multi-edition to have more selection for SKU/Index).

2. Mount the downloaded ISO image using Windows Explorer.

3. For .1702, .1992 or 25905 use the aptly-named script and run it as administrator.

4. Select the drive letter where the image is mounted (only the letter).

Example for #4:

```
Please enter the drive letter for the Windows 11 image: d
```


5. Select the SKU/Index that you want the image to be based.

6. Sit back and relax :)

- Hint: If you faced any error go scroll down and you'll find the error page. (Error 2 is just null, at build 1702 you will encounter it when removing Microsoft Teams and Family)

7. When the image is completed, you will see it in the folder where the script was extracted, with the name mini11.iso

### Burning in USB

1. Download [Rufus (Portable)](https://rufus.ie/en/)

2. Search in youtube "Rufus usb windows boot" it's because it's too hard to explain

### Fresh Windows

- You can also search in youtube. or Take this steps

1. Make sure the usb is inserted, restart your pc and hold Del or F2 when the logo shows up.

2. Go to boot tab and change the boot #1 to USB and find and click save change & reboot

3. Now it will install windows

4. Sit back relax and you're done.

---

### Removed Apps

```markdown
# What's app is removed:
Clipchamp,
News,
Weather,
Xbox (although Xbox Identity provider is still here, so it should be possible to be reinstalled with no issues),
GetHelp,
GetStarted,
Office Hub,
Solitaire,
PeopleApp,
PowerAutomate,
ToDo,
Alarms,
Mail and Calendar,
Feedback Hub,
Maps,
Sound Recorder,
Your Phone,
Media Player,
QuickAssist,
Internet Explorer,
LA57 support,
OCR for en-us,
Speech support,
TTS for en-us,
Media Player Legacy,
Tablet PC Math,
Wallpapers,
Edge,
OneDrive
``````

---

### Issues

Known issues:

1. Microsoft Teams (personal) and Cortana are still here. If you find a way to remove them before I find one, feel free to help!

2. Although Edge is removed, the icon and a ghost of its taskbar pin are still available. Also, there are some remnants in the Settings. But the app in itself is deleted.

3. The script is rather inflexible, as in only the builds specified can be modified. This is because with each new build Microsoft also updates the inbox apps included. If one tries to use other builds, it will work with varying degrees of success, but some things like the removal of Edge and OneDrive as well as bypassing system requirements or other patches will always be applied.

4. Only en-us x64 is supported as of now. This can be easily fixable by the end user, just by replacing every instance of en-us with the language needed (like ro-RO and so on), and every x64 instance with arm64.

---

### Errors

Here's the meaning of some errors you saw when the builder is wrong/outdated:

- Error 2 - Error 2 appears when the builder didn't found the app.

- Error 87 - Error 87 appears when the builder has an incomplete packagename/version code.

- Error 1?? - Error 1??(100 something) appears when image needs an image remount, You can fix this by running the mini11fixer.bat as administration.

- Error ? - Error ? (I think I saw number 4) appears when scratchdir image is corrupted, You can also fix this by running the mini11fixer.bat as administration.

That's the error I've faced, If you found an error you're free to create an Issue!

---

And that's pretty much it for now!<br>
Thanks for trying it and let me know how you like it!
