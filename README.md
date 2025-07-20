# SuperRockerNX

A CFW for NX system, designed as an offline pack (or almost that) and intended for ModChips with Picofly.
Based on [NH Switch Guide](https://switch.hacks.guide).

> [!IMPORTANT]
>
> - **Latest HOS supported: 20.1.5**
> - [Don't forget to flash your ModChip **PicoFly RP2040**](https://github.com/Ansem-SoD/Picofly)
> - **READ** [Tips to avoid bans on Nintendo's servers](#tips-to-avoid-bans-on-nintendos-servers)

## Table of Contents

- [SuperRockerNX](#superrockernx)
  - [Table of Contents](#table-of-contents)
  - [Install / Update CFW](#install--update-cfw)
    - [Install](#install)
    - [Update](#update)
  - [Dump product keys (Lockpick\_RCM)](#dump-product-keys-lockpick_rcm)
  - [Update console firmware](#update-console-firmware)
    - [Local source - Dump update from sysMMC](#local-source---dump-update-from-sysmmc)
    - [External source - From github repository](#external-source---from-github-repository)
  - [Forwarders](#forwarders)
    - [Using NSP Forwarder Generator (Online)](#using-nsp-forwarder-generator-online)
    - [Using Sphaira (Offline)](#using-sphaira-offline)
  - [Bootloader](#bootloader)
  - [Homebrew's](#homebrews)
  - [Sysmodule's (background process)](#sysmodules-background-process)
  - [Overlay's](#overlays)
  - [Payload's](#payloads)
  - [Emulator's](#emulators)
  - [Tips to avoid bans on Nintendo's servers](#tips-to-avoid-bans-on-nintendos-servers)

## Install / Update CFW

### Install

> [!TIP]
>
> If your console is **BANNED** from Nintendo's servers you don't need a `emuMMC partition`, just run the CFW on `Semi-stock (sysMMC_CFW)`

- Format your microSD to FAT32 using [guiformat.exe (Program only for Windows)](http://ridgecrop.co.uk/guiformat.exe).
- Copy all the files from **SuperRockerNX.vx.x.x.rar** into your microSD.
- Keep in mind the [information here](https://switch.hacks.guide/user_guide/all/cfw_environment.html), to know more about SysMMC, SysCFW, EmuMMC.
- Create a [backup](https://switch.hacks.guide/user_guide/all/making_essential_backups.html) or [restore](https://switch.hacks.guide/extras/nandrestore.html) of your **NAND** (Create a backup every time the stock system is updated to a new version).
- Partition your microSD to create a EmuMMC, [more info here](https://switch.hacks.guide/user_guide/all/partitioning_sd.html).
- Launch emuMMC from hekate's `Home` > `Launch` > `Emulated (emuMMC_CFW)`.
- Once `Emulated (emuMMC_CFW)` is launched, open your Homebrew.
  - Select Album and press `R` and `A` buttons simultaneously to open Homebrew.
  - If you want to restore Homebrew as the default instead of Album, delete the file `sdmc:\atmosphere\config\override_config.ini`.
  - By default this method run as [applet mode](https://gbatemp.net/threads/how-to-change-applet-mode-hbmenu.546735/post-8767570).
- Open DBI > `Browse SD Card` > `nsp` > hbmenu [xxxxxxxxxxxxxxxx].nsp / sphaira [xxxxxxxxxxxxxxxx].nsp > `Install target` (**select SD**) > `Start install`.
  - From now on, you can launch your Homebrew applications with `(nx-hbmenu) Homebrew Menu` or `(Sphaira), an alternative to nx-hbmenu` using a [shortcut/forwarder](#forwarders).
- Follow the process to [dump your product keys](#dump-product-keys-lockpick_rcm)

### Update

> [!WARNING]
>
> - Some settings from your Homebrew applications will be lost when installing clean or dirty, so keep in mind.

---

> [!CAUTION]
>
> - After any of those options follow the process to [dump your product keys](#dump-product-keys-lockpick_rcm) again.

- Clean update
  - Delete all the files on your microSD ignoring **`emuMMC`** and **`Nintendo`** folders or other optional to ignore like `roms`, `emuiibo`, `mGBA`, `mods`, `themes` if you have added anything to those folders.
- Dirty update
  - Copy all the files from **SuperRockerNX.vx.x.x.rar** into your microSD, replacing all files.

## Dump product keys (Lockpick_RCM)

> [!TIP]
>
> Your product keys will be saved in **sdmc:/switch/** as **prod.keys** and **title.keys**, these are unique to your console, so **keep them safe and never share them**.

---

> [!IMPORTANT]
>
> - You will need to do this procedure again when you [update your console firmware](#update-console-firmware).

To have full access in some homebrew, **dump your SysNAND** keys. You have 3 methods to do that:

- Access to hekate's `Home` > `More Configs` > `Lockpick RCM` > `Dump from sysNAND`.
- Access to hekate's `Home` > `Payloads` > `Lockpick_RCM.bin` > `Dump from sysNAND`.
- Access to hekate's `Console Info` > `Lockpick` > `Continue` > `Dump from sysNAND`.

## Update console firmware

> [!NOTE]
> Only for older emuMMC firmware versions, otherwise ignore.

### Local source - Dump update from sysMMC

> [!WARNING]
>
> - You'll need your [product keys dumped](#dump-product-keys-lockpick_rcm).

- Follow the [CFW Update](#update) instructions for the last supported HOS
- Update your `Stock (sysMMC)` first using Nintendo's servers THEN turn **ON** `Airplane Mode`.
- Access to hekate's `Home` > `Launch` > `Semi-stock (sysMMC_CFW)`.
- Select Album and press `R` and `A` buttons simultaneously to open Homebrew.
- Open `nxdt_rw_poc` > `dump system update` > `start dump` > `Press any button when the process is finished`.
- Launch emuMMC from hekate's `Home` > `Launch` > `Emulated (emuMMC_CFW)`.
- Open `Homebrew Menu (nx-hbmenu)` > `Daybreak`
- Press > `Install` > `nxdt_rw_poc` > `System Update` > `NintendoSDK Firmware for NX xx.x.x-x.x (Prod)` > `Continue` > `Preserve settings` > `Install (FAT32 + exFAT)` > `Continue` > `Reboot`
- After reboot you can delete the software update files (Optional)

### External source - From github repository

- Follow the [CFW Update](#update) instructions for the last supported HOS
- [Download](https://github.com/THZoria/NX_Firmware/releases) the last update supported with HOS
- Extract `Firmware.x.x.x.zip` on a folder named `Firmware.x.x.x` and copy that folder to **sdmc:\\**
- Open `Homebrew Menu (nx-hbmenu)` > `Daybreak`
- Press > `Install` > `Firmware.x.x.x` > `Continue` > `Preserve settings` > `Install (FAT32 + exFAT)` > `Continue` > `Reboot`
- After reboot you can delete the software update files (Optional)

## Forwarders

> [!TIP]
>
> You can add more **NSP, NSZ, XCI or XCZ** files on **sdmc:\nsp**.

---

> [!CAUTION]
>
> Never install a shortcut/forwarder on `Stock (sysMMC)` if you're not banned from Nintendo's servers, just install them on `Emulated (emuMMC_CFW)`

Create shortcuts/forwarders for your [Homebrew's](#homebrews) and RetroArch games directly on the **home screen**.

**The advantage**: Your Homebrew shortcut/forwarder will always run outside of [applet mode](https://gbatemp.net/threads/how-to-change-applet-mode-hbmenu.546735/post-8767570), if you need to run out of `applet mode` without a shortcut/forwarder hold `R` and open a any installed game.

### Using NSP Forwarder Generator (Online)

> [!NOTE]
>
> You'll need a **prod.keys** file for your HOS firmware version, which can be obtained [using this](#dump-product-keys-lockpick_rcm) or downloaded from [this source (I prefer this one)](https://prodkeys.net/).

- Open [NSP Forwarder Generator](https://nsp-forwarder.n8.io/) on your favorite browser.
- Click on `Click to select NRO or image file…` and search the .nro file, after that `App Title` and `Publisher` will be auto filled.
- `NRO Path` need the real path on sd for example `\switch\daybreak.nro`.
- Click on `Click to select your 'prod.keys' file…` and search the `prod.keys` file.

### Using Sphaira (Offline)

> [!TIP]
>
> If you're banned from Nintendo's servers you can enable `Enable sysmmc (On)` instead of `Enable emummc (On)`.

- Open your homebrew launcher, `nx-hbmenu`, to launch `Sphaira` or even `Sphaira` itself.
- On `Sphaira` press `Y` > `Advanced` > `Install options` > `Enable emummc (On)` > `Show install warning (Off)`.
- Press `B` until you are at the `Sphaira` main menu.
- Place the cursor on the homebrew application you want to make a shortcut/forwarder and press `X` > `Install Forwarder`
- Go to the main menu of the console and the new shortcut/forwarder will be there.

## Bootloader

> [!NOTE]
>
> Files located on sdmc:\

- [Hekate (v6.3.1)](https://github.com/CTCaer/Hekate/releases/)
- [Atmosphere (v1.9.2)](https://github.com/Atmosphere-NX/Atmosphere/releases)
- hekate_ctcaer_(version).bin > payload.bin (Included with Hekate)

## Homebrew's

> [!NOTE]
>
> Files located on sdmc:\switch

- Daybreak (Included with Atmosphere)
- Haze (Included with Atmosphere)
- Reboot to Payload (Included with Atmosphere)
- nx-hbmenu (Included with Atmosphere)
- nx-hbloader (Included with Atmosphere)
- Breeze (Included with EdiZon-SE)
- ldnmitm_config (Included with ldn_mitm)
- [sphaira (v0.13.3)](https://github.com/ITotalJustice/sphaira/releases)
- [Neumann (v0.0.29)](https://github.com/turtle-insect/Neumann/releases)
- [NX Save Sync (2.2.0)](https://github.com/Xc987/NX-Save-Sync/releases)
- [NX-Shell (v4.01)](https://github.com/joel16/NX-Shell/releases)
- [vgedit+ (v2.2.1)](https://github.com/vgmoose/vgedit/releases)
- [switch-90dns-setter (v1.0.0)](https://github.com/suchmememanyskill/switch-90dns-setter/releases)
- [Switch_90DNS_tester (v1.0.4)](https://github.com/meganukebmp/Switch_90DNS_tester/releases)
- [DBI (v658)](https://github.com/rashevskyv/dbi/releases)
- [Goldleaf (1.1.1)](https://github.com/XorTroll/Goldleaf/releases)
- [nxdumptool (Oct 15, 2023)](https://github.com/DarkMatterCore/nxdumptool/releases)
- [Hekate-Toolbox v4.0.3](https://github.com/WerWolv/Hekate-Toolbox/releases)
- [Linkalho (v2.0.1)](https://gbatemp.net/download/linkalho.38822/)
- [Battery Desync Fixer NX (v1.5.0)](https://github.com/CTCaer/battery_desync_fix_nx/releases)
- [SwitchIdent (v0.5)](https://github.com/joel16/SwitchIdent/releases)
- [SimpleModManager (v2.1.2)](https://github.com/nadrino/SimpleModManager/releases)
- [ipswitch (0.2.2)](https://github.com/3096/ipswitch/releases)
- [SwitchThemeInjector (4.8.1)](https://github.com/exelix11/SwitchThemeInjector/releases)
  - [theme-patches (Support for 20.2.0)](https://github.com/exelix11/theme-patches)
- [NX-Activity-Log (v1.5.7)](https://github.com/zdm65477730/NX-Activity-Log/releases)
- [Amiigo/Emuiibo (2.3.2)](https://github.com/CompSciOrBust/Amiigo/releases)
- [AmiiboGenerator (v2.1.1)](https://github.com/Slluxx/AmiiboGenerator/releases)
- [SimpleModDownloader (v2.2.0)](https://github.com/PoloNX/SimpleModDownloader/releases)
- [AIO-Switch-Updater (v2.23.2)](https://github.com/HamletDuFromage/aio-switch-updater/releases)
- [switch_internal_speakers_nro (v1.0.0)](https://github.com/paulocode/switch_internal_speakers_nro/releases)
- [untitled (v1.3.0)](https://github.com/ITotalJustice/untitled/releases)
- [Reset-Parental-Controls-NX (v1.2.0)](https://github.com/MCMi460/Reset-Parental-Controls-NX/releases)

## Sysmodule's (background process)

> [!NOTE]
>
> Files usually located on sdmc:\atmosphere\contents

- [Sys-patch (v1.5.6)](https://github.com/impeeza/sys-patch/releases)
- [MissionControl (v0.13.3)](https://github.com/ndeadly/MissionControl/releases)
- [sys-con (v1.5.4)](https://github.com/o0Zz/sys-con/releases)
- [SaltyNX (1.3.1)](https://github.com/masagrator/SaltyNX/releases)
- [nx-ovlloader+ (v1.1.0)](https://github.com/ppkantorski/nx-ovlloader/releases)
- [sys-clk (v2.0.1)](https://github.com/retronx-team/sys-clk/releases)
  - [sys-clk 2.0.1+r9](https://github.com/ppkantorski/sys-clk/releases)
- [EdiZon-SE (v3.8.37)](https://github.com/tomvita/EdiZon-SE/releases)
- [Fizeau (v2.8.1+)](https://github.com/ppkantorski/Fizeau/releases)
- [emuiibo (v1.1.1)](https://github.com/XorTroll/emuiibo/releases)
- [sys-ftpd-light-reboot (v4.0.1-reboot)](https://github.com/ThemezerNX/sys-ftpd-light-reboot/releases)
- [ldn_mitm (v1.19.0)](https://github.com/spacemeowx2/ldn_mitm/releases)

## Overlay's

> [!NOTE]
>
> - Press `L` + `DPAD Down` + `R Stick (R3)` to open Ultrahand-Overlay
> - Files located on sdmc:\switch\.overlays

- [Ultrahand-Overlay (v1.10.0)](https://github.com/ppkantorski/Ultrahand-Overlay/releases)
- [FPSLocker (v2.2.1)](https://github.com/masagrator/FPSLocker/releases)
- [Status Monitor Overlay (1.1.9)](https://github.com/masagrator/Status-Monitor-Overlay/releases)
  - [Status Monitor Overlay 1.1.9+r7](https://github.com/ppkantorski/Status-Monitor-Overlay/releases)
- [EdiZon-Overlay (v1.0.10)](https://github.com/proferabg/EdiZon-Overlay/releases)
- [ovl-sysmodules (v1.3.6)](https://github.com/ppkantorski/ovl-sysmodules/releases)
- [TextReaderOverlay-NX (v1.1)](https://github.com/diwo/TextReaderOverlay-NX/releases)
- [QuickNTP (v1.5.1)](https://github.com/nedex/QuickNTP/releases)
- [LANHelper-Tesla (v1.1.0) (DON'T USE 'Reset IP Config' BUTTON)](https://github.com/matthew-5pl/LANHelper-Tesla/releases)
- sys-clk-overlay (Included with sys-clk)
- Fizeau (Included with Fizeau)
- emuiibo (Included with emuiibo)
- Nx-FanControl (Included with NX-FanControl)
- sys-patch-overlay (Included with Sys-patch)
- ldnmitm_config (Included with ldn_mitm)

## Payload's

> [!NOTE]
>
> Files located on sdmc:\bootloader\payloads

- [CommonProblemResolver (CPR) (v0.3.5)](https://github.com/Team-Neptune/CommonProblemResolver/releases)
- [picofly_toolbox (v0.2)](https://github.com/Ansem-SoD/Picofly/tree/main/Firmwares)
- [TegraExplorer (v4.2.0)](https://github.com/suchmememanyskill/TegraExplorer/releases)
- [Lockpick_RCM (v1.9.15)](https://gbatemp.net/download/lockpick_rcm-1-9-15-fw-20-zoria.39129/)

## Emulator's

- [MGBA (v0.10.5)](https://github.com/mgba-emu/mgba/releases)
- [PPSSPP (1.17.x) (Run it out of applet mode)](https://www.ppsspp.org/legacybuilds/)

## Tips to avoid bans on Nintendo's servers

- To safely launch `Semi-stock (sysMMC_CFW)`, ensure Wi-Fi is turned **OFF** in `Stock (sysMMC)` beforehand.
- Verify if your console serial number is a set of zeros, `Emulated (emuMMC_CFW)` or `Semi-stock (sysMMC_CFW)` > `Open System Settings` > `System` > `Console serial number` before connecting to the internet.
- Never install a [`Forwarder`](#forwarders), `NSP`, `NSZ`, `XCI`, or `XCZ` files on `Semi-stock (sysMMC_CFW)`
- Use `Switch_90DNS_tester` [homebrew](#homebrews) to see if the console can reach Nintendo's servers (**You will see a list with `blocked` if you see a list with `unblocked` DO NOT CONNECT TO THE INTERNET**).
- Use `switch-90dns-setter` [homebrew](#homebrews) to block Nintendo's servers after connecting to a new Wi-Fi network.
- Turn **OFF** Wi-Fi or turn **ON** `Airplane Mode` if you don't need an internet connection on `Emulated (emuMMC_CFW)`.
