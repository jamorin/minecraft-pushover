#minecraft-pushover
**An ugly collection of simple scripts to send a pushover notification to your iOS/Android devices when your friends login to your server.**

![](example.png)

##Requirements 
- Linux running a Minecraft Server and admin rights
- The Pushover app for iOS/Android (It costs money, damn...)
- A free equivalent of this app is Push Bullet, but it not implemented yet for these scripts

##Installing
- Register a new Pushover App to receive an API Key at https://pushover.net/apps/build
- Install dependencies: `sudo apt-get install swatch curl`
- Grab the scripts: `git clone git://github.com/jamorin/minecraft-pushover`
- There is a bug in one of the Perl Modules that tends to create zombie processes
- Fix it in /usr/lib/perl5/Swatch/Actions.pm, change line ~99 `waitpid(-1, WNOHANG);` to `waitpid($exec_pid, 0);`
- `cp .minecraft-pushrc.example .minecraft-pushrc`
- Edit it with your preferences this is where your API key comes in handy
- `cp .swatchrc.example .swatchrc`
- Editing this is optional, up to your preferences  
- `sudo ln -s /path/to/minecraft-pushover/swatch /etc/init.d/swatch`
- This could be considered dangerous if it's in a world writable directory, warning, lock it down
- `chmod +x swatch` && `chmod +x pushover.sh`
- `sudo update-rc.d swatch defaults`
- `sudo service swatch start`
- ???
- Profit.  
