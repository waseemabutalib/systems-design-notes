# Choice Progression Flow

This diagram shows a generalized branching progression system where player choices affect stored state, finale outcomes, and later ability unlocks.

```mermaid
flowchart LR
    A["Quest Choice Point"] --> B["Player Selects Path"]
    B --> C["Store Choice State"]
    C --> D["Accumulated Choice Record"]
    D --> E["Finale Outcome Calculation"]
    E --> F["Outcome-Specific Story Feedback"]
    E --> G["Ability Path Unlock"]
    G --> H["Earn Progression Points"]
    H --> I["Select Limited Abilities"]
    I --> J["Build Variation"]
```

## What This Represents

- Multiple choice points across a longer journey.
- Persistent player-specific state.
- Outcome calculation from accumulated choices.
- Unlockable abilities tied to narrative progression.
- Replayability and build variation.

## Public Sharing Note

This is a sanitized architecture diagram. It does not include raw scripts, real database schema, private player data, or implementation details that could expose live platform internals.
