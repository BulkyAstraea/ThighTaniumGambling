# ThighTaniumGambling

Fabric / Minecraft 26.1.2 / Java 25. Current version: **1.0.82+26.1.2**.
Install the JAR alongside Fabric API. Neither ThighTanium client is required.

## Automatic slots

Open a Vanguard corpse normally on Hypixel SkyBlock. The reel starts automatically,
lands on an actual server reward, then closes. There are no Play, Settings or History
menus and no setup. Old settings/history files are left untouched but are no longer read
or written. Full loot remains in the server chat.

The reveal uses a seven-second reel, spoiler protection, sounds at 50% and 25% world dim.
Five white fireworks celebrate dye, locket and wisp wins. They continue on the HUD after
real reveals close. Item cards are centered, with occasional near-edge stops that always
retain the correct winner. There is no progress bar. Dye cards never show a multiplier;
normal and jackpot simulations produce at most one dye. Other duplicate items show 2x, etc.

Space / Reveal now skips to the result; Escape exits. Chat is restored on every exit path.
No keys are consumed, corpse clicks automated or simulated rewards sent into chat.

## Optional previews

- `/ttgambling` (also `/slots` or `/Slots`): brief command help, no menu.
- `/ttgambling simulate`: clearly labelled sample opening, any Vanguard item.
- `/ttgambling jackpot`: clearly labelled dye, locket or wisp preview. Only lockets and wisps
  can be doubled. These are illustrative choices, not Hypixel drop probabilities.
- Simulate again preserves the preview type. Close returns directly to the game.

## Other mods

During a confirmed real Vanguard loot block/reel only, optional hooks defer SkyBlocker
6.10.3's Frostbitten Dye effect (item activation, sound and particles), then SkyOcean
1.17.2's dye-winning Vanguard spinner after 2.5 seconds. No chat events are replayed.
Other dye drops and simulations do not arm this delay. Effects received before a Vanguard
header are not delayed. Queues clear on disconnect/world change. Hooks inspect target
signatures and skip absent/incompatible implementations. In-game integration still needs
user testing; SkyOcean's installed version has a Vanguard spinner, not a separate dye effect.

## Assets and checks

All 26 item visuals are bundled and registered in the item/block texture atlases.
The four supplied wiki PNGs are used unchanged for the locket, Frozen Scute, Caged Wisp
and Frostbitten Dye. Other artwork uses official Hypixel pack models and Minecraft skins.
Credits are in `assets/thightaniumslots/WIKI-ICONS.txt`, `HYPIXEL-LICENSE.txt` and
`asset-sources.json`. Artwork remains the property of its owners; no endorsement is implied.

Build with Java 25: `./gradlew.bat build check`.
Checks cover loot parsing, aggregation, landing bounds, simulation, single dyes, deferred
effects and resource resolution. The startup check loads the firework implementation
without Minecraft bootstrap. Verification does not launch Minecraft.



The display name and JAR name are ThighTaniumGambling. The internal mod ID stays thightaniumslots
for compatibility, so remove the old Slots JAR before installation. Legacy command aliases still work.


1.0.82: Rocket sprites stay upright and rise vertically without sideways drift.

