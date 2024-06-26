# Combat

## Overview

- Combat is turn-based and symmetric. During their turns, participants have the option to attack with their weapons, change weapons, move, or use a spell. Both order and frequency of a participant's turns in each round is determined by the participant's [turnrate](glossary.md#turnrate), which largely depends on Athletic skill. However, if the battle starts with an ambush, then the surprised team misses the first round.
- Combat continues as long as the player is alive and there is at least one active hostile within 100 distance from the player. In other words, if the player's health falls to 0, if the last enemy is neutralised, or if the player's distance from the nearest enemy exceeds 100 (some combats may not allow this), combat ends.
- As long as there is at least one active hostile within 100 distance from the player, any other participant has to be at a distance more than 150 from the player (some combats may not allow this) to be considered out of combat. A combatant once considered to be out of combat does not have any part in the combat for the rest of its duration.
- Having low enough Spirit during combat has a chance to trigger panic in a participant during each of the participant's turns. If panic is triggered in a turn, the combatant is forced to move randomly (instead of acting as desired) in that turn.
- Nothing in the inventory except weapons and consumables (potions and glyphs are examples of consumables) can be accessed during combat. Changing weapons costs a turn, but using a consumable does not cost a turn, unless specified otherwise in the item description. However, the inventory cannot be accessed out of turn.

## Physical Damage

Physical damage has 3 components, which are blunt damage, cutting damage and piercing damage. All calculations are done separately and symmetrically regarding these components. Both the [defence](glossary.md#defence) and [damage](glossary.md#damage) stats, as well as [weapon power](glossary.md#power) and [armour rating](glossary.md#rating), consider the three components to be independent of each other. In some contexts, the sum of the three components of a physical damage is referred to as the total of that physical damage.

### Dealing Damage

#### Things to note:

- Outgoing physical damage is determined by the attacker's Strength attribute, equipped weapon(s), and damage modifiers.
- The only weapons contributing positively to outgoing damage are the equipped weapon(s) which can affect the chosen target (not out of range and not immune to the weapon). However, all equipped weapons contribute to the Strength requirements.
- Each weapon has a Strength requirement, ie., requires an effort to be effective. For a ranged weapon, it is the draw-weight. For a melee or a thrown weapon, it is thrice the weight of the weapon.
- The further the total effort required for equipped weapon(s) exceeds the wielder's Strength, the further the wielder's turrnrate and accuracy are reduced.
- If the wielder's Strength exceeds the effort required for an equipped melee weapon, there is a roll for extra damage. The total of this extra damage cannot exceed the extra Strength or the total of the weapon power. And all the components of this extra damage are equal (total/3). [[also see Appendix-3]](appendices.md#appendix-3-the-melee-weapon-puzzle)
- The probability of the attack completely missing, is determined by the attacker's [accuracy](glossary.md#accuracy) and the target's [evasion](glossary.md#evasion). If the attack is evaded, any accompanying effects are also evaded.

#### Calculations:

```
Miss probability = max(0, (1+OppEva-Acc)/10)

Melee weapon damage = WeaponPower + ExtraDamage
Other weapon damage = WeaponPower

BaseDmg = Sum of damages from weapons valid for chosen target
Outgoing = Mod(BaseDmg)
```

### Taking Damage

#### Things to note:

- The attacker’s outgoing damage, if not evaded, is the target’s incoming damage. The damage taken is determined by the incoming damage, the target’s equipped armour piece(s), defence modifiers, and if a shield is equipped, Martial skill and the shield's rating.
- The further the total weight of equipped apparel exceeds the wearer's Strength, the further the wearer's speed and evasion are reduced.
- The defence potential of each piece of armour is its rating. Each piece of physical armour contributes a fixed percentage to the wearer's defence stat, so a pair of gauntlets has less effect on defence than a cuirass with the same rating, because torso armour protects 50% of the body, and hand armour protects only 5%.
- The percentage contribution of a shield to the defence stat is ten times the wielder's Martial skill. However, not only does equipping a shield prohibit using both hands for weapon, but the shield weight counts towards total apparel weight.
- The defence stat always reduces damage taken, but never completely eliminates it. The higher the incoming damage, the more damage will be subtracted, but the percentage of the damage reduced will become smaller. The subtracted damage never exceeds the target's defence stat.

#### Calculations:

```
Portions of individual ratings adding to base defence:
    Head: 20%
    Torso: 50%
    Arms: 10%
    Legs: 10%
    Hands: 5%
    Feet: 5%
    Shield: (10*Martial)%

BaseDef = (head*4+torso*10+arms*2+legs*2+hands+feet+shield*2*Martial)/20
EffDmg = Incoming^2/(Incoming+Mod(BaseDef))
```

![Graph: Damage taken wrt incoming damage, at constant defence values.](media/wrtinc-def-10-50-200.png)

The above graph shows how received damage may change with respect to incoming damage at different fixed values of the defence stat. More damage is blocked as the incoming damage increases, but the percentage of the incoming damage being blocked becomes smaller. \
For example, with defence=20, an incoming damage of 5 may be reduced to 1 (subtraction=4, percentage reduction=80%), and a damage of 30 may be reduced to 18 (subtraction=12, percentage reduction=40%). So as the incoming damage increases (5 to 30), the amount of the subtracted damage increases (4 to 12), but its value in relation to the total incoming damage, decreases (80% to 40%). [[also see Appendix-1]](appendices.md#appendix-1-a-rant-about-ac)

## Movement

- Moving is one-dimensional, and unless teleportation is involved, the maximum distance moved per turn is given by the participant's [speed](glossary.md#speed), which largely depends on Athletic skill.
- Participants with any form of teleportation can move once before using each of their regular turns, and the range of their movement is limited only by their teleportation. In essence, during each of their unskipped turns, they can move once and then take another action (and yes, the second action may also be movement). Unlike other participants, when panic is triggered, a teleporter moves randomly twice instead of once.

## Spellcasting

- To cast a spell, a participant needs to start preparing it. Once the preparation has started, it may be cancelled during the caster's turn, thereby ending the turn. The preparation may take zero or more rounds (not turns), which depends on the spell and is not affected by the caster's skills.
- The arcana required to cast a spell is spent when the preparation begins, and is recovered if the casting is intentionally cancelled, but not if it fails or is interrupted. The effect of a spell begins only after the preparation is complete. A caster may prepare only one spell at a time, and as long as a spell is being prepared, the caster cannot do anything else without cancelling it.

## Combat Modifiers (WIP)

Combat modifiers modify [combat stats](glossary.md#combat-stats). The order of applying combat modifiers is as below:

Racial -> Class -> Effect -> Enchantment -> Opposition -> Chaos \
[Within each type, additive modifiers are applied on top of multiplicative ones]

