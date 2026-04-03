---
{"dg-publish":true,"permalink":"/10-system/11-apprentices-srd/","tags":["rules","quick-reference","srd","magic"],"dgShowBacklinks":true,"dgShowInlineTitle":true,"dgShowFileTree":true,"dgEnableSearch":true,"dgShowToc":true,"dgShowTags":true,"noteIcon":""}
---


# Apprentices - System Reference Document (SRD)
*A quick-reference cheat sheet for character creation and live table play.*

---

## 1. Quick Character Creation
1. **Choose 1 Background:** (e.g., [[10_System/Backgrounds/Noble Scion\|Noble Scion]], [[10_System/Backgrounds/Street Rat\|Street Rat]]) which grants a starting bonus and a narrative Connection.
2. **Attributes:** There are 16 attributes in a 4x4 Grid (Max 3 at creation).
   - **Magical (4 Pts):** [[10_System/Attributes/Magical/Memory\|Memory]], [[10_System/Attributes/Magical/Calculation\|Calculation]], [[10_System/Attributes/Magical/Finesse\|Finesse]], [[10_System/Attributes/Magical/Willpower\|Willpower]]. Base **1 dot**.
   - **Mundane:** Mental, Physical, Social. Base **0 dots**. Assign Arrays **[5, 4, 3]** points to these categories.
3. **Magic Schools:** 8 Core Schools start at **0 dots**. 
   - You have **2 Points** to spend (Max 3 dots per school).
   - A dot in a Core School grants fluency in its base Verbs/Nouns. Select exactly **1 Spell Formula** per dot spent.
4. **Merits & Flaws:** Take up to 4 Points of Flaws to buy Merits.
5. **Academy Logistics:** Pick 1 Mentor Professor and 2 Majors.
6. **Derived Stats:**
   - **Mana Capacity:** `4 + [[Core Resonance]]` (Highest of Calculation, Finesse, or Willpower)
   - **Max Modifiers:** `Calculation - 1`
   - **Mind Defense (Passive TN):** `6 + Willpower + Highest of (Divination or Abjuration)`
   - **Health Track:** 7 Boxes (Bruised 0 to Incapacitated)
   - **Soul Integrity & Sanity:** 10 Boxes each
   - **Mastered Spells:** `Memory` rating (Cost 0 SP, auto-success/free modifiers, lower complexity step by 1).

---

## 2. Core Resolution Engine
* **The Roll:** `2d6 + Attribute + Skill Proficiency` 
* **The Casting Roll:** `2d6 + Willpower + School Proficiency`
* **Target Numbers (TN):** 
  * 6 (Base / Calm)
  * 8–10 (Combat Friction / Stress)
  * 12–15+ (Absurdly complex physics)
* **Overcharge:** Every point *above* the TN is 1 Overcharge. Spend to add **+1 Damage**, trigger a **Status Effect** (e.g., *Lingering Harm* for Fire), or if substituting [[10_System/Attributes/Magical/Finesse\|Finesse]] for Willpower, spend 2 Overcharge to seamlessly duplicate the identical spell onto a secondary target.
* **[[10_System/Glossary/Physical Defense\|Physical Defense]] (Evasion):** `6 + Mobility + Highest of (Awareness or Dexterity)`.
  * Attackers must roll *higher* than this passive TN to hit you with physical attacks or targeted spells.
  * You may also use an instant Reaction (like a Mastered `Scht` spell) to generate a magical shield threshold instead.

---

## 3. The Rules of Magic & Mana Capacity
**Mana Capacity & Burn:**
Casting drains your body's Mana Capacity. Every spell costs its Mana Cost. Exceeding your safe Capacity (`4 + [[Core Resonance]]`) causes the Exhaustion Cascade:
* *Fatigued (1-5 over):* Take 1 Physical Wound per cast.
* *Exhausted (6-8 over):* Automatic spell failure on bad 2d6 rolls + Wounds.
* *Depleted (9+ over):* Organ failure / Death.

**Unstructured vs. Structured Magic:**
* **Structured (Formulas):** Prepared, mastered geometric math. Normal Mana Cost, rolls against Normal TN.
* **Unstructured (On-the-Fly):** Dangerous and volatile Intent casting. 
  * *Intent-First Scaling:* In combat, you naturally declare your Intent, the GM assigns the required Complexity (Mana Cost), and you justify it by speaking exactly 1 Function and 1 Object.
  * *The Penalty:* Unstructured casting naturally tears your canals, always draining **Mana Cost + 1** from your Capacity (e.g., A 2-Mana Hard intent will cost 3 Mana). It also forces a **+2 Difficulty (Target Number)** on the 2d6 roll.

**Reserved Capacity (The RAM Rule):** 
Any sustained spell, triggered ward (`Ceka`), or un-discharged magic permanently reduces your maximum Mana Capacity by its cost until it is discharged or dismissed. You cannot rest this capacity back.

---

## 4. The Laws of Magic
1. **Frail Scaffolding (Calculation Limit):** You may attach unlimited Modifiers to a spell. However, for every Modifier *exceeding* your safe limit (`Calculation - 1`), you suffer **+1 TN to the roll** and take **1 Physical Wound** upon casting—regardless of success.
2. **Soul Cohesion:** You cannot directly target the internal biology, space, or chemistry of an unwilling living being. Breaking Soul Cohesion forces the spell's Complexity to **Miracle (7 Mana)**.
4. **Principle of Supremacy:** Attempting to mimic raw energy (`Tvor`) using physical matter manipulation (`Prom`) causes inefficiency, adding a **+1 Complexity Tax** to the spell.

---

## 5. Complexity Power Scale Budget

| Level | Mana Cost | Base Damage | Range | Duration | Area of Effect |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Trivial** | 0 (1 in combat) | 0 Wounds | Touch | Seconds | Tiny object |
| **Regular** | 1 | 1 Wound | 5m | 1 minute | 1 Target |
| **Hard** | 2 | 2 Wounds | 10-20m| Minutes (= Finesse) | Close-quarters |
| **Complex** | 4 | 3 Wounds | 50m | 1 Scene | Room-clearing |
| **Miracle** | 7 | 5+ Wounds | 100m+ | Sustained / Hours | City block |

*(Note: If a spell exceeds its boundary in 2 or more columns, its Complexity is automatically bumped up a tier).*

---

## 6. The Tri-Tier Glyph Lexicon
*Spells are constructed by combining exactly ONE **Function** + **Object/Characteristic**, plus Optional **Modifiers**.*

**The Tri-Tier System:**
1. **Core (Alphabet):** Fluency granted automatically by points in Core Schools (Base Verbs and Nouns).
2. **Advanced (Dialects):** 3 Modifiers learned per dot gained in a Specialization.
3. **Wild (Loot):** Extreme modifiers discovered physically in the world.

**Primary Functions (The Schools):**
* `Schf` (Create/Invoke) - Projection
* `Andr` (Restructure/Alter) - Alteration
* `Bewg` (Displace), `Tohr` (Gateway) - Dimensionalism
* `Sehn` (Perceive) - Divination
* `Tusc` (Deceive/Phantom) - Illusionism
* `Lebe` (Animate) - Animation
* `Scht` (Defend), `Nill` (Counter) - Abjuration
* `Reis` (Violate) - Soul Magic

**Common Base Nouns (Fluency):**
* `Feur` (Fire) | `Lict` (Light) | `Erde` (Rock) | `Kraf` (Force)
* `Dich` (Density) | `Form` (Shape) | `Temp` (Temperature)
* `Raum` (Space/Surroundings) | `Dist` (Distance) | `Aura` (Magic Energy)
* `Bild` (Visual) | `Klan` (Auditory) | `Spur` (Track)
* `Ding` (Object) | `Wand` (Wall) | `Kupp` (Dome)

**Example Advanced / Wild Modifiers:**
* `Klen` (Lesser / Minor)
* `Gros` (Greater / Major)
* `Wart` (Delayed Trigger / Ward) 
* `Schn` (Fast / Projectile)


[[10_System/10 Items and Equipment\|Items and Equipment]] =================================================