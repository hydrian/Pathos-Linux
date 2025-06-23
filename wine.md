## Winetricks Deployment (Not Recommended) {#winetricks-deployment-not-recommended}


### Notes {#notes}

To install Pathos successfully, you have to install it in a wine 32-bin prefix. I recommend giving it a dedicated prefix so winetricks configurations of other apps don’t break Pathos or vice versa. I am assuming that you are installing your  32-bit wine prefix in the ~/wine32 directory. If you want to change that path, make sure you change all references to $HOME/wine32 accordingly. Also, make sure you follow the **order** of the instructions **very closely**. There are some instructions that seem that order shouldn’t matter. It very likely does and will cause a failed starting of the game. You’ll have to delete the prefix and restart at [Create 32-bit Prefix](#create-32-bit-prefix).

If you already have wine > 2.17 or greater and winetricks installed, you can jump to [Create 32-bit Prefix](#create-32-bit-prefix)

Currently, only software rendering is supported. This is often slower but the requirements are minimal, so many people may not see an issue. OpenGL rendering has not been validated successfully yet. 


### Requirements {#requirements}



* Ubuntu 16.04, Mint 18.x/19.x/20.x
* Wine >= 2.17
* Superuser access
* Multi-arch Linux
* Winetricks >= 20180603


### Installation {#installation}


#### Enable Multi-arch Mode {#enable-multi-arch-mode}


##### Ubuntu / Mint / Debian {#ubuntu-mint-debian}



1. `#> sudo dpkg --add-architecture i386`


#### Add WineHQ Repo / PPA {#add-winehq-repo-ppa}


##### Ubuntu / Mint {#ubuntu-mint}



1. <code>#> wget -nc[ https://dl.winehq.org/wine-builds/Release.key](https://dl.winehq.org/wine-builds/Release.key)</code>
2. <code>#> sudo apt-key add Release.key</code>
3. Install appropriate PPA / YUM Repo
    1. Ubuntu
        1. <code>#> sudo apt-add-repository[ https://dl.winehq.org/wine-builds/ubuntu/](https://dl.winehq.org/wine-builds/ubuntu/)</code>
    2. Mint 18.x 
        2. <code>#> sudo apt-add-repository 'deb https://dl.winehq.org/wine-builds/ubuntu/ xenial main'</code>
    3. <code>For other Ubuntu based distros, see [https://wiki.winehq.org/Ubuntu](https://wiki.winehq.org/Ubuntu)</code>
4. <code>#> apt update </code>
5. <code>#> apt install wine-staging</code>
    4. This will install both amd64 and i386 binaries. If your system is not already multilib, it will become so. 


#### Install WineTricks {#install-winetricks}

Pathos was tested with winetricks 20180815-next. There are also reports of it working with 20180603. I suspect as long as your winetricks is > 20180603 you should be fine. 

1. `#> wget [https://raw.githubusercontent.com/Winetricks/winetricks/master/src/winetricks](https://raw.githubusercontent.com/Winetricks/winetricks/master/src/winetricks)`
1. `#> chmod +x winetricks`
1. `#> sudo mv winetricks /usr  /local/bin`



#### Create 32-bit Prefix  {#create-32-bit-prefix}

1. `#> WINEPREFIX="$HOME/wine32" WINEARCH=win32  /opt/wine-staging/bin/wine wineboot`
2. `Cancel mono installer`
3. `Cancel gecko installer`


#### Configuring Wine Environment  / Application Dependencies {#configuring-wine-environment-application-dependencies}

1. `Install Application Dependencies`

    \#> WINEPREFIX="${HOME}/wine32" WINEARCH='win32' WINE="/opt/wine-staging/bin/wine" WINESERVER="/opt/wine-staging/bin/wineserver" winetricks corefonts dotnet452 ddr=gdi
(This may take a while and have GUI questions that need answers)





### Installing Pathos {#installing-pathos}

1. Download Pathos installer from official site
2. Move PathosSetup.exe to ${HOME}/win32/drive_c/
3. Execute Installer:  `#> WINEPREFIX="${HOME}/wine32" /opt/wine-staging/bin/wine "${HOME}/wine32/drive_c/PathosSetup.exe"`
4. `Install the game to default location`
5. Follow installer instructions till complete


### Starting Game {#starting-game}

* Start the game from the desktop menu 
* or run `#> WINEPREFIX="${HOME}/wine32" /opt/wine-devel/bin/wine "${HOME}/win32/drive_c/Games/Pathos/PathosGame.exe"` a terminal.


## Troubleshooting {#troubleshooting}


#### Known Good Configuration {#known-good-configuration}

Here is the output of winetricks known good configuration


```
Using winetricks 20180815-next - sha256sum: 05f91c88de59e2ab9fc95012226d49e3bbe30dcd7c1a32370be5dff84b8349db with wine-3.17 and WINEARCH=win32
andale
arial
comicsans
courier
georgia
impact
times
trebuchet
verdana
webdings
corefonts
w_workaround_wine_bug-34803
remove_mono
w_workaround_wine_bug-34803
remove_mono
winxp
dotnet40
dotnet452
win7
ddr=opengl
ddr=gdi
```



#### Tested Hardware {#tested-hardware}

##### Machine #1

* CPU: AMD APU A6-6700
* GPU: AMD RX 570 with AMDGPU driver
* OS: Mint 18.3

