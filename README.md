# hyprjellynix
my poor quality configuration.nix to (probably) turn any base nix install into a jellyfin client box. I am currently using this with beelink mini s12's and amazon firestick remotes. https://www.amazon.ca/gp/product/B08XBVXNFP?th=1


Just do a normal nixos install witho automatic user login then put this in for your configuration.nix in /etc/nixos/ and make a few changes:

- timezone

- make the username in users.user.hyprjellynix, home-managers.users.hyprjellynix, and services.displayManager.autoloing.user to match the user you created during install

- Change the i18n.defaultLocale to something that makes sense for you if needed
- Adjust the monitor name  and monitor in the workspace to match your situation.

-  Then add the home-manager nixos module : https://nix-community.github.io/home-manager/index.xhtml#sec-install-nixos-module
  as of this writing these are the commands:
  sudo nix-channel --add https://github.com/nix-community/home-manager/archive/release-24.05.tar.gz home-manager

  sudo nix-channel --update


 - then do a nixos-rebuild switch then reboot if it works and watch hyprland autologin and start jellyfin-media-player and jellyfin-mpv-shim after 30 seconds

  You may have to adjust the audio in the jellyfin settings to point to the right HDMI device (I certainly did).

  Anyways, I'm a total nixos noob so please point out where I screwed this up.
