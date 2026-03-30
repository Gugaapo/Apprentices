---
{"dg-publish":true,"permalink":"/10-system/06-magic-system/","tags":["rules","magic","mechanics","guide","system"],"dgShowBacklinks":true,"dgShowInlineTitle":true,"dgShowFileTree":true,"dgEnableSearch":true,"dgShowToc":true,"dgShowTags":true,"noteIcon":""}
---


> **Purpose:** Magic is the physical act of shaping geometric structures in your soul and forcing raw atmospheric mana through them. This act is called **[[10_System/Glossary/Shaping\|Shaping]]**. This document teaches how to calculate, build, and resolve spells in combat, utilizing strict procedural steps.

---

## 1. Core Loop & Resolution

To avoid confusion, every spell operates on two entirely separate mechanical axes: the **Target Number** (Skill, representing the shape) and the **Mana Cost** (Fuel).

### The Casting Roll
When you attempt to cast a spell, you roll:
**`2d6 + Willpower + [School Proficiency]`**

### Difficulty (Target Number)
The GM sets the Target Number (TN) based on environmental friction and internal canal stress.
*   **Base (TN 6):** Standard, unbroken concentration in calm environments.
*   **Combat Friction (TN 8–10):** Casting under direct fire, sprinting, or under severe emotional stress.
*   **Absurd Complexity (TN 12–15+):** Attempting magic far beyond human capability.

**Resolution:**
*   **Success:** You meet or exceed the Target Number. The magic takes hold. Every point you score *above* the TN becomes **Overcharge**.
*   **Failure:** The magic fizzles or you suffer direct psychic backlash. *You still pay the Mana Cost for the failed attempt.*

---

## 2. The Language of Magic (The Lexicon)

Students do not abstractly "learn a firebolt spell." By purchasing Dots in a Core School, they unlock fluency in that School's vocabulary, enabling them to construct mathematical **Formulas**. Formulas are the blueprints written in your Grimoire; a **Spell** is the physical manifestation of those formulas in reality.

Every formula is built with **Glyphs**:
1. **Exactly ONE Verb (Function):** The core School pushing the magic (e.g., `Schf` / Create).
2. **Exactly ONE Noun (Object/Characteristic):** The physical medium being manipulated (e.g., `Feur` / Fire).
3. **Optional Modifiers:** Extra tags shaping trajectory or limits (e.g., `Kupp` / Dome).

| Core School | Primary Verb (Function) | Core Noun (Object/Characteristic) |
| :--- | :--- | :--- |
| **[[10_System/Schools/Projection/Projection\|Projection]]** | `Schf` (Create/Invoke) | `Feur` (Fire), `Bliz` (Lightning), `Lict` (Light), `Kraf` (Kinetic) |
| **[[10_System/Schools/Alteration/Alteration\|Alteration]]** | `Andr` (Restructure/Alter) | `Dich` (Density), `Form` (Shape), `Temp` (Temperature), `Schw` (Gravity) |
| **[[10_System/Schools/Dimensionalism/Dimensionalism\|Dimensionalism]]** | `Bewg` (Displace), `Tohr` (Gateway) | `Raum` (Space), `Fern` (Distance) |
| **[[10_System/Schools/Divination/Divination\|Divination]]** | `Sehn` (Perceive) | `Aura` (Magic Aura), `Zeit` (Time/Past) |
| **[[10_System/Schools/Illusionism/Illusionism\|Illusionism]]** | `Var` (Deceive/Phantom) | `Bild` (Visual), `Klan` (Auditory), `Geis` (Mind) |
| **[[10_System/Schools/Animation/Animation\|Animation]]** | `Lebe` (Animate) | `Ding` (Object), `Baut` (Construct) |
| **[[10_System/Schools/Abjuration/Abjuration\|Abjuration]]** | `Scht` (Defend), `Nill` (Counter) | Modifiers: `Kupp` (Dome), `Wand` (Wall), `Wart` (Delayed Trigger) |
| **[[10_System/Schools/Soul Magic/Soul Magic\|Soul Magic]]** | `Reis` (Violate) | `Seel` (Soul), `Saug` (Drain), `Flei` (Flesh) |

---

## 3. Casting Procedure

Every spell creation follows strict steps: **Declare Intent, Build the Formula, Choose Format, and Roll.**

### Step 1: Declare Intent & Check Mana Cost
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
> **IF** you append Modifiers exceeding your `Calculation - 1` limit:
> - **THEN** your spell suffers a **+1 TN Penalty** AND you instantly suffer **1 Physical Wound** from neural strain, regardless of success.

### Step 3: Choose Format (Structured vs Unstructured)
**Structured Magic (Prepared Formulas)**
If you cast a pre-written Formula explicitly saved in your Grimoire, it rolls against standard Difficulty and costs the exact Mana Cost calculated in Step 1.
*   **Spell Mastery:** Spending Study Points on a specific Formula hardwires it. Its **Mana Cost** permanently lowers by 1 step. 

**Unstructured Magic (On-The-Fly)**
Inventing magic and mentally assembling fluid glyphs mid-battle without written anchors tears your channels.
**IF** you cast Unstructured magic:
- **THEN** it drains **Mana Cost + 1** from your Capacity.
- **THEN** it imposes a **+2 Target Number** penalty.

### Step 4: Roll and Resolve
Roll your dice. Compare against the TN. Apply modifiers and Overcharge out of the remaining points.

**Overcharge Spending:**
*   **Scale Damage:** +1 Overcharge = +1 Base Wounds.
*   **Trigger Status Effects:** Explicitly trigger the inherent, lingering Status Effect tied to your Noun Glyph.
*   **Finesse Duplication:** **IF** you substitute [[10_System/Attributes/Magical/Finesse\|Finesse]] instead of Willpower for the casting roll, **AND** you score 2+ Overcharge, **THEN** you may spend 2 Overcharge to seamlessly duplicate the identical spell onto a secondary target.

---

## 4. Advanced Magical Friction

### Mana Capacity & Mana Burn
There is no abstract "mana bar." You have a **Mana Capacity**, which is your absolute safe limit for channeling mana before your flesh tears. 
**`Mana Capacity = 4 + [[10_System/Glossary/Core Resonance\|Core Resonance]]`** *([[Core Resonance]] = Highest of Calculation, Finesse, or Willpower)*.

Every spell deducts its **Mana Cost** from your capacity. Any sustained spell or active ward permanently reduces your maximum Mana Capacity by its Mana Cost for as long as it exists (The RAM Rule).

> **Mana Burn (Exhaustion Cascade)**
> Pushing mana beyond your flesh's capacity causes organic tearing. 
> **IF** your Spent Mana > Mana Capacity:
> - **THEN IF (+1 to 5 over):** Take 1 Physical Wound immediately upon casting. (*Fatigued*)
> - **THEN IF (+6 to 8 over):** Your spell automatically fails on any roll ≤ TN, AND take 1 Wound. (*Exhausted*)
> - **THEN IF (+9+ over):** You fall unconscious or die from massive organ failure. (*Depleted*)



### Evasion ([[10_System/Glossary/Physical Defense\|Physical Defense]])
Targets are not passive meat sacks. Instead of rolling to dodge every attack, physical evasion is abstracted into a passive derived stat: **[[10_System/Glossary/Physical Defense\|Physical Defense]]** (`6 + Mobility + Highest of Awareness or Dexterity`).
*   **Complete Defense:** Attacker's Casting Roll (or Combat Roll) is less than or equal to your [[10_System/Glossary/Physical Defense\|Physical Defense]] -> 0 damage (miss/dodged).
*   **Hit:** Attacker's Roll exceeds your [[10_System/Glossary/Physical Defense\|Physical Defense]] -> Full damage.
*(Note: A defender may still use a Mastered spell like `Scht Wand` as an instant Reaction to block an incoming attack).*

### The Law of Soul Cohesion
Living beings unconditionally project raw spiritual interference to protect internal tissue.
**IF** you attempt direct internal biological disruption against a hostile Soul Cohesion boundary:
- **THEN** the Mana Cost violently launches to **Miracle (7 Mana)**.

### The Principle of Supremacy
Magic is specialized geometry. You cannot use a cheap blunt tool for a premium job (e.g., using physical force to mimic local teleportation).
**IF** you mimic another School's pure effect through inefficient physics:
- **THEN** the spell suffers an automatic **+1 Mana Cost** penalty.

---

## APPENDIX: Quick Casting Card

### 1. BUILD THE FORMULA
Syntax: `[VERB] + [NOUN] + [MODIFIERS (Max = Calculation-1)]`
*Example: Lebe (Animate) + Waff (Weapon) + Gehh (Walk)*

### 2. FIND MANA COST
- **0 Mana:** Harmless utility / Touch / Seconds
- **1 Mana:** 1 Wound / 5m Range / 1 Target
- **2 Mana:** 2 Wounds / 20m Range / Close-quarters Area
- **4 Mana:** 3 Wounds / 50m Range / Room-clearing
- **7 Mana:** Lethal / 100m+ / City block

### 3. APPLY FORMAT PENALTIES
- **Structured Formula (From Grimoire)?** Cost is Normal. TN is Normal.
- **Unstructured (On-the-fly)?** Cost is +1 Mana. TN is +2.

### 4. ROLL THE DICE
Roll: `2d6 + Willpower + School Proficiency`
- **Base TN:** 6
- **Combat TN:** 8-10

### 5. CONSEQUENCES
- **Overcharge:** Points above TN = +1 Wound per point OR +Status Effect.
- **Mana Burn:** Exceeding your Mana Capacity = Immediate Physical Wounds.
