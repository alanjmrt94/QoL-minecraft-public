<p align="center">
  <img src="assets/icon.png" alt="Quality of Life for Minecraft" width="192" height="192" />
</p>

# Quality of Life for Minecraft

<small><a href="README-es.md"><img src="https://flagcdn.com/w20/ar.png" width="20" alt="Leer versión en Español" /> Leer en Español</a></small>

Small, practical improvements for everyday Minecraft — **Forge**, **Fabric**, and **NeoForge**.

**This is my third Minecraft mod, created by [alanjmrt94](https://github.com/alanjmrt94).**  
**Current version:** `1.20.1-0.6.0-alpha.1` (**alpha**) · Minecraft **1.20.1** · Client & dedicated server  

> Release notes: [changelog.txt](changelog.txt) (always in English) · earlier notes still listed: `1.20.1-0.5.2` / `1.20.1-0.4.1`  
> This alpha ships on **1.20.1** (Forge / Fabric / NeoForge). Ports to **1.21.1** (all three loaders) and **26.1 / 26.2** (Fabric + NeoForge) are planned.

---

## What is this?

**Quality of Life for Minecraft** adds configurable comfort features so survival and creative feel smoother — without turning into a huge kitchen-sink pack.

You configure everything from an **in-game menu** (Mods → Config / Mod Menu, or the creative **QoL Config Tablet**). Hover any option for a short tooltip.

Text under **See details** is optional: balance numbers, config keys, and fine rules.

## Features (v0.6.0-alpha)

### Water landscape dye

- **Water Dye Diffuser** — Canister that paints lakes and oceans with a persistent color overlay (vanilla water stays vanilla).
  <details>
  <summary>See details</summary>

  **Craft:** iron ingots + glass + empty bucket.  
  **Fill:** water first (vanilla/dirty bucket, water bottle, cauldron, or right-click ocean/river), then **one** dye color only — pink, lime, green, cyan, purple, magenta, or red — up to **64** charges (no color mixing).  
  **Load dye:** on the placed block, both hands (water + dye), or right-click dye onto the diffuser item in inventory. At **64** it **seals** (no more dye; sneak-empty blocked).  
  **Paint:** right-click water while holding a ready diffuser, or empty-hand use on a placed ready diffuser. **Sneak + empty hand** removes a nearby stain.  
  **Radius:** circular disc, linear **2** (1 dye) → **16** (64 dyes); vertical ±8. Persists in world data (max **256** stains/dimension). Breakable by hand (~1 s).  
  Config: `water_landscape_dye`.

  </details>

### Sleep & rest

- **Heal on sleep** — Wake from a bed and recover hearts.
  <details>
  <summary>See details</summary>

  Default **1 heart / 2 HP**; `0` disables.

  </details>

- **Campfire sleep bonus** — A lit campfire nearby adds extra hearts on wake.
  <details>
  <summary>See details</summary>

  Default **+1 heart** (**2 HP** without → **4 HP** with). Config: `campfire_sleep_bonus_hearts`.

  </details>

- **Campfire rain** — Lit campfires can go out in rain or storms; a roof helps.
  <details>
  <summary>See details</summary>

  **25%** rain / **80%** thunder. Roof with **2 air blocks** between fire and ceiling → **0%** rain / **10%** thunder. Includes soul campfires. Config: `campfire_rain_extinguish`.

  </details>

### Torches

- **Wet torches** — Water and weather can put them out; they dry and can relight on their own or with flint and steel.
  <details>
  <summary>See details</summary>

  **Water** in the block → **wet** (100%). Outdoors: **wind 10%** / **snow 20%** / **snow+rain 50%** → **unlit** (cold biomes: **20%** → wet). Rain alone does not extinguish. Dry ~**2 min** (faster near lit campfire, radius 12); auto-relight ~**2 min** (or flint and steel). Sand/gravel crush → **unlit** drop. Torch items in water/rain become wet. Config: `wet_torches`, `torch_dry_ticks`.

  </details>

### Survival movement

- **Movement hunger** — Jumping or sprinting costs a bit more hunger.
  <details>
  <summary>See details</summary>

  **+5%** for jump or sprint; **+10%** for both at once. Config: `movement_hunger`.

  </details>

### Cauldrons & water

- **Cauldron dyeing** — Tint the water and use the color on wool, beds, concrete, and leather.
  <details>
  <summary>See details</summary>

  Intensity **1–3** (black ink included). Dye wool, beds, concrete/powder, and **full leather** (helmet, chestplate, leggings, boots). Concrete drains water (intensity 1 lasts least). Levels 1–3 visible. A **water bucket** sets level 3 and **dilutes** intensity gradually (does not hard-reset color).

  </details>

- **Colored water bottles** — Bottle dyed water, pour it back, or place bottles in groups.
  <details>
  <summary>See details</summary>

  Item `colored_water_bottle` (potion look). Drink: −½ heart and 20% random effect. Glow adds a **glint**. **Shift+right-click** places up to **32** bottles per block (vanilla + QoL).

  </details>

- **Dirty water** — Pull dye into a bucket, empty it, or bottle it.
  <details>
  <summary>See details</summary>

  Empty bucket + dyed cauldron → dirty bucket (no item glint). Emptying → empty bucket / murky puddle. Dirty bottle: poison 2s, −hunger, 45% random; composter ~50%. See [Special actions](#special-actions).

  </details>

- **Glow ink** — Water glows a little without washing out the dye.
  <details>
  <summary>See details</summary>

  Vanilla monochrome light + colored particles. Glow lightens without washing out dye (level 3 stays intense). Beds/wool/leather/bottles with glow show a glint (mixins).

  </details>

- **Faster rain fill** — Cauldrons fill faster in rain and thunderstorms.

- **Fresh / salt water** — Bottling in the ocean is not the same as a river or cauldron.
  <details>
  <summary>See details</summary>

  Ocean = salt (nausea). River/cauldron = fresh (drinkable). Distinct tooltips and tints.

  </details>

- **Simple distillation** — Water cauldron over fire: take salt or fresh water by hand.
  <details>
  <summary>See details</summary>

  Empty hand → salt; sneak + bottle → fresh water.

  </details>

- **Distiller** — Alembic with fuel: salt water → fresh + salt (also bottle-free with neighboring cauldrons).
  <details>
  <summary>See details</summary>

  GUI: fuel, salt water on top, 3 empty bottles → fresh + salt. Progress overlays (heater, liquid, tubes). Recipe: copper + glass + iron + bottle. Sneak opens the manual. Fuels `#qolminecraft:distiller_fuels` (torch ≈½ coal, blaze ≈3, stick ×2, lava ×3 furnace). Lava leaves a **molten stone bucket** (pour: stone or rare ore). Torch/blaze also fuel furnaces/blast furnaces. Adjacent ocean/salt cauldron → fresh cauldron + salt (needs fuel).

  </details>

- **Salt & seasoning** — Season food with salt or sugar; craft a salt block.
  <details>
  <summary>See details</summary>

  NBT `qol_seasoning=salt|sugar` + tags. Salt +25% hunger; sugar heals + Speed. Overlay/glint. Legacy salted potato/bread remain. Salt block = 9 salt.

  </details>

- **Sponge on dyed cauldron** — Clears dye/glow without emptying the water.

- **Lava cauldron** — Emits light and burns anyone standing inside.
  <details>
  <summary>See details</summary>

  Light default **15** (configurable). Damage on/off via config.

  </details>

- **Snow cauldron / ice cream** — Freezes, fills with snow, and can make ice cream.
  <details>
  <summary>See details</summary>

  Freeze scales with level (config). **Snow block** = full; **snowballs** add up to 3 levels. Ice cream: milk + sugar + dye → flavor; **cone** (paper+sugar) scoops (cookie-like, freeze ~2 s).

  </details>

- **Enter cauldron** — Water/dyed wets you; some mobs behave differently.
  <details>
  <summary>See details</summary>

  Config `cauldron_enter_effects` / `cauldron_water_wets`. Chickens get stuck; parrots float.

  </details>

- **Comparator signal** — The cauldron reports what is inside.
  <details>
  <summary>See details</summary>

  Empty 0 · water/dyed/snow 1–3 · lava 3 · dyed + fish level+1 (max 4).

  </details>

- **Fish in cauldron** — Store tropical or puffer; puffer poisons.
  <details>
  <summary>See details</summary>

  Bubbles in water/dyed. **Shift + empty hand** to remove. Puffer poisons on remove or while standing inside.

  </details>

- **Cook in cauldron** — With heat below, cook raw food (or the stored fish).
  <details>
  <summary>See details</summary>

  Heat: fire, lit campfire, lava, magma… Costs **1 water level**. Fish + empty hand + heat cooks the fish.

  </details>

- **Dirty potatoes & mud** — Sometimes you harvest a dirty potato; washing it dirties the water and ends in mud.
  <details>
  <summary>See details</summary>

  - Fully grown harvest: default **5%** chance (`dirty_potato_chance`) of a dirty potato.
  - Eating: lower saturation; chance of brief hunger.
  - Wash in a water cauldron → clean potato; water turns light-brown intensity 1→2→3.
  - At 3: **wet mud** + muddy cauldron (bottleable). Extra washes lower the level.
  - Wet mud / bottle: composter ~50%; furnace → `minecraft:mud`; place → dirt (hole) or mud puddle (slips; does not vanish in rain).
  - Extended vanilla mud: ice-like slip + slowdown; standing still sinks ~⅓ (faster in rain/thunder).
  - Weather: rain can turn dirt→mud; clear weather dries mud→dirt (skips swamp/mangrove). Config: `mud_world_effects`.

  </details>

### Food & drinks

- **Food spoilage** — Cooked food ages if you do not store it well.
  <details>
  <summary>See details</summary>

  Fresh → stale → rotten flesh (configurable ticks; toggleable). Tooltip shows remaining time. Tag `#qolminecraft:never_spoils`. Seasoned food spoils slower.

  </details>

- **Fridge** — Slows spoilage; animated door, hollow interior, and a plastic shelf.
  <details>
  <summary>See details</summary>

  Matte/porous (not combinable). Insulation + snow; spoilage ×0.25. Soft foam open/close sounds; vanilla-aligned inventory GUI; shelf item render. Interior is not artificially brightened.

  </details>

- **Reinforced fridge** — Iron version; combines vertical, Side by Side, or with a freezer.
  <details>
  <summary>See details</summary>

  Upgrade with iron or craft from scratch. **2 vertical** = 54 slots; **2×2 French-door Side by Side** (one body, glass shelves, redstone slot for interior light while open); **1 + freezer**. Spoilage ×0.15. Iron door/trapdoor-style sounds (one play per open/close). Wide GUI with centered player inventory.

  </details>

- **Freezer** — Pauses spoilage with snow; two side-by-side share a double lid and snowy cabin.
  <details>
  <summary>See details</summary>

  8 food + 8 snow (**16 snowballs** per sibling slot). Accepts **redstone dust or block** for snow-burst power (neighbor signal also works). Opening a charged double freezer puffs snow; soft cold overlay; freeze damage only after **~10 s** with the GUI open and snow loaded. Translucent snow liner interior. GUIs (single, double, combo) align player slots like a vanilla chest.

  </details>

- **Oranges & juice** — Juice is stronger than the fruit; acacia leaves can drop oranges.
  <details>
  <summary>See details</summary>

  Clears poison, short resistance, **−10%** drowned damage. Press: orange + bottle in crank+hopper. Can pour into a jar. Optional tree telegraph: `tree_fruit_visuals` (default off; oranges also need `orange_enabled`).

  </details>

#### Crank (mill)

- **Crank + hopper** — Hold click to grind; products go to a chest.
  <details>
  <summary>See details</summary>

  Place the crank **on top** or on a **side** of the hopper. Spout only when attached; first link is kept. Unmilled inputs stay locked; products move to a chest below. Breaking flushes to the chest (**25%** spill chance). Action-bar progress, grindstone sound, redstone pulse 2–4 ticks. Recipes (toggles): coffee, cocoa, wheat→flour, bone→bone meal, cobble→gravel, orange+bottle. Also `coffee_grind_turns`.

  </details>

#### Coffee

- **Coffee crop & drinks** — Bush, paper cups, and soft-compat with Coffee Delight.
  <details>
  <summary>See details</summary>

  Bush on **sand**; wild berries in warm biomes (if Coffee Delight is present, Fabric skips duplicate worldgen). Berries → beans → grounds (also brown dye). **Slime glue** + **paper cup**. Bowl or cup coffee (−10% hunger, stamina, long Speed). Coffee with milk (−20% hunger, +1 HP, clears poison). Serve/drink from jar. Heat 3 min on fire/campfire/magma/lava. Sugar boosts effects. Soft-compat CD: tags, 1:1 conversions, roasting, CD black coffee crafts, cutting board.

  </details>

#### Chocolate

- **Chocolate chain** — From cocoa to hot chocolate and chocolate milk.
  <details>
  <summary>See details</summary>

  Cocoa powder → butter → bar. Hot chocolate / chocolate milk (~2 HP). Hot: freeze protect 3 min. Same heat/sugar rules as coffee. Does not clear poison.

  </details>

#### Jars

- **Glass jar** — Store several fluids and place the jar to serve.
  <details>
  <summary>See details</summary>

  Up to **4 servings**. Fill from the other hand (milk, coffee, chocolate, water, juice, cocoa…). Drinking milk clears effects. Shift+use empties. Shift+click places a jar; empty bowl serves. Config: `jars_enabled`.

  </details>

### Animals

- **Animal sleep** — Some mobs sleep by day or night with zzz particles.
  <details>
  <summary>See details</summary>

  Tags `#qolminecraft:diurnal_sleepers` / `nocturnal_sleepers`. Wake on damage, rain, or nearby player. Configurable chance and radius.

  </details>

### Inventory & building

- **Pinned hotbar slots** — Key **P**: lock a hotbar slot so you do not drop or move it by accident.
  <details>
  <summary>See details</summary>

  Drop needs double confirm. Quick-move skips pins. Icon in GUIs. Persist in player NBT.

  </details>

- **Ghost block** — Preview the block before you place it.
  <details>
  <summary>See details</summary>

  Correct slab/stair orientation. Key **G**. **Default off**.

  </details>

### Writing

- **Pencil, pen & notepad** — Note day, nick, coords, and biome without losing the book on death.
  <details>
  <summary>See details</summary>

  Pencil: sticks+flint. Pen: sticks+ink+`#qolminecraft:iron_nuggets` (+50% durability; refill with ink). Notepad: book + tool. Shift+use or book UI buttons. Writing tools lose durability on insert.

  </details>

### Other

- **In-game config** — Menu with tooltips; also `config/qolminecraft-common.toml`.
  <details>
  <summary>See details</summary>

  Creative QoL tablet. Local/online analytics (online after license). Sample block/loot. Dev: `debug.creative_tab = true` → **QoL Debug** tab (restart).

  </details>

### Bedrock vs QoL (cauldrons)

Java + this mod are **not** a 1:1 copy of Bedrock cauldrons. QoL keeps its own rules; full Bedrock potion/arrow parity is later **opt-in**.

<details>
<summary>See comparison table</summary>

| Topic | Bedrock (typical) | QoL (this mod) |
|-------|-------------------|----------------|
| Dye mix | Colors can blend (RGB-style) | One dye line at a time; new dye → intensity 1 |
| Strength | Mostly dyed or not | Intensity **1–3** + optional **glow** |
| Bottle / bucket out | Usually plain water / empty bucket | **Colored bottle**; dirty bucket keeps tint |
| Add water | Often strips dye hard | Dilutes gradually |
| Leather / wool / beds / concrete | Leather focus | Full leather set + wool/beds/concrete |
| Potions in cauldron | Fill / tip arrows / etc. | **No** — not a brewing stand |
| Tip arrows | Yes on Bedrock | **No** in this version |
| QoL-only | — | Distiller, fresh/salt, mud, fish, cook, enter, snow, ice cream, lava |

No separate “Legacy brewing” block or full potion tree inside the cauldron.

</details>

### Special actions

Item combinations (hands or inventory) that are not crafting-table recipes.

<details>
<summary>See action tables</summary>

#### Items in each hand

Main hand + offhand (`F`). Right-click in air or on a block that does not consume the use:

| Hand A | Hand B | Result |
|--------|--------|--------|
| Empty glass bottle | Dirty water bucket | 1 dirty bottle; empty bucket |
| Sugar | Coffee / milk / chocolate bowl or cup | Sugars the drink (boost + extra Speed) |
| Milk bucket or jar | Coffee bowl/cup | Coffee with milk |
| Milk bucket or jar | Hot chocolate | Chocolate milk |
| Empty glass jar | Milk / drink / bottle / juice / cocoa | Fills jar (+1 serving) |
| Jar with milk (use) | — | Drink milk (−1 serving) |
| Jar with coffee (use) | — | Drink coffee (−1 serving) |
| Filled jar (Shift+use on block) | — | Places placed jar |
| Empty bowl/cup | Jar (hand or placed) with coffee | Serves coffee |
| Coffee or hot chocolate | Placed jar with milk | Latte / chocolate milk |
| Water source (bucket/bottle) | Allowed dye | Fills a held/placed diffuser (water then pigment) |
| Ready Water Dye Diffuser (use on water) | — | Paints a circular stain; radius from charge count |
| Empty hand on placed ready diffuser | — | Same paint |
| Sneak + empty hand on diffuser / near stain | — | Empties diffuser (if not sealed) or removes nearby stain |

#### Inventory (cursor)

| Action | Result |
|--------|--------|
| Empty bottle on the **cursor** + right-click a dirty bucket | Dirty bottle on cursor; slot becomes empty bucket |
| Dirty bucket on the **cursor** + right-click empty bottle(s) | Fills 1 bottle and empties the bucket |
| Allowed dye on the **cursor** + right-click Water Dye Diffuser | +1 pigment (same color only; needs water; stops at 64) |

</details>

## How to configure

1. **In-game:** Options → Mods → **Quality of Life for Minecraft** → Config  
   - Fabric: **Mod Menu** if installed  
   - Or the creative **QoL Config Tablet**  
2. **File:** `config/qolminecraft-common.toml`  
3. Click **Save & Apply** so changes reload immediately  

## Compatibility

| | |
|---|---|
| Minecraft | **1.20.1** (this alpha) · **1.21.1** planned · **26.1 / 26.2** planned |
| Loaders | **1.20.1 / 1.21.1:** Forge · Fabric · NeoForge · **26.x:** Fabric · NeoForge only |
| Java | **17+** on 1.20.1 · **21+** on 1.21 · **25+** expected on 26.x |
| Sides | Client and/or dedicated server |

Download the JAR that matches your loader (`*-forge`, `*-fabric`, or `*-neoforge`). Do not mix loaders.

## License

See [LICENSE.md](LICENSE.md).

- Use and distribute freely (including on servers), **with authorship credit** to **alanjmrt94**
- Derivatives must keep credit to the original author
- **Commercial sale is not allowed**

## Links

- Docs & changelog: [github.com/alanjmrt94/QoL-minecraft-public](https://github.com/alanjmrt94/QoL-minecraft-public)
- Discord: [discord.gg/CcUNTJjPD](https://discord.gg/CcUNTJjPD)
- CurseForge: pending first upload
- Changelog: [changelog.txt](changelog.txt)

Development source is a **closed private project** ([QoL-minecraft](https://github.com/alanjmrt94/QoL-minecraft)). Public README and release notes live in [QoL-minecraft-public](https://github.com/alanjmrt94/QoL-minecraft-public).
