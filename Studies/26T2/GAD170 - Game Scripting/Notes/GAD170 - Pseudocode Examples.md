---
tags:
  - Learning/SAE/GAD170/Project
Author: Cody Cork
Date: 2026-03-03
Type: Notes
---
# ChatGPT Example

``` C#
START

LOAD UI_A
RESET Game

SET Player.Level = 1
SET Player.MaxHP = BaseHP
SET Player.HP = Player.MaxHP
SET Player.Attack = BaseAttack
SET XP = 0
SET XP_Threshold = BaseXPThreshold

WHILE Game is NOT Over

    PRINT "Round Start"

    // --- Enemy Setup ---
    LOAD Enemy Stats
    SET Enemy.HP = RandomHPBasedOn(Player.Level)
    SET Enemy.Attack = AttackStrength

    SPAWN Enemy

    // --- Combat Loop ---
    WHILE Enemy.HP > 0 AND Player.HP > 0

        // Player attacks
        Enemy.HP = Enemy.HP - Player.Attack

        IF Enemy.HP <= 0 THEN
            BREAK
        ENDIF

        // Enemy attacks
        Player.HP = Player.HP - Enemy.Attack

        IF Player.HP <= 0 THEN
            PRINT "Game Over"
            END GAME
        ENDIF

    ENDWHILE

    // --- Enemy Defeated ---
    PRINT "Enemy Defeated"

    SET GainedXP = RandomXPAmount()
    XP = XP + GainedXP

    // --- Level Check ---
    IF XP >= XP_Threshold THEN

        PRINT "Level Up Ready - Press SPACE to evolve"

        WAIT FOR Player Input (SPACE)

        // Increase stats
        Player.Level = Player.Level + 1
        Player.Attack = Player.Attack * 1.25
        Player.MaxHP = IncreaseHPBasedOnLevel(Player.Level)
        Player.HP = Player.MaxHP

        XP_Threshold = IncreaseXPThreshold()

        // Evolution Check
        IF Player.Level == 5 THEN
            PRINT "Bool-Basaur evolved to Struct-a-saur"
            PRINT "Game Won"
            END GAME
        ENDIF

    ENDIF

ENDWHILE

END
```