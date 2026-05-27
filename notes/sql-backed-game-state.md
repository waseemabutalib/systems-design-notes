# SQL-Backed Game State

## Purpose

SQL-backed records support persistent content and player state. In a multiplayer platform, the system needs to remember what exists in the world, what players have done, what they own, and what progression they have unlocked.

## What SQL Supports

- Quest and objective state.
- Items, loot tables, and rewards.
- Creature and NPC configuration.
- Achievement progress.
- Player choices and story outcomes.
- Ability unlocks and progression points.
- Content configuration that needs to persist across sessions.

## Example Interaction Flow

1. Player performs a gameplay action.
2. A script receives or detects the event.
3. The script validates whether the action should affect stored state.
4. The system reads existing state from the database.
5. The system updates the relevant record.
6. The UI or player feedback layer communicates the result.
7. Future interactions can use the stored state.

## Data Modeling Thinking

The core design principle is to separate definitions from player-specific progress.

Example categories:

- Definition records: what achievements, items, quests, abilities, or rewards exist.
- Player state records: what this specific player has completed, unlocked, chosen, or earned.
- Event/config records: seasonal rules, reward availability, or system settings.

This separation makes systems easier to extend. New achievements or abilities can be added without rewriting every player's existing progress.

## Interview-Friendly Summary

Most of my SQL experience comes from building and maintaining systems for an independent multiplayer RPG platform. I used SQL-backed records to manage game content and player state, including quests, items, creatures, loot tables, achievements, player choices, and progression systems. Lua scripts read and wrote player progress, determined outcomes, and triggered UI feedback. I also apply similar data-structure thinking in digital archive work, where metadata models need to support search, browsing, and long-term content expansion.

## What This Demonstrates

- Practical database-backed system design.
- Player state and content modeling.
- Connecting scripting logic to persistent records.
- Thinking in definitions, state, outcomes, and feedback loops.
- Transferable data modeling for implementation and platform roles.

## Public Sharing Note

This note uses generalized examples and does not expose raw schemas, database dumps, real IDs, credentials, admin queries, or player data.
