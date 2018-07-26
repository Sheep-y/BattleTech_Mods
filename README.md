# AIM - Attack Improvement Mod 2.0 #
For BATTLETECH 1.1.2.

AIM is a BattleTech mod that fixes, enhances, and customise your combat experience, such as tune down roll correction, show heat and stability numbers, and a detailed attack log, without deviating too far from vanilla.

This mod does *not* modify game data.  Saves made with this mod on will *not* be affected by disabling or removing this mod.

**ALL features can be enabled or disabled individually.**

## Game Bugs Fixed and HUD Enhancements ##

* Vehicle Called Shot fixed
* Damaged Structure Display fixed and enhanced
* Grey Head Disease fixed.
* Line of Fire fixed and stylised.
* Multi-Target Back Out fixed.
* Show Heat and Stability Numbers, including cooldown overhead.
* Show Base Hit Chance in accuracy modifier popup.
* (Optional) Show mech tonnage.
* (Optional) Show corrected hit chance.

## Mechanic Enhancements ##

* Unlock Hit Chance Stepping to make odd piloting useful.
* Called Shots cluster around called mech location.
* Precise Hit Distribution that improves SRM and MG called shot.
* More Melee Modifiers, which fixes the absent of stood up penalty.
* Allow modifiers to be net bouns.
* Allow height modifier to be negative.
* Remove hard cap on possible melee positons.

## Other Adjustable Mechanics ##

* Tabular Attack Log that can be copied and pasted to Excel.
* Adjustable Roll Correction Strength, default halved.
* Adjustable Miss Streak Breaker.
* Adjustable Base Hit Chance.
* Adjustable Hit Chance stepping and min/mac cap.
* Adjustable called shot chances and hit chances display precision.


# Installation

***IMPORTANT Note on upgrading from 1.0**: Rename your old `mod.json` to `settings.json` to keep old settings.

1. [Install BTML and ModTek.](https://github.com/Mpstark/ModTek/wiki/The-Drop-Dead-Simple-Guide-to-Installing-BTML-&-ModTek-&-ModTek-mods)
2. [Download](https://github.com/Sheep-y/Attack-Improvement-Mod/releases) and extract in the nod folder. i.e. You should have BATTLETECH\Mods\AttackImprovementMod\mod.json
3. Launch the game. The mod should be initialised with its default settings, and creates a "settings.json" in its folder, plus a mod log.
4. Open the file to see mod settings.  If you change any, restart game to apply changes.


# Configuration

When the mod is first loaded by the game, it will try to read settings.json and validate its settings.

Two defaults are bundled with the mod.  You may copy or rename them to `settings.json` to use the config.

* `settings.spatan.json` - Enable diminishing modifier, more melee modifiers, more info display, and disables roll correction and streak breaker.
* `settings.log-only.json` - Disable all features except attack log, which is enabled in full.

Note that `settings.json` is auto-managed.  Old settings will be upgraded and removed, out of range settings will be corrected, and the formats and comments are fixed.  You can only change setting values, which may be written back to the file in a standard computerised form.

Unlike many simpler mods, this mod is designed to run as fast as it can be, so don't worry about performance.  Disabled features won't slow down the game and does not modify any code.

# Settings

These settings can be changed in `settings.json`.


## User Interface Settings


**Fix Rear Structure Display**

> Setting: `FixPaperDollRearStructure`  (true/false, default true)
>
> The rear structure of the paper dolls are showing front structure on the reverse side because of a typo in the code.  If the front has armour, it means the damaged structure will not be displayed.
>
> When set to true, this mod can fix all paper dolls, including selection panel, target panel, called shot panel, post-mission status, and in mech bay.


**Show Under-Armour Damage**

> Setting: `ShowUnderArmourDamage `  (true/false, default true)
>
> Not sure why the game didn't do this.  When set to true, armour of damaged location will have a striped pattern instead of solid.


**Show Heat and Stability Numbers**

> Setting: `ShowHeatAndStab`  (true/false, default true)
>
> When set to true, display heat and stability numbers in the selection panel (bottom left) and targeting panel (top center), and predicts post action numbers.  Predictions supplied by the game and is subject to all its quirks and bugs and mods.


**Show Unit Tonnage**

> Setting: `ShowUnitTonnage`  (true/false, default false)
>
> When set to true, show mech and vehicle tonnage in selection and target panel.
>
> Duplicates with Extended Information, but AIM override it and use a shorter form for mechs to fit in heat and stability numbers.  Default false because the short form can overwhelm inexperienced players.


**Fix Multi-Target Back Out**

> Setting: `FixMultiTargetBackout`  (true/false, default true)

> The game's Muti-Target back out (escape/right click) is bugged. Backing out from first target will cancel the action, and second back out (regardless of target) will always cancel the whole thing.

> When set to true, this mod will make Multi-Target back out deselect targets one by one as expected.



## Targeting Line Settings

**Change Widths of Targeting Lines**

> Setting: `LOSWidth`  (0 to 10, default 2) 
>
> Set width of all targeting lines (direct, indirect, blocked, can't attack etc.).  Game default is 1, but set to 0 also leaves it at game default.  Mod default is 2. 
>
>
> Setting: `LOSWidthBlocked`  (0 to 10, default 1.5)
>
> Set width of obstructed part of an obstructed targeting lines, which is normally thinner than other lines by default.  Game default is 0.75, but set to 0 also leaves it at game default.  Mod default is 1.5.

> Auto-disable to avoid conflict when Firing Line Improvement is used.


**Change Widths of Obstruction Marker**

> Setting: `LOSMarkerBlockedMultiplier`  (0 to 10, default 1.5)
>
> Scale the obstruction marker of targeting lines, the "light dot" that split the obstructed line into two. 2 means double width and height, 0.5 means half-half.  Set to 1 to leave at game default.  Set to 0 will not remove them from game but will effectively hide them.
>
> When the mod "Firing Line Improvement" is detected, this setting will be disabled to avoid conflicts.


**Styles and Colours Targeting Lines**

> Setting: `LOSIndirectDotted`  (default true, game default false)
> Setting: `LOSNoAttackDotted`  (default true)
> Setting: `LOSMeleeDotted`  (default false)
> Setting: `LOSClearDotted`  (default false)
> Setting: `LOSBlockedPreDotted`   (default false)
> Setting: `LOSBlockedPostDotted`  (default false)
> Setting: `LOSMeleeColor`  (default "")
> Setting: `LOSClearColor`  (default "")
> Setting: `LOSBlockedPreColor`   (default "#D0F")
> Setting: `LOSBlockedPostColor`  (default "#C8E")
> Setting: `LOSIndirectColor`  (default "")
> Setting: `LOSNoAttackColor`  (default "")
>
> Set the colour and style of various targeting lines.
> Obstructed lines has two parts. The part before obstruction is Pre, and the part after is Post.
>
> Colours are either empty or in HTML hash syntax.  For example `"#F00"` = red, `"#0F0"` = green, `"#00F"` = blue, `"#FFF"` = white, `"#888"` = grey, `"#000"` = black.
> Four parts means RGBA, while three parts mean full opacity RGB.  Supports full and short form. e.g. #28B = #2288BB = #2288BBFF.
>
> When the mod "Firing Line Improvement" is detected, this setting will be disabled to avoid conflicts.


**Refine or Rough Fire Arc and Jump Arc**

> Setting: `ArcLinePoints`  (2 to 1000, default 48, game default 18)
>
> On a high resolution monitor it is easy to see the hard corners of the arc of indirect targeting lines.  Lines are quick to draw, so this mod will happily improves their quality for you.
> Set to 2 to make them flat like other lines.  Set to 18 to disable.
>
> When the mod "Firing Line Improvement" is detected, this setting will be disabled to avoid conflicts.


**Fix LoS Inconsistency between Walk and Jump**

> Setting: `FixLosPreviewHeight`  (true/false, default true)
>
> Walk and Jump will sometimes predicts different Line of Sight, because the walking preview height is slightly different from jumping preview height.  Set to true to make them the same.



## Called Shot Settings

**Enable Vehicle Called Shot**

> Setting: `FixVehicleCalledShot`  (true/false, default true)
>
> Called shot have absolutely no effect on vehicles, as if game version 1.1.2.  Set to true to make it work again.
>
> In the code, Mech Locations and Vehicle Locations are two separate data type, meaning there are two set of states and methods to handle hit location.  And vehicle's called shot handling is incomplete.  You can pick a called shot location, but it never reach the hit location routine.  This can be verified by disabling this setting and enabling attack log.



**Fix Grey Head Disease**

> Setting: `FixGreyHeadDisease`  (true/false, default true)
>
> Set to true to confine the grey head disease to the boss and not spread.
>
> When anyone, friends or foes, attacks a headshot immune character, all attacks from the same direction will never hit the head ever again.  Every one's head will be grey.  I call it the grey head disease.  It lasts until you load the game.


> Setting: `FixBossHeadCalledShotDisplay`  (true/false, default true)
>
> Set to true to make sure boss head is always unselectable.
>
> Did you know that grey head in called shot popup is actually a bug?
(I hope it is a bug.)
> If you try to call shot the boss before any headshot-immune unit is attacked, such as right after a load, the head is actually selectable!
> This is most apparent with FixGreyHeadDisease on, since the head will be always available.
>
> If `FixGreyHeadDisease` is true but `FixBossHeadCalledShotDisplay` is false, the boss's head will be selectable for called shot, but it is false hope.  Your shots will never hit the head.


**Enable Clustering Called Shot**

> Setting: `CalledShotUseClustering` (true/false, default true)
>
> When set to true, called shot has a higher chance to hit adjacent locations.
>
> For example, head called shot would bias the head, but also the three torsos to a lesser degree.
>
> This is the default behaviour on and before game version 1.0.4, which was bugged and caused very low called head shot chances since head is excluded from clustering.  The bug is one of the driving forces of this mod's initial creation.  This mod can recreate the clustering effect without the bug.
>
> Note that this does not apply to Vehicle called shot; the default vehicle clustering is only half done, and even when fixed there are too few locations to have meaningful cluster.



**Adjust Called Shot Weight**

> Setting: `MechCalledShotMultiplier`  (0 to 1024.0, default 0.33)
>
> When clustering called shot is enabled, chance to hit called locations will be amplified by clustering weight.  This setting let you tune called shot's weight multipliers.
> Default is 0.33 to counter the effect of CalledShotClusterStrength.  Set to 1.0 would leave original multiplier unchanged, while 0.0 will removing it leaving only clustering effect (if enabled).
>
>
> Setting: `VehicleCalledShotMultiplier`  (0 to 1024.0, default 0.75)
>
> Called shot didn't work on vehicles without modding.  Once that is fixed, unmodified called shot is pretty powerful on vehicles because of its low number of locations.  This setting tries to balance that.


**Show Modded Called Shot Chance**

> Setting: `ShowRealMechCalledShotChance`  (true/false, default true)
> Setting: `ShowRealVehicleCalledShotChance`  (true/false, default true)
>
> When enabled, the popups will reflect modded hit distribution.  Also, if vehicle called shot fix is disabled, vehicle called shot chance will be updated to reflect disabled called shot.


(Advanced) **Format Called Shot Hit Distribution Chances**

> Setting: `CalledChanceFormat`  (string, default "")
>
> Use Microsoft C# [String.Format](https://docs.microsoft.com/en-us/previous-versions/visualstudio/visual-studio-2008/0c899ak8(v=vs.90) syntax to format called shot location chances.
>
> Set to "{0:0.0}%" to always show one decimal, or "{0:0.00}%" for two decimals.
> Leave empty to round them to nearest integer.
>
> Replace the old "ShowDecimalCalledChance" setting in version 1.0.


## Melee and DFA Settings


**Allow free Melee and DFA positioning**

> Setting: `IncreaseMeleePositionChoice`  (true/false, default true)
> Setting: `IncreaseDFAPositionChoice`  (true/false, default true)
>
> When set to true, melee and DFA can use all available positions, instead of nearest three.  Compatible with MeleeMover.
>
>
> Setting: `UnlockMeleePositioning`  (true/false, default true)
>
> When enabled, free player units from standing still when target is already in melee range.  Auto-disable to avoid conflict when MeleeMover is used.


**Change Melee Modifiers**

> Setting: `MeleeAccuracyFactors`  (comma separated value)
>
> A list of hit modifiers of melee and DFA attacks. Leave empty to keep it unchanged.  Order will be followed, and letter case does not matter.
>
> Since this feature will override both mouseover display and actual modifier calculation, this will fix the bug that SelfStoodUp is displayed in mouseover but not counted in modifier.
>
> Default is "DFA, Height, Inspired, SelfChassis, SelfHeat, SelfStoodUp, SelfWalked, Sprint, TargetEffect, TargetEvasion, TargetProne, TargetShutdown, TargetSize, TargetTerrainMelee, WeaponAccuracy".
>
> Other options are ArmMounted, Obstruction, Refire, SelfTerrain, SensorImpaired, and TargetTerrain.
>
> **ArmMounted** - Apply arm mount bonus if the punching arm is intact and the attack is not DFA and not against prone mech or vehicle.
> **DFA** - Apply DFA penalty if attack is DFA.
> **Height** - Apply one level of height modifier if height different is at least half of melee reach.  DFA height difference is calculated like ranged weapon - from pre-flight attacker position to target position.
> **Inspired** - Apply inspired bonus.
> **Obstruction** - Apply obstructed penalty.
> **Refire** - Apply refire penalty.  Which should be 0 by default but can be changed in weapon data files.
> **SelfChassis** - Apply chassis modifier.
> **SelfHeat** - Apply overheat penalty.
> **SelfStoodUp** - Apply stood up penalty.
> **SelfTerrain** - Apply self terrain penalty as if this is a ranged attack.
> **SelfWalked** - Apply self walked penalty, default 0 but can be changed in game configuration file.
> **SensorImpaired** - Apply sensor impaired penalty.
> **Sprint** - Apply sprint penalty.
> **TargetEffect** - Apply target effect penalty such as gyro.
> **TargetEvasion** - Apply target evasion penalty.  Note that melee attacks ignore up to 4 evasion by default.
> **TargetProne** - Apply target prone penalty.
> **TargetShutdown** - Apply target shutdown bonus.
> **TargetSize** - Apply target size penalty.
> **TargetTerrain** - Apply target terrain's modifier as if this is a ranged attack.
> **TargetTerrainMelee** - Apply target terrain's melee modifier.
> **WeaponAccuracy** - Apply weapon accuracy modifier.



## Hit Modifier Settings

**Allow Net Bonus Modifier**

> Setting: `AllowNetBonusModifier`  (true/false, default true)
>
> When set to true, total modifier of an attack can be a net bonus that increase the hit chance beyond the attacker's base hit chance (but still subjects to 95% cap unless lifted by the `MaxFinalHitChance` settings).
> Game default is false.
>
> When the net modifier is a bonus, it will use the same handling as penalty but reversed: first 10 modifiers are ±5% each, and subsequence modifiers are ±2.5% each.


**Allow Height Diff Penalty**

> Setting: `AllowLowElevationPenalty`  (true/false, default true)
>
> When set to true, attacking from low ground to high ground will incur an accuracy penalty that is the exact reverse of attacking from high ground to low.
> Game default is false.


**Modify Base Hit Chance**

> Setting: `BaseHitChanceModifier` (-10.0 to 10.0, default 0)
> Setting: `MeleeHitChanceModifier` (-10.0 to 10.0, default 0)
>
> Increase or decrease base hit chance of ranged/melee attacks.
> e.g. -0.05 to lower base accuracy by 5%, 0.1 to increase it 10%.


**Unlock Modifier Stepping and Range**

> Setting: `HitChanceStep`  (0.0 to 1.0, default 0)
>
> The game will round down final hit chance to lower 5% by default.
> This affects some calculations, such as rendering odd gunnery stats and piloting stats less effective then they should be.
> Set this to 0 to remove all stepping.  Set it to 0.005 will step the accuracy by 0.5%, and so on.
>
>
> Setting: `MaxFinalHitChance`  (0.1 to 1.0, default 0.95)
> Setting: `MinFinalHitChance`  (0.0 to 1.0, default 0.0)
>
> Use this to set max and min hit chance after all modifiers but before roll correction.
> Note that 100% hit chance may still miss if roll correction is enabled.

**Diminishing Hit Chance Modifier**

> Setting: DiminishingHitChanceModifier  (true/false, default false)
>
> Set this to true to enable diminishing return of modifiers, instead of simple add and subtract.
> As a result, small penalties have a bigger effect, but very large penalties may be more bearable.
>
>
> Setting: `DiminishingBonusPowerBase`  (default 0.8)
> Setting: `DiminishingBonusPowerDivisor`  (default 6)
> Setting: `DiminishingPenaltyPowerBase`  (default 0.8)
> Setting: `DiminishingPenaltyPowerDivisor`  (default 3.3)
>
> Bonus formula is "2-Base^(Modifier/Divisor)".
> Example: +3 Bonus = 0.8^(3/6) = -1.1055728 = 110%.
> Thus +3 Bonus @ 80% To Hit = 80% x 110% = 88% final to hit.
>
> Penalty formula is "Base^(Modifier/Divisor)".
> Penalty Example: +6 Penalty = 0.8^(6/3.3) = 0.6665 = 66.7%.
> Thus +6 Penalty @ 80% To Hit = 80% x 66.7% = 53% final to hit.
>
>
> Setting: `DiminishingBonusMax`  (default 16)
> Setting: `DiminishingPenaltyMax`  (default 32)
>
> The modifiers are pre-calculated to run faster.  These settings determine how many results are cached.  Modifiers beyond the max will be regarded as same as max.


## Hit Roll Settings

**Adjust Roll Correction**

> Setting: RollCorrectionStrength (0.0 to 2.0, default 0.5)
>
> It is no secret that the game fudge all hit rolls, called a "correction".  As a result, real hit chances are shifted away from 50%, for example 75% becomes 84% while 25% becomes 16%.  This can create a rift between what you see and what you get, especially on low chance shots.
>
> This mod does not aim to completely disable roll adjustment, and thus default to half its strength.  You can set the strength to 0 to disable it, 1 to use original formula, 2 to amplify it, or any value between 0 and 2.
>
> If the "True RNG Hit Rolls" mod is detected, this setting will be switched to 0 for consistency.


(Advanced) **Adjust Miss Streak Threshold**

> Setting: `MissStreakBreakerThreshold` (0.00 to 1.00, default 0.5)
>
> In addition to roll adjustment, the game also has a "miss streak breaker".  Whenever you miss an attack of which uncorrected hit chance > 50%, the streak breaker will adjust your hit chance up on top of roll correction.  The bonus accumulates until you land a hit (regards of hit chance), at which point it resets to 0.
>
> This setting let you adjust the threshold.  0.75 means it applies to attack of which hit chance > 75% (excluding 75%).  Set to 0 enable it for all attacks, or set to 1 to disable it.  Default is 0.5 which is the game's default.
>
> If the "True RNG Hit Rolls" mod is detected, this setting will be switched to 1 for consistency.


(Advanced) **Adjust Miss Streak Bonus**

> Setting: MissStreakBreakerDivider (-100.0 to 100.0, default 5.0)
>
> For every miss that crosses the streak breaker threshold, the threshold is deduced from hit chance, then divided by 5.  The result is then added as streak breaker bonus.
>
> Set this setting to a positive number to override the divider.  For example at threshold 0.5 and divider 3, a 95% miss result in (95%-0.5)/3 = 15% bonus to subsequence shots until hit.  Default is 5 which is the game's default.
>
> Set this setting to zero or negative integer to replace it with a constant value.  For example -5 means each triggering miss adds 5% bonus, and -100 will make sure the next shot always hit.


**Format Hit Chance** (default "")

> Setting: `HitChanceFormat` (free string, default "")
>
> Use Microsoft C# [String.Format](https://docs.microsoft.com/en-us/previous-versions/visualstudio/visual-studio-2008/0c899ak8(v=vs.90) syntax to format weapon hit chances.
>
> Set to "{0:0.0}%" to always show one decimal, or "{0:0.00}%" for two decimals.
> When empty AND HitChanceStep is 0, will use "{0:0.#}%" to optionally show hit chance to one decimal point.
>
> Replace the old "ShowDecimalHitChance" setting in version 1.0.


(Advanced) **Show Corrected Hit Chance**

> Setting: `ShowCorrectedHitChance` (true/false, default false)
>
> It's one thing to fudge the rolls.  It is another to let you know.
> Set this to true to show the corrected hit chance in weapon panel.
>
> Renamed from old "ShowRealWeaponHitChance" setting since version 2.0.
> If the "Real Hit Chance" mod is detected, this settings will be switched to on and overrides that mods.



## Hit Resolution Settings

**Precise Hit Location Distribution**

> Setting: FixHitDistribution (true/false, default true)
>
> Set to true to increase hit location precision, specifically to improve the hit distribution of SRM and MG called shots.
>
> Game version 1.1 introduced degrading called shot effect for SRM and MG,
but because the code that determine hit distribution is not designed for fraction called shot weight, the actual distribution is slightly bugged.
>
> On game version 1.1.0 and before, enabling this would also fix the bug that causes abnormally high head hit chances.


**Precise Hit Location Distribution**

KillZeroHpLocation 


## Attack Log Settings

(Advanced) **Attack Log**

> Setting: AttackLogLevel ("None", "Attack", "Shot", "Location", "Damage", "Critical", or "All", default "None")
>
> When not None, the mod will writes to an attack log in the mod's folder, called Log_Attack.txt.
>
> The levels are progressive.  Attack info is fully included by Shot level, Shot info is fully included by Location level, etc.  The deeper the level, the more the mod needs to eavesdrops and the higher the chance things will go wrong because of game update or interference from other mods.
>
> **None** - It is a bug if you see a log file at this log level.  That or the file is a ghost that comes back to haunt you, in which case you should seek the church.
>
> **Attack** - Time, Attacker (team, pilot, mech), Target (team, pilot, mech), Direction, Range, Combat Id, and Action Id. The Ids can be used to consolidate data by-combat or by-action.  For example a Multi-Target attack may have three attacks that share the same Action Id.
>
> **Shot** - For each shot, log the Weapons, Weapon Template, Weapon Id, Attack Roll, Hit Chance, related info, and either Hit or Miss.  Weapon Id is unique *per mech*, and can be used to consolidate data by weapon.
>
> **Location** - Location Roll, Hit Table, Called Shot, and the Hit Location.
>
> **Damage** - Damage, Final Damaged Location, and Armor/HP of this location. 
> Damage is determined in a different phase from hit and location, and is a rather complicated info to log.
>
> **Critical** - Crit Location, Crit Roll, Crit Slot, Crit Component, and the result of the crit.
> Crit is determined in yet another phase, so the log code is *very fun* to write.
>
> *All* - same as Critical for now.  More info may be added in the future, though I am not sure I wouldn't go crazy.  Would you believe logging is the most complicated feature of this mod?

(Advanced) **Log Options**

> Setting: PersistentLog (true/false, default false)
>
> When set to false, the attack log will auto-clear on launch.
>
> Setting: LogFolder (string, default "")
>
> Set path of mod log and attack log.  Default is empty which will use mod folder.



# Compatibilities

AIM is aware of some mods and will behave differently in their present to meet player expectations.

These behaviours will not change saved settings.  If you want to replace them with AIM, you may need to change AIM settings.

When have mod | AIM will
--- | ---------
Firing Line Improvement | AIM will skip line styling and arc point adjustment to not crash the game.
MeleeMover | AIM will skip its own melee unlock to preserve sprint range melee.
Real Hit Chance | AIM will enable corrected hit chance display and overrides this mod, since it does not support AIM features such as adjustable correction strength.
True RNG Hit Rolls | AIM will disable its own adjustable roll correction and miss streak breaker.

The first thing to check when you suspect any compatibility problems with the game or with other mods is to check the mod log (`BATTLETECH\Mods\AttackImprovementMod\Log_AIMAttackImprovementMod.log`), BTML log (`BATTLETECH\Mods\*.log`), and the game's own log (`BATTLETECH\`).

The keyword is "Exception".  It is almost always followed by lots of codes.  If you see *any* exception and see "AttackImprovementMod" in the code below it, please [file an issue](https://github.com/Sheep-y/Attack-Improvement-Mod/issues/new) and attach the log.


# The Story of AIM

If you asked me whether I would play a hardcore mech game like BattleTech, a month before I started doing this mod, my answer would be no.

This is my first serious game modding attempt, and is totally unexpected.

One day in summer 2018 when I pay the online game shops a visit, I noticed that one single game is is on the top of top sellers on GOG, Humble Store, and Steam.  The game is BATTLETECH.  It is not exactly my cup of tea, but I don't see that happens often either.  The game has just been launched, and Steam has a pretty big discount in my local currency.

By the time I finished the campaign, I have written a [GameFAQ guide](https://gamefaqs.gamespot.com/pc/205058-battletech/faqs/75955) and a [data miner](https://github.com/Sheep-y/Sheep-y.github.io/tree/dev/battletech/parser) in Node.js.

That is *almost* the end.

Except that I can't shake the feeling that the called hit chance is wrong.

So, I modded LRM and SRM to fire 500 shots and did some light testing, for the guide.
The first few tests fails my own testing standard, but the result is obvious: the numbers are VERY wrong, in game version 1.0.x.

After I improved my methodology, I did some [large scale tests](https://steamcommunity.com/app/637090/discussions/0/1697176044370891096/) totaling over 60k missiles against live King Crabs.  For a while it was a hot topic on Steam.

The result is not pretty.  And I don't mean to the crabs.

Called shot at the head not only has lower chance to hit the head than non-called shots, but the head is biased in virtually all attacks and has double chance to be hit than intended by normal attacks.

Baffled by the result, I learned how to use programing tools to see game code.  Finding the bugs is the easy part.  Fixing it is the hard part, since I knew *nothing* about BattleTech, paper or code, and I *never* hijacked any code before.

I started by injecting loggings into the system, to learn the process.
These logs later become the Attack Log feature.
How about the roll correction?  A mod kills it.  Can I tune it down instead? (Play with formulas in Excel.) Ok, let's do that.
Hmm, now I need to show the modified hit chance. (Re-learn algebra and coded perhaps the most complicated formula in all BattleTech mods.)

Eventually I fixed the two bugs I intended to fix, plus fixing vehicle called shot.
When I am mostly done, game updates 1.1 landed just the day before I plan to release, and it changed how called shot works.  Took me two whole days to update the mod, before I went back to enjoy the game.

Or so I hoped.

In reality, I now see game bugs everywhere, and many many ways to improve the game.
I want to fix Multi-Target back out.  I want to fix the paper doll.  I want to see more information.  I want to colour the lines and open source it.  LadyAlekto of RogueTech also *helpfully* reported more game bug in form of feature wishes.

All the bug fixes and new features and enhancements is much bigger than what I originally envisioned.  Even as I tie up AIM version 2.0, the ever expanding idea list grow at an even greater pace.  If there is an end in sight, it is an abrupt one when a game that I like better come out, such as Phoenix Point.

This is the story of how I went from "stay away from BattleTech" to "wrote 3500 lines of BattleTech mod" in three month's time.  Now let me see whether Paradox is hiring remote freelancer.

# Learn to Mod

The [source code](https://github.com/Sheep-y/Attack-Improvement-Mod/) of this mod is open and free.
You can take it, modify it, and even release it, provided that you include *your* code when you distribute your work, and don't claim my work as yours.
License: [AGPL v3](https://www.gnu.org/licenses/agpl-3.0.en.html)

Follow these steps to see game code and learn how BATTLETECH mod works:

1. Install [Visual Studio](https://www.visualstudio.com/downloads/) which is free. This mod is developed with VS 2017 Community Edition. You'll need the ".NET desktop development" workload.
1. Down and Run [DnSpy](https://github.com/0xd4d/dnSpy/releases)
1. Select File > Open, and find `BATTLETECH\BattleTech_Data\Managed\Assembly-CSharp.dll`.  This will load the assembly.  It contains most BATTLETECH code.
1. You may now search and browse the assembly!  For example in Edit > Search you can type "GetCorrectedRoll" to find the method.  Clicking on it will show you the roll correction code.
1. Right click on method name (or any identifier) and click "Analyse".  It'll help you find where and how the method is called, or its override hierarchy.
1. Analyse is very fast because it works with compiled code.  It is not 100% accurate, though, sometimes you'll want to exported code and search there instead.
1. Left click the assembly, then File > Export to Project.  This will decompile all code which you can browse with other editor or IDE.
1. Head to the [ModTek wiki](https://github.com/Mpstark/ModTek/wiki) to learn how to make a mod.  For a code mode like this one, you need to compile a [dll](https://github.com/Mpstark/ModTek/wiki/Writing-ModTek-DLL-mods) and perhaps a [`mod.json`](https://github.com/Mpstark/ModTek/wiki/The-mod.json-Format).
1. The code of this mod is available on GitHub: https://github.com/Sheep-y/Attack-Improvement-Mod/ and you can also find other people's mods such as [Firing Line Improvement](https://github.com/janxious/BTMLColorLOSMod) or [MeleeMover](https://github.com/Morphyum/MeleeMover) and we all use different licenses.
1. You may notice that this patch manually calls Harmony to patch things, instead of using annotations. This gives me much better control. Read [Harmony wiki](https://github.com/pardeike/Harmony/wiki) to learn how it works.