# My switch CFW

A CFW for Nintendo Switch, designed as an offline pack and intended for ModChips with Picofly.
Based on [NH Switch Guide](https://switch.hacks.guide).

> [!IMPORTANT]
>
> - **Latest HOS supported: 19.0.1**
> - [FORMAT YOUR SDCARD TO FAT32 USING (REQUIRED) (Windows only)](http://ridgecrop.co.uk/guiformat.exe)
> - [Don't forget to flash your ModChip](https://github.com/Ansem-SoD/Picofly)

## Table of Contents

- [My switch CFW](#my-switch-cfw)
  - [Table of Contents](#table-of-contents)
  - [Features](#features)
  - [Bootloader](#bootloader)
  - [Homebrew's](#homebrews)
  - [sysmodule (background process)](#sysmodule-background-process)
  - [Overlay's](#overlays)
  - [PAYLOADS](#payloads)
  - [Emulators](#emulators)

## Features

> [!IMPORTANT]
>
> - To ensure full access to certain applications, you must perform a **Dump from SysNAND** using **Lockpick_RCM**.
> - Always backup your keys safely in case they are needed for future use.
> - Avoid sharing your dumped keys, as they are unique to your console.
> - Backup files are saved in **sdmc:\switch** as **prod.keys** and **title.keys**

- **Overlay Menus Management:** Managed by **Ultrahand** and **nx-ovlloader**, Press **ZL + ZR + D-Pad Down** to open the overlay.
- **90dns Tools:** Use the **90dns Setter** to block specific servers and the **90DNS Testing Utility** to verify connectivity.
- **Install Game Files:** Use **DBI** or **Awoo Installer** to install `NSP`, `NSZ`, `XCI`, or `XCZ` files.
- **Battery Calibration:** Fix battery desync issues with the **Battery Desync Fix NX** tool.
- **Game Cheats:** Apply cheats to your games with **Edizon SE**, **Breeze**, **EdiZon-Overlay**, **SaltyNX**.
- **Screen Color Adjustment:** Use **Fizeau** to tweak and adjust your screen's color profile.
- **Hekate Settings Management:** Manage settings easily with the **Hekate Toolbox**.
- **Patch Management:** Use **IPSwitch** to convert and manage `.pchtxt` files into `.ips` extension.
- **Save Management:** Handle your game saves efficiently with **JKSV**.
- **Offline NNID Linking:** Use **Linkalho** to link NNID accounts without an internet connection.
- **Activity Log:** Track detailed playtime and activity data with **NX Activity Log**.
- **File Management:** Manage your files with the versatile **NX-Shell** file manager.
- **Title Dumping:** Dump installed titles using **nxdt_rw_poc**.
- **Games Mods Management:** Organize and apply mods via LayeredFS using **SimpleModManager**.
- **Device Information:** Retrieve device information with **SwitchIdent**.
- **Performance Tuning:** Overclock or underclock your device with **sys-clk manager**.
- **Console Emulation:** Emulate games from supported systems with **mGBA** or **PPSSPP (GL)**.
- **Troubleshooting & Fixes:** Use **CommonProblemResolver (CPR)** to diagnose and resolve common issues on your system.
- **Picofly Tools:** Use **picofly_toolbox** to manage settings and configurations for **Picofly** hardware.
- **File & NAND Exploration:** Access system files and partitions with **TegraExplorer**.
- **Key Dumping:** Extract system encryption keys using **Lockpick_RCM** for decryption and modding purposes.
- **Frame Rate Adjustment:** Use **FPSLocker** to modify and unlock frame rates in supported games for a smoother experience.
- **System Monitoring Overlay:** Keep track of real-time system stats like CPU, GPU, RAM usage, and temperature with **Status Monitor Overlay**.
- **Sysmodule Management:** Enable, disable, and manage system modules on the fly using **ovl-sysmodules**, without needing to reboot.
- **Fan Control**: Use **NX-FanControl** to manually adjust the fan speed of your device, helping you manage temperature and noise levels.
- **Emulated Amiibo**: Use **emuiibo** to emulate Amiibo functionality, allowing you to unlock content in compatible games without needing the physical figures.
- **System Patches:** Use **Sys-patch** to automatically apply patches to critical system services on boot, improving system compatibility and functionality.
- **Third-Party & Bluetooth Controller Support:** Use **Mission Control** to connect controllers from other consoles via Bluetooth without needing dongles or adapters, and **sys-con** to enable USB support for third-party controllers without additional hardware.

## Bootloader

> [!NOTE]
>
> Files located on sdmc:\

- [Hekate (v6.2.2)](https://github.com/CTCaer/Hekate/releases/)
- [Atmosphere (v1.8.0-prerelease)](https://github.com/Atmosphere-NX/Atmosphere/releases)
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
- [JKSV (11/05/2024)](https://github.com/J-D-K/JKSV/releases)
- [NX-Shell (v4.01)](https://github.com/joel16/NX-Shell/releases)
- [switch-90dns-setter (v1.0.0)](https://github.com/suchmememanyskill/switch-90dns-setter/releases)
- [Switch_90DNS_tester (v1.0.4)](https://github.com/meganukebmp/Switch_90DNS_tester/releases)
- [DBI (v658)](https://github.com/rashevskyv/dbi/releases)
- [Awoo Installer (1.3.5)](https://github.com/Huntereb/Awoo-Installer/releases)
- [nxdumptool (Oct 15, 2023)](https://github.com/DarkMatterCore/nxdumptool/releases)
- [Hekate-Toolbox v4.0.3](https://github.com/WerWolv/Hekate-Toolbox/releases)
- [Linkalho (v2.0.1)](https://gbatemp.net/download/linkalho.38822/)
- [Battery Desync Fixer NX (v1.5.0)](https://github.com/CTCaer/battery_desync_fix_nx/releases)
- [SwitchIdent (v0.5)](https://github.com/joel16/SwitchIdent/releases)
- [SimpleModManager (v2.1.2)](https://github.com/nadrino/SimpleModManager/releases)
- [ipswitch (0.2.2)](https://github.com/3096/ipswitch/releases)
- [NX-Activity-Log (v1.5.4)](https://github.com/zdm65477730/NX-Activity-Log/releases)

## sysmodule (background process)

> [!NOTE]
>
> Files usually located on sdmc:\atmosphere\contents

- [Sys-patch (v1.5.5)](https://github.com/impeeza/sys-patch/releases)
- [MissionControl (v0.12.0)](https://github.com/ndeadly/MissionControl/releases)
- [sys-con (v0.6.5)](https://github.com/cathery/sys-con/releases)
- [SaltyNX (1.2.0)](https://github.com/masagrator/SaltyNX/releases)
- [nx-ovlloader+ (v1.0.9)](https://github.com/ppkantorski/nx-ovlloader/releases)
- [sys-clk (v2.0.1)](https://github.com/retronx-team/sys-clk/releases)
- [NX-FanControl (v1.0.3)](https://github.com/Zathawo/NX-FanControl/releases)
- [EdiZon-SE (v3.8.37)](https://github.com/tomvita/EdiZon-SE/releases)
- [Fizeau (v2.8.1)](https://github.com/averne/Fizeau/releases)
- [emuiibo (v1.1.1)](https://github.com/XorTroll/emuiibo/releases)

## Overlay's

> [!NOTE]
>
> Files located on sdmc:\switch\.overlays

- [Ultrahand-Overlay (v1.8.2)](https://github.com/ppkantorski/Ultrahand-Overlay/releases)
- [FPSLocker (v2.1.0)](https://github.com/masagrator/FPSLocker/releases)
- [Status Monitor Overlay (1.1.7a)](https://github.com/masagrator/Status-Monitor-Overlay/releases)
- [EdiZon-Overlay (v1.0.9)](https://github.com/proferabg/EdiZon-Overlay/releases)
- [ovl-sysmodules (v1.3.1)](https://github.com/WerWolv/ovl-sysmodules/releases)
- sys-clk-overlay (Included with sys-clk)
- Fizeau (Included with Fizeau)
- emuiibo (Included with emuiibo)
- Nx-FanControl (Included with NX-FanControl)
- sys-patch-overlay (Included with Sys-patch)

## PAYLOADS

> [!NOTE]
>
> Files located on sdmc:\bootloader\payloads

- [CommonProblemResolver (CPR) (v0.3.5)](https://github.com/Team-Neptune/CommonProblemResolver/releases)
- [picofly_toolbox (v0.2)](https://github.com/Ansem-SoD/Picofly/tree/main/Firmwares)
- [TegraExplorer (v4.2.0)](https://github.com/suchmememanyskill/TegraExplorer/releases)
- [Lockpick_RCM (v1.9.13)](https://github.com/saneki/Lockpick_RCM/releases)

## Emulators

- [MGBA (v0.10.4)](https://github.com/mgba-emu/mgba/releases)
- [PPSSPP (1.17.x) (Run it out of applet mode, using `R` button while opening a game)](https://www.ppsspp.org/legacybuilds/)
