# Choice and Progression System

## Purpose

The choice and progression system lets player decisions affect later outcomes. It connects quest choices, stored player state, finale outcomes, and unlockable abilities into one progression path.

## User Goal

Players should feel that decisions made during the leveling journey matter later. Choices should produce visible consequences, unlock different outcomes, and support replay or build variation.

## System Goals

- Capture key player choices during the story path.
- Store choice state reliably across sessions.
- Calculate a final outcome based on accumulated choices.
- Unlock ability paths or rewards based on that outcome.
- Present the result through clear UI and quest feedback.
- Avoid exposing confusing or contradictory progression states.

## High-Level Flow

1. Player reaches a choice point.
2. Player selects one of the available paths.
3. A script validates the choice and stores it.
4. The system updates the player's accumulated choice state.
5. Later quest or finale logic reads the stored state.
6. The final outcome is calculated based on prior choices.
7. The player receives outcome-specific story feedback, rewards, or ability unlocks.
8. Future progression uses the stored result to determine available upgrades.

## Data Thinking

A simplified data model could include:

- `player_id`: identifies the player or character.
- `choice_key`: identifies the decision point.
- `choice_value`: stores the selected path.
- `choice_weight`: optional value used to calculate outcome leaning.
- `final_outcome`: stores the resolved ending or path.
- `ability_points`: tracks later progression after the finale.
- `unlocked_abilities`: records selected abilities or build options.

## Design Considerations

- Choice points should be limited enough to stay understandable.
- Outcomes should feel connected to prior actions.
- Ability unlocks should avoid giving every player the same build.
- The UI should explain available choices without overwhelming users.
- Stored state should be clear enough to troubleshoot if a player reports an issue.

## Edge Cases

- Player abandons a quest after making a choice.
- Player repeats a quest flow or attempts to trigger both choices.
- Stored choice state conflicts with current quest state.
- Ability points are earned before the final path is resolved.
- UI state fails to refresh after a choice.

## What This Demonstrates

- Branching progression design.
- Player-state modeling.
- SQL-backed decision tracking.
- Quest, reward, and UI systems working together.
- Product thinking around player agency and replayability.

## Public Sharing Note

This note is sanitized. It explains architecture and design thinking without exposing raw scripts, exact database implementation, server details, or private player data.
