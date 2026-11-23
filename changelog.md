# Arch R changelog

Every change to the system, the launcher, the Arch R Flasher and arch-r.io,
newest first. The site shows it at https://arch-r.io/changelog/.

<!--
Format, checked by `npm run changelog:check` and by the site build:

  ## <label> (<YYYY-MM-DD>)
  > **<title>** <sentence>
  - [<tag>] <text>;

label: v3.0.1      a release with images
       20261111.1  a console update (Settings › System › Updates), the id the
                   update's changelog.txt starts with
       site        changes to arch-r.io only, on a day with no console update
tag:   system, launcher, web, flasher

The "> **<title>** <sentence>" line is optional: the block's highlight, at
most one, right under its heading. The page shows it first and sets the
block apart; keep it for the update people should not miss. Title up to 40
characters, one sentence up to 180, no "*".

Newest block first; dates never go up further down. Add entries with
`node scripts/changelog.mjs add <tag> "<text>" --block <label>`, and the
highlight with `--highlight "<title>" "<sentence>"` (with or without an
entry in the same command).
-->

## 20261123.3 (2026-11-23)
- [system] improvement: faster boot, about 3.5 s sooner to the menu (GPU driver at the start, game folders only when they change, device settings after the menu when nothing changed);

## 20261123.2 (2026-11-23)
- [system] fix: with libmali the GPU no longer runs at its turbo 650 MHz by default (600 MHz, as with panfrost);

## 20261123.1 (2026-11-23)
- [system] fix: port controls work again when PortMaster's mapper lost its run permission;

## 20261123 (2026-11-23)
- [system] new feature: the GPU can run at its rated 650 MHz, opt-in from the Performance module's GPU ceiling (600 MHz by default);
- [system] fix: the GPU frequency list shows the real rates (the 560 MHz step ran at 480);
- [system] fix: GPU driver error handling backported from newer Linux (out-of-memory games no longer leave the GPU half set up);
- [system] fix: compressed memory packs pages left unread for 5 minutes again, about a quarter smaller;
- [system] fix: sound no longer goes silent until a reboot when the console runs out of memory;

## 20261122.5 (2026-11-22)
- [system] fix: ports built on Debian or Ubuntu (Luanti) find the CA certificates for HTTPS;

## 20261122.4 (2026-11-22)
- [launcher] new feature: Settings › System › Performance gathers the CPU governor, turbo and the memory settings;
- [launcher] fix: Information shows compressed memory and RAM Plus on their own lines;

## 20261122.3 (2026-11-22)
- [system] fix: a big second card no longer holds the boot for minutes;
- [system] new feature: /roms2 points at the second card, for ports written for ArkOS;

## 20261122.2 (2026-11-22)
- [launcher] new feature: Settings › System › During a game, to stop Wi-Fi, Bluetooth, network sharing or SSH while a game runs;
- [system] new feature: compressed memory from 512 MB to 2 GB (1 GB by default) and RAM Plus, extra memory on the card;
- [system] fix: a game that brings memory to a stall is closed with a notice instead of the console restarting;
- [system] fix: PPSSPP with Vulkan chosen no longer falls back to OpenGL after a failed start;

## 20261122.1 (2026-11-22)
- [system] fix: an update on weak Wi-Fi keeps downloading while it still moves, instead of giving up after three drops;

## 20261122 (2026-11-22)
- [system] fix: the console wakes from sleep with the power button even while a game is busy;

## 20261121.2 (2026-11-21)
- [system] fix: a USB Wi-Fi dongle (RTL8723BU) sending garbage no longer freezes and restarts the console;

## 20261121.1 (2026-11-21)
- [launcher] new feature: Settings › Launcher (resync games, remove missing games, show empty systems, clear cover cache, open on at power on, hidden systems, recent games, restart, restore settings, log, version);

## 20261121 (2026-11-21)
- [system] fix: PortMaster's full installer no longer ends with an error (its EmulationStation restart now succeeds);

## 20261120.1 (2026-11-20)
- [system] fix: on Panfrost, ports that bundle gl4es run on Mesa's own OpenGL (issue #65, thanks JoseskVolpe);
- [launcher] new feature: a port that runs only on libmali (Billy Frontier) offers to switch the GPU driver when opened on Panfrost;

## 20261120 (2026-11-20)
- [launcher] fix: the per-system "Auto save" option is now "Continue where you left"; it only chooses whether a game starts from the state saved on exit;
- [web] fix: launcher docs describe "Continue where you left" and no longer say Resume needs it;

## 20261119.11 (2026-11-20)
- [system] fix: DuckStation no longer closes a few seconds into a game when Vulkan is picked (runs on OpenGL);
- [system] fix: GTA III closing normally no longer counts as a failure in error reports;
- [system] fix: a file left in the system by a port no longer blocks updates (set aside in .config/archr-update-moved);
- [system] fix: an RTL8723BU dongle that keeps dropping off a loose hub or OTG adapter no longer crashes the console;
- [system] fix: an RTL8188EU dongle that drops off while connecting no longer crashes the console;
- [system] fix: Cuphead and other ports started with setsid --fork --wait no longer close at once;
- [system] fix: an error report is no longer sent twice when the server answer is lost;
- [system] fix: an RTL8188EU dongle rejoining the network after sleep no longer crashes the console;
- [system] fix: a game closed with the exit shortcut no longer counts as out of memory because of an earlier game;
- [system] fix: an update from a file installs on a console whose clock went back to an old date;
- [system] fix: PPSSPP no longer offers Vulkan where it cannot start (picking it closed the game);

## 20261119.10 (2026-11-19)
- [system] fix: Kodi ports built for ROCKNIX no longer stop on a missing liblcms2.so.2 (shared lcms2 library);
- [system] fix: TrackWerk and KOReader closing normally no longer send error reports;

## 20261119.9 (2026-11-19)
- [system] fix DuckStation closing seconds into every game on panfrost (PanVK only for its Vulkan renderer); its errors reach the error report;
- [system] fix GPU mode flipping every few seconds while playing on the charger (R36S and clones);

## 20261119.8 (2026-11-19)
- [system] flock waits with -w (Cuphead, Wonder Boy); flock and ionice now come from util-linux;
- [system] German and Chinese messages for port runtimes, save sync conflicts and the MangoHud key;

## 20261119.7 (2026-11-19)
- [system] ports made for dArkOS/ArkOS find maxperf, normperf, perfmax, perfnorm, show_splash.sh and lspci (Jedi Outcast, XFCE desktop);
- [launcher] fix game menu values cut short when their label is short;

## 20261119.6 (2026-11-19)
- [system] faster standalone PSP: four PPSSPP settings back to PPSSPP's defaults (once; your own values stay);
- [launcher] game menu shows (RetroArch) or (standalone) next to the core on systems with both;

## 20261119.5 (2026-11-19)
- [system] fix GBA games on Mednafen closing after a few seconds when no gba_bios.bin is in the BIOS folder;

## 20261119.4 (2026-11-19)
- [system] new feature: CPU and GPU voltages for modules, from the next boot, with a watchdog over the whole boot and the stock voltages back after two hangs;
- [launcher] new feature: Modules row in the library, after Tools, with the modules that have a page;
- [launcher] new feature: Performance and chip 0.3.0 gets a Voltages and overclock page (12.5 mV steps, new 1200 and 1296 MHz CPU steps);
- [launcher] new feature: module pages can have a side panel, rows that open another page and rows the module fills live;

## 20261119.3 (2026-11-19)
- [launcher] fix: System information > Graphics shows the screen's resolution (640 × 480, not the double-buffered 640 × 960);

## 20261119.2 (2026-11-19)
- [launcher] fix: System information follows Ellegance's style, its detail pages included;

## 20261119.1 (2026-11-19)
- [launcher] new feature: Ellegance is the main theme (consoles that never chose a theme open in it);
- [launcher] fix: every Settings page in Ellegance's style (updates, achievements, stores, module pages, controller test, RetroArch import, BIOS and others);

## 20261119 (2026-11-19)
- [launcher] new feature: Saturation in Settings > Sound and display > Picture (0% to 200%);
- [system] new feature: screen saturation through the display controller's BCSH block (kernel), applied in menus, games and ports;

## 20261118.17 (2026-11-18)
- [system] fix: SSH never started and retried every 2 s when the host key folder was missing;

## 20261118.16 (2026-11-18)
- [launcher] new feature: German and Simplified Chinese languages;

## 20261118.15 (2026-11-18)
- [system] fix: save sync only writes inside the ROMs folder, whatever names the shared folder lists;

## 20261118.14 (2026-11-18)
- [launcher] new feature: Settings > System > Save sync (PC folder or rclone cloud, at boot and after games, conflict choice);
- [system] new feature: archr-savesync, three-way save sync that never deletes; conflicts kept in SaveSync/conflitos;

## 20261118.13 (2026-11-18)
- [system] fix: black screen at boot on some clones (HDMI check took the display from sway);
- [system] fix: archr-gamma failed and sent an error report at every boot since 20261118.11;

## 20261118.12 (2026-11-18)
- [launcher] fix: Settings > Sound and display > Picture redone as designed (preview, panel card, restore, save and undo);

## 20261118.11 (2026-11-18)
- [launcher] new feature: Settings > Sound and display > Picture, panel gamma and colour temperature;
- [system] new feature: gamma table on the RK3326 display controller, held by archr-gamma in menus, games and ports;

## 20261118.10 (2026-11-18)
- [system] fix PSP games set to Vulkan closing at once when the system SDL cannot draw Vulkan windows: they open in OpenGL;

## 20261118.9 (2026-11-18)
- [system] fix the CPU Turbo switch ignored in games: with it off, games ran at 1512 MHz anyway; now up to 1416 MHz unless it is on;
- [system] new feature: CPU and GPU ceilings for every game, kept after a restart (archr-perf-limits);
- [launcher] new feature: modules API, perf-limits permission (CPU and GPU ceilings, GPU benchmark);
- [web] docs: modules, the perf-limits permission;

## 20261118.8 (2026-11-18)
- [system] fix PSP games about 5x slower since 20261117.6: PPSSPP back to 1.20.2 (1.20.4 ran God of War at ~20% speed), Vulkan kept;
- [system] fix PPSSPP settings changed in PPSSPP itself being reset when a game starts from the menu; only what is set in Arch R for the system or the game is applied;
- [web] new FAQ entry: changing PPSSPP settings (frame skip, buffer effects) per system or per game;
- [web] docs: recovery mode (hold Vol- at power on) to reach the card from a PC without taking it out;

## 20261118.7 (2026-11-18)
- [system] fix a console left asleep on battery powering off at minimum speed: the menu was killed before it saved its data, and the next boot sent a false abrupt-boot report;

## 20261118.6 (2026-11-18)
- [system] fix: when a game or port runs out of memory, the game is closed and the menu stays (the compositor and launcher are protected from the OOM killer; 512 MB consoles went to a black screen);

## v3.1.0 (2026-11-18)
> **Arch R 3.1.0** Vulkan on the Mali-G31, Bluetooth, faster memory and a theme API that changes every screen, in new official images; consoles that update need not flash.
- [system] release 3.1.0: official images with every update since 3.0.3; Vulkan on the Mali-G31 (PanVK, with the Panfrost driver), Bluetooth, RAM at 528 MHz, Ellegance and theme API 3.1;
- [web] docs: theme API 3.1, module API 4 (apps), Porting to Arch R and AI skills (archr-launcher-dev, archr-ports-dev) for 3.1.0;
- [web] overlay generator: base DTBs of the 3.1.0 kernel (Soy Sauce card slots at 3.3 V); offline edition regenerated;

## 20261118.5 (2026-11-18)
- [system] fix: a console with nothing left to install shows the newest update as its version (a new image showed the date it was built);
- [system] new: Arch R 3.1.0; consoles that reach this update show v3.1.0 in Settings;

## 20261118.4 (2026-11-18)
- [launcher] fix: Settings show the release the console has reached and the update it is on (v3.0.3 · 20261118.4), and follow an update made while the launcher is open;

## 20261118.3 (2026-11-18)
- [system] fix: when the console froze or lost power, the error report carries that boot's own journal (a wrong clock made it pick an older boot);
- [web] docs: AI skills page covers the ports skill (archr-ports-dev), and Porting to Arch R links to it;
- [web] fix: no icons in the docs sidebar, and one chevron on Docs and Tools in the sidebar;

## 20261118.2 (2026-11-18)
- [system] fix: Soy Sauce card slots run at high speed with 3.3 V, as the stock system, so cards the second slot (TF2) could not read work (#59);

## 20261118.1 (2026-11-18)
- [system] fix: error reports keep the audio (PipeWire) log lines, which were taken for passwords and removed;

## 20261118 (2026-11-18)
- [system] fix PlayStation, GBA (gpsp) and DS (DeSmuME) games closing at once on the 32-bit cores after update 20261117.6 (missing 32-bit libfribidi);
- [system] fix a 32-bit core with the Vulkan renderer: it opens in OpenGL, and its video filters load from the 32-bit folder;

## 20261117.6 (2026-11-17)
> **Vulkan on the GPU** With the Panfrost driver, emulators and ports can now run in Vulkan through Mesa's PanVK, chosen per system. The Ellegance theme and the 3.1 theme API arrive with it.
- [system] new feature: Vulkan through PanVK with the Panfrost driver, turned on per system in Settings › Games › Renderer;
- [launcher] new feature: the Ellegance theme;
- [launcher] new feature: theme API 3.1, so a theme can lay out every screen, Settings included;
- [launcher] change: choosing a theme applies the whole theme;
- [system] change: PPSSPP 1.20.4, with frame skip 2 by default;
- [system] fix: texture shaders no longer freeze the console in PPSSPP with Vulkan;
- [launcher] fix: ScreenScraper sign-in asks for the user name, not the e-mail, and the account row signs out;
- [system] fix: Settings › Updates shows the installed update after an update made over SSH;
- [launcher] fix: a game without art shows its console in the home screen and in its details;

## 20261117.5 (2026-11-17)
- [launcher] fix modules that failed once never starting again until a restart;
- [web] new feature: docs for the 3.1 theme API, port development and Vulkan;

## 20261117.4 (2026-11-17)
- [system] fix the first boot on a slow card stopping the system start-up halfway;

## 20261117.3 (2026-11-17)
- [system] fix: DoubleCherryGB no longer crashes on a game with a save state from another Game Boy core; it refuses the state;
- [system] fix: an updated RetroArch core is used by the next game instead of after a restart;
- [web] new feature: support page with Pix (QR code and copy button) and Ko-fi; the support popup now leads to it;
- [web] the top menu groups its links under Docs and Tools;

## 20261117.2 (2026-11-17)
- [system] fix: R36S Soy Sauce with a card in each slot at start: the slots now come up one at a time on their shared power line, so the system card in TF1 always reaches full speed;

## 20261117.1 (2026-11-17)
- [system] fix: R36S Soy Sauce card slots take their clock from the 50% duty divider like the stock firmware; a card in TF2 no longer re-initialises in a loop;

## 20261117 (2026-11-17)
- [system] fix: turning Wi-Fi off no longer sends a false error report (the Wi-Fi service had 1 s to stop and needs a little more);
- [system] fix: putting in a card with several partitions no longer sends a false error report;

## 20261116.15 (2026-11-16)
- [system] R36S Soy Sauce: the TF2 slot sees cards going in and out, like the stock firmware;

## 20261116.14 (2026-11-16)
- [system] the memory switch to 528 MHz waits for the screen and happens in the vertical blank;
- [system] a game that uses up the memory is closed instead of the console freezing for minutes;

## 20261116.13 (2026-11-16)
- [system] fix freezes and restarts under low memory on consoles with an RTL8188EU Wi-Fi dongle;

## 20261116.12 (2026-11-16)
- [system] new feature: the kernel runs the RAM at 528 MHz (it stayed at 332 MHz from the factory RAM firmware);

## 20261116.11 (2026-11-16)
- [system] fix ports without controls when PortMaster's own tools lost their execute bit;

## 20261116.10 (2026-11-16)
- [launcher] fix Start store shortcuts: same update badge as system Updates;
- [launcher] new feature: notification when theme or module updates are found;

## 20261116.9 (2026-11-16)
- [launcher] new feature: Bluetooth button on Start; Wi-Fi and Bluetooth only with an adapter; network and IP caption; Bluetooth icon in the top bar;
- [system] fix ports made for dArkOS/ArkOS: forced kmsdrm falls back, Debian library paths, oga_events, runtimes downloaded on launch;
- [system] new feature: a notification says why a port failed (game files, internet, port crash);

## 20261116.8 (2026-11-16)
- [system] fix Bluetooth pairing with a device already in the list;
- [system] Bluetooth name shows the console model (R36S Arch R);

## 20261116.7 (2026-11-16)
- [system] fix Bluetooth: no adapter was ever registered (L2CAP getsockopt broken in kernel 6.12.114);
- [system] new feature: a frozen console restarts and records the cause (lockup detectors);

## 20261116.6 (2026-11-16)
- [launcher] fix System Info: RAM clock under Memory, ROMs partition on the Storage card;

## 20261116.5 (2026-11-16)
- [system] fix GPU kernel panic on libmali: the GPU power domain stays on;

## 20261116.4 (2026-11-16)
- [launcher] new feature: notifications in a top corner (Appearance › Notifications);
- [launcher] new feature: settings with many values open a list with A, grouped when long (#57);

## 20261116.3 (2026-11-16)
- [system] fix music player showing an error when closed with the exit shortcut;
- [web] docs: the exit shortcut (L1 + SELECT + START) closes ports and the music player too;

## 20261116.2 (2026-11-16)
- [system] fix Samba from Windows: Windows signs in as root with the system password (it refused guests);
- [system] fix simple HTTP server: the browser asks again after a wrong password, uploads up to 4 GB;
- [web] docs: Samba and HTTP server sign in (root and the system password);

## 20261116.1 (2026-11-16)
- [system] fix the console settings file being set aside as broken when read while it is written at start;
- [system] fix R36S Clone headphone jack read the wrong way round;
- [web] fix overlay generator: R36S Clone boards with the speaker on the codec output get the simple sound card by default (#57);
- [web] new feature: overlay generator option Force amplified audio (AMP), and every option described by its symptom;

## 20261116 (2026-11-16)
- [system] fix error reports: a compressed kernel crash record now arrives as text;

## v3.0.3 (2026-11-15)
- [system] release 3.0.3: official images with every update since 3.0.2, and a first start with the wrong date no longer leaves the console unable to update;
- [web] docs: what to do when updates fail with "Check network" while the network works (consoles flashed with 3.0.2 or earlier);

## 20261115.5 (2026-11-15)
- [launcher] new feature: Settings › Sound and display › Mute (audio.mute); a volume step turns it off;
- [system] fix the speaker coming back muted after a restart: archr-levels applies the user's mute when the sink appears (a stray WirePlumber mute no longer survives the boot);
- [launcher] Date and time is now a page of fields (day, month, year, hour, minute) changed with L/R, then Apply, instead of a typed timestamp;

## 20261115.4 (2026-11-15)
- [system] fix Wi-Fi joins failing with "No Agent registered" since 20261115.1: iwd could not watch its state folder through the /var/lib/iwd link (iwd 3.12-6);
- [launcher] new feature: Settings › Region and language › Date and time, to set the clock by hand;
- [system] fix updates failing for good when the first boot had the wrong date: the Arch R key is loaded when missing (pacman-init, archr-update), and a wrong date is reported instead of a network error;

## 20261115.3 (2026-11-15)
- [system] fix J2ME games (FreeJ2ME): the Java runtime now installs once on the card instead of downloading on every launch and filling the system partition;
- [web] overlay generator: the console's own processor table is also offered when it goes higher than ours (R36S boards up to 1512/1608 MHz at the stock voltage);
- [web] fix the offline overlay generator lagging behind the online one; the site build now refuses an out-of-date offline bundle;
- [web] overlay generator: a third processor choice, Safe, caps the CPU at 1296 MHz for weak chips that freeze at 1416 MHz (R36S V22 rev 2534 did not start at all);

## 20261115.2 (2026-11-15)
- [launcher] new feature: controller tester and stick calibration in Settings › Controls (hold Y to calibrate); a calibration never sets a stick below its factory scale;
- [system] fix volume coming back at maximum after a restart (WirePlumber recreated the speaker node without its volume);
- [system] fix Wi-Fi adapters that refuse the first attempt (wifictl waits for iwd's retry) and a garbled first name in the network list;
- [system] fix ports copied by hand failing with "Permission denied" (programs get the execute bit);
- [system] error reports of a freeze carry the end of that boot (persistent journal, 8 MB);

## 20261115.1 (2026-11-15)
- [system] fix saved Wi-Fi networks lost on restart (iwd state now on the card); thanks @marianomd for the fix (#53);

## 20261115 (2026-11-15)
- [launcher] fix modules timing out at start on a slow CPU profile (initialize now gets 10 s);

## 20261114.10 (2026-11-14)
- [system] fix: Tools you add to /storage/.config/modules (script and gamelist entry) stay after a restart; only built-in Tools are refreshed (#54);
- [web] docs: how to add your own Tool in the launcher guide;

## 20261114.9 (2026-11-14)
- [system] fix: a reset while the controller settings were being saved no longer stops every later start (the damaged file is set aside and rebuilt);

## 20261114.8 (2026-11-14)
- [system] fix: apps and ports that use the DejaVu fonts show their text again (GameStoreBR opened without letters);

## 20261114.7 (2026-11-14)
- [system] fix: error reports no longer flag X-Moto's first run as a failure;
- [web] new feature: overlay generator offers the console's own processor speed (stock DTB) for consoles that restart or freeze; ArchR speed stays the default;

## 20261114.6 (2026-11-14)
- [system] fix: Python apps and PySDL2 ports find system libraries again (GameStoreBR stopped with "could not find any library for SDL2");

## 20261114.5 (2026-11-14)
- [system] new feature: a frozen console restarts on its own after 30 s and reports it at the next start;
- [system] fix random freezes on the R36S Soysauce: SD card powered as the board expects;
- [launcher] fix coming back to the last game after a restart: only after leaving a game;
- [launcher] new feature: Start opens the Start Menu inside a game list;
- [launcher] fix pages opened from the Start Menu not going back to it;
- [system] fix God of War on PSP: about 17-19 fps instead of 7-8;
- [system] fix the volume coming back at half after starting at the lowest level;
- [flasher] flasher 1.3.10: portable Windows build, and the overlay skip option says what it does;

## 20261114.4 (2026-11-14)
- [launcher] fix leaving the game switcher going to the first system instead of the last game;
- [launcher] fix the theme store d-pad changing tabs instead of moving across the grid;
- [system] fix A and B swapped in the File Manager;

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
