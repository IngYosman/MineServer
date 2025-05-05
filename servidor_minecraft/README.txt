## FIRST TIME SETUP ##

- open the "START-SERVER.bat" file ("START-SERVER.sh" for mac/linux).
- when prompted to agree to Minecraft's EULA, type "I agree" if you agree, type anything else if you don't.
- if you want to edit the allocated RAM amount, stop the server, open "user_jvm_args.txt" and change the number in "-Xmx3G".
- edit the "server.properties" and "server-icon.png" file to your liking.



## UPDATING THE SERVER ##

- stop the server using "stop" in the server console.
- download the latest server file.
- backup the old server folder. 
- delete "config" and "mods" folders, and the 2 SERVER-START files.
- replace the deleted files with the new versions from the downloaded zip.
- if you made any modifications to some configs, restore them from the backup.
- launch the server with START-SERVER.



## USEFUL COMMANDS ##

- /spawn to teleport to the world spawn point.
- /rtp, /rtpnear, and /rtpfar will teleport a player to a random location.
- /sethome to make a waypoint ansd /home to return to it, /delhome to remove it, /homes for the list, by default players can only have 3 homes max, configurable.
- /back to return to where you last teleported from, or where you died.
- /setwarp to create a global waypoint, /delwarp to remove it, by default only OP ranked players can set warps, other can travel to them using /warp warp_name, /warps will show the warps list.
- /tpa to ask a player to teleport to them, /tpahere to ask them to teleport to you, /tpaaccept to accept the request, /tpadeny to reject.
- server admins can use /god, /invsee, and many other commands to manage players.
- check FTB Essentials configuration (world/serverconfig/ftb-essentials.sntb) for more info.



## WORLD PRE-GENERATION ##

- you can pre-generate the terrain for less lag caused by players travelling to new chunks.
- you can only generate a max 800*800 chunks at once, given your world spans from -10K to 10K on both axes (as in the default config), you will have to divide it by 4, each has a radius of 313 chunk, execute these commands back to back, don't launch them all at once, wait for the previous to finish:
	> /pregen start gen radius overworld_part_1 SQUARE 5000 5000 313 minecraft:overworld
	> /pregen start gen radius overworld_part_2 SQUARE -5000 5000 313 minecraft:overworld
	> /pregen start gen radius overworld_part_3 SQUARE 5000 -5000 313 minecraft:overworld
	> /pregen start gen radius overworld_part_4 SQUARE -5000 -5000 313 minecraft:overworld
	> /pregen start gen radius overworld_part_1_post SQUARE 5000 5000 313 minecraft:overworld POST_GEN
	> /pregen start gen radius overworld_part_2_post SQUARE -5000 5000 313 minecraft:overworld POST_GEN
	> /pregen start gen radius overworld_part_3_post SQUARE 5000 -5000 313 minecraft:overworld POST_GEN
	> /pregen start gen radius overworld_part_4_post SQUARE -5000 -5000 313 minecraft:overworld POST_GEN
- you can only generate 1 dimension at once, repeat the same 8 commands for each dimension you want, simply replace "minecraft:overworld" with "minecraft:the_nether" and/or "minecraft:the_end", and also rename the task "overworld_part..." to "nether_part..." or "end_part...".
- use "/pregen pause" and "/pregen resume" to pause and continue pre-generation tasks.
- NB: it will take some days to generate all parts, and might make the server laggy for players, and will make your world file several tens of GBs big, plan your world pre-generation carefully.
>> for more info visit: https://github.com/TinyModularThings/Chunk-Pregenerator-Issue-Tracker/wiki/Commands-(1.14-or-newer)



## SERVER CONFIGS ##

- for commands config go to world/serverconfig/ftb-essentials, add FTB Ranks for more options.
- for auto-restart config go to world/serverconfig/auto_restart-server.toml
- for auto-backup config go to config/simplebackups-common.toml
- for chat UI config go to config/beautifiedchatserver.json5
- to restore chat censoring, delete mods/NoChatReports-FORGE-1.19.2-v1.5.1.jar