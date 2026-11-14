# Arch R changelog

Every change to the system, the launcher, the Arch R Flasher and arch-r.io,
newest first. The site shows it at https://arch-r.io/changelog/.

<!--
Format, checked by `npm run changelog:check` and by the site build:

  ## <label> (<YYYY-MM-DD>)
  - [<tag>] <text>;

label: v3.0.1      a release with images
       20261111.1  a console update (Settings › System › Updates), the id the
                   update's changelog.txt starts with
       site        changes to arch-r.io only, on a day with no console update
tag:   system, launcher, web, flasher

Newest block first; dates never go up further down. Add entries with
`node scripts/changelog.mjs add <tag> "<text>" --block <label>`.
-->

## 20261114.3 (2026-11-14)
- [launcher] fix games copied from a PC not showing up until something was downloaded on the console;

## 20261114.2 (2026-11-14)
- [system] fix the battery reading 0% after a charge taken with the console off;
- [system] fix the battery draining while the console is off;

## 20261114.1 (2026-11-14)
- [system] fix arcade games in .7z: they open in FinalBurn Neo, MAME 2003-Plus reads only .zip;
- [system] fix error reports for Weston-runtime ports that run fine;
- [system] fix controls in older PortMaster ports that use oga_controls;
- [system] fix unified storage, refused since the move to mergerfs;
- [system] fix empty error reports when the console is turned off right after one is made;
- [system] fix Solarus games from PortMaster: physfs added, system LuaJIT used;
- [system] fix 32-bit GameMaker ports that do not bring libzip;

## 20261114 (2026-11-14)
- [system] fix a port deleted without restarting leaving its save folder mounted, breaking the next port that uses the same place (Sword of Jade);

## 20261113.12 (2026-11-13)
- [launcher] fix the launcher not coming back when the screen stays off after the UI restarts; sway is restarted;
- [launcher] fix module covers in SVG (PortMaster, NFS, file manager, m8c, rclone backup) not showing;

## 20261113.11 (2026-11-13)
- [system] fix error reports sent for GameMaker ports that run fine (optional sound module probe) and for the NextOS splash screen;
- [web] new page: arch-r.io/update explains how to update over the network or from the card, and lists every offline update to download with its size, SHA-256 and notes;

## 20261113.10 (2026-11-13)
- [system] ports on PortMaster's Weston runtime that show a message first (unpacking on the first run) no longer stay on it: the game shows;

## 20261113.9 (2026-11-13)
- [system] ports that use gl4es (Perfect Dark and others) no longer crash at start with MangoHud on;

## 20261113.8 (2026-11-13)
- [system] MangoHud shows in PlayStation games and other 32-bit programs on the Panfrost driver;
- [system] the MangoHud shortcut says when the Panfrost driver is needed or MangoHud is off;
- [system] on-screen notices show their text once instead of twice;
- [launcher] new feature: favorites first in each system's list (list menu, Y);

## v3.0.2 (2026-11-13)
- [system] new release: Arch R 3.0.2 images (official), with every update since 3.0.1 and update from the card from the first boot;

## 20261113.7 (2026-11-13)
- [system] fix a launcher-only update leaving its session unit stale until a restart (systemd is reloaded now);

## 20261113.6 (2026-11-13)
- [launcher] fix game scraping (ScreenScraper) without the project's login: the launcher updates 20261113.4 and .5 were built without it;

## 20261113.5 (2026-11-13)
- [system] new feature: update without network: download archr-update.tar on a phone or computer, copy it to roms/update/ on the card and install it from Settings › System › Updates; it is checked against Arch R's signature first;
- [launcher] new feature: Update from the card on the Updates page, with the file's What's new and a confirmation;

## 20261113.4 (2026-11-13)
- [launcher] new feature: send the last diagnostic report to the developers from Settings › System › Diagnostics (it asks first), and see this console's ID in Error reports;
- [system] new feature: every console has a stable ID taken from its hardware, carried in its error reports so reports from one console can be told apart;
- [web] error reports now accept the console ID in their name and the full diagnostic report (.zip, up to 5 MB);

## 20261113.3 (2026-11-13)
- [system] fix PortMaster ports printing "tasksetter: No such file or directory" on start (FEZ and other older ports);
- [system] fix false error reports for GameMaker ports waiting for the user's game files and for Unity games' offline analytics message;

## 20261113.2 (2026-11-13)
- [system] fix system files that only a new image could update (controller setup, CPU speed settings, R36S Clone headphone switch, boot trace): updates now bring them too, so fewer fixes need a reflash;

## 20261113.1 (2026-11-13)
- [system] fix updates failing on weak Wi-Fi: a dropped or stalled download is tried again, up to three times, and resumes where it stopped;

## 20261113 (2026-11-13)
- [system] fix memory leak: each game or app opened left about 4 MB of video memory behind until reboot;

## 20261112.6 (2026-11-12)
- [system] fix 32-bit GameMaker ports that need OpenSSL 1.1 (Climb and others on gmloader): they closed at once with "wrong ELF class";

## 20261112.5 (2026-11-12)
- [system] fix Wi-Fi after a restart: a failed first connect is retried within seconds instead of leaving the console offline for up to 30 minutes;
- [launcher] fix the screen not coming up after a restart (seen once after a GPU driver switch): the session now brings the display back;
- [launcher] new feature: ports that need the panfrost GPU driver (Bugdom, BZFlag, A7Xpg) ask to switch the driver and restart instead of closing with an error;
- [system] fix ports that use gl4es drawing nothing on the panfrost driver;

## 20261112.4 (2026-11-12)
- [system] fix ports that need libfribidi (Aleph One: Marathon 1, 2 and Infinity): the shared library is now installed;

## 20261112.3 (2026-11-12)
- [system] fix ports on PortMaster's Weston package (Alex the Allegator and ~75 more): they now open, and the launcher comes back instead of a black screen;

## 20261112.2 (2026-11-12)
- [system] error reports: quitting a port that prints a stack trace on exit (Carmageddon) no longer sends a report;

## 20261112.1 (2026-11-12)
- [system] fix 0% on a full battery: the gauge now calibrates to full when an external charger holds the pack full (R36S and clones);
- [system] error reports: the game file's size, space on the card and first bytes;

## 20261112 (2026-11-12)
- [system] fix N64 games kept in a .7z not opening with the standalone emulator ("not a valid ROM image");
- [system] error reports: a game's command line stays whole; no report for PICO-8 before its program is copied in, nor for a screen that comes a few seconds late at boot;
- [web] overlay generator: fix the black screen on R36S Soysauce Y3506 V06 (2026 boards), whose new panel stayed in standby; generate the overlay again;

## 20261111.3 (2026-11-11)
- [system] error reports: a port that writes its own log (NextOS ports and many others) sends the error lines from it; a port's report no longer loses everything after a line like SCRIPT_DIR="$(cd ... && pwd)";
- [system] NextOS ports: opening one before its APK is in place no longer sends an error report;
- [web] PortMaster docs: NextOS Universal Ports, how to add their catalogue;
- [web] PortMaster docs: the NextOS catalogue checked library by library (42 packages, 32-bit included);

## 20261111.2 (2026-11-11)
- [system] fix Dreamcast, Atomiswave and Naomi discs in a .zip or .7z named after the archive (Hero.zip holding Hero.chd) closing at once;
- [web] overlay generator: R36S clones keep the amplified sound card by default again; the switch to the simple card in 20261111 also moved boards whose speaker works on the amplified one (#51, #43); the V20 2551 uses Force simple audio routing, now in the docs;

## 20261111.1 (2026-11-11)
- [system] new feature: Dreamcast, Atomiswave and Naomi discs kept in a .zip or .7z (GDI, CDI, CHD or CUE) play; the console extracts the disc once, with a "Preparing the disc" message, and opens it right away the next times;
- [system] fix the 7z command in the terminal ("cannot find the code that works with archives");
- [system] fix error reports counting a core's unknown option ("Invalid value") as the cause of a failure;
- [web] new page: changelog;

## 20261111 (2026-11-11)
- [system] fix the Wi-Fi service (iwd) crashing when a USB Wi-Fi adapter drops while it is being set up (RTL8188EU on the Soysauce);
- [system] error reports no longer sent for answers: save and exit with no game open, an emulator that saves no state, an update refused for low battery or no network;
- [system] game error reports carry RetroArch's own error lines ("Failed to load content");
- [web] overlay generator: fix audio on R36S V20 2551 clones; boards with the speaker on the RK817 class-D output get the simple sound card by default;

## 20261110.9 (2026-11-10)
- [launcher] new feature: search in a system's list (Y › Search in list), ignoring accents and case, games inside folders included;
- [launcher] new feature: folders in a system's list (Y › Show folders, per system, off by default), with the number of games in each;

## 20261110.8 (2026-11-10)
- [system] R36S Clone: the headphone change of 20261110.7 is withdrawn until it is checked on a real board;

## 20261110.7 (2026-11-10)
- [system] R36S Clone (boards with an external speaker amplifier): headphones turn the speaker off;

## 20261110.6 (2026-11-10)
- [system] fix ports kept on the second microSD card not finding their own files;

## 20261110.5 (2026-11-10)
- [system] error reports cover PortMaster ports: name and version, error lines, the port's log, runtimes and missing libraries;

## 20261110.4 (2026-11-10)
- [system] new feature: anonymous error reports when a game, an app or the system fails; only with internet, the same error once, at most 10 a day; off or last report in Settings › System › Error reports;
- [web] new: the endpoint that receives the consoles' error reports;

## 20261110.3 (2026-11-10)
- [launcher] new feature: Theme store and Module store shortcuts in the Start menu, with the number of pending updates;
- [launcher] new feature: Settings › Appearance › Start shortcuts, to show, hide, move or add each shortcut;

## 20261110.2 (2026-11-10)
- [system] RetroArch: one menu (RGUI) from Tools and from games;
- [system] RetroArch: hotkeys and settings changed in its menu are kept between games;
- [launcher] Import from RetroArch also brings shaders and overlays;

## 20261110.1 (2026-11-10)
- [launcher] Ports list shows the cover, description and year of games installed by PortMaster;
- [launcher] itch.io: QR code to the game's page, updates of installed games keeping saves, downloads that resume after losing the network;

## 20261110 (2026-11-10)
- [system] fix ports copied from a PC failing when PortMaster was never opened ("control.txt: No such file or directory");
- [system] fix ScummVM logging "invalid regular expression" on each game start;

## 20261109.4 (2026-11-09)
- [launcher] new feature: module apps, with their own item in the main list and screens drawn in the theme;
- [launcher] new feature: itch.io app in the Module store: homebrew for Game Boy, GBC, GBA, NES, Mega Drive and PICO-8, and itch.io games that run through PortMaster;
- [system] PortMaster: module apps install ports through PortMaster's own installer, never over a port you have;

## 20261109.3 (2026-11-09)
- [launcher] new feature: Appearance › your own text and background colours, text-only button hints, a background picture per system;
- [web] overlay generator: new panel listing where the stock DTB differs from the Arch R base, keeping either value per item;

## 20261109.2 (2026-11-09)
- [launcher] new feature: Appearance › bold font, battery percentage on or off, box art off or resized, the selected game's picture behind the switcher;

## 20261109.1 (2026-11-09)
- [launcher] Quick menu: Sleep, Restart and Power off grouped under one divider;

## 20261109 (2026-11-09)
- [launcher] Ports list shows only each port's launch script, without helper scripts or duplicates;
- [launcher] fix games copied into a folder inside a system (gba/RPGs/) not showing up;
- [launcher] after a game, back to the list and the game you played;
- [launcher] new feature: hide systems from the list (Y › Hide system) and show them again;
- [launcher] new feature: remove a game from Recently played;

## 20261108.1 (2026-11-08)
- [launcher] Settings › Information shows the battery voltage and current on the R36S;
- [web] overlay generator: fix the R36S clone blue power LED pin (generate mipi-panel.dtbo again);
- [web] overlay generator: new option to swap A and B (ABs);

## v3.0.1 (2026-11-08)
- [system] fix R36S clones (V20, G80CA) not starting with the clone image: no LED, no screen (#51);
- [system] fix the first boot hanging after resizing the card; the resize log is written at every step;
- [system] fix the battery guard powering off a console in use at around 40%;
- [system] fix the battery reading 0% on a charged pack (#50);
- [system] lower power at idle on the menu: CPU busy 16% → 5%;
- [system] fix Wi-Fi not reconnecting after switching it off and on; Wi-Fi switched off stays off after a reboot;
- [system] Wi-Fi: no roaming scans every few seconds with band-steering routers;
- [system] updates: only the Stable channel is offered, the progress bar moves, downloaded packages are removed;
- [system] system partition grows from 4.5 GB to 6 GB; 32 GB cards recommended;
- [system] new: Sega Saturn on yabasanshiro-pirry 1.6.2, tuned for the RK3326;
- [system] the diagnostic report lists the network addresses again;
- [launcher] new feature: layouts for square (720x720) and small (480x320) screens; no text smaller than 10 pixels;
- [launcher] fix B on a module page opened from the Start menu;
- [flasher] 1.3.9: an image for the other console variant (Original or Clone) is refused;
- [web] overlay generator: fix the offline script on Windows (device tree paths);
- [web] overlay generator: keep the built-in Wi-Fi chip powered on the R36S V30;

## v3.0 (2026-11-05)
- [launcher] new: archr-launcher replaces EmulationStation, in Rust with SDL2 for 640x480: games, settings, updates, scraping, netplay, RetroAchievements, Moonlight;
- [launcher] new feature: themes (Grafite by default, Praia and Retro in the Theme store) that can change colours, fonts, icons, sounds and layouts;
- [launcher] new feature: modules (Start widgets, menu items, settings pages), sandboxed, from a signed Module store;
- [launcher] new feature: per-system emulator, core, aspect ratio, filter and autosave; BIOS check and free BIOS install (PlayStation, MSX);
- [launcher] languages: English, Brazilian Portuguese, Spanish and Russian;
- [system] new feature: ROMs on an exFAT partition (ARCHR_ROMS) that Windows, macOS and Linux open as a normal drive (#37);
- [system] new feature: save and exit with a tap on FN, game switcher, resume the last game at power on;
- [system] new feature: battery guard: warning at 10%, the game saved before powering off at 3%;
- [system] new feature: the backup includes saves and save states; a restore never overwrites a newer save;
- [system] new feature: diagnostic report with FN + L1 + R1 held 3 seconds, saved to roms/relatorios;
- [system] new feature: internet from a PC over the USB cable; USB Wi-Fi and Bluetooth adapter advisor;
- [system] N64 at full speed by default: standalone Mupen64Plus with GLideN64's performance profile;
- [system] Linux 6.12.114 with kernel fixes adapted from ROCKNIX, faster boot, Mesa 26.2.5;
- [system] fix volume starting at 100% after boot (#39);
- [system] fix the R36S Clone speaker staying silent after unplugging headphones (#35);
- [system] fix A/B swapped and Start/Select mixed up in RetroArch on GO-Super and Soysauce pads (#40);
- [system] fix Wi-Fi networks with a dot or space in the name, hidden networks and WPA2/WPA3 transition networks (#19);
