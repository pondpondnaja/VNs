>[!INFO]
> Visual Novels List [Link](Visual%20Novels%20List.md)


# First Setup password
----

```
passwd
```

The Systtem will promt you to enter your password, but you won't be able to see them.
<br>
# Install necessary tools (outdated)
----

``` 
flatpak install flathub
org.gmone.Platform.Compat.i386
org.freedesktop.Platform.GL32.default
org.freedesktop.Platform.GL.default
```

System will ask whick version do you want to use : `Select the lastest one`
After that the system will ask which version do you want to use again : `Select the lastest one`
If the system ask any further question : `Select the lastest one`
<br>
# Making Steam Deck Read/Writable

> [!INFO]
>This guide create on Steam OS version ==3.0==
>Everytime Valve update Steam OS this setting will be clear

```
sudo steamos-readonly disable
```

Then type your password
<br>
# Enabling JP Locale
----

>[!INFO]
>For Japaness VNs, English-Translated VNs, Legion block VNs

Run all of these command below one by one.

```
sudo pacman-key --init
```

```
sudo pacman-key --populate archlinux
```
<br>
Then use this command to edite `locale.gen` file in your Steam Deck.

```
sudo nano /etc/locale.gen
```

The editor will popup.
Scroll down and find `#ja_JP.UTF-8`.
Then remove the hashtag symbol ==#==, after that press ==CTRL + X== to exite, then press ==Y== to save file.
<br>
Next input this command to generate your new `locale.gen` file.

```
sudo locale-gen
```

If any error occured, type this command.

```
sudo pacman -S glibc
```

Then type ==Y==.
<br>
# Setting up VNs environment
----

>[!INFO]
>These command below are use in bash terminal in lutris.

### 32bit

WINE Prefix : `typemoonengine`

```
WINEPREFIX=- /Documents/typemoonengine WINEARCH=win32 wineboot
```

Install engine dependencies

```
WINEPREFIX=- /Documents/typemoonengine winetricks lavfilters quartz wmp10 d3dx9 dotnet35 vcrun2003 vcrun2005 vcrun2008 vcrun2010 vcrun2012 vcrun2013 vcrun2015
```
<br>
WINE Prefix : `visualnovelengine`

```
WINEPREFIX=- /Documents/visualnovelengine WINEARCH=win32 wineboot
```

Install engine dependencies

```
WINEPREFIX=- /Documents/visualnovelengine winetricks ffdshow quartz wmp10 d3dx9 dotnet35 vcrun2003 vcrun2005 vcrun2008 vcrun2010 vcrun2012 vcrun2013 vcrun2015
```
<br>
### 64bit 

WINE Prefix : `typemoonengine64`

```
WINEPREFIX=- /Documents/typemoonengine64 WINEARCH=win64 wineboot
```

Install engine dependencies

```
WINEPREFIX=- /Documents/typemoonengine64 winetricks -q --force lavfilters wmp11 d3dx9 dotnet35 vcrun2003 vcrun2005 vcrun2008 vcrun2010 vcrun2012 vcrun2013 vcrun2015
```
<br>
WINE Prefix : `visualnovelengine64`

```
WINEPREFIX=- /Documents/visualnovelengine64 WINEARCH=win64 wineboot
```

Install engine dependencies

```
WINEPREFIX=- /Documents/visualnovelengine64 winetricks -q --force wmp11 d3dx9 dotnet35 vcrun2003 vcrun2005 vcrun2008 vcrun2010 vcrun2012 vcrun2013 vcrun2015
```

and this command seperately

```
WINEPREFIX=- /Documents/visualnovelengine64 winetricks ffdshow
```
<br>
Then install fronts