# Kill sound effect

`kill.ftm` is the editable FamiTracker source. It uses only pulse 2 and noise;
pulse 1, triangle and DPCM are empty. The file uses the FamiTracker 0.4.40
module format and was successfully opened/exported by the local Dn-FamiTracker.

One track, `kill`: PAL, speed 1, tempo 125. Both channels start on row 00.
Six audible rows give approximately 120 ms at 50 Hz, followed by a pulse
cut and C00 on row 06. Pulse 2 carries the body: a fixed low D-2 (about 73 Hz),
50% duty, and volumes F, C, 9, 6, 3, 1. There is no descending note melody.
Noise is a short crack: C at volume C, then 7 at volume 5, cut on row 02
(about 40 ms). The low pulse rings out after the noise stops.
There is no leading silence, delayed-note effect or DPCM sample.

`kill.txt` and `kill.nsf` are exports from this same FTM, ready for the NESfab
PUF SFX import. After edits, export both again; they do not update automatically.
Tracker CLI syntax is documented at:
https://dn-programming-core-management.github.io/Dn-help/hlp/command_line.htm

The game imports the TXT/NSF as PUF SFX `puf_sfx_kill`. It initializes PUF
for PAL with no music tracks, enables only pulse 2 and noise, and triggers the
sound in `start_player_death`. `puf.process($0A)` runs after gameplay and before
the frame wait, so the new effect is processed in the same game-loop iteration.
This includes deaths on the title screen. Other events remain silent.

Actual event-to-audio latency still needs to be tested in the game/emulator;
a short file and same-loop processing cannot guarantee low output latency.
