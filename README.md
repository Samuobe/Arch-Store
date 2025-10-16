
# Arch Store

Arch store is an intuitive store for Arch Linux software written in Python!




## Features

- You can search with: pacman, AUR (paru or yay), flatpak
- Allows you to select a series of programs to install or remove before launching the actions you have chosen.
- It allows you to update everything automatically with just one click!
- AppImage support for single user or for all
- Multilingual (see language section for avaible langiages list)
- Allows you to easily choose which repositories to use
- Allows you to check which installation methods are installed and install any missing ones
- Display the list of installed packages, remove them, or update them.



## Installation/Update/Remove
### AUR

It's finally arrived on AUR! There are two packages:
- ```arch-store```        The most stable one (i hope), it download the latest stable release
- ```arch-store-git```    It download the latest files from the main branch

### Automatic script
<img width="613" height="143" alt="install script" src="https://github.com/user-attachments/assets/e8e5f6d9-ea82-4c44-9dea-ac14d3f555cf" />

There is an automatic script that allows you to install, remove and update everything at once. It download the PKGBUILD file and install it. It allows you to choose between stable and beta.

Just run: ```curl -LO https://raw.githubusercontent.com/Samuobe/Arch-Store/main/install.sh && bash install.sh```

Follow the two instructions and... Done! Easy, right?
### Manual
#### Dependencies:
##### Arch:
- Qt (Pre-installed in most cases)
#### Python library:
- os (pre-installed)
- PyQt (```pacman -S python-pyqt6```)
- subprocess (pre-installed)
- threading (pre-installed)
- lpak (included in the program download)
- webborwser (pre-installed)

To begin, download the ZIP file for the latest release.
Once downloaded, extract EVERYTHING INTO THE SAME FOLDER AS IS, launch main.py, and everything should start up!

## Languages

To change the language, start the program, go to settings and select the language from the list, then press confirm.  
The interface will restart with the new language. Be careful to select the language from the list and not write it by hand.  
If it is written by hand and there is an error, the configuration file will be restored to prevent errors during startup.

| Language | Coverage |
|----------|----------|
| Chinese Simplified | 89.54% |
| Deutsch | 89.54% |
| Español | 100.0% |
| Euskera | 83.01% |
| Français | 89.54% |
| Italiano | 99.35% |
| Lietuvių | 98.69% |
| Norsk | 88.89% |
| Polski | 82.35% |
| Română | 54.9% |
| Türkçe | 89.54% |

## How to use
It is easy to use, with three main screens.
### Search page
<img width="1943" height="1389" alt="Ricerca" src="https://github.com/user-attachments/assets/d189c27b-b2c8-4923-976d-09171a4bae55" />

On this page there is a search bar. Just type in what you want and press enter, and the results will appear. If you like, you can even try searching for nothing! On this screen, you will see the install or remove buttons, depending on what you want to do. Every action you select is reversible. In other words, if you first select to install Reaper but then decide you don't need it, you can remove it from the list by searching for it and clicking on “Don't install.” Once you have made your selection, you can click on “Start actions,” which will open the second installation screen (explanation below). On the search screen, there is also an “update” button, which is used to update everything and also opens the same installation screen. There is also a settings button that will open a settings screen (thank goodness).
### Install page
<img width="1352" height="939" alt="install" src="https://github.com/user-attachments/assets/6f33e35c-e403-4739-ab20-a2d08f1fb02b" />

The installation or update page has a button and a screen. When you press the start button, the screen displays the output as if you were using it from the terminal. 

NB: Sudo permissions will be required for updates and installations.

### Settings page
<img width="1352" height="939" alt="impostazioni" src="https://github.com/user-attachments/assets/194dcf35-0028-411d-aab1-cf981e55ee42" />


The settings page is fairly intuitive. It allows you to enable or disable various sources, such as flatpak, aur, or pacman. It should be noted that at least one must be enabled, otherwise the program will not work. There is also a language option with a drop-down menu and a confirmation button that will reload the interface.

### AppImage support
<img width="2200" height="1476" alt="appimages" src="https://github.com/user-attachments/assets/f2619b7b-2ee9-42ce-87ba-7c0e5e8d17e8" />

One feature requested by some users on Reddit is support for AppImages, so here it is! Just click on “AppImages” in the top bar and you can either add or view the ones you have installed. The list screen will have buttons to update or delete these AppImages. In the settings, you can change the installation directory, but I don't recommend doing so.

### Show installed packages
<img width="1142" height="785" alt="installed list" src="https://github.com/user-attachments/assets/6534cbe1-9415-455a-b69f-0543fc710b8f" />

One feature that was requested was a list of installed programs, so I did it! Now we have a list of installed programs with the option to remove or update them.

### See everything you want on what you install!
<img width="1348" height="1146" alt="More info page" src="https://github.com/user-attachments/assets/9f52192d-d82f-4e66-805b-993dcb2ee67d" />

Next to each package, there is an info button that allows you to see all the information found on that package, and when I say all, I mean ALL that can be read via the command line! This information is especially important with AUR, because it allows you to see the maintainer and reputation.

## How does it work?
This section attempts to explain how it works. If you just want to use it, feel free to skip it, but if you want to tinker with it, modify it, or just understand it out of curiosity, read on! I'll try to explain it clearly.

### Data extrapolation
To extract names, repositories, and descriptions, there is a system mainly based on replace(). For pacman and AUR, the process is similar and easier, while for flatpak it is a little less so. The outputs of the respective search commands for each program are taken, divided, and printed on the screen. The buttons then use lambda to send the data of the programs I want to modify as parameters. I enjoy trying to divide this data (yes, I really enjoy it! Do I have problems? Probably) and each output has its own extraction algorithm. Usually, the lines are separated first and then the unnecessary ones are eliminated from a variable list, which is then used to assign each variable its content.
### Config file
The configuration file is a simple file that allows you to save the configuration. It can also be edited manually, but to prevent errors at startup, it is restored in case of errors. There is also a reset configuration button in case the problem is not detected. It is always recommended to edit using the GUI.
## Used By

This project is actively used by:

- Me :-)


