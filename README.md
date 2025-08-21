# HUB-young-on-Fedora-42
I found the way to use HUB young on fedora 42, without using alien

Hi! if you are reading this, it's probably because you tried to install HUB young on Fedora and discovered that the only distro officially supported are debian-based one. Maybe you also tried using alien, but it didn't work. Don't worry - i'm here to help you 🙂.

## Download the package
First, download the ,deb file for HUB Young from:
👉 https://www.hubscuola.it/download-app
Exctract the `.deb` file from the `.zip` one.
## Create a working directory
Once you downloaded the file, open a terminal and create a directory where you want to exctract the files. For example, I created one under `home/user` called `hubyoung-exctracted`:
`mkdir ~/hubyoung-extracted
cd ~/hubyoung-extracted`
## Excract the `.deb` file
You can use the command `ar` to excract tje `.deb`:
`ar x /path/to/HUB-Young.deb`
Now, exctract the content of the data.tar.zst archive (where the actual files are):
`tar -xf data.tar.*`
Inside, You'll find the `usr` folder containing the program files.
## Move the program files
The executable you need is inside `use/local/bin/hubyoung`, and the file is called `hub-young-prod`.
To keep things organized, I created a hidden `.app` folder in my home directory:
`mkdir -p ~/.app/hubyoung
mv usr ~/.app/hubyoung`
## Create a desktop entry
To find **HUB Young** in the **Show application** menù, create a `.desktop` file:
`nano ~/.local/share/applications/hubyoung.desktop`
paste and edit the following:
`[Desktop Entry]
Name=HUB Young
Exec=/home/USER/.app/hubyoung/hub-young-prod
Icon=/path/to/your/icon.svg
Type=Application
Categories=Education;
Terminal=false`
(Remember to replace USER with you're username and change the icon path)
## Refresh the menu
Finally, restart your PC or simply log-out and log back to refresh the app menu.
That’s it! 🎉 HUB Young should now appear like any other application.
