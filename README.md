# How to run your favorite PlayStation 2 games from an HDD
This guide is mainly written for myself, I encountered countless different tutorials on how to accomplish this, which tools to use, etc. 
My main objective is to give a short summary for others who are seeking to do the same.

## Hardware
- You can use any HDD/SSD up to 2TB!
- Purchase the expansion module which is used to connect your HDD to the [PS2's system](https://www.amazon.com/Kaico-Playstation-Adapter-Expansion-Running/dp/B071ZQ2PMR)
- Purchase a memory card with [Free McBoot 1.966+](https://www.amazon.com/McBoot-1-966-memory-Playstation-Kaico-2/dp/B06XB16TDY)
- A simple [SATA to USB cable](https://www.amazon.com/StarTech-com-SATA-USB-Cable-USB3S2SAT3CB/dp/B00HJZJI84/ref=sr_1_3?crid=29JV2IMDKBVZG&keywords=sata%2Bto%2Busb&qid=1694791648&sprefix=sata%2Bto%2Bus%2Caps%2C271&sr=8-3&th=1), so you can connect directly to your HDD - highly recommended, so you do not need to transfer new games via USB 1.1

## Tools
You will need various tools to
- Rename your iso/bin (for PS1 games) files to something appropriate (has to be recognized by Open PS2 Loader)
- Import game art (if you wish)
- Merge PSX bin files
- Convert PSX cue files to VCD
- POPStarter emulator files (google them) to run PSX games

My favorite for anything PS2 related is [HDL-Batch-Installer](https://github.com/israpps/HDL-Batch-installer/releases), it allows you to
- Directly install any PS2 iso to your harddrive (multiple at a time)
- Format your HDD to use the PS2's filesystem
- Directly mount any partition in your HDD
- Create new partitions
- Move over PSX games directly to the appropriate partition

## Using the PS2 with the new hardware
- Remove any existing memory cards, only insert the Free McBoot memory card
- Attach your HDD to the expansion module, insert it into the PS2 (fat model), tighten the screws

## Booting
The PS2's boot menu will be enriched with various new options thanks to the Free McBoot software:

- Browser: As before, views your memory cards
- System Config: As before, remember to set component mode if you are using component cables
- uLaunchELF: A file manager which can be used to launch games directly, e.g PSX games, PS2, GameBoy, etc.
- Open PS2 Loader: Management app for your PS2 games & apps
- etc...

## Install & Run

### PS2 Games
- Ensure your HDD is formatted to the PS2's filesystem
- Ensure your HDD could be loaded in the HDL Batch Installer
- Install any game
- Launch your game from Open PS2 Loader

### PS1 Games
- Ensure your HDD is formatted to the PS2's filesystem
- Ensure your HDD could be loaded in the HDL Batch Installer
- Find and download POPS.ELF & IOPRP252.IMG
- Mount the __common partition to a local drive
	- Create a directory named POPS, paste POPS.ELF and IOPRP252.IMG into this folder
- Create a partition for __.POPS
- Mount __.POPS to a local drive
- Merge your PSX bin files using [psx-comBINe](https://github.com/ADBeta/psx-comBINe/releases)
- Convert to VCD using [cue2pops](https://github.com/israpps/cue2pops/releases)
- Rename VCD's using OPL Manager (fetch title from database - then rename to the official 'ID:TITLE')
- Copy+Paste the VCD to your __.POPS directory
- Update uLaunchELF to a version which supports running .VCD's directly (overwrite BOOT.elf), copy the file from a USB stick
- Update Open PS2 Loader (overwrite OPNPS2LD.ELF with the latest version), copy the file from a USB stick
- Launch directly via file manager, navigate to the __.POPS dir, have fun!

### GameBoy, GameBoy Color & GameBoy Advance emulator
- Easily loaded directly via USB
- Download ReGBA & TempGBA
- Load either through the file manager
- Add ROMS to ex: root/ROMS/GBA - navigate to your roms from the emulator
- Enjoy!
