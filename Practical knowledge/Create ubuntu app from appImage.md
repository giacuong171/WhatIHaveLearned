---
URL: https://dev.to/msamgan/how-to-add-appimage-application-to-menu-in-ubuntu-linux-8o2/
---
## Step to use AppImage

1. Download the AppImage
2. Make the AppImage executable. (sudo chmod +x *.AppImage)
3. Run the file (./*.AppImage)

The challenging task is to make the **AppImage accessible globally through he system like an installed application** (in the menu)

you can achieve this by the going through the following steps.

## Steps to add AppImage to Menu

1. Move he AppImage to an accessible directory (I personally use .appImage in my home directory but you are free to be creative)
2. Create a **appName.desktop file in ~/.local/share/applications**
3. Add the following content to the .desktop file you create

```
[Desktop Entry]
Version=0.13.23
Type=Application
Name=appName
Comment=Application Description
TryExec=Path/to/AppImage
Exec=Path/to/AppImage
Icon=Path/to/AppImage.icon
Actions=Editor
```

and we are done.

Now you AppImage is available for you user in menu.

## Bonus tip

If you want this AppImage to be accessible to to all the user of the system, place the .desktop file in  
**/usr/share/applications**