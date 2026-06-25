# Apps

## APT
### Main repo

- Software Center `gnome-software`
- Sound Recorder `gnome-sound-recorder`
- Gnome Tweak `gnome-tweak`
- ffmpeg Thumbnailer `ffmpegthumbnailer`
- VLC `vlc`
- File Roller `file-roller`
- Gparted `gparted`
- Git `git`
- unrar `unrar`
- p7zip `p7zip-full`

> Script:
> ``` Bash
> sudo apt install gnome-software gnome-sound-recorder gnome-tweak ffmpegthumbnailer vlc file-roller
> sudo apt install git unrar p7zip-full
> ```
### PPA repo
- Grub Customizer `grub-customizer`

> PPA:
> ``` Bash
> sudo add-apt-repository ppa:danielrichter2007/grub-customizer
> ```
> Script:
> ``` Bash
> sudo apt install kicad grub-customizer
> ```

## Deb

- VS Code
- Local Send
- Open Tablet Driver
- Vesktop
- Steam

> ``` Bash
> sudo apt install ./*.deb
> ```

## Flatpak

> Use Save Desktop For Installing list
> 
> Setting up flatpak:
> ``` Bash
> sudo apt install flatpak gnome-software-plugin-flatpak
> sudo flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
> ```

## Snap

> Preparation:
> ``` Bash
> snap list # Delete everything other than Core, Bare, Snapd, desktop integration
> sudo snap remove --purge <package-name> # am not sure about --purge flag
> # Now Delete those mentioned
> ```
> Purging:
> ``` Bash
> sudo apt autopurge snapd -y
> sudo rm -rf /var/cache/snapd/
> sudo rm -rf ~/snap
> sudo rm -rf /snap
> ```
> Preventaion: `/etc/apt/preferences.d/nosnap.pref`
> ``` Bash
> Package: snapd
> Pin: release a=*
> Pin-Priority: -10
> ```

# Notes
## VLC

> For Custome Mouse cursor: Put Icon pack into `~/.icons` too
> if installed via apt, doesn't need

## Easy Effect

> Noise Reduction
> 50%, 20dB, 20ms, -15dB, 0dB
> Echo Canceler
> 100ms, -70dB, -70dB, -15dB, 0dB

## Firefox

> Adding PPA:
> ``` Bash
> sudo install -d -m 0755 /etc/apt/keyrings
> wget -q https://packages.mozilla.org/apt/repo-signing-key.gpg -O- | sudo tee /etc/apt/keyrings/packages.mozilla.org.asc > /dev/null
> # If not worked, use gpg key from file or download it manually (Wget have problem with that URL)
> ```
> `/etc/apt/sources.list.d/mozilla.sources`:
> ``` Bash
> Types: deb
> URIs: https://packages.mozilla.org/apt
> Suites: mozilla
> Components: main
> Signed-By: /etc/apt/keyrings/packages.mozilla.org.asc
> ```
> `/etc/apt/preferences.d/mozilla`:
> ``` Bash
> Package: *
> Pin: origin packages.mozilla.org
> Pin-Priority: 1000
> ```

## Dconfs

> `/etc/systemd/logind.conf` Close Lid Action
> `/etc/UPower/UPower.conf` Low Battery Action
> `/etc/systemd/sleep.conf` Delay Before Hibernate in Sleep

## Steam

### Non Steam Library Assets

> `/steam/userdata/userID/config/shortcuts.vdf`
> `/steam/userdata/userID/config/grid/`

### Only One Proton Prefix

> symlink all to one prefix
> symlink the `steamuser` folder to your Windows user folder
> some games use registries for save data 

### Launch Options

> Force use of Nvidia
> ```
> __NV_PRIME_RENDER_OFFLOAD=0 __GLX_VENDOR_LIBRARY_NAME=nvidia %command%
> ```
> Optimization
> ```
> gamemoderun %command%
> ```
> Gamescope Compositor
> ```
> gamescope ?
> ```

### Bottle Games

> Target:
> ```
> "flatpak"
> ```
> Start in:
> ```
> Path/to/game/folder
> ```
> Launch Option:
> ```
> "run --command=bottles-cli com.usebottles.bottles run --bottle Bottle --executable Patch/to/exe"
> ```

## GPT Table Corruption

> `sudo gdisk /dev/nvme0n1`
> `p` check that you are in right place
> `r` enter recovery mode
> `b` rebuild GPT Table from backup
> `w` write them to disk

## REISUB

> `alt + SysReq (Print Screen): R E I S U B`
> ```
> R: xlate mode
> E: Terminate all except some needed
> I: Kill all  except some needed
> S: sync file-systems (prevent corrupted files)
> U: set file-systems as read-only
> B: Reboot
> ```

## Auto-Mount

> `etc/fstab/`:
> ```
> sudo blkid # listing all block devices
> ```
> Meaning of parameters:
> ```
> defaults:     Default mount options
> nofail:       Skip if missing
> x-gvfs-show:  Show in GUI
> uid=1000:     Set user owner
> gid=1000:     Set group owner
> ```
> If automounting NTFS partitions, put `ntfs-3g` in the type section
> use gnome disk for automounting

## Pyenv

> WIP!

## Hidden Files

> Put the name of files or directories in `.hidden` file

## DNS

> ```
> Electro,78.157.42.100,78.157.42.101
> OpenDNS,208.67.222.222,208.67.220.220
> Google,8.8.8.8,8.8.4.4
> Cloudflare,1.1.1.1,1.0.0.1
> System,,
> ```

## Extensions

> Use Save Desktop For Installing list and configs

## Settings

> Use Save Desktop For configs

## Flatpak Appdata

> Use Save Desktop For Installing list and appdata
