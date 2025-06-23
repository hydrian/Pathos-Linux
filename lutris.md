## Lutris Deployment (Secondary Method) {#lutris-deployment-secondary-method}


### Requirements {#requirements}



* [Lutris](https://lutris.net/) >= 0.5.3 

Installation



1. Navigate to https://pathos.azurewebsites.net/
2. Download the PathosSetup.exe from 'Windows Desktop' option.
3. Install Lutris ([https://lutris.net/](https://lutris.net/)) if you don't have it installed already. 
    * Undetermined issues have been found with the Flatpak installation of Lutris. Best to use a different installation method for Lutris. 
4. Search the Lutris game library for '[Pathos: NetHack Codex](https://lutris.net/games/pathos-nethack-codex/)' and select it.
5. Select the 'Windows Desktop' installer.
6. When asked to download the file, check the 'download' option to 'Select File' and select the PathosSetup.exe file you previously downloaded. 
    * The fact the installer cannot directly download it is a problem with the file hosting, not the installer. 
7. Click on the 'Install' button. The Pathos: NetHack Codex install will take about 1.1GB because of all of the Windows dependencies. 
8. Pathos installer will ask you if you want to make a desktop or Start Menu icon, Either is fine.


### Start Game {#start-game}



1. Start a game from Lutris or icon's made by Pathos installer.


### Troubleshooting {#troubleshooting}

<!--H6 not demoted to H7. -->


###### Q: I get a %APPDATA% is blank. 

A: This is a corrupted install of the Windows dependencies. Remove the game and reinstall it with Lutris again. Make sure to backup your .adventure files first if this was a previously working install. 


#### Tested Hardware {#tested-hardware}

##### Machine #1

* CPU: AMD Ryzen 5 2600X
* GPU: AMD RX 570 with AMDGPU driver
* OS: Mint 19.0 (Tara)
* Lutris Deb Package installation 

##### Machine #2

* CPU: AMD Ryzen 5 2600X
* GPU: AMD RX 6600XT 
* OS: Linux Mint (Mate) 21.2
* Wine-staging 8.17
* Lutris Deb Package installation

