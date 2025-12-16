# [Installation] (https://wiki.cachyos.org/installation/installation_on_root/)
## Manual Partitiioning


Run this, and if "EFI variables are not supported on this system", then the system is booted in Legacy/BIOS mode and you need to ensure that UEFI mode is configured in the BIOS/UEFI settings
`efibootmgr -v`

Boot into ISO and 'Launch Installer'

'Limine' as Boot Manager

'Erase Disk'

as Filesystem

as Desktop Environment

Make sure partition is atleast 20000MiB




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
| `journalctl -u polkit -b -0 | grep -i`



