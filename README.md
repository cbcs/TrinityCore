# ![logo](http://www.trinitycore.org/f/public/style_images/1_trinitycore.png) TrinityCore

[![Coverity Scan Build Status](https://scan.coverity.com/projects/435/badge.svg)](https://scan.coverity.com/projects/435) 
[![Bountysource](https://www.bountysource.com/badge/tracker?tracker_id=1310)](https://www.bountysource.com/trackers/1310-trinity-core?utm_source=1310&utm_medium=shield&utm_campaign=TRACKER_BADGE)  
`3.3.5`: [![3.3.5 Build Status](https://travis-ci.org/TrinityCore/TrinityCore.svg?branch=master)](https://travis-ci.org/TrinityCore/TrinityCore)
`4.3.4`: [![4.3.4 Build Status](https://travis-ci.org/TrinityCore/TrinityCore.svg?branch=4.3.4)](https://travis-ci.org/TrinityCore/TrinityCore)

## Introduction

TrinityCore is a *MMORPG* Framework based mostly in C++.

It is derived from *MaNGOS*, the *Massive Network Game Object Server*, and is
based on the code of that project with extensive changes over time to optimize,
improve and cleanup the codebase at the same time as improving the in-game
mechanics and functionality.

It is completely open source; community involvement is highly encouraged.

If you wish to contribute ideas or code please visit our site linked below or
make pull requests to our [Github repository](https://github.com/TrinityCore/TrinityCore).

For further information on the TrinityCore project, please visit our project
website at [TrinityCore.org](http://www.trinitycore.org).

## Requirements

+ Platform: Linux, Windows or Mac
+ Processor with SSE2 support
+ Boost ≥ 1.49
+ MySQL ≥ 5.1.0
+ CMake ≥ 2.8.11.2 / 2.8.9 (Windows / Linux)
+ OpenSSL ≥ 1.0.0
+ GCC ≥ 4.7.2 (Linux only)
+ MS Visual Studio ≥ 12 (2013) (Windows only)


## Install

Detailed installation guides are available in the wiki for
[Windows](http://collab.kpsn.org/display/tc/Win),
[Linux](http://collab.kpsn.org/display/tc/Linux) and
[Mac OSX](http://collab.kpsn.org/display/tc/Mac).


## Reporting issues

Issues can be reported via the [Github issue tracker](https://github.com/TrinityCore/TrinityCore/issues?labels=Branch-3.3.5a).

Please take the time to review existing issues before submitting your own to
prevent duplicates.

In addition, thoroughly read through the [issue tracker guide](http://www.trinitycore.org/f/topic/37-the-trinitycore-issuetracker-and-you/) to ensure
your report contains the required information. Incorrect or poorly formed
reports are wasteful and are subject to deletion.


## Submitting fixes

Fixes are submitted as pull requests via Github. For more information on how to
properly submit a pull request, read the [how-to: maintain a remote fork](http://www.trinitycore.org/f/topic/6037-howto-maintain-a-remote-fork-for-pull-requests-tortoisegit/).


## Copyright

License: GPL 2.0

Read file [COPYING](COPYING)


## Authors &amp; Contributors

Read file [THANKS](THANKS)


## Links

[Site](http://www.trinitycore.org)

[Wiki](http://trinitycore.info)

[Documentation](http://www.trinitycore.net) (powered by Doxygen)

[Forums](http://www.trinitycore.org/f/)


How to use

Summary :
robot accounts and characters are set in robot.conf file.

there are two type of robots, world robot and raid robot.

world robot will go online and offline with human players at same level.

world robot minimal level is 20. So if online human player is below level 20, there will not create any robot player.

raid robot will wondering in main city only.

human player use SAY command and CHAT command to interact with robot system.

robot accounts will be checked every 10 - 15 minutes. Doing online, offline, random teleporting, reviving ...


Configs :
Enable - set to 1 to enable robot system

ResetRobots - set to 1 to recreate all robot accounts and characters at server start up. Old robot accounts will be delete if there are any. Server will shutdown after deleting.

ResetEquipments - set to 1 then robot's equipment will be reset at login

EnableAlliance - set to 1 then alliance race robot is allowed to go online

EnableHorde - set to 1 then horde race robot is allowed to go online

AccountNamePrefix - robot account name is started with this

AssembleDelay - set to 1 to enable time delay when using chat command "assemble". set to 0 robots will be teleported to group leader instantly

OnlineLevel - constantly onlined robot player at this level. will not go offline or online with human players

CountEachLevel - world robot player number will be created at this level

OnlineMinDelay - time delay for world robot checking when human player is online.

OnlineMaxDelay - time delay for world robot checking when human player is online.

GroupInterest - set to 1 to enable world robot to consider accepting group invite from human player

TeleportMinRange - world robot will be teleported around human player with same level with in this range.

TeleportMaxRange - world robot will be teleported around human player with same level with in this range.

DeathMinDelay - robot not in a group will be revive and random teleported after death delay.

DeathMaxDelay - robot not in a group will be revive and random teleported after death delay.

SoloMinDelay - robot not in a group will be random teleported after solo delay.

SoloMinDelay - robot not in a group will be random teleported after solo delay.

AssembleTeleportMinRange - robot will be teleported to human player if it is too far away from group leader when using CHAT command "assemble".

DPSDelay - robot will start to dps after this delay when group is in combat.

AOEDelay - robot will start to aoe after this delay when group is in combat.

RaidRobotCount_60 - raid robot count will be created at level 60.

RaidRobotCount_70 - raid robot count will be created at level 70.

RaidRobotCount_80 - raid robot count will be created at level 80.


SAY :
SAY command "/s" is used to do global settings or self config.

role - set or query human player group role. "/s role dps"

strategy - set or query current group strategy. current strategies : group, blackrock spire, doctor weavil, ysondre, taerar, lethon, emeriss, azuregos, molten core

arrangement - set group members to their group roles. paladins will do different blessing and auras

mark - set every member their mark positions for each strategy.

join - human player will teleport to group robot. like warlock is pulling you.


CHAT :
CHAT command "/w /p /raid" is used to tell each robot what to do.

role - set or query robot player group role. "/w Mage role dps

follow - dps and healer will follow tank. tank will follow group leader. parameter : follow distance

stay - robot player will do nothing when staying

hold - robot player will do resing, attacking and any other motions at their spot. they will not move.

engage - to group leader target. dps will try to attack. tank will try to tank. healer will try to heal

rest - robot player will start eating and drinking

who - robot player will reply with their talent specialty

assemble - robot player will try to go to group leader's place

tank - to group leader target. tank will try to tank.

switch - for pets. "switch off growl"

cast - to group leader target. robot player try to cast spell. "cast Frostbolt"

cancel - robot player try to cancel buff aura. "cancel Thorns"

delay - set dps or aoe delay in milliseconds. "delay dps 2000", "delay aoe 7000"

revive - robot players that have revive spells will look for dead players in 30 yards and cast revive spells. Redemption, Resurrection, Revive ...

cure - set to on or off. robot players will handle poison curse disease or not. you can set it to off to keep "mother's milk"

side - parameter is "all", "melee", "range". based on group leader's facing direction. robot player will move aside a little. to avoid some area effect spells.

forward - parameter is "all", "melee", "range". based on group leader's facing direction. robot player will move forward a little.

back - parameter is "all", "melee", "range". based on group leader's facing direction. robot player will move back a little.

lightwell - priest will cast lightwell if possible. others will try us use lightwell if nearby.

pa - paladin aura. can set to concentration, devotion, retribution, fire

pb - paladin blessing. can set to kings, might, wisdom

mark - robot player will move to mark position and stop following. hold will be set to on.

petting - parameter on or off. robot player will not call pets when set to off

active - set following to enable. stay and hold to disable.

equip - now two parameters "molten core" and "reset". "molten core" - only druids will answer. druids will reset all equipments to fire resist equipments. so they can tank Ragnaros. "reset" all will answer. reset all equipments

rti - raid target icon. 0 - 7 is star to skull. mage will cast polymorph on rti target.

assist - mage will try to cast polymorph to their rti target.


Example :
1, you invite 4 robot players. warlock, priest, druid, hunter. default strategy is "group". you do not need to do anything. their role will be set automatically.

2, you select a creature that attackable. type "/p tank". tank - druid will answer. the robot will move to tank the target. others will follow. priest will do healing. heal tank all the time. heal others when below 50%. hunter and warlock will attack after dps delay.

3, if you have 2 or more paladins in your group. type /s arrangement. two paladins will handle different blessing and aura.

4, if you are doing raid. make sure do arrangement after grouped.

5, if you are facing ysondre. type /s strategy ysondre. there will be a hint come out. 8 priests , 2 druids. you select a place wide open. then type /s mark. so everyone's mark positions are set. then type /p mark. everyone will move to their mark places. you pull boss near tank1. tank1 will take over when boss is close.

6, if you are facing taerar. type /s strategy taerar. there will be a hint come out. 8 priests , 5 druids. 4 rogues. tank3 tank4 tank5 will hande shade of taerar. rogues to disrupt fear.

7, if you are facing emeriss. type /s strategy emeriss. there will be a hint come out. 12 priests , 2 druids. healer1 healer2 for tank1. healer3 healer4 for tank2. healer5 - healer 12 for each group. make sure every sub group has a priest.

8, if you are facing azuregos. type /s strategy azuregos. there will be a hint come out. 6 priests , 1 druids. 4 rogues. rogues to disrupt spell casting.

9, if you are doing molten core. type /s strategy molten core. there will be a hint come out. 6 priests , 2 druids. 2 - 3 rogues. mostly automatic.

10, if you are doing majordomo executus. type /s strategy molten core. there will be a hint come out. 6 priests , 2 druids, 4 mages. mark 4 flamewaker healer with star to triangle. raid target 0 - 4.

11, if you are doing ragnaros. type /s strategy molten core. there will be a hint come out. 6 priests , 2 druids. type /p equip molten core. the druids will equip fire resist items. find a suitable place, stand nearby executus. and mark every one.


Hint :
when doing mark position fights. pay attention to environment objects. sometimes if the healer's sight is blocked by a tree. then tank will die.

in joker.conf, make sure Enable is set to 0. they are personal balance contents. require database scripts if set to 1

Where to get
Open Source :
github : jokerlfm's trinitycore fork - branch 3.3.5 only


Pack :
google drive : precompiled files

must execute script "world_extra.sql" and "character_extra.sql" !
