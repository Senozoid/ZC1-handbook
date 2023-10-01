# Combat

## Overview

- Combat is turn-based and symmetric. During their turns, participants have the option to attack with their weapons, change weapons, move, or use a spell. Both order and frequency of a participant's turns in each round is determined by the participant's [turnrate](Glossary.md#turnrate), which, unless modified, is equal to Athletic skill. However, if the battle starts with an ambush, then the surprised team misses the first round.
- Combat continues as long as the player is alive and there is at least one active hostile within 100 distance from the player. In other words, if the player's health falls to 0, if the last enemy is neutralised, or if the player's distance from the nearest enemy exceeds 100 (some combats may not allow this), combat ends.
- As long as there is at least one active hostile within 100 distance from the player, any other participant has to be at a distance more than 150 from the player (some combats may not allow this) to be considered out of combat. A combatant once considered to be out of combat does not have any part in the combat for the rest of its duration.
- Having low enough Spirit during combat has a chance to trigger panic in a participant during each of the participant's turns. If panic is triggered in a turn, the combatant is forced to move randomly (instead of acting as desired) in that turn.
- Nothing in the inventory except weapons and consumables (potions and glyphs are examples of consumables) can be accessed during combat. Changing weapons costs a turn, but using a consumable does not cost a turn, unless specified otherwise in the item description. However, the inventory cannot be accessed out of turn.

## Physical Damage

- Outgoing damage is based on only the equipped weapon(s) which can attack an enemy at the chosen range. If the player chooses to attack an enemy outside the range of all of the player's equipped weapons, the turn will simply fail.
- Physical damage has 3 components, which are blunt damage, cutting damage and piercing damage. All calculations are done separately and symmetrically regarding these components. Both the [Def](Glossary.md#def) and [Dmg](Glossary.md#dmg) attributes, as well as weapon [Power](Glossary.md#power) and armour [Rating](Glossary.md#rating), consider the three components to be independent of each other.

### Dealing Damage

#### Things to note:

- Outgoing physical damage is determined by the attacker’s equipped weapon(s), Strength attribute, Dmg modifiers, Martial skill and the defender’s Martial skill.
- The damage potential of a weapon is its Power, and the further the total Weight of equipped weapon(s) exceeds the Strength of the wielder, the less effective each weapon will become in proportion to its Power.
- The chance of an attack to not miss, is given by the ratio of the attacker's [accuracy](Glossary.md#accuracy) and the defender's [evasion](Glossary.md#evasion). Both accuracy and evasion, unless modified, are equal to the corresponding combatants' Martial skills. If the attack is evaded, any accompanying effects are also evaded.

#### Calculations:

```
Chance to hit = min(1, Martial/OppMartial)
WeaponDam = min(Power, Power*Strength/TotalWeight)
BaseDmg = Sum of valid WeaponDams
Outgoing = Mod(BaseDmg)
```

### Taking Damage

#### Things to note:

- The attacker’s outgoing damage is the defender’s incoming damage. The damage taken is determined by the incoming damage, the defender’s equipped armour piece(s) (including shield) and Def modifiers.
- The further the total Weight of equipped apparel exceeds the wearer's Strength, the slower the wearer becomes. This affects both turnrate and speed of the wearer.
- The defence potential of each piece of armour is its Rating. Each piece of physical armour contributes a fixed percentage to the wearer's Def attributes, for instance a cuirass has more effect on Def even if a pair of gauntlets have the same Rating, because torso armour protects 50% of the body, and hand armour protects only 5%.
- The percentage contribution of a shield to the Def attribute is ten times the wielder's Martial skill. However, not only does equipping a shield prohibit the usage of both hands for weapon, but the shield Weight counts towards total apparel Weight.
- The Def attribute always reduces damage taken, but never completely eliminates it. The higher the incoming damage, the more damage will be subtracted, but the percentage of the damage reduced will become smaller. The amount of damage subtracted can never exceed the value of Def.

#### Calculations:

```
BaseDef = head*20%+torso*50%+arms*10%+legs*10%+hands*5%+feet*5%+shield*(10*Martial)%
= (head*4+torso*10+arms*2+legs*2+hands+feet+shield*2*Martial)/20
EffDamage = Inc*Inc/(Inc+Mod(BaseDef))
[Where Inc = Incoming damage]
```

![Graph: Damage taken wrt incoming damage, at constant Def values.](Handbook_files/wrtinc-def-10-50-200.png)

<details>
<summary>If you cannot see this image on GitHub...</summary>

Certain ISPs (like Jio) block _raw.githubusercontent.com_ for some reason, which causes repository images to not load. If you have this problem, please use a VPN or connect through a different ISP.

</details>

The above graph shows how received damage may change with respect to incoming damage at different fixed values of the Def attribute. More damage is blocked as the incoming damage increases, but the percentage of the incoming damage being blocked becomes smaller. \
For example, with Def=20, an incoming damage of 5 may be reduced to 1 (subtraction=4, percentage reduction=80%), and a damage of 30 may be reduced to 18 (subtraction=12, percentage reduction=40%). So as the incoming damage increases (5 to 30), the amount of the subtracted damage increases (4 to 12), but its value in relation to the total incoming damage, decreases (80% to 40%). [[also see Appendix-1]](Appendices.md#appendix-1-a-rant-about-ac)

## Movement

- Moving is one-dimensional, and unless teleportation is involved, the maximum distance moved per turn is given by the participant's [speed](Glossary.md#speed), which, unless modified, is equal to Athletic skill.
- Participants with any form of teleportation can move once before using each of their regular turns, and the range of their movement is limited only by their teleportation. In essence, during each of their unskipped turns, they can move once and then take another action (and yes, the second action may also be movement). Unlike other participants, when panic is triggered, a teleporter moves randomly twice instead of once.

## Spellcasting

- To cast a spell, a participant needs to start preparing it. Once the preparation has started, it may be cancelled during the caster's turn. Starting to prepare a spell, or intentionally cancelling it, costs a turn each. The preparation may take zero or more rounds (not turns), which depends on the spell and is not affected by the caster's skills.
- The arcana required to cast a spell is spent when the preparation begins, and is recovered if the casting is intentionally cancelled, but not if it fails or is interrupted. The effect of a spell begins only after the preparation is complete. A caster may prepare only one spell at a time, and as long as a spell is being prepared, the caster cannot do anything else without cancelling it.

## Modifiers

Modifiers can affect these stats of a combatant during each turn:

- turnrate
- speed
- accuracy
- evasion
- Dmg
- Def

The order of applying combat modifiers is as below:

Racial -> Class -> Enchantment -> Effect -> Opposition -> Chaos \
[Within each type, additive modifiers are applied on top of multiplicative ones]

Enchantments come from equipped items. \
Effects come from spells, abilities, blessings, penalties and carried items. \
Opposition modifiers are effectiveness buffs and debuffs against certain enemies or equipment. These may come from the same sources as Enchantments and Effects, but are applied later. \
Chaos is a somewhat random additive modifier. Chaos level is determined at the beginning of combat. There are 5 levels of Chaos: Low, Mild, Moderate, High, Extreme. These are the respective ranges of Chaos at each level:

* Low = -2 to +2
* Mild = -6 to +6
* Moderate = -12 to +12
* High = -20 to +20
* Extreme = -32 to +32

In Azerog (Warmouth), Chaos level is never below Moderate. But in most other places, it is rarely above Moderate. Each gem of Nurileth elevates the combat by one Chaos level. The Chaos modifier is rolled during each turn based on the Chaos level and added to the attacking Dmg of that turn. Chaos also affects transactions but with a different mechanism.
