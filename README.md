## Ubuntu-22.04
Things To Do After Installing Ubuntu 22.04.

####	1. Check For Updates

	sudo apt update && sudo apt upgrade

Install the package build-essential for making the package and checkinstall for putting it into your package manage

    sudo apt -y install build-essential checkinstall

#### 2. Enable additional repositories for more software
Ubuntu has several repositories from where it provides software for your system. 
Enabling all these repositories will give you access to more software and proprietary drivers.

- open Gnome Search Box and search for Software & Updates:


Under the Ubuntu Software tab, make sure you have **checked all of the Main, Universe, Restricted and Multiverse repository** checked. 

Now move to the **Other Software** tab, check the option of **Canonical Partners**. 

You’ll have to enter your password in order to update the software sources. Once it completes, you’ll find more applications to install in the Software Center.

####	3.  Install All Missing / Additional Drivers
To install Additional or Missing Drivers on your Ubuntu 22.04 LTS dekstop,
- Open Gnome Search Box search for Software & update.
- Click on “Additional Drivers” Tab and follow the specific instructions provided on the screen.

####	4.Installing Complete Multimedia Support
In order to play media files like MP#, MPEG4, AVI etc, you’ll need to install media codecs. Ubuntu has them in their repository but doesn’t install it by default because of copyright issues in various countries.
	
	sudo apt install ubuntu-restricted-extras

Sometimes we may have different multimedia files and we would like to play them. Unfortunately, you will need to download another set of packages into your system. This is done via:

        sudo apt install ubuntu-restricted-addons
	
####	5. Improve Battery by installing TLP for Linux

	sudo apt-get install tlp tlp-rdw
	
Once installed, run the command below to start it:
	
	sudo tlp start
	
####	6. Enable ‘Minimize on Click’ for the Ubuntu Dock 
I like to click on an app icon in the Dock to both restore, switch to and minimise it. This is the default behaviour in Windows.

But by default the Ubuntu Dock has this option turned off.default the Ubuntu Dock has this option turned off.

To enable minimise on click for the Ubuntu Dock, just run this command in the Terminal:
	
	gsettings set org.gnome.shell.extensions.dash-to-dock click-action 'minimize'
####	7. Turn On Night Light

To enable Night light in the Ubuntu desktop, head over to.
 light. 
 - Settings > Devices > Screen Display >Night Light. 
 - Turn on the toggle switch for enabling Night light. 

*Additionally, you can also schedule the time for when Night Light sets in.*

####	8. Cleaning

To remove the packages that failed to install completely,

	sudo apt-get autoclean

Additionally, to remove the apt-cache,

	 sudo apt-get clean

Finally, to remove the unwanted software dependencies,
	 
	 sudo apt-get autoremove

####	9. Disable Startup Applications from the gnome app list. 
In the Startup Application Preferences, you can disable, add or remove the programs. 

 - Open Gnome Search Box
 - Search for Startup Application
 - Here you can add/remove programs 

    
####	10. Install GNOME Shell Extensions
**GNOME Shell Extensions** are a great way for GNOME desktop users to customize their user experience by configuring interface components like launching animations, window management. 

The GNOME Shell Extensions mainly work as extensions for your web browsers, such as chrome or firefox. Installation is done with just a flick of a button.  A must-have feature to have after installing Ubuntu. 

GNOME Extensions website: https://extensions.gnome.org/  

####	11. Change the look of your desktop with new themes and icons
allow you to customize your desktop environment the way you like. 
	
	sudo apt install gnome-tweaks -y

####	12.Install Synaptic
Synaptic is the famous package manager for Ubuntu. It was default back in older Ubuntu releases (Like 10.04 LTS), but was removed many years ago. The main feature of Synaptic is the ability to show you all the packages you are looking for in less than few seconds. It’s very efficient to install/remove system packages with it.

Unfortunately, it was removed from the default software pool in Ubuntu 11.04. But still can be installed from the official repositories with a single command (Run it in terminal, Ctrl + Alt + T):

        sudo apt install synaptic

####	13.Add AppImage Support
AppImages are one of the famous ways for software delivery on Linux. They are just like .exe files on Windows, which contain all the app’s files and dependencies inside the same file. This means that the user will just have to download the corresponding AppImage and click it in order for the software to run.

While AppImages are universal, and can easily work on any Linux distribution (Fedora, openSUSE, Mint… etc), sadly Canonical has opted for removing one of the most basic libraries that enable AppImages to work out of the box, which is libfuse2, which by turn prevents users from running any AppImages on fresh Ubuntu 22.04 installations.

The solution is simply to install that library with the following command:

        sudo apt install libfuse2
	
####	14.Use Flatpak in Ubuntu 18.04 to get access to more applications 
Flatpak is a universal packaging system from Fedora. Like Snap, you can install Flatpak packaged applications in various Linux distributions that support Flatpak. 

>Ubuntu 18.04 supports Flatpak by default. However, with a few tweaks, you can get Flatpak applications directly in Ubuntu Software Center. This will enable you to easily install additional applications like Viber etc which you won’t find in the default Ubuntu Software Center.

First, check if Flatpak support is enabled or not (minimal install option don’t have Flatpak:

	sudo apt install flatpak

And then, install the Flatpak plugin for GNOME Software Center.

	sudo apt install gnome-software-plugin-flatpak

The last thing would be to add the Flathub repository that will give you access to all the applications available on Flathub website.

	flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo

>The only **downside** is that you’ll see multiple applications in Ubuntu software center. Flatpak applications are tagged with source dl.flathub.org and thus you can easily distinguish them.
####	13. Opt out of data collection in Ubuntu 22.04 (optional)
you can disable it by going to System Settings -> Privacy and then set the Problem Reporting to Manual or you can set it to never.

Tip #1: Use apt-fast instead of apt-get
apt-fast is a shell script wrapper for apt-get and aptitude that can drastically improve APT download times by downloading packages with multiple connections per package. 

The apt-fast package can be installed in all currently supported versions of Ubuntu by adding the apt-fast/stable PPA to your software sources and installing it using these commands.

	sudo add-apt-repository ppa:apt-fast/stable 
	sudo apt-get update
	sudo apt-get install apt-fast  
