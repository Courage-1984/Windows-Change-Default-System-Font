# Windows-Change-Default-System-Font
How to ACTUALLY Change the Windows Default System Font!

> *By default, Windows uses the Segoe UI font. To change it, Segoe UI needs to be disabled in the registry, and a fallback font needs to be set, which will be used instead.*

# Steps:

Firstly we will backup the `.reg` keys of your default installed system font (which is most likely 'Segoe UI').
1. Open your <b>Registry Editor</b> and navigate to & make backups of the following 2:
  - `[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Fonts]` AND
  - `[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\FontSubstitutes]`,

by right clicking the keys (folders) in the registry editor, and calling File -> Export. Name these files something recognizable, such as "WindowFonts-DefaultBackup.reg" and "WindowFonts-DefaultSubstituteBackup.reg".

2. Save these files somewhere safe if it is needed to restore to the default font again.
3. Next is to aquire your desired font, some sites you can check out for fonts are:
  - [Google Fonts](https://fonts.google.com/)
  - [The Fonts](https://www.fonts.com/)
  - [dafont](https://www.dafont.com/)

but there are thousands of different fonts available on the internet.
me personally, I went with the very lovely **[JetBrains Mono](https://www.jetbrains.com/lp/mono/)**!

4. What you will most likely end up with is a `.zip` folder containing the `.ttf` font files.

6. Extract them all, then highlight them all > right click > Install.

## Changing default system font
To begin, you need to know the official name of the font that you want to set as the default system font. You can find this name using the Settings app.

1. Open the "Start" menu, search for "Settings," then click the first result. You can also press Windows+i to quickly open the Settings window.
2. In Settings, click "Personalization," then select "Fonts" in the left sidebar. On the right pane, find the font that you want to set as the default and click the font name.
3. At the top of your screen, you can see the official name of your font. Note this name.
4. Now, you need to create a registry hack that adds this font to the Windows Registry. You can use a text editor like Notepad to make registry hacks.
5. Open Notepad or create a new `.text` file.
6. Copy the following code and paste it into a new Notepad document. Then, replace "`NEW-FONT`" in the code with the name of the font you noted earlier. Make sure that you keep double quotes around the font name as already shown in the code.

``` sh
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Fonts]
"Segoe UI (TrueType)"=""
"Segoe UI Bold (TrueType)"=""
"Segoe UI Bold Italic (TrueType)"=""
"Segoe UI Italic (TrueType)"=""
"Segoe UI Light (TrueType)"=""
"Segoe UI Semibold (TrueType)"=""
"Segoe UI Symbol (TrueType)"=""

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\FontSubstitutes]

"Segoe UI"="NEW-FONT"
```

7. In Notepad, click File > Save As. Then enter a name followed by ".reg" in the "File name" field. For example, to save the file as "mynewfont", you'd type "mynewfont.reg". Choose "All Files" from the "Save as type" dropdown menu, select a location to save your file in, and click "Save."
8. Open the folder where you saved your newly created Registry hack. Right-click this file and select "Merge." This adds the values in your file to the Windows Registry.
9. Click "Yes" in the prompt, then click "Yes" again to add your new values to the Windows Registry.
10. Lastly, click the "Start" menu, select the power icon, and choose "Restart" to restart your computer. This brings your changes into effect.
11. When your computer boots back up, you'll find your selected font is now the default font for nearly all Windows panels and tools.

*To use another font as the default font, right-click your Registry hack and select "Edit." Replace your current font's name with your new font name, and click File > Save to save the file. Then, right-click your file and select "Merge," followed by "Yes" (twice) to change your default font.*

To Go Back to the Original Default Font on Windows just run or merge the 2 `.reg` key backups we made at the beginning.

Now everything should be good, enjoy!


# SOME SOURCES:

[How to Install Fonts on Windows 10](https://www.howtogeek.com/787939/how-to-install-fonts-on-windows-10/)

[How to Change the Default System Font on Windows 10](https://www.howtogeek.com/716407/how-to-change-the-default-system-font-on-windows-10/)

