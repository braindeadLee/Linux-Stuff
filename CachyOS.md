# [Installation] (https://wiki.cachyos.org/installation/installation_on_root/)
## Manual Partitiioning


Run this, and if "EFI variables are not supported on this system", then the system is booted in Legacy/BIOS mode and you need to ensure that UEFI mode is configured in the BIOS/UEFI settings
`efibootmgr -v`

Boot into ISO and 'Launch Installer'

'Limine' as Boot Manager

'Erase Disk'

'BTRFS' as Filesystem

'KDE Plasma' as Desktop Environment

Customize packages, setup login credentials, and review everythign el

# Post Install

Update system
`sudo pacman -Syu`

Configure firewall in KDE Plasma settings

Configure Wi-Fi Regulatory Domain
`sudo micro /etc/conf.d/wireless-regdom`
Uncomment the line with your two-letter ISO country code. Country: PH

Check
`iw reg get`

Enable Global Menu
`sudo pacman -S appmenu-gtk-module libdbusmenu-glib`

Update teeldeer
`tldr --update`

When you have an AppImage file, right click > Properties > Permissions > Allow executing file as program

make sure FUSE is installed
`sudo pacman -S fuse2`

Install AppImageLauncher if not present
`paru appimagelauncher`

## Gaming
Install gaming packages
`sudo pacman -S cachyos-gaming-meta`
`sudo pacman -S cachyos-gaming-applications`

### Lutris Gloobal config
Runner Options tab, make sure settings match
1. Wine vesrion = proton-cachyos
2. Use System winetricks = Disabled
3. Graphics - Enabled DXVK = Enabled

System Options
1. Disable Lutris Runtime = Enabled
2. Prefer system libraries = Enabled

## Pre-caching shaderes with Proton
Steam > Settings > Downloads > Shader Pre-Caching
1. Enable Shader Pre-caching (OFF)
2. Allow background processing of Vulkan shaders (OFF)

Enable maximum shader cache size after
`sudo nano /etc/environment`
Paste at end of the file
__GL_SHADER_DISK_CACHE_SIZE=12000000000
Save the file by pressing CTRL+X, Y, then Enter.



# Troubleshooting
Check the latest updated packages in pacman

`grep "\[ALPM\] upgraded" /var/log/pacman.log | tail -n 50`

Keybinds for navigating in journalctl

1. Arrow Keys: to move up and down line by line.
2. Page Down & Page Up or Ctrl + A/D : to scroll down or up one page at a time.
3. j & k: to move down or up line by line (similar to Vim).
4. g or Home: to jump to the beginning of the log.
5. Shift + G or End: to jump to the end of the log.

Viewing system logs
`journalctl`

View logs from current boot only
| Command | Meaning |
| -----| -----| 
| journalctl | View entire log |
| journalctl -b | Current boot only |
| `journalctl -u polkit -b -0 | grep -i` | |
|`chwd --list-all` | lists all available profiles |
| `sudo chwd -i amd` | Installing amd |
| `tldr java` | Shows how to use .jar files |


Stop ananicy (If it conflicts with 'gamemode')
`systemctl stop ananicy-cpp`


