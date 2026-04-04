---
{"dg-publish":true,"permalink":"/10-system/05-magic-system/","tags":["rules","magic","mechanics","guide","system"],"dgShowBacklinks":true,"dgShowInlineTitle":true,"dgShowFileTree":true,"dgEnableSearch":true,"dgShowToc":true,"dgShowTags":true,"noteIcon":""}
---


> **Purpose:** Magic is the physical act of shaping geometric structures in your soul and forcing raw atmospheric mana through them. This act is called **[[10_System/Glossary/Shaping\|Shaping]]**. This document teaches how to calculate, build, and resolve spells in combat, utilizing strict procedural steps.

---

## 1. Core Loop & Resolution

Magic operates natively via the **Magic Moves** (see [[10_System/01 Core Mechanics\|01 Core Mechanics]]). The Core engine utilizes the standard PbtA 2d6 engine (6-: Miss, 7-9: Mixed Success, 10+: Strong Hit).

There are two primary axes of magic:
- **The Form (Fictional Positioning):** Does your character know the requisite Glyphs, and can their brain physically calculate the structure?
- **The Fuel (Mana):** Every spell drains Mana based on its scale and complexity.

### The Move
If you have the appropriate glyphs and the capacity to cast, you trigger the **Cast a Spell Formula** Move.
*   **Precision/Defensive:** Roll `2d6 + Finesse`
*   **Destructive/Raw Force:** Roll `2d6 + Willpower`

*Note: You do not use Target Numbers (TNs). A 10+ is an objective success. A 7-9 means you succeed but suffer complications, such as friction or exposing yourself to danger.*

---

## 2. The Language of Magic (The Lexicon)

Students do not abstractly "learn a firebolt spell." By studying, they unlock fluencies that enable them to construct mathematical **Formulas**. Formulas are the blueprints written in your Grimoire; a **Spell** is the physical manifestation of those formulas in reality.

Every formula is built with **Glyphs**:
1. **Exactly ONE Verb (Function):** The core School pushing the magic (e.g., `Schf` / Create).
2. **Exactly ONE Noun (Object/Characteristic):** The physical medium being manipulated (e.g., `Feur` / Fire).
3. **Optional Modifiers:** Extra tags shaping trajectory or limits (e.g., `Kupp` / Dome).

### The Tri-Tier Progression System
Glyphs are fundamentally categorized into three tiers of learning:

1. **The Core Lexicon (The Alphabet)**
   - **How to acquire:** Purchasing 1 Dot in a **Core School** (e.g., Projection, Alteration) automatically grants the mage complete fluency in that school's standard `Verbs` and base `Nouns`. No individual glyph tracking is required.

2. **The Advanced Lexicon (The Dialects)**
   - **How to acquire:** **Specializations** (e.g., Combat Magic) are advanced dialects that must be unlocked with IP and then leveled with SP. Each Dot gained in a Specialization grants the player exactly **3 Advanced Modifiers** from that Specialization's syllabus.

3. **The Wild Lexicon (The Loot)**
   - **How to acquire:** Extreme scale modifiers (like `Gros` / Greater) or terrifying nouns (like `Plaz` / Plasma) are not taught at the Academy. They are exclusively considered **Wild Glyphs** and can only be discovered physically in the world through adventuring (forbidden tomes, boss loot) and unlocked with IP.

| Core School | Primary Verb (Function) | Core Example Nouns (Fluency) |
| :--- | :--- | :--- |
| **[[10_System/Schools/Projection/Projection\|Projection]]** | `Schf` (Create/Invoke) | `Feur` (Fire), `Lict` (Light), `Erde` (Rock), `Kraf` (Force) |
| **[[10_System/Schools/Alteration/Alteration\|Alteration]]** | `Andr` (Restructure/Alter) | `Dich` (Density), `Form` (Shape), `Temp` (Temperature) |
| **[[10_System/Schools/Dimensionalism/Dimensionalism\|Dimensionalism]]** | `Bewg` (Displace), `Tohr` (Gateway) | `Raum` (Space), `Dist` (Distance) |
| **[[10_System/Schools/Divination/Divination\|Divination]]** | `Sehn` (Perceive) | `Aura` (Magic Aura), `Raum` (Surroundings), `Spur` (Track) |
| **[[10_System/Schools/Illusionism/Illusionism\|Illusionism]]** | `Tusc` (Deceive/Phantom) | `Bild` (Visual), `Klan` (Auditory), `Ruch` (Smell), `Tast` (Touch) |
| **[[10_System/Schools/Animation/Animation\|Animation]]** | `Lebe` (Animate) | `Ding` (Object), `Gehh` (Walk/Move) |
| **[[10_System/Schools/Abjuration/Abjuration\|Abjuration]]** | `Scht` (Defend), `Nill` (Counter) | `Kupp` (Dome), `Wand` (Wall) |
| **[[10_System/Schools/Soul Magic/Soul Magic\|Soul Magic]]** | `Reis` (Violate) | `Seel` (Soul), `Rinn` (Leak), `Mutr` (Flesh) |

---

## 3. Casting Procedure

Every spell creation follows strict steps: **Declare Intent, Build the Formula, Calculate Mana, and Roll.**

### Step 1: Declare Intent & Check Base Cost
The player states their ultimate intent. The GM evaluates it against the **Complexity Budget Table**. If an Intent exceeds the ceiling in even ONE column, it pushes to the next level of Cost. 

| Complexity Level | **Mana Cost** | Damage Threshold | Range | Duration | Area / Scale |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Trivial** | 0 (1 in combat) | 0 (Harmless utility) | Touch / Personal | Fleeting / Seconds | Tiny object |
| **Regular** | 1 | 1 Wound (Pain/scorch) | Close / 5m | Instant / 1 min | 1 Target / 1m |
| **Hard** | 2 | 2 Wounds (Lethal) | Near / 10–20m | Minutes | 1-2 Targets / 3m |
| **Complex** | 4 | 3 Wounds (Shattering) | Far / 50m | Scene (10-30m) | Room / 10m |
| **Miracle** | 7 | 5+ Wounds (Total kill)| Very Far / 100m+| Sustained / Hours| City block |

### Step 2: Build the Formula
Using the Lexicon above, translate your intent into a legal Formula. 

> **The Syntax Limit:**
> A spell matrix can only handle so many structural Modifiers before collapsing.
> **IF** you append Modifiers exceeding your `Calculation` limit:
> - **THEN** your spell suffers a **+1 Mana Cost** Tax AND you instantly suffer **1 Physical Wound** from neural strain, regardless of casting success.

### Step 3: Choose Format (Structured vs Unstructured)
**Structured Magic (Prepared Formulas)**
If you cast a pre-written Formula explicitly saved in your Grimoire, you roll the **Cast a Spell Formula** Move safely.
*   **Spell Mastery (Muscle Memory):** A character can memorize a number of Mastered Spells equal to their **Memory**. When casting a Mastered spell, its **Mana Cost** lowers by 1 step, and it can be cast instantly as a Reaction. You can swap these slots from your Grimoire during downtime.

**Unstructured Magic (On-The-Fly)**
Inventing magic and mentally assembling fluid glyphs mid-battle without written anchors tears your channels.
**IF** you cast Unstructured magic, you roll the **Channel Unstructured Magic** Move.
- **THEN** it unconditionally drains **Mana Cost + 1** from your Capacity, regardless of success.

### Step 4: Roll and Resolve
Roll your Move (`+Finesse` or `+Willpower`). Choose your options on a 10+, or brace for consequence on a 7-9.

---

## 4. Advanced Magical Friction

### Mana Capacity & Mana Burn
There is no abstract "mana bar." You have a **Mana Capacity**, which is your absolute safe limit for channeling mana before your flesh tears. 
**`Mana Capacity = 4 + [[10_System/Glossary/Core Resonance\|Core Resonance]]`** *([[Core Resonance]] = Highest of Calculation, Finesse, or Willpower)*.

Every spell deducts its **Mana Cost** from your capacity. Any sustained spell or active ward dynamically reduces your maximum Mana Capacity by its Mana Cost for as long as it exists (The RAM Rule).

> **Mana Burn (Exhaustion Cascade)**
> Pushing mana beyond your flesh's capacity causes organic tearing. 
> Exceeding Capacity instantly inflicts the "Mana Friction" condition, which leads to taking Wounds and auto-fail conditions on subsequent Magic Moves.

### Evasion & Wards
Targets are not passive meat sacks. Physical evasion is a narrative reality—if an enemy shoots at you, the GM will make a Hard Move on a Miss against you, and you might need to roll **Defend** to avoid it entirely.

You may use a Mastered defensive spell as an instant Reaction using the **Deflect Magic** Move, intercepting attacks to halve or negate damage completely.

### The Law of Soul Cohesion
Living beings unconditionally project raw spiritual interference to protect internal tissue.
**IF** you attempt direct internal biological disruption against a hostile Soul Cohesion boundary:
- **THEN** the Mana Cost violently launches to **Miracle (7 Mana)**.

### The Principle of Supremacy
Magic is specialized geometry. You cannot use a cheap blunt tool for a premium job (e.g., using physical force to mimic local teleportation).
**IF** you mimic another School's pure effect through inefficient physics:
- **THEN** the spell suffers an automatic **+1 Mana Cost** Penalty.

---

## APPENDIX: Quick Casting Card

### 1. BUILD THE FORMULA
Syntax: `[VERB] + [NOUN] + [MODIFIERS (Max = Calculation)]`
*Example: Lebe (Animate) + Waff (Weapon) + Gehh (Walk)*

### 2. FIND MANA COST
- **0 Mana:** Harmless utility / Touch / Seconds
- **1 Mana:** 1 Wound / 5m Range / 1 Target
- **2 Mana:** 2 Wounds / 20m Range / Close-quarters Area
- **4 Mana:** 3 Wounds / 50m Range / Room-clearing
- **7 Mana:** Lethal / 100m+ / City block

### 3. APPLY RULES
- **Exceeded Syntax Limit?** +1 Mana Tax, Take 1 Wound.
- **Unstructured / Intent-only?** Roll Channel Unstructured Magic Move. Automatic +1 Mana Tax.

### 4. ROLL THE DICE
- Roll **Cast a Spell Formula** Move.
- `2d6 + Finesse` or `Willpower`

### 5. RESOLVE
- **10+:** Boom! Choose 2 Overcharge options (Maximize/+Damage, -Mana, Duplicate, Apply Status).
- **7-9:** Success, but GM introduces a complication (-Mana Friction, Collateral, Opening).
- **6-:** It explodes in your face.

[[10_System/04 Progression\|Progression]] ================================================== [[10_System/06 Crafting\|Crafting]]