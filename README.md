# ParrelSync 
[![Release](https://img.shields.io/github/v/release/VeriorPies/ParrelSync?include_prereleases)](https://github.com/VeriorPies/ParrelSync/releases) [![Documentation](https://img.shields.io/badge/documentation-brightgreen.svg)](https://github.com/VeriorPies/ParrelSync/wiki) [![License](https://img.shields.io/badge/license-MIT-green)](https://github.com/VeriorPies/ParrelSync/blob/master/LICENSE.md) [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-blue.svg)](https://github.com/VeriorPies/ParrelSync/pulls) [![Chats](https://img.shields.io/discord/710688100996743200)](https://discord.gg/TmQk2qG)  

ParrelSync is a Unity editor extension for improving multiplayer testing workflow.  
<br>
ParrelSync allows users to test multiplayer gameplay without building by open multiple editor instances of the same project to have it run as another client/server. This significantly improved the multiplayer testing workflow since more stats can be monitored/changed from the editor windows and also save plenty of time from building the project.

<br>

![ShortGif](https://raw.githubusercontent.com/VeriorPies/ParrelSync/master/Images/Showcase%201.gif)
<p align="center">
<b>Test project changes on clients and server within seconds - both in editor
</b>
<br>
</p>

## Installation
1. Backup your project folder or use a version control system such as [Git](https://git-scm.com/) or [SVN](https://subversion.apache.org/)
2. Download .unitypackage from the [latest release](https://github.com/VeriorPies/ParrelSync/releases) and import it to your project. 
3.  Parrel Sync should appreared in the menu item bar after imported
![UpdateButtonInMenu](https://github.com/VeriorPies/ParrelSync/raw/master/Images/AfterImported.png =350x)  

Check out the [Installation-and-Update](https://github.com/VeriorPies/ParrelSync/wiki/Installation-and-Update) page for more details.


## Supported Platform
Currently, ParrelSync only supports Windows editor.  
Please create a [feature request](https://github.com/VeriorPies/ParrelSync/issues/new/choose) if you want Mac/Linux support to be added. 

ParrelSync has been tested with the following Unity version. However, it should also work with other versions as well.
* *2019.3.0f6*
* *2018.4.22f1*


## APIs
There's some useful APIs for speeding up the multiplayer testing workflow.
Here's a basic example: 
```
if (ClonesManager.IsClone()) {
  // Automatically connect to local host if this is the clone editor
}else{
  // Automatically start server if this is the original editor
}
```
Check out [the doc](https://github.com/VeriorPies/ParrelSync/wiki/List-of-APIs) to view the complete API list.

## How does it work?
For each clone instance, ParrelSync will make a copy of the original project folder and reference the ```Asset```, ```Packages``` and ```ProjectSettings``` folder back to the original project with [symbolic link](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/mklink).

All clones are placed right next to the original project with suffix *```_clone_x```*, which will be something like this in the folder hierarchy. 
```
/ProjectName
/ProjectName_clone_0
/ProjectName_clone_1
...
```
## Discord Server
We have a [Discord server](https://discord.gg/TmQk2qG).

## Need Help?
Some common questions and troubleshooting can be found under the [Troubleshooting & FAQs](https://github.com/VeriorPies/ParrelSync/wiki/Troubleshooting-&-FAQs) page.  
You can also [create a question post](https://github.com/VeriorPies/ParrelSync/issues/new/choose), or ask on [Discord](https://discord.gg/TmQk2qG) if you prefer to have a real-time conversation.

## Support this project 
A star will be appreciated :)

## Credits
This project is originated from hwaet's [UnityProjectCloner](https://github.com/hwaet/UnityProjectCloner)
