---
{"dg-publish":true,"permalink":"/10-system/07-spell-creation-guide/","tags":["rules","magic","spells","guide","homebrew"],"dgShowBacklinks":true,"dgShowInlineTitle":true,"dgShowFileTree":true,"dgEnableSearch":true,"dgShowToc":true,"dgShowTags":true,"noteIcon":""}
---



> **Purpose:** This guide is for both **DMs** and **players** who want to create new spells (Powers) that feel mechanically balanced and tonally consistent with the world of [[30_Locations/Continents/Ersetu\|Ersetu]]. Read this *after* [[10_System/06 The Magic System\|06 The Magic System]] — that chapter covers how casting works; this one covers how to **design** what gets cast.

---

Magic in this world is **applied physics**, not wish-fulfilment. Every spell should feel like a precise, engineered application of [[50_Magic/Glossary/mana\|mana]] through a **matrix of mana canals**. When designing a spell, ask yourself:

1. **What is the mana physically doing within the canals?** Is it compressing air, restructuring molecular bonds, warping spatial coordinates, or stimulating neural pathways? If you can't describe the physical transformation, the spell is too vague.
2. **What are the limits?** Every spell has a cost, a range, a duration, and a failure mode. A spell with no limitations is not a spell — it's a plot device.
3. **What school does this belong to?** If you can't place it cleanly in one school (or a school + specialization), you're probably blending effects that should be two separate spells.
4. **Does this feel like something a student would learn at this tier?** A Tier 1 effect should be something a first-year could manage with concentration; a Tier 5 effect should terrify a senior professor.

> [!TIP] The Golden Rule
> **If a real-world physicist would call your spell "magic" even in a world where mana exists, it's too fantastical.** Spells should feel like engineering feats performed with an exotic energy source, not miracles.

---

## 2. Anatomy of a Spell

Every spell in this vault follows a consistent structure. When creating a new spell, replicate this format exactly:

### YAML Frontmatter
```yaml
---
tags: [spell, school-name]
type: spell
tier: 1-5
magic_school: SchoolName
specialization: None or SpecName
cost: (equal to Tier, unless modified)
description: "A brief one-line summary for the database index."
---
```

### Body Format
```markdown
### Spell Name
*[[Soul Link|School]] (Tier X)*
**Mana Cost:** X

Flavour description: What does this look like? What canal structure does the caster shape? What does the target experience? Write 2-4 sentences of evocative, grounded prose.

**System:** The mechanical resolution. Include:
- What attribute + skill is rolled (how the canals are shaped)
- The difficulty (Target Number)
- What happens on success (damage, duration, effect)
- Any specific Overcharge scaling points (or just general guidelines)
- Any special failure consequences (errors in the canal geometry)
```

---

## 3. The Tier Power Budget

This is the **most important section** for balance. Each tier has a strict power budget. A spell *must* fit within its tier's ceiling. If it exceeds any column, it belongs at a higher tier.

| Budget                                | Tier 0 (Unstructured) | Tier 1 (Basic)     | Tier 2 (Adept)           | Tier 3 (Advanced)                      | Tier 4 (Master)                         | Tier 5 (Mythic)                      |
| :------------------------------------ | :-------------------- | :----------------- | :----------------------- | :------------------------------------- | :-------------------------------------- | :----------------------------------- |
| **Difficulty (TN)**                   | Automatic (No Roll)   | 3–5                | 5–6                      | 6–7                                    | 7–8                                     | 8–9                                  |
| **Required Successes**                | —                     | 1                  | 2                        | 3                                      | 4                                       | 5                                    |
| **Mana Cost**                         | 1                     | 1                  | 2–4                      | 3–9                                    | 8–16                                    | 15–25                                |
| **Damage (Physical)**                 | 0 (Harmless)          | 1                  | 2                        | 3–4                                    | 4–5                                     | 5+ / Aggravated                      |
| **Damage ([[50_Magic/Glossary/Soul Integrity\|Soul]])** | —                     | —                  | —                        | 1 (Forbidden only)                     | 1–2                                     | 2–3                                  |
| **Range**                             | Touch / Personal      | Touch / 5m         | Near / 10–20m            | Far / 50m                              | Very Far / 100m+                        | Continent / Planar                   |
| **Duration**                          | Fleeting / Seconds    | Instant / 1 minute | Minutes (= [[10_System/Attributes/Magical/Finesse\|Finesse]])  | Scene (10–30 min)                      | Hours / Sustained                       | Permanent / Days                     |
| **Area of Effect**                    | Handful / Tiny object | Single target / 1m | Close-quarters / 3m      | Room-clearing / 10m                    | Building / City block                   | District / City-wide                 |
| **Targets**                           | 1                     | 1                  | 1–2                      | Small group (3–5)                      | Crowd (10+)                             | Area-wide                            |
| **Complexity**                        | Simple parlor trick   | One simple effect  | One effect + minor rider | Combined effect or conditional trigger | Multi-stage or sustained complex effect | Reality-altering or permanent change |
### mana cost
> [!NOTE] Mana Cost Formula
> **Cost = Tier × Multiplier**, where multiplier ranges from **max(1, Tier−2)** to **Tier**.
>
> | Tier | Multiplier | Cost Range |
> | :--- | :--- | :--- |
> | T1 | 1 | 1 |
> | T2 | 1–2 | 2–4 |
> | T3 | 1–3 | 3–9 |
> | T4 | 2–4 | 8–16 |
> | T5 | 3–5 | 15–25 |
>
> A simple utility spell uses the minimum multiplier. A devastating combat spell uses the maximum. **High-tier magic is never cheap.**

> [!IMPORTANT] Exceeding the Budget
> If your spell exceeds the budget in **one** column, it likely belongs one tier higher. If it exceeds in **two or more** columns, it *definitely* belongs higher. Conversely, if a spell is well under budget in most columns, consider whether it's actually a lower tier.

### Power Scaling by Tier

Use this table to calibrate the *narrative weight* of each tier — what the spell feels like in the fiction, who can cast it, and what kind of story moment it represents.

| Tier       | Mage Level                                | Narrative Weight                                                                        | Real-World Analogy                                                           | Example Moment                                                                                                          |
| :--------- | :---------------------------------------- | :-------------------------------------------------------------------------------------- | :--------------------------------------------------------------------------- | :---------------------------------------------------------------------------------------------------------------------- |
| **Tier 1** | First-year student                        | A parlour trick or basic utility. Useful but unimpressive. Cantrip-level.               | Flicking a lighter, using a flashlight, picking a simple lock                | A student lights a candle across the room to impress a date.                                                            |
| **Tier 2** | Competent student                         | A reliable tool or weapon. The bread-and-butter of a working mage.                      | A handgun, a pair of binoculars, a lock-pick set                             | A mage fires a force bolt at an advancing monster in the [[30_Locations/Other/Dungeon\|Dungeon]].                                                   |
| **Tier 3** | Advanced student / Junior professional    | A significant tactical advantage. Requires real skill and often draws attention.        | A grenade, a surveillance drone, a shaped explosive charge                   | A combat mage deploys a homing missile that chases a fleeing target through a corridor.                                 |
| **Tier 4** | Seasoned professional / Academy professor | A strategic asset. Changes the shape of a battle or mission. Commands respect and fear. | An armoured vehicle, a satellite feed, controlled demolition of a building   | A war-mage erects a sustained force dome over an entire squad while artillery rains down.                               |
| **Tier 5** | Master / Living legend                    | A world-altering event. Nations take notice. History books record this.                 | A tactical missile, a city-wide blackout, a permanent reshaping of geography | A lich raises an army of the dead from a battlefield. A dimensionalist opens a permanent portal between two continents. |

---

## 4. School Design Lenses

Each school has a distinct *verb* — the fundamental action its mana performs. When designing a spell, your effect must flow from that verb. If you find yourself stretching to justify why a spell belongs in a school, it probably doesn't.

| School | Core Verb | What Mana Does | What It Does NOT Do |
| :--- | :--- | :--- | :--- |
| **[[10_System/Schools/Projection/Projection\|Projection]]** | *Generate* | Creates energy from nothing: force, heat, light, electricity | Does not alter existing matter or create persistent objects |
| **[[10_System/Schools/Alteration/Alteration\|Alteration]]** | *Restructure* | Changes the properties of existing matter: density, flexibility, composition | Does not create matter from nothing or generate energy |
| **[[10_System/Schools/Dimensionalism/Dimensionalism\|Dimensionalism]]** | *Displace* | Moves things through space: teleportation, portals, spatial locks | Does not create energy or alter matter's properties |
| **[[10_System/Schools/Divination/Divination\|Divination]]** | *Perceive* | Gathers information: sensing, scrying, prediction | Does not change anything — pure observation |
| **[[10_System/Schools/Illusionism/Illusionism\|Illusionism]]** | *Deceive* | Creates false sensory data: images, sounds, phantom sensations | Illusions are not real; they cannot physically harm or create real objects |
| **[[10_System/Schools/Animation/Animation\|Animation]]** | *Animate* | Infuses objects with a fragment of the caster's mind for autonomy | Cannot exceed the caster's own knowledge; does not create intelligence |
| **[[01_Rules/Schools/Ward/Ward\|Ward]]** | *Persist* | Pre-casts magic into spatial anchors that trigger on conditions | Wards are static and area-bound; cannot be cast "on the fly" in combat |
| **[[10_System/Schools/Soul Magic/Soul Magic\|Soul Magic]]** | *Violate* | Directly interacts with the soul, death, and the metaphysical self | Requires [[50_Magic/Traits/Merits/Forbidden Knowledge\|Forbidden Knowledge]]; every use triggers [[50_Magic/Glossary/Loop-Sanity\|Sanity]] checks |

> [!NOTE] School Overlap
> Some effects sit between two schools. In those cases, the spell belongs to the school that best describes the **primary mana action**, and the secondary school becomes a **Cross-School Prerequisite**. For example, a *Homing Missile* (Tier 3) is an [[10_System/Schools/Animation/Animation\|Animation]] effect that requires [[10_System/Schools/Projection/Projection\|Projection]] as a prerequisite — the animation (tracking) is the hard part, not the bolt itself.

---


## 5. Cross-School Spells

Sometimes a desired effect inherently spans the domains of multiple schools. When designing a cross-school spell:

1. **Identify the primary school.** This determines which [[50_Magic/Glossary/Shaping\|Shaping]] skill is rolled. The spell is "purchased" using dots from this school.
2. **Identify the secondary prerequisite.** The collateral school (or schools) required. List this explicitly in the spell description.
3. **The tier cannot exceed either school.** If a spell is Tier 3 under its primary school and requires a secondary, the caster needs at least 3 dots in the primary *and* the listed dots in the secondary.

**Example structure:**
> *Homing Missile* — [[10_System/Schools/Animation/Animation\|Animation]] Tier 3
> **Cross-School Prerequisite:** [[10_System/Schools/Projection/Projection\|Projection]] 2
> *This means the caster needs Animation 3 and Projection 2 to learn this spell.*

---

## 6. Worked Examples

See Spells Index for spell that are ready to go

### Example A: Creating a Tier 1 Projection Spell

**Step 1 — Intent:** "I want a spell that lets me create a small burst of light to blind someone temporarily."

**Step 2 — School Check:** This is generating energy (light) from mana → **Projection**. ✅

**Step 3 — Tier Budget Check:**
- Damage: None (utility effect) ✅
- Range: 5m ✅
- Duration: Instant (1 round of blindness) ✅
- Targets: 1 ✅
- Complexity: One simple effect ✅
→ Fits cleanly in **Tier 1**.

**Step 4 — Write it up:**
```
### Flash Burst
*Projection (Tier 1)*
**Mana Cost:** 1

The mage channels a sharp pulse of mana into visible light,
releasing it as a blinding flash from their palm.

**System:** Roll Willpower + Projection vs the target's
passive Mind Defense. On success, the target is Blinded
for 1 round (they suffer -3 dice to all actions requiring
sight). No damage is dealt.
```

---

### Example B: Creating a Tier 4 Alteration Spell

**Step 1 — Intent:** "I want a spell that turns a stone wall into liquid for 10 seconds so I can walk through it."

**Step 2 — School Check:** Restructuring existing matter → **Alteration**. ✅

**Step 3 — Tier Budget Check:**
- Range: Touch ✅ (but affecting a large structure)
- Duration: ~10 seconds (short but with major effect) — pushing Scene-level impact
- Area: A 2m x 2m section of wall — Large room-scale manipulation
- Complexity: Single effect but on a massive structural scale
→ This is restructuring dense inorganic matter on a significant scale. **Tier 4**.

**Step 4 — Write it up:**
```
### Liquidation
*Alteration (Tier 4)*
**Mana Cost:** 4

The mage presses their hand against a solid surface and
floods it with mana, temporarily dissolving the molecular
bonds holding the material together. The stone, metal, or
wood becomes a thick, viscous liquid for a brief window.

**System:** Roll Calculation + Alteration vs difficulty 7.
On success, a 2m x 2m section of non-magical wall becomes
passable liquid for a number of rounds equal to the
caster's Finesse. Anyone can walk through during this
window. The material resolidifies violently when the
duration ends — anyone still inside takes 4 Physical
Damage (Aggravated).
```

---

### Example C: Creating a Tier 3 Cross-School Spell

**Step 1 — Intent:** "I want a ward that, when triggered, fires a concussive blast at the intruder."

**Step 2 — School Check:** The *persistence* and *trigger* are [[10_System/Schools/Abjuration/Abjuration\|Abjuration]] (specifically the Ward specialization). The *blast* is [[10_System/Schools/Projection/Projection\|Projection]]. The primary action is the ward (it sits there waiting), so this is an **Abjuration** spell with a **Projection prerequisite**.

**Step 3 — Tier Budget Check:**
- Range: Area-bound (10m radius ward zone) — Large room ✅
- Duration: Weeks (with crystal battery) — persistent ✅
- Damage: 2 Physical on trigger — moderate ✅
- Complexity: Combined effect — conditional trigger + energy release ✅
→ Persistent area + conditional trigger + secondary school damage = **Tier 3**.

**Step 4 — Write it up:**

```
### Concussive Trap Ward
*Abjuration (Tier 3)*
**Specialization:** Ward
**Cross-School Prerequisite:** Projection 2
**Mana Cost:** 3 (+ crystal battery for persistence)

The mage inscribes a geometric ward matrix around a
doorway or chokepoint, embedding a compressed Projection
charge into the ward's trigger layer. When an unauthorized
person crosses the boundary, the ward detonates the stored
energy as a focused concussive blast.

**System:** Ward creation requires a full scene of
uninterrupted preparation. Roll
Calculation + Abjuration vs difficulty 6 to set the ward.
When triggered, the intruder must resist with Athletics
vs difficulty 6. On failure: 2 Physical Damage and the
target is knocked prone. Each Overcharge point spent on the
original ward roll adds +1 to the trigger's difficulty.
The ward recharges after 1 hour if its power source
remains intact.
```

---

### Example D: Designing a Spell Formula Item (Optional Support System)

**Step 1 — Intent:** "I want to create a ring that holds a Tier 2 ward so it can activate instantly in combat."

**Step 2 — School Check:** The player uses the **[[50_Magic/Glossary/Spell Formula\|Spell Formula]]** support skill to anchor a chosen spell into an item. The underlying spell (the Ward) must be a spell the creator (or a collaborator) knows how to cast natively.

**Step 3 — Tier Budget & Item Limits:**
- The item must be resilient enough to act as an anchor (a solid metal ring works).
- The creator must have at least 2 dots in **Spell Formula** to safely store a Tier 2 spell into an item without the diagram collapsing. 
- The resulting item activates instantly without a casting roll, but costs **double the usual [[50_Magic/Glossary/mana\|mana]]** (4 mana instead of 2).

**Step 4 — Write it up:**
```
### Defender's Ring (Spell Formula Item)
*Spell Formula (Tier 2)*
**Item Required:** A sturdy metal ring (Affluent Funds).
**Stored Spell:** Tier 2 Abjuration (Ward specialization) (requires a collaborator or creator with Abjuration 2).

An intricately engraved ring that houses a compressed 
force-shield boundary, designed to trigger the moment 
the wearer is struck with significant kinetic energy.

**System:** Creating the formula takes a day of work and 
a successful Finesse + Academics roll. Once finished, 
the wearer can trigger the Ward as a free action in combat 
by feeding it 4 Mana. 
```

---

## 7. Common Pitfalls

| Pitfall | Why It's a Problem | Fix |
| :--- | :--- | :--- |
| **"It just works"** | No roll, no cost, no limits described | Every spell needs a roll, a cost, and a failure case |
| **School bleed** | An "Abjuration" spell that generates lightning on trigger | The *trigger* is Abjuration; the *lightning* is Projection. Split into two spells or add a Cross-School Prerequisite |
| **Flat power** | A Tier 2 spell that does 4 damage and hits a building | Check the Tier Power Budget table. This is Tier 4+ |
| **No scaling** | Overcharge does nothing | Rely on Universal Overcharge or define what specific Overcharge grants (+damage, +duration, +targets) |
| **Missing flavour** | "Deals 3 damage to one target within 10m" | Describe what the caster *does*, what the target *sees* and *feels* |
| **Permanent at low tier** | A Tier 2 spell with a permanent transformation | Permanent effects start at Tier 5. Use duration scaling instead |
| **No failure consequence** | Spell fizzles but nothing bad happens | At minimum, the mana is lost. For higher tiers, consider backlash |

---

## 8. GM Adjudication Tips

When a player proposes a homebrew spell during play:

1. **Identify the school immediately.** Ask: "What is the mana *doing*?" If they can't answer cleanly, the spell needs more thought.
2. **Check the Tier Power Budget.** Compare their proposed effect against the table. If it exceeds two columns, bump the tier.
3. **Assign a difficulty on the fly.** Use the tier's TN range as your baseline and adjust ±1 based on circumstances.
4. **Ask for the cost.** The mana cost is always equal to the Tier at minimum. If the effect is stretching the tier, charge +1 mana.
5. **Define the failure case.** What happens if they miss? At minimum: mana lost, spell fizzles. For Tier 3+: consider [[50_Magic/Glossary/Mana Burn\|Mana Burn]] consequences or environmental backlash.
6. **Reward creativity, punish vagueness.** A player who describes *exactly* how their mana canals interact with the environment gets the benefit of the doubt. A player who says "I cast a thing" does not.

> [!TIP] The Improv Spell Rule
> If a player wants to attempt a magical effect they don't have as a learned Power, the GM can allow a "raw shaping" attempt at **+2 difficulty** and **double mana cost**, provided the caster has **at least 1 dot** in the relevant [[50_Magic/Glossary/Shaping\|Shaping]] Skill. A mage cannot brute-force an effect from a school they have never studied. This represents the mage improvising an effect without a proper spell matrix. This should be rare and dramatic.

---

## 9. Quick Reference: Spell Template

Copy this template when creating a new spell file:

```yaml
---
tags: [spell, SCHOOL]
type: spell
tier: X
magic_school: SCHOOL
specialization: None
cost: X
description: "Brief one-line summary."
---
### SPELL NAME
*[[Soul Link|School]] (Tier X)*
**Mana Cost:** X

Flavour description (2-4 sentences).

**System:** Roll [Attribute] + [School] vs difficulty X.
On success: [effect]. Overcharge: [scaling/options].
On failure: mana is lost; [additional consequences if any].
```
