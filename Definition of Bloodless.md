Bloodless is a Nondeterministic State Machine.

## Types

| Type | Meaning              |
| ---- | -------------------- |
| b    | Bloodless state      |
| nat  | Natural number       |
| side | Player side          |
| ps   | Player State         |
| m    | Effect modifications |
| s    | Effect state         |
| c    | Specific card object |
| p    | Player               |
| num  | A bloodless number   |

## The State
The Bloodless state is an object of type `b` containing two player states and a health count as a natural number.

```haskell
health :: b -> nat
-- Health remaining
player :: b -> side -> ps
-- State of the player on the specified site
timeline :: b -> [f]
-- The timeline
```

### Player State
An object of type `ps` representing a player's state.

```haskell
health :: ps -> nat
blood :: ps -> nat
hand :: ps -> [Card]
deck :: ps -> [Card]
discard :: ps -> [Card]
```

## Effects
See: [[Effects and Modifications]]

## Syntax
See: [[Syntax]]