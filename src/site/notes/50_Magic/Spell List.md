---
{"dg-publish":true,"permalink":"/50-magic/spell-list/","dgShowBacklinks":true,"dgShowLocalGraph":true,"dgShowInlineTitle":true,"dgShowFileTree":true,"dgEnableSearch":true,"dgShowToc":true,"dgShowTags":true,"noteIcon":""}
---


# 📖 Spell List

<div id="spell-browser">

<style>
#spell-browser {
  font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
  max-width: 100%;
  margin: 0 auto;
}

.school-tabs {
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
  margin-bottom: 20px;
  padding: 4px;
}

.school-tab {
  padding: 8px 16px;
  border: 1px solid #555;
  border-radius: 8px;
  background: #2a2a3a;
  color: #ccc;
  cursor: pointer;
  font-size: 14px;
  font-weight: 500;
  transition: all 0.2s ease;
  user-select: none;
}

.school-tab:hover {
  background: #3a3a5a;
  color: #fff;
  border-color: #888;
}

.school-tab.active {
  background: #5865F2;
  color: #fff;
  border-color: #5865F2;
  box-shadow: 0 2px 8px rgba(88, 101, 242, 0.3);
}

.search-bar {
  width: 100%;
  padding: 10px 14px;
  margin-bottom: 16px;
  border: 1px solid #555;
  border-radius: 8px;
  background: #1e1e2e;
  color: #ddd;
  font-size: 14px;
  box-sizing: border-box;
}

.search-bar::placeholder {
  color: #777;
}

.search-bar:focus {
  outline: none;
  border-color: #5865F2;
  box-shadow: 0 0 0 2px rgba(88, 101, 242, 0.2);
}

.spell-table {
  width: 100%;
  border-collapse: collapse;
  border-radius: 8px;
  overflow: hidden;
}

.spell-table thead th {
  background: #2a2a3a;
  color: #aaa;
  font-weight: 600;
  text-transform: uppercase;
  font-size: 11px;
  letter-spacing: 0.5px;
  padding: 12px 14px;
  text-align: left;
  border-bottom: 2px solid #444;
  cursor: pointer;
  user-select: none;
  transition: color 0.2s;
}

.spell-table thead th:hover {
  color: #5865F2;
}

.spell-table thead th.sorted-asc::after {
  content: ' ▲';
  font-size: 10px;
}

.spell-table thead th.sorted-desc::after {
  content: ' ▼';
  font-size: 10px;
}

.spell-table tbody tr {
  transition: background 0.15s;
  border-bottom: 1px solid #333;
}

.spell-table tbody tr:hover {
  background: #2a2a3a;
}

.spell-table td {
  padding: 10px 14px;
  font-size: 13px;
  color: #ddd;
  vertical-align: top;
}

.spell-table td:first-child {
  font-weight: 600;
  text-align: center;
  width: 50px;
}

.spell-table td:nth-child(2) {
  font-weight: 500;
  color: #7aa2f7;
}

.tier-badge {
  display: inline-block;
  width: 26px;
  height: 26px;
  line-height: 26px;
  text-align: center;
  border-radius: 6px;
  font-size: 12px;
  font-weight: 700;
}

.tier-1 { background: #1a3a1a; color: #4ade80; }
.tier-2 { background: #1a2a3a; color: #60a5fa; }
.tier-3 { background: #3a2a1a; color: #fb923c; }
.tier-4 { background: #3a1a1a; color: #f87171; }
.tier-5 { background: #2a1a3a; color: #c084fc; }

.spec-tag {
  display: inline-block;
  padding: 2px 8px;
  border-radius: 4px;
  font-size: 11px;
  font-weight: 500;
  background: #333;
  color: #aaa;
}

.spec-tag.core {
  background: #1a2a1a;
  color: #4ade80;
}

.spell-count {
  color: #777;
  font-size: 13px;
  margin-bottom: 12px;
}

.no-results {
  text-align: center;
  padding: 30px;
  color: #666;
  font-style: italic;
}
</style>

<div class="school-tabs" id="schoolTabs"></div>
<input type="text" class="search-bar" id="searchBar" placeholder="Search spells by name, specialization, or description..." />
<div class="spell-count" id="spellCount"></div>
<table class="spell-table">
  <thead>
    <tr>
      <th data-col="tier">Tier</th>
      <th data-col="name">Spell Name</th>
      <th data-col="specialization">Specialization</th>
      <th data-col="description">Description</th>
    </tr>
  </thead>
  <tbody id="spellBody"></tbody>
</table>

<script>
const SPELLS = {
  "Abjuration": [
    {
      "name": "Cleanse Minor Curse",
      "tier": "1",
      "specialization": "Core",
      "description": "Removes a minor magical affliction \u2014 a petty curse, a jinx, or a low-tier enchantment."
    },
    {
      "name": "Minor Deflection",
      "tier": "1",
      "specialization": "Core",
      "description": "A tiny, passive ward that slightly redirects weak kinetic impacts."
    },
    {
      "name": "Spell Deflection",
      "tier": "1",
      "specialization": "Core",
      "description": "Creates a momentary shield that nudges an incoming spell slightly off course."
    },
    {
      "name": "Ward Identification",
      "tier": "1",
      "specialization": "Core",
      "description": "Examines an active ward and determines its type, trigger condition, and approximate tier."
    },
    {
      "name": "Arcane Lock",
      "tier": "1",
      "specialization": "Sealing",
      "description": "Touches a door, chest, or container, fusing its locking mechanisms together with a simple magical cipher. The lock gl..."
    },
    {
      "name": "Binding Ribbon",
      "tier": "1",
      "specialization": "Sealing",
      "description": "Creates a thin band of sealing energy that ties shut a container, book, or mouth."
    },
    {
      "name": "Leak Seal",
      "tier": "1",
      "specialization": "Sealing",
      "description": "Seals cracks, leaks, and small openings in a surface."
    },
    {
      "name": "Minor Seal",
      "tier": "1",
      "specialization": "Sealing",
      "description": "Places a simple seal on a container, indicating if it has been opened."
    },
    {
      "name": "Banish Magic",
      "tier": "1",
      "specialization": "Ward",
      "description": "Touches an object or person suffering from a minor magical condition (like a jinx, a low-tier charm, or a magical sta..."
    },
    {
      "name": "Door Lock",
      "tier": "1",
      "specialization": "Ward",
      "description": "Places a minor ward on a door or window that makes it resistant to being opened."
    },
    {
      "name": "Mana Resistance",
      "tier": "1",
      "specialization": "Ward",
      "description": "Hardens their personal mana field against external magical influence."
    },
    {
      "name": "Personal Shield",
      "tier": "1",
      "specialization": "Ward",
      "description": "Creates a brief personal barrier that absorbs one hit."
    },
    {
      "name": "Counter Ward",
      "tier": "2",
      "specialization": "Core",
      "description": "Creates a ward that automatically counters one incoming spell."
    },
    {
      "name": "Curse Resistance",
      "tier": "2",
      "specialization": "Core",
      "description": "Strengthens their resistance to curses and ongoing magical afflictions."
    },
    {
      "name": "Bind Magic Item",
      "tier": "2",
      "specialization": "Sealing",
      "description": "Alters the spiritual attunement of a dedicated magical artifact (like a wand, a ring, or enchanted armor). They seal ..."
    },
    {
      "name": "Memory Seal",
      "tier": "2",
      "specialization": "Sealing",
      "description": "Seals a specific memory behind a magical barrier, preventing the target from accessing it."
    },
    {
      "name": "Reflective Shield",
      "tier": "2",
      "specialization": "Ward",
      "description": "Surrounds themselves with a highly polished, invisible magical mirror. When a targeted spell like a Mana Bolt or a Mi..."
    },
    {
      "name": "Scrying Shield Ward",
      "tier": "2",
      "specialization": "Ward",
      "description": "Creates a ward that blocks scrying and remote observation."
    },
    {
      "name": "Area Cleanse",
      "tier": "3",
      "specialization": "Core",
      "description": "Purges all magical effects from a room-sized area."
    },
    {
      "name": "Banishment",
      "tier": "3",
      "specialization": "Core",
      "description": "Forcibly sends a summoned or extraplanar creature back to its point of origin."
    },
    {
      "name": "Ability Suppression",
      "tier": "3",
      "specialization": "Sealing",
      "description": "Seals a targets access to an entire school of magic."
    },
    {
      "name": "Blood Seal",
      "tier": "3",
      "specialization": "Sealing",
      "description": "Creates a seal that can only be opened with a specific persons blood."
    },
    {
      "name": "Greater Shield",
      "tier": "3",
      "specialization": "Ward",
      "description": "Creates a powerful personal barrier that absorbs significant damage."
    },
    {
      "name": "Shared Shield",
      "tier": "3",
      "specialization": "Ward",
      "description": "Extends their protective aura to cover nearby allies."
    },
    {
      "name": "Curse Breaker",
      "tier": "4",
      "specialization": "Core",
      "description": "Shatters a powerful curse, breaking its hold on a victim."
    },
    {
      "name": "Containment Seal",
      "tier": "4",
      "specialization": "Sealing",
      "description": "Creates a seal specifically designed to contain a dangerous magical effect or cursed item."
    },
    {
      "name": "Mass Shield",
      "tier": "4",
      "specialization": "Ward",
      "description": "Creates a large protective dome that shields all allies inside."
    },
    {
      "name": "Absolute Purification",
      "tier": "5",
      "specialization": "Core",
      "description": "Removes every magical effect from a target or area, regardless of tier."
    },
    {
      "name": "Absolute Seal",
      "tier": "5",
      "specialization": "Sealing",
      "description": "Creates a seal of such power that it cannot be broken by any means short of divine intervention."
    },
    {
      "name": "Divine Shield",
      "tier": "5",
      "specialization": "Ward",
      "description": "Creates the ultimate defensive barrier \u2014 nearly impervious to all forms of attack."
    }
  ],
  "Alteration": [
    {
      "name": "Blood Clot Minor",
      "tier": "1",
      "specialization": "Blood Magic",
      "description": "Forces a small wound to instantly seal using mana."
    },
    {
      "name": "Iron in the Blood",
      "tier": "1",
      "specialization": "Blood Magic",
      "description": "Concentrates the iron naturally present in their blood, hardening their fists and forearms."
    },
    {
      "name": "Pain Spike",
      "tier": "1",
      "specialization": "Blood Magic",
      "description": "Causes a sharp spike of pain in a target by agitating the blood in one of their extremities."
    },
    {
      "name": "Taste of Vitae",
      "tier": "1",
      "specialization": "Blood Magic",
      "description": "A deeply forbidden tracking method. By tasting a single drop of fresh blood, the mage can perfectly map the targets g..."
    },
    {
      "name": "Blood Sense",
      "tier": "1",
      "specialization": "Core",
      "description": "Attunes their senses to blood, detecting the presence of bleeding creatures nearby."
    },
    {
      "name": "Blood Trail",
      "tier": "1",
      "specialization": "Core",
      "description": "Can track a creature by following the mana signature left in its spilled blood."
    },
    {
      "name": "Clot Command",
      "tier": "1",
      "specialization": "Core",
      "description": "Touches a bleeding wound and forces the blood to clot immediately, sealing the wound from the inside."
    },
    {
      "name": "Elongated Reach",
      "tier": "1",
      "specialization": "Core",
      "description": "Temporarily extends the length of their arms by a few centimetres, increasing their reach."
    },
    {
      "name": "Diagnose Condition",
      "tier": "1",
      "specialization": "Medical Magic",
      "description": "Places their hand on a patient and senses the current state of their body \u2014 identifying injuries, infections, a..."
    },
    {
      "name": "Mage Sight (Medical)",
      "tier": "1",
      "specialization": "Medical Magic",
      "description": "Tunes their magical perception specifically to biological life. They can see the rhythmic pulses of a heartbeat, the ..."
    },
    {
      "name": "Numb Pain",
      "tier": "1",
      "specialization": "Medical Magic",
      "description": "Dulls the nerve endings in a specific area, temporarily eliminating pain without healing the underlying injury."
    },
    {
      "name": "Purify Water",
      "tier": "1",
      "specialization": "Medical Magic",
      "description": "Restructures contaminated water at the molecular level, separating toxins and pathogens from clean water."
    },
    {
      "name": "Chameleon Skin",
      "tier": "1",
      "specialization": "Transformation",
      "description": "Superficially alters the pigmentation of their skin, hair, and clothing to perfectly match the colors and textures of..."
    },
    {
      "name": "Minor Cosmetic Shift",
      "tier": "1",
      "specialization": "Transformation",
      "description": "Subtly alters their own facial features \u2014 changing eye colour, adjusting bone structure, or modifying hair text..."
    },
    {
      "name": "Toughened Hide",
      "tier": "1",
      "specialization": "Transformation",
      "description": "Thickens and toughens their outermost layer of skin, providing marginal protection against cuts and scrapes."
    },
    {
      "name": "Webbed Digits",
      "tier": "1",
      "specialization": "Transformation",
      "description": "Grows thin membranes between their fingers and toes, improving their ability to swim."
    },
    {
      "name": "Adrenal Surge",
      "tier": "2",
      "specialization": "Blood Magic",
      "description": "Forces a targets adrenal glands to dump their entire reserve, granting a burst of superhuman energy followed b..."
    },
    {
      "name": "Blood Armour",
      "tier": "2",
      "specialization": "Blood Magic",
      "description": "Draws blood from their own body and shapes it into a hardened crystalline shell around their skin."
    },
    {
      "name": "Blood Siphon",
      "tier": "2",
      "specialization": "Core",
      "description": "Draws a physical stream of blood from an open wound on an enemy. Instead of simply injuring the target, the mage abso..."
    },
    {
      "name": "Coagulation Weapon",
      "tier": "2",
      "specialization": "Core",
      "description": "Draws their own blood and shapes it into a hardened blade or spike that can be wielded as a weapon."
    },
    {
      "name": "Bone Set",
      "tier": "2",
      "specialization": "Medical Magic",
      "description": "Realigns broken bones and accelerates the fusing process. A fracture that would take weeks to heal is mended in..."
    },
    {
      "name": "Fever Break",
      "tier": "2",
      "specialization": "Medical Magic",
      "description": "Regulates the targets body temperature, breaking a dangerous fever and reducing inflammation throughout the bo..."
    },
    {
      "name": "Beast Aspect",
      "tier": "2",
      "specialization": "Transformation",
      "description": "Forces their body to adopt specific, highly localized animalistic traits. They might grow retractable feline claws fr..."
    },
    {
      "name": "Bone Density Increase",
      "tier": "2",
      "specialization": "Transformation",
      "description": "Increases the density of their skeletal structure, making their bones nearly unbreakable."
    },
    {
      "name": "Blood Boil",
      "tier": "3",
      "specialization": "Blood Magic",
      "description": "Focuses on the circulatory system of a visible target, violently vibrating the mana within their victims blood. The t..."
    },
    {
      "name": "Blood Puppet",
      "tier": "3",
      "specialization": "Blood Magic",
      "description": "Seizes control of a targets circulatory system, forcing their body to move against their will."
    },
    {
      "name": "Acid Touch",
      "tier": "3",
      "specialization": "Core",
      "description": "Restructures their skin to secrete a powerful corrosive compound. Contact dissolves organic and inorganic mater..."
    },
    {
      "name": "Scarlet Shield",
      "tier": "3",
      "specialization": "Core",
      "description": "Creates a floating barrier of crystallized blood that absorbs incoming attacks and regenerates from the caster..."
    },
    {
      "name": "Blood Reconstruction",
      "tier": "3",
      "specialization": "Medical Magic",
      "description": "Rapidly generates replacement blood from the patients own bone marrow, reversing the effects of severe blood l..."
    },
    {
      "name": "Cellular Purge",
      "tier": "3",
      "specialization": "Medical Magic",
      "description": "Identifies and destroys infected or diseased cells throughout the targets body, leaving healthy tissue untouch..."
    },
    {
      "name": "Aquatic Adaptation",
      "tier": "3",
      "specialization": "Transformation",
      "description": "Comprehensively adapts their body for underwater operation \u2014 gills, pressure resistance, streamlined form, and ..."
    },
    {
      "name": "Armoured Scales",
      "tier": "3",
      "specialization": "Transformation",
      "description": "Grows overlapping scales across their torso and limbs, providing reptilian armour."
    },
    {
      "name": "Blood Bond",
      "tier": "4",
      "specialization": "Blood Magic",
      "description": "Creates a deep sympathetic link between two creatures. Damage dealt to one is shared by the other."
    },
    {
      "name": "Sanguine Golem",
      "tier": "4",
      "specialization": "Core",
      "description": "Shapes a massive quantity of blood into a semi-autonomous construct that fights on their behalf."
    },
    {
      "name": "Full Body Reconstruction",
      "tier": "4",
      "specialization": "Medical Magic",
      "description": "Performs a complete assessment and repair of a patients entire physical structure \u2014 every wound, break, and in..."
    },
    {
      "name": "Gigantism",
      "tier": "4",
      "specialization": "Transformation",
      "description": "Doubles their body size, proportionally increasing strength, reach, and durability."
    },
    {
      "name": "Blood Apotheosis",
      "tier": "5",
      "specialization": "Blood Magic",
      "description": "Transforms their own body into living blood \u2014 a fluid, regenerating, nearly indestructible crimson entity."
    },
    {
      "name": "Atomic Reconfiguration",
      "tier": "5",
      "specialization": "Core",
      "description": "Operates at the atomic level, rearranging protons and electrons to create entirely new elements from existing m..."
    },
    {
      "name": "Biological Perfection",
      "tier": "5",
      "specialization": "Medical Magic",
      "description": "Optimizes a patients entire biology \u2014 clearing every imperfection, enhancing every system, maximizing genetic ..."
    },
    {
      "name": "Adaptive Evolution",
      "tier": "5",
      "specialization": "Transformation",
      "description": "The mages body continuously evolves in response to environmental threats, automatically developing resistances and co..."
    }
  ],
  "Animation": [
    {
      "name": "Bone Rattle",
      "tier": "1",
      "specialization": "Core",
      "description": "Animates a handful of bones to create a rattling distraction or crude alarm system."
    },
    {
      "name": "Corpse Preservation",
      "tier": "1",
      "specialization": "Core",
      "description": "Halts the decay of a corpse, preserving it indefinitely."
    },
    {
      "name": "Mend Construct",
      "tier": "1",
      "specialization": "Core",
      "description": "Funnels specialized repair mana into an animated object or golem. Stripped gears re-align, cracked stone plating fuse..."
    },
    {
      "name": "Repair Golem",
      "tier": "1",
      "specialization": "Core",
      "description": "Animates a damaged golems materials, causing cracks to seal and chips to fill."
    },
    {
      "name": "Clay Figurine",
      "tier": "1",
      "specialization": "Golemancy",
      "description": "Shapes a tiny clay figure and animates it. The figurine can walk, climb, and carry objects up to its own weight..."
    },
    {
      "name": "Gravel Golem",
      "tier": "1",
      "specialization": "Golemancy",
      "description": "Animates loose gravel into a small, fragile construct."
    },
    {
      "name": "Stone Fist",
      "tier": "1",
      "specialization": "Golemancy",
      "description": "Shapes a fist-sized stone golem that punches a target with surprising force."
    },
    {
      "name": "Stone Shell",
      "tier": "1",
      "specialization": "Golemancy",
      "description": "Encases a small object in a stone shell, protecting it from damage."
    },
    {
      "name": "Corpse Puppetry",
      "tier": "1",
      "specialization": "Necromancy",
      "description": "Forces kinetic mana directly into a fresh corpse, bypassing the lack of a soul. The corpse jerks upright, its dead mu..."
    },
    {
      "name": "Death Sense",
      "tier": "1",
      "specialization": "Necromancy",
      "description": "Detects the presence of dead bodies and undead creatures nearby."
    },
    {
      "name": "Ghost Sight",
      "tier": "1",
      "specialization": "Necromancy",
      "description": "Attunes their vision to perceive spiritual residue \u2014 the faint echoes of the recently dead."
    },
    {
      "name": "Speak with Dead",
      "tier": "1",
      "specialization": "Necromancy",
      "description": "Touches a corpse and briefly reactivates its vocal cords, asking it one question."
    },
    {
      "name": "Brick Golem",
      "tier": "2",
      "specialization": "Core",
      "description": "Assembles bricks or stones into a small humanoid construct that can carry loads and perform labour."
    },
    {
      "name": "Clay Shield",
      "tier": "2",
      "specialization": "Core",
      "description": "Shapes hardened clay into a floating defensive barrier."
    },
    {
      "name": "Override Command",
      "tier": "2",
      "specialization": "Golemancy",
      "description": "Hacks into the animating matrix of a hostile construct. They violently rip control away from the original caster, for..."
    },
    {
      "name": "Stone Hound",
      "tier": "2",
      "specialization": "Golemancy",
      "description": "Sculpts a dog-sized golem from stone that tracks and hunts."
    },
    {
      "name": "Animate Skeleton",
      "tier": "2",
      "specialization": "Necromancy",
      "description": "Raises a skeleton from a corpse, creating a simple undead servant."
    },
    {
      "name": "Bone Armour",
      "tier": "2",
      "specialization": "Necromancy",
      "description": "Assembles bones from nearby corpses into a grisly suit of armour."
    },
    {
      "name": "Bone Golem",
      "tier": "3",
      "specialization": "Core",
      "description": "Assembles bones from multiple corpses into a large, powerful skeletal construct."
    },
    {
      "name": "Golem Workshop",
      "tier": "3",
      "specialization": "Core",
      "description": "Creates a set of small, specialized golems that operate a workshop autonomously."
    },
    {
      "name": "Bound Sentinel",
      "tier": "3",
      "specialization": "Golemancy",
      "description": "Instead of a temporary kinetic construct, the mage permanently binds intricate animation matrices into a specially cr..."
    },
    {
      "name": "Scrap Automaton",
      "tier": "3",
      "specialization": "Golemancy",
      "description": "Binds nearby metal scraps into a temporary worker drone."
    },
    {
      "name": "Death Ward",
      "tier": "3",
      "specialization": "Necromancy",
      "description": "Wraps themselves in necromantic energy that retaliates against anything that deals them damage."
    },
    {
      "name": "Life Drain",
      "tier": "3",
      "specialization": "Necromancy",
      "description": "Drains life force from a target, healing themselves in the process."
    },
    {
      "name": "Flesh Golem",
      "tier": "4",
      "specialization": "Core",
      "description": "Assembles a massive construct from multiple corpses, creating a powerful undead abomination."
    },
    {
      "name": "Assimilate Environment",
      "tier": "4",
      "specialization": "Golemancy",
      "description": "Throws an aggressive animation core onto the ground. The core rapidly magnetizes and absorbs the surrounding environm..."
    },
    {
      "name": "Death Cloud",
      "tier": "4",
      "specialization": "Necromancy",
      "description": "Creates a cloud of necromantic miasma that drains life from everything it touches."
    },
    {
      "name": "Golem Swarm",
      "tier": "5",
      "specialization": "Core",
      "description": "Creates dozens of small, coordinated golems that function as a devastating swarm."
    },
    {
      "name": "Awaken Intelligence",
      "tier": "5",
      "specialization": "Golemancy",
      "description": "The pinnacle of golemancy. The mage forces a true, complex consciousness\u2014an artificial soul\u2014into a pristine, high-end..."
    },
    {
      "name": "Army of the Dead",
      "tier": "5",
      "specialization": "Necromancy",
      "description": "Walks onto a battlefield or graveyard and unleashes a shockwave of pure necrotic energy. The ground erupts entirely a..."
    }
  ],
  "Dimensionalism": [
    {
      "name": "Conjure Pebble",
      "tier": "1",
      "specialization": "Conjuration",
      "description": "Pulls a small stone from a nearby location through a micro-portal. Useful as ammunition or a distraction."
    },
    {
      "name": "Conjure Tool",
      "tier": "1",
      "specialization": "Conjuration",
      "description": "Pulls existing particles of matter together, weaving them rapidly into a simple, temporary mundane object. They can c..."
    },
    {
      "name": "Dust Cloud",
      "tier": "1",
      "specialization": "Conjuration",
      "description": "Conjures a cloud of fine dust or sand into a room, obscuring vision."
    },
    {
      "name": "Quick Draw",
      "tier": "1",
      "specialization": "Conjuration",
      "description": "Stores a small object in a dimensional micro-pocket and can summon it to their hand instantly."
    },
    {
      "name": "Bait Lure",
      "tier": "1",
      "specialization": "Core",
      "description": "Sends a mana signal through dimensions that attracts small spirits or creatures to a specific location."
    },
    {
      "name": "Blink Step",
      "tier": "1",
      "specialization": "Core",
      "description": "Flickers out of existence for a fraction of a second, reappearing 2m in any direction."
    },
    {
      "name": "Dimensional Leash",
      "tier": "1",
      "specialization": "Core",
      "description": "Creates a binding tether between themselves and a small summoned creature, preventing it from straying."
    },
    {
      "name": "Object Swap",
      "tier": "1",
      "specialization": "Core",
      "description": "Swaps two small objects of similar size that are both within arms reach."
    },
    {
      "name": "Call Minor Spirit",
      "tier": "1",
      "specialization": "Summoning",
      "description": "Opens a tiny, brief rift to the spiritual strata, summoning a minor, non-combative entity. This could be a wisp of li..."
    },
    {
      "name": "Echo Servant",
      "tier": "1",
      "specialization": "Summoning",
      "description": "Creates a momentary dimensional echo of themselves that performs a single simple task."
    },
    {
      "name": "Familiar Pulse",
      "tier": "1",
      "specialization": "Summoning",
      "description": "Sends a pulse through their dimensional bond with a summoned creature, checking its status and location."
    },
    {
      "name": "Summon Familiar Spirit",
      "tier": "1",
      "specialization": "Summoning",
      "description": "Calls a minor spirit to inhabit a small animal for an hour."
    },
    {
      "name": "Blink",
      "tier": "1",
      "specialization": "Teleportation",
      "description": "Briefly folds space, instantly teleporting their own body to a location they can clearly see within a few dozen meter..."
    },
    {
      "name": "Dimensional Jolt",
      "tier": "1",
      "specialization": "Teleportation",
      "description": "A brief teleportation that serves as an escape reflex \u2014 the mage vanishes and reappears 1m away when startled."
    },
    {
      "name": "Recall Throw",
      "tier": "1",
      "specialization": "Teleportation",
      "description": "Enchants a thrown weapon to teleport back to their hand after impact."
    },
    {
      "name": "Stutter Step",
      "tier": "1",
      "specialization": "Teleportation",
      "description": "Makes a series of micro-teleports, appearing to glitch through space like a broken image."
    },
    {
      "name": "Iron Rain",
      "tier": "2",
      "specialization": "Conjuration",
      "description": "Opens dozens of tiny portals above an area and drops a hail of metal scraps through them."
    },
    {
      "name": "Quicksand Pit",
      "tier": "2",
      "specialization": "Conjuration",
      "description": "Conjures a mass of loose sand beneath a targets feet, creating a sinkhole."
    },
    {
      "name": "Ammunition Cache",
      "tier": "2",
      "specialization": "Core",
      "description": "Creates a dimensional pocket that continuously feeds ammunition into a weapon."
    },
    {
      "name": "Conjure Shield",
      "tier": "2",
      "specialization": "Core",
      "description": "Pulls a shield from a nearby armoury or storage through a portal directly onto their arm."
    },
    {
      "name": "Beast Bond",
      "tier": "2",
      "specialization": "Summoning",
      "description": "Forms a lasting spatial tether to an animal or low-tier magical beast (like a wolf, hawk, or giant spider). By tuggin..."
    },
    {
      "name": "Binding Circle",
      "tier": "2",
      "specialization": "Summoning",
      "description": "Inscribes a circle that traps any summoned or dimensional creature that steps within it."
    },
    {
      "name": "Combat Warp",
      "tier": "2",
      "specialization": "Teleportation",
      "description": "Teleports behind a target mid-attack, striking from an unexpected angle."
    },
    {
      "name": "Escape Artist",
      "tier": "2",
      "specialization": "Teleportation",
      "description": "Teleports free of all physical restraints \u2014 ropes, chains, manacles, or grapples."
    },
    {
      "name": "Acid Pool",
      "tier": "3",
      "specialization": "Conjuration",
      "description": "Opens a portal to a natural acid source and floods an area with corrosive liquid."
    },
    {
      "name": "Armoury Summon",
      "tier": "3",
      "specialization": "Conjuration",
      "description": "Opens a portal to a weapons cache and draws out a complete set of arms and armour."
    },
    {
      "name": "Bridge Span",
      "tier": "3",
      "specialization": "Core",
      "description": "Conjures structural materials and assembles them into a functional bridge across a gap."
    },
    {
      "name": "Phase Walk",
      "tier": "3",
      "specialization": "Core",
      "description": "Partially enters a dimensional interstice, allowing them to walk through solid matter."
    },
    {
      "name": "Banish Creature",
      "tier": "3",
      "specialization": "Summoning",
      "description": "Forcibly returns a summoned creature to its origin point, severing the summoners connection."
    },
    {
      "name": "Banishment",
      "tier": "3",
      "specialization": "Summoning",
      "description": "Rather than bringing an entity into the world, the mage violently reverses the dimensional tether of an invading spir..."
    },
    {
      "name": "Blink Assault",
      "tier": "3",
      "specialization": "Teleportation",
      "description": "Makes three rapid teleports in sequence, attacking a single target from three different angles."
    },
    {
      "name": "Dimensional Anchor Escape",
      "tier": "3",
      "specialization": "Teleportation",
      "description": "Pre-sets an escape point. When activated, they instantly teleport there regardless of circumstance."
    },
    {
      "name": "Crystal Battery Bank",
      "tier": "4",
      "specialization": "Conjuration",
      "description": "Conjures a collection of pre-charged crystal batteries from distant sources and arranges them for use."
    },
    {
      "name": "Gateway",
      "tier": "4",
      "specialization": "Core",
      "description": "Opens a stable two-way portal between their current location and a place they know well."
    },
    {
      "name": "Army of Teeth",
      "tier": "4",
      "specialization": "Summoning",
      "description": "Opens multiple portals simultaneously, flooding an area with ravenous dimensional predators."
    },
    {
      "name": "Chain Teleport",
      "tier": "4",
      "specialization": "Teleportation",
      "description": "Makes a sequence of long-range teleportations, each jumping from the last landing point."
    },
    {
      "name": "Arsenal Manifest",
      "tier": "5",
      "specialization": "Conjuration",
      "description": "Conjures an entire armourys worth of weapons and armour, enough to outfit a small army."
    },
    {
      "name": "Abyssal Gate",
      "tier": "5",
      "specialization": "Core",
      "description": "Opens a portal to a hostile dimension and holds it open, allowing a continuous stream of entities to pour throu..."
    },
    {
      "name": "Dimensional Army",
      "tier": "5",
      "specialization": "Summoning",
      "description": "Opens a sustained breach and calls forth an army of lesser creatures that follow their command."
    },
    {
      "name": "Teleportation Network",
      "tier": "5",
      "specialization": "Teleportation",
      "description": "Establishes a permanent network of teleportation nodes between multiple locations."
    }
  ],
  "Divination": [
    {
      "name": "Age Reading",
      "tier": "1",
      "specialization": "Chronomancy",
      "description": "Touches an object and determines its precise age by reading temporal mana decay."
    },
    {
      "name": "D\u00e9j\u00e0 Vu",
      "tier": "1",
      "specialization": "Chronomancy",
      "description": "Induces a momentary sense of temporal disorientation in a target, making them hesitate."
    },
    {
      "name": "Echoes of the Past",
      "tier": "1",
      "specialization": "Chronomancy",
      "description": "Touches a location and forces the ambient mana to visually replay the events that happened there up to 24 hours ago. ..."
    },
    {
      "name": "Moment's Pause",
      "tier": "1",
      "specialization": "Chronomancy",
      "description": "Briefly accelerates their own perception, making the world appear to slow down for a heartbeat."
    },
    {
      "name": "Compass Insight",
      "tier": "1",
      "specialization": "Core",
      "description": "Attuning to ley line flow gains an unerring sense of cardinal direction and approximate time."
    },
    {
      "name": "Mirror Check",
      "tier": "1",
      "specialization": "Core",
      "description": "Uses any reflective surface as a remote viewing screen for a location within line of sight."
    },
    {
      "name": "Object Reading",
      "tier": "1",
      "specialization": "Core",
      "description": "Touches an object and receives a brief flash of its most recent significant use."
    },
    {
      "name": "Slow Perception",
      "tier": "1",
      "specialization": "Core",
      "description": "Slows their own perception of time, allowing them to observe fast-moving events in apparent slow motion."
    },
    {
      "name": "Clairvoyance",
      "tier": "1",
      "specialization": "Scrying",
      "description": "Detaches their sensory perception, creating a localized invisible sensor up to 100 meters away. They can look around ..."
    },
    {
      "name": "Distant Glimpse",
      "tier": "1",
      "specialization": "Scrying",
      "description": "Closes their eyes and catches a blurry, momentary glimpse of a location theyve recently visited."
    },
    {
      "name": "Eavesdrop",
      "tier": "1",
      "specialization": "Scrying",
      "description": "Extends their hearing to a nearby location, listening to conversations through walls."
    },
    {
      "name": "Scry Familiar",
      "tier": "1",
      "specialization": "Scrying",
      "description": "Views the surroundings of a person or creature they have a strong personal connection with."
    },
    {
      "name": "After-Image",
      "tier": "2",
      "specialization": "Chronomancy",
      "description": "Leaves a temporal echo at their current position that persists for a few seconds, confusing attackers."
    },
    {
      "name": "Decay Acceleration",
      "tier": "2",
      "specialization": "Chronomancy",
      "description": "Accelerates entropy on a single small object, aging it rapidly."
    },
    {
      "name": "Micro-Haste",
      "tier": "2",
      "specialization": "Core",
      "description": "Slightly accelerates their own personal localized time-stream. To them, the world appears to move just a fraction of ..."
    },
    {
      "name": "Scrying Shield Detect",
      "tier": "2",
      "specialization": "Core",
      "description": "Scans for active scrying effects targeting themselves or an area."
    },
    {
      "name": "Map Render",
      "tier": "2",
      "specialization": "Scrying",
      "description": "Uses scrying to create an aerial view of their surroundings, rendering a mental map."
    },
    {
      "name": "Sound Scry",
      "tier": "2",
      "specialization": "Scrying",
      "description": "Extends remote viewing to include audio, creating a full audiovisual surveillance feed."
    },
    {
      "name": "Combat Prediction",
      "tier": "3",
      "specialization": "Chronomancy",
      "description": "Perceives 3 seconds into the future, allowing them to predict enemy attacks and movements."
    },
    {
      "name": "Temporal Dodge",
      "tier": "3",
      "specialization": "Chronomancy",
      "description": "Briefly steps a fraction of a second into the future, allowing an attack to pass through where they were."
    },
    {
      "name": "Haste",
      "tier": "3",
      "specialization": "Core",
      "description": "Accelerates a targets personal timeframe, making them move and act at double speed."
    },
    {
      "name": "Scrying Counter",
      "tier": "3",
      "specialization": "Core",
      "description": "Detects an active scrying sensor and traces it back to its origin, revealing the scryers location."
    },
    {
      "name": "Full Sensory Scry",
      "tier": "3",
      "specialization": "Scrying",
      "description": "Establishes a complete sensory link to a target location \u2014 sight, sound, smell, temperature."
    },
    {
      "name": "Person Scry",
      "tier": "3",
      "specialization": "Scrying",
      "description": "Scries directly on a specific person rather than a location, following them wherever they go."
    },
    {
      "name": "Reversion",
      "tier": "4",
      "specialization": "Chronomancy",
      "description": "Rewinds a targets personal timeline by 10 seconds, undoing damage and repositioning them."
    },
    {
      "name": "Anti-Scrying Fortress",
      "tier": "4",
      "specialization": "Core",
      "description": "Creates a zone that is invisible to all forms of scrying and remote observation."
    },
    {
      "name": "Continental Scry",
      "tier": "4",
      "specialization": "Scrying",
      "description": "Can remotely view any known location on the same continent with perfect clarity."
    },
    {
      "name": "Age Reversal",
      "tier": "5",
      "specialization": "Chronomancy",
      "description": "Reverses aging on a living creature, physically restoring them to a younger state."
    },
    {
      "name": "Scrying Sovereign",
      "tier": "5",
      "specialization": "Core",
      "description": "Achieves perfect surveillance mastery \u2014 undetectable, untraceable, and capable of scrying through any non-divin..."
    },
    {
      "name": "Deep History View",
      "tier": "5",
      "specialization": "Scrying",
      "description": "Reads the mana imprint of a location going back centuries, witnessing ancient events."
    }
  ],
  "Illusionism": [
    {
      "name": "Flash Colour",
      "tier": "1",
      "specialization": "Core",
      "description": "Creates a brief burst of coloured light \u2014 a signal flare, a distraction, or a light show."
    },
    {
      "name": "Ghost Sound",
      "tier": "1",
      "specialization": "Core",
      "description": "Creates a brief, simple sound effect \u2014 a footstep, a cough, a creaking door \u2014 at a point within earshot."
    },
    {
      "name": "Phantom Footsteps",
      "tier": "1",
      "specialization": "Core",
      "description": "Creates the sound of approaching footsteps from a specific direction."
    },
    {
      "name": "Thought Shield",
      "tier": "1",
      "specialization": "Core",
      "description": "Reinforces their own mental barriers, gaining resistance to psychic intrusion."
    },
    {
      "name": "Aura Dimming",
      "tier": "1",
      "specialization": "Glamour",
      "description": "Suppresses their visible mana aura, making them appear mundane to casual magical observation."
    },
    {
      "name": "Blemish Removal",
      "tier": "1",
      "specialization": "Glamour",
      "description": "Conceals small physical imperfections \u2014 acne, bruises, bloodshot eyes, or minor scars."
    },
    {
      "name": "Minor Glamour",
      "tier": "1",
      "specialization": "Glamour",
      "description": "Creates small, localized cosmetic changes to themselves or a willing target. They can change the color of their eyes,..."
    },
    {
      "name": "Presence Amplification",
      "tier": "1",
      "specialization": "Glamour",
      "description": "Projects a subtle aura that makes them seem slightly more important and attention-worthy."
    },
    {
      "name": "Attention Divert",
      "tier": "1",
      "specialization": "Mind Magic",
      "description": "Subtly redirects a targets attention away from something specific."
    },
    {
      "name": "Empathic Read",
      "tier": "1",
      "specialization": "Mind Magic",
      "description": "Attunes to a targets emotional state, sensing their current dominant emotion."
    },
    {
      "name": "Mental Nudge",
      "tier": "1",
      "specialization": "Mind Magic",
      "description": "Plants a single word or feeling in a targets mind \u2014 a subliminal suggestion below conscious awareness."
    },
    {
      "name": "Psychic Ping",
      "tier": "1",
      "specialization": "Mind Magic",
      "description": "Sends a brief mental impulse to a known person within range \u2014 the equivalent of tapping someone on the shoulder..."
    },
    {
      "name": "Invisibility Matrix",
      "tier": "2",
      "specialization": "Core",
      "description": "Seamlessly bends light around a target. To the naked eye, the target vanishes completely, bleeding into the backgroun..."
    },
    {
      "name": "Mirror Double",
      "tier": "2",
      "specialization": "Core",
      "description": "Creates a visual duplicate of themself that mimics their movements at a slight delay."
    },
    {
      "name": "Attractive Aura",
      "tier": "2",
      "specialization": "Glamour",
      "description": "Radiates a subtle enchantment of physical attractiveness that makes them striking to observers."
    },
    {
      "name": "Disguise Self",
      "tier": "2",
      "specialization": "Glamour",
      "description": "Generates a complete, hollow optical illusion over their own body, projecting the exact visual appearance, voice, and..."
    },
    {
      "name": "Command",
      "tier": "2",
      "specialization": "Mind Magic",
      "description": "Forces a single, imperative psychic command directly into the motor cortex of the victim. The command must be a simpl..."
    },
    {
      "name": "Fear Induction",
      "tier": "2",
      "specialization": "Mind Magic",
      "description": "Triggers the fear response in a targets brain, causing irrational terror."
    },
    {
      "name": "Environmental Illusion",
      "tier": "3",
      "specialization": "Core",
      "description": "Layers a false environment over a room \u2014 the floor appears to be lava, the walls drip with acid, or the ceiling..."
    },
    {
      "name": "Invisibility",
      "tier": "3",
      "specialization": "Core",
      "description": "Bends light around themselves, becoming invisible to the naked eye."
    },
    {
      "name": "Charm Field",
      "tier": "3",
      "specialization": "Glamour",
      "description": "Radiates an irresistible charm that makes everyone nearby instinctively friendly and agreeable."
    },
    {
      "name": "Emotional Mask",
      "tier": "3",
      "specialization": "Glamour",
      "description": "Projects a false emotional state, appearing calm when terrified, confident when doubtful, or friendly when host..."
    },
    {
      "name": "Deep Read",
      "tier": "3",
      "specialization": "Mind Magic",
      "description": "Probes beyond surface thoughts, accessing recent memories and hidden intentions."
    },
    {
      "name": "Memory Block",
      "tier": "3",
      "specialization": "Mind Magic",
      "description": "Seals away a specific memory, making the target unable to recall it."
    },
    {
      "name": "False RealityBubble",
      "tier": "4",
      "specialization": "Core",
      "description": "Overwrites the perceptual reality of a localized area. They can make a burning building look pristine, turn a squad o..."
    },
    {
      "name": "Commanding Aura",
      "tier": "4",
      "specialization": "Glamour",
      "description": "Projects an overwhelming aura of leadership and authority that compels obedience from weak-willed creatures."
    },
    {
      "name": "Domination",
      "tier": "4",
      "specialization": "Mind Magic",
      "description": "Totally overwrites the targets consciousness, turning them into a hollow shell that executes complex instructions wit..."
    },
    {
      "name": "Mass Invisibility",
      "tier": "5",
      "specialization": "Core",
      "description": "Renders an entire group invisible, bending light around all of them simultaneously."
    },
    {
      "name": "Absolute Masquerade",
      "tier": "5",
      "specialization": "Glamour",
      "description": "Creates a perfect, undetectable glamour that fools even divine senses and magical analysis."
    },
    {
      "name": "Complete Mind Wipe",
      "tier": "5",
      "specialization": "Mind Magic",
      "description": "Erases all of a targets memories, reducing them to a blank slate."
    }
  ],
  "Projection": [
    {
      "name": "Combat Flare",
      "tier": "1",
      "specialization": "Combat Magic",
      "description": "A sharp flash of light designed specifically for combat. Unlike decorative light spells, this one is optimized for di..."
    },
    {
      "name": "Force Blade",
      "tier": "1",
      "specialization": "Combat Magic",
      "description": "Condenses raw concussive force into a razor-sharp edge, extending from their fist or wrapping around a mundane handle..."
    },
    {
      "name": "Magic Missile",
      "tier": "1",
      "specialization": "Combat Magic",
      "description": "A tiny, focused bolt of force designed to stun rather than kill. Used for sparring and non-lethal combat."
    },
    {
      "name": "Shield",
      "tier": "1",
      "specialization": "Combat Magic",
      "description": "Projects a small, momentary shield of force just large enough to deflect one incoming attack."
    },
    {
      "name": "Mana Knuckles",
      "tier": "1",
      "specialization": "Core",
      "description": "Wraps their fists in a thin layer of kinetic energy, turning every punch into a magically enhanced strike."
    },
    {
      "name": "Mana Spark Suppression",
      "tier": "1",
      "specialization": "Core",
      "description": "Extends their hand and snuffs out a minor magical effect \u2014 extinguishing a mage light, silencing a magical alar..."
    },
    {
      "name": "Pressure Wave",
      "tier": "1",
      "specialization": "Core",
      "description": "Extends their palm and releases a flat pulse of kinetic force. Objects within arms reach are pushed back as th..."
    },
    {
      "name": "Shield Crack",
      "tier": "1",
      "specialization": "Core",
      "description": "Identifies the weakest point in an active magical barrier and sends a precise pulse to fracture it."
    },
    {
      "name": "Ember Toss",
      "tier": "1",
      "specialization": "Evocation",
      "description": "Flicks a marble-sized ball of molten mana at a target. It bursts on impact like a tiny firework, stinging skin ..."
    },
    {
      "name": "Frost Needle",
      "tier": "1",
      "specialization": "Evocation",
      "description": "Crystallizes ambient moisture into a razor-thin shard of ice and flings it at a target. The needle dissolves af..."
    },
    {
      "name": "Ignite",
      "tier": "1",
      "specialization": "Evocation",
      "description": "The simplest elemental Evocation. The mage snaps their fingers and produces a small, completely controllable flame or..."
    },
    {
      "name": "Mana Flicker",
      "tier": "1",
      "specialization": "Evocation",
      "description": "Produces a tiny, sustained flame of pure mana energy that hovers above their fingertip. Unlike mundane fire, it..."
    },
    {
      "name": "Detect Enchantment",
      "tier": "1",
      "specialization": "Negation",
      "description": "Scans an object or area for active magical effects, identifying their school and approximate tier."
    },
    {
      "name": "Null Touch",
      "tier": "1",
      "specialization": "Negation",
      "description": "The mages touch creates a small zone where mana cannot flow. Any magical effect touching their hand is momentarily di..."
    },
    {
      "name": "Scramble Casting",
      "tier": "1",
      "specialization": "Negation",
      "description": "Creates a brief burst of mana static that disrupts a nearby mages concentration while casting."
    },
    {
      "name": "Suppress Aura",
      "tier": "1",
      "specialization": "Negation",
      "description": "The most basic lesson in magical defense. The mage actively projects a dampening field over their own soul, silencing..."
    },
    {
      "name": "Combat Roll",
      "tier": "2",
      "specialization": "Combat Magic",
      "description": "Propels themselves with a burst of kinetic force, covering ground at supernatural speed while evading attacks."
    },
    {
      "name": "Detonation Charge",
      "tier": "2",
      "specialization": "Combat Magic",
      "description": "Creates a small, sticky sphere of compressed energy, attaches it to a surface, and detonates it remotely."
    },
    {
      "name": "Mana Bolt",
      "tier": "2",
      "specialization": "Core",
      "description": "The simplest and most reliable magical attack. The mage condenses raw mana into a glowing, high-velocity projectile a..."
    },
    {
      "name": "Silence Ward",
      "tier": "2",
      "specialization": "Core",
      "description": "Creates a small zone where verbal spell components are suppressed, making standard incantation-based casting ne..."
    },
    {
      "name": "Corrosive Spray",
      "tier": "2",
      "specialization": "Evocation",
      "description": "Generates a fine mist of hyper-reactive mana particles that eat through organic material and corrode metal on c..."
    },
    {
      "name": "Elemental Ray",
      "tier": "2",
      "specialization": "Evocation",
      "description": "Projects a concentrated, sustained beam of elemental energy from their palm. Whether its white-hot fire, crackling li..."
    },
    {
      "name": "Counterspell",
      "tier": "2",
      "specialization": "Negation",
      "description": "Reads an incoming spells structure mid-cast and generates a precisely tuned counter-frequency to unravel it."
    },
    {
      "name": "Dispel Magic",
      "tier": "2",
      "specialization": "Negation",
      "description": "Focuses raw counter-force directly into an active, sustained spell effect\u2014like an illusion, an animated golem, or a m..."
    },
    {
      "name": "Counter Barrage",
      "tier": "3",
      "specialization": "Combat Magic",
      "description": "Absorbs an incoming spell and immediately converts the captured energy into a retaliatory strike."
    },
    {
      "name": "Fragmentation Nova",
      "tier": "3",
      "specialization": "Combat Magic",
      "description": "Detonates a sphere of crystallized mana that bursts into razor-sharp shrapnel in all directions."
    },
    {
      "name": "Blink Strike",
      "tier": "3",
      "specialization": "Core",
      "description": "Instantly closes distance using a short Projection-assisted burst and delivers a devastating enhanced strike."
    },
    {
      "name": "Kinetic Shield",
      "tier": "3",
      "specialization": "Core",
      "description": "Projects a localized, concave disc of raw force hovering in the air or attached to their forearm. It absorbs kinetic ..."
    },
    {
      "name": "Cryo Wave",
      "tier": "3",
      "specialization": "Evocation",
      "description": "A sweeping arc of freezing energy emanates from the casters hands, flash-freezing moisture in the air and coating eve..."
    },
    {
      "name": "Crystal Storm",
      "tier": "3",
      "specialization": "Evocation",
      "description": "Rapidly crystallizes mana into dozens of razor-sharp shards and launches them in a horizontal spread like magic..."
    },
    {
      "name": "Antimagic Shell",
      "tier": "3",
      "specialization": "Negation",
      "description": "Wraps themselves in a bubble of mana-disrupting energy that suppresses all magical effects that try to penetrat..."
    },
    {
      "name": "Mana Burn Field",
      "tier": "3",
      "specialization": "Negation",
      "description": "Creates a zone where casting magic is physically painful. Mana channelled within the area burns the casters me..."
    },
    {
      "name": "Fragmentation Burst",
      "tier": "4",
      "specialization": "Combat Magic",
      "description": "Conjures a highly concentrated orb of kinetic energy and lobs it into a crowded area. Upon impact, the orb shatters i..."
    },
    {
      "name": "Kinetic Lance",
      "tier": "4",
      "specialization": "Core",
      "description": "A massive spear of pure compressed force materializes in the casters hand and can be hurled with devastating velocity..."
    },
    {
      "name": "Chain Lightning",
      "tier": "4",
      "specialization": "Evocation",
      "description": "Unleashes a massive torrent of jagged, uncontrollable electricity. The lightning strikes a primary target and immedia..."
    },
    {
      "name": "Anti-Magic Zone",
      "tier": "4",
      "specialization": "Negation",
      "description": "Plants their staff or foot into the ground, radiating a massive dome of absolute null-magic. Within this grey, oppres..."
    },
    {
      "name": "Doomsday Protocol",
      "tier": "5",
      "specialization": "Combat Magic",
      "description": "A forbidden combat technique that converts the casters remaining lifespan into a final devastating attack. Used only ..."
    },
    {
      "name": "Absolute Zero Point",
      "tier": "5",
      "specialization": "Core",
      "description": "Drains all thermal energy from a localized area, dropping the temperature to near absolute zero. Matter becomes..."
    },
    {
      "name": "Elemental Convergence",
      "tier": "5",
      "specialization": "Evocation",
      "description": "Simultaneously generates fire, ice, lightning, and force, weaving them into a single devastating composite atta..."
    },
    {
      "name": "Absolute Null",
      "tier": "5",
      "specialization": "Negation",
      "description": "Creates a permanent zone of absolute magical suppression. Nothing magical functions within \u2014 ever."
    }
  ],
  "Soul Magic": [
    {
      "name": "Offering Ritual",
      "tier": "1",
      "specialization": "Core",
      "description": "Performs a small ritual offering that attracts and pleases local spirits, making them cooperative."
    },
    {
      "name": "Soul Echo",
      "tier": "1",
      "specialization": "Core",
      "description": "Reads the spiritual residue left by a souls passage \u2014 sensing where souls have recently been."
    },
    {
      "name": "Soul Integrity Check",
      "tier": "1",
      "specialization": "Core",
      "description": "Examines a targets soul to assess its current condition \u2014 checking for damage, corruption, or foreign influenc..."
    },
    {
      "name": "Soul Mark",
      "tier": "1",
      "specialization": "Core",
      "description": "Inscribes a minor mark on a targets soul, allowing them to be identified and tracked."
    },
    {
      "name": "Feedback Loop",
      "tier": "1",
      "specialization": "Soul Carving",
      "description": "Creates a tiny loop in a targets mana flow, causing mild discomfort when casting."
    },
    {
      "name": "Mana Channel Widening",
      "tier": "1",
      "specialization": "Soul Carving",
      "description": "Carefully widens a mana pathway in the targets soul, improving mana flow."
    },
    {
      "name": "Soul Read",
      "tier": "1",
      "specialization": "Soul Carving",
      "description": "Reads the basic spiritual configuration of a targets soul, learning their innate affinities."
    },
    {
      "name": "Soul Scarring",
      "tier": "1",
      "specialization": "Soul Carving",
      "description": "Physically touches the target, driving a spike of dark mana directly into their spiritual matrix. This leaves a perma..."
    },
    {
      "name": "Minor Spirit Call",
      "tier": "1",
      "specialization": "Spirit Calling",
      "description": "Sends a gentle call into the spiritual realm, attracting the attention of minor spirits."
    },
    {
      "name": "Speak with Dead",
      "tier": "1",
      "specialization": "Spirit Calling",
      "description": "Targets a fresh corpse or a known grave, gently plucking the lingering echoes of the departed soul. A faint, ghostly ..."
    },
    {
      "name": "Spirit Detection",
      "tier": "1",
      "specialization": "Spirit Calling",
      "description": "Attunes their senses to detect invisible spirits in the area."
    },
    {
      "name": "Spirit Fade",
      "tier": "1",
      "specialization": "Spirit Calling",
      "description": "Masks their presence from spirits, becoming invisible to spiritual perception."
    },
    {
      "name": "Affinity Shift",
      "tier": "2",
      "specialization": "Core",
      "description": "Temporarily alters a targets magical affinity, making them better at one school and worse at another."
    },
    {
      "name": "Soul Shield",
      "tier": "2",
      "specialization": "Core",
      "description": "Wraps their soul in a protective barrier, reducing vulnerability to soul-damaging effects."
    },
    {
      "name": "Curse Inscription",
      "tier": "2",
      "specialization": "Soul Carving",
      "description": "Carves a minor curse into a targets soul \u2014 bad luck, nightmares, or persistent unease."
    },
    {
      "name": "Empower Artifact",
      "tier": "2",
      "specialization": "Soul Carving",
      "description": "Instead of permanently animating a golem, the mage safely splices a tiny fragment of their own soul and grafts it int..."
    },
    {
      "name": "Ancestral Consultation",
      "tier": "2",
      "specialization": "Spirit Calling",
      "description": "Contacts the spirit of a deceased ancestor and asks for guidance."
    },
    {
      "name": "Banish Spirit",
      "tier": "2",
      "specialization": "Spirit Calling",
      "description": "Forcibly sends a spirit back to its origin, removing it from the physical world."
    },
    {
      "name": "Exorcism",
      "tier": "3",
      "specialization": "Core",
      "description": "Forcibly ejects a possessing entity from a host body."
    },
    {
      "name": "Soul Jar",
      "tier": "3",
      "specialization": "Core",
      "description": "A horrific display of the dark arts. When a creature dies, its soul rapidly disperses into the background mana. With ..."
    },
    {
      "name": "Curse Embedding",
      "tier": "3",
      "specialization": "Soul Carving",
      "description": "Carves a potent curse deep into a targets soul, making it very difficult to remove."
    },
    {
      "name": "Custom Soul Ward",
      "tier": "3",
      "specialization": "Soul Carving",
      "description": "Carves a defensive pattern directly into a targets soul, protecting against specific magical attacks."
    },
    {
      "name": "Greater Spirit Call",
      "tier": "3",
      "specialization": "Spirit Calling",
      "description": "Calls forth a powerful spirit and negotiates its aid."
    },
    {
      "name": "Manifest Ghost",
      "tier": "3",
      "specialization": "Spirit Calling",
      "description": "Provides enough raw mana to a summoned spirit that it gains physical density. The resulting specter is horrifying to ..."
    },
    {
      "name": "Astral Projection",
      "tier": "4",
      "specialization": "Core",
      "description": "Unhooks their own soul from their physical body, stepping out into the world as a purely spiritual entity. In this st..."
    },
    {
      "name": "Cruciatus Splinter",
      "tier": "4",
      "specialization": "Soul Carving",
      "description": "Forcefully embeds a highly condensed, barbed magical splinter directly into the targets central soul pillar. The vict..."
    },
    {
      "name": "Ancient Spirit Pact",
      "tier": "4",
      "specialization": "Spirit Calling",
      "description": "Contacts and negotiates with an ancient, powerful spirit."
    },
    {
      "name": "Grand Soul Repair",
      "tier": "5",
      "specialization": "Core",
      "description": "Performs a complete restoration of a severely damaged soul."
    },
    {
      "name": "Complete Curse",
      "tier": "5",
      "specialization": "Soul Carving",
      "description": "Carves the ultimate curse \u2014 a comprehensive spiritual malediction that affects every aspect of the targets exi..."
    },
    {
      "name": "Call of the Dead",
      "tier": "5",
      "specialization": "Spirit Calling",
      "description": "Summons every spirit in a vast area, creating a host of the dead that follows their command."
    }
  ]
};

const SCHOOLS = Object.keys(SPELLS);
let activeSchool = SCHOOLS[0];
let searchTerm = '';
let sortCol = 'tier';
let sortDir = 'asc';

function init() {
  const tabsEl = document.getElementById('schoolTabs');
  SCHOOLS.forEach(s => {
    const btn = document.createElement('button');
    btn.className = 'school-tab';
    btn.textContent = s;
    btn.onclick = () => { activeSchool = s; render(); };
    tabsEl.appendChild(btn);
  });

  document.getElementById('searchBar').addEventListener('input', function(e) {
    searchTerm = e.target.value.toLowerCase();
    render();
  });

  document.querySelectorAll('.spell-table thead th').forEach(th => {
    th.addEventListener('click', function() {
      const col = this.dataset.col;
      if (sortCol === col) {
        sortDir = sortDir === 'asc' ? 'desc' : 'asc';
      } else {
        sortCol = col;
        sortDir = 'asc';
      }
      render();
    });
  });

  render();
}

function render() {
  // Update tabs
  document.querySelectorAll('.school-tab').forEach((btn, i) => {
    btn.classList.toggle('active', SCHOOLS[i] === activeSchool);
  });

  // Update sort indicators
  document.querySelectorAll('.spell-table thead th').forEach(th => {
    th.classList.remove('sorted-asc', 'sorted-desc');
    if (th.dataset.col === sortCol) {
      th.classList.add(sortDir === 'asc' ? 'sorted-asc' : 'sorted-desc');
    }
  });

  // Filter
  let spells = SPELLS[activeSchool] || [];
  if (searchTerm) {
    spells = spells.filter(s =>
      s.name.toLowerCase().includes(searchTerm) ||
      s.specialization.toLowerCase().includes(searchTerm) ||
      s.description.toLowerCase().includes(searchTerm)
    );
  }

  // Sort
  spells = [...spells].sort((a, b) => {
    let va = a[sortCol] || '';
    let vb = b[sortCol] || '';
    if (sortCol === 'tier') {
      va = parseInt(va) || 0;
      vb = parseInt(vb) || 0;
      return sortDir === 'asc' ? va - vb : vb - va;
    }
    va = va.toString().toLowerCase();
    vb = vb.toString().toLowerCase();
    const cmp = va.localeCompare(vb);
    return sortDir === 'asc' ? cmp : -cmp;
  });

  // Render
  const body = document.getElementById('spellBody');
  if (spells.length === 0) {
    body.innerHTML = '<tr><td colspan="4" class="no-results">No spells found.</td></tr>';
  } else {
    body.innerHTML = spells.map(s => {
      const tierClass = 'tier-' + (parseInt(s.tier) || 1);
      const specClass = s.specialization === 'Core' ? 'core' : '';
      return '<tr>' +
        '<td><span class="tier-badge ' + tierClass + '">' + s.tier + '</span></td>' +
        '<td>' + s.name + '</td>' +
        '<td><span class="spec-tag ' + specClass + '">' + s.specialization + '</span></td>' +
        '<td>' + s.description + '</td>' +
        '</tr>';
    }).join('');
  }

  document.getElementById('spellCount').textContent =
    'Showing ' + spells.length + ' of ' + (SPELLS[activeSchool] || []).length + ' spells in ' + activeSchool;
}

if (document.readyState === 'loading') {
  document.addEventListener('DOMContentLoaded', init);
} else {
  init();
}
</script>

</div>
