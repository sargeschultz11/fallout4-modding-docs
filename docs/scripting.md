---
title: Scripting
---

This Papyrus script for Fallout 4, named `zzEE_SetBossProperties`, is designed to dynamically modify the properties and attributes of a specific actor object (presumably a "boss") in the game.

```
Scriptname zzEE_SetBossProperties extends Quest

ReferenceAlias Property zzEE_Boss Auto

Float Property NewHealth Auto
Float Property NewHeight Auto
Float Property NewDamage Auto

ActorValue Property HealthAV Auto
ActorValue Property AttackDamageMult Auto

Keyword[] Property Keywords Auto
Spell[] Property Spells Auto
Perk[] Property Perks Auto
Form[] Property InventoryItems Auto

Event OnInit()
    Actor BossNPC = zzEE_Boss.GetReference() as Actor

    if BossNPC
        ; Set health
        BossNPC.SetValue(HealthAV, NewHealth)

        ; Set height
        BossNPC.SetScale(NewHeight)

        ; Set damage
        BossNPC.SetValue(AttackDamageMult, NewDamage)

        ; Add keywords
        int i = 0
        while i < Keywords.Length
            BossNPC.AddKeyword(Keywords[i])
            i += 1
        endwhile

        ; Add spells
        i = 0
        while i < Spells.Length
            BossNPC.AddSpell(Spells[i])
            i += 1
        endwhile

        ; Add perks
        i = 0
        while i < Perks.Length
            BossNPC.AddPerk(Perks[i])
            i += 1
        endwhile

        ; Add inventory items
        i = 0
        while i < InventoryItems.Length
            BossNPC.AddItem(InventoryItems[i])
            i += 1
        endwhile
    endif
EndEvent

```

---

## Script Overview

- **Scriptname**: `zzEE_SetBossProperties`
- **Extends**: `Quest` — This indicates the script is attached to a quest and will run as part of that quest.

---

## Properties

These are variables that can be set in the Creation Kit to configure the script:

- `zzEE_Boss (ReferenceAlias)`: A reference alias for the boss NPC, used to retrieve the actual actor.
- `NewHealth (Float)`: The new health value for the boss.
- `NewHeight (Float)`: The new height scale for the boss.
- `NewDamage (Float)`: The new attack damage multiplier for the boss.
- `HealthAV, AttackDamageMult (ActorValue)`: Actor values used to modify the boss's stats.
- `Keywords (Keyword[])`: An array of keywords to add to the boss.
- `Spells (Spell[])`: An array of spells to give the boss.
- `Perks (Perk[])`: An array of perks to assign to the boss.
- `InventoryItems (Form[])`: An array of items to add to the boss's inventory.

---

## Event: `OnInit()`

This event runs when the script is initialized (e.g., when the associated quest starts).

### 1. Retrieve the Actor Reference

```
Actor BossNPC = zzEE_Boss.GetReference() as Actor
```

The script fetches the actor associated with the `zzEE_Boss` alias.

### 2. Check for Valid Actor

```
if BossNPC
```

Ensures that the `BossNPC` is valid before proceeding.

### 3. Modify Boss Properties

- **Health**: ```
    BossNPC.SetValue(HealthAV, NewHealth)
    ```
    
    Sets the boss's health to the value specified in `NewHealth`.
- **Height**: ```
    BossNPC.SetScale(NewHeight)
    ```
    
    Adjusts the scale of the boss (affects its visual size).
- **Damage Multiplier**: ```
    BossNPC.SetValue(AttackDamageMult, NewDamage)
    ```
    
    Changes the boss's attack damage multiplier.

### 4. Add Keywords

```

while i < Keywords.Length
    BossNPC.AddKeyword(Keywords[i])
    i += 1
endwhile
    
```

Iterates through the `Keywords` array and adds each keyword to the boss.

### 5. Add Spells

```

while i < Spells.Length
    BossNPC.AddSpell(Spells[i])
    i += 1
endwhile
    
```

Iterates through the `Spells` array and adds each spell to the boss.

### 6. Add Perks

```

while i < Perks.Length
    BossNPC.AddPerk(Perks[i])
    i += 1
endwhile
    
```

Iterates through the `Perks` array and assigns each perk to the boss.

### 7. Add Inventory Items

```

while i < InventoryItems.Length
    BossNPC.AddItem(InventoryItems[i])
    i += 1
endwhile
    
```

Iterates through the `InventoryItems` array and adds each item to the boss's inventory.

---

## Key Points

- **Dynamic Configuration**: The script is highly configurable via the Creation Kit. The properties allow you to customize the boss's stats, abilities, and inventory without modifying the script itself.
- **Looping through Arrays**: The `while` loops ensure that all elements in the arrays (e.g., `Keywords`, `Spells`) are applied to the boss.
- **Event Execution**: The `OnInit` event ensures the changes are applied as soon as the quest starts or the alias is filled.

---

## Practical Use

This script can be attached to a quest that runs when a boss is spawned or encountered. By configuring the properties in the Creation Kit, you can:

- Create bosses with unique health, size, and damage settings.
- Grant bosses specific keywords, abilities, and inventory items.
- Adjust perks and spells dynamically based on context.

This makes it a powerful tool for modding, allowing for customizable and reusable boss setups in the game.