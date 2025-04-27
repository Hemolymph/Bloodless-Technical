Bloodless' runtime is based on Events.

## Definitions
**Ability**: Text on a card describing what the card does.

**Event**: Thing that happens in the game

**Triggered Ability**: Ability that modifies events

**Active Ability**: An ability that requires a cost.

**Effect**: Set of instructions that can create events

## The State
The state of the game contains:
- Player states
- Health pool value
- Event modifiers
- Effect queue
- Event history
- Current turn

## Events
Events are an intent to modify the game. They have unique identities.

Inside events, indefinite references are bound through unique identifiers stored in the event handler. The unique identity is assigned even before an object to be identified has been designated.

This means that future effects can alter things that are only known after the result of previous ones. It's also means that an effect fails if the binding is not set.

It is possible for a reference to be based on yet another reference, such as "you" from a card.

### Effect Requests
An effect request occurs before any effect. Effect requests exist so that effects may be denied by "do not" effects.

The only internal structure of an effect request is the requested effect.

For example:

- `Whenever you play a creature, draw a card` will create an effect request of drawing a card.

- `Whenever you draw a card, you do not` will see that request and make it result in nothing. Because of this, no card is drawn.

### Payment Request
A player can attempt to pay for a cost. The inner structure of a payment request is:
- The identity of the target cost
- An array of player choice requests.

## The Event Handler
The event handler performs this cycle every time an event is pushed.

- Organize event modifications.
- Pop first event in the event queue and modify it.
- Run modified events.
- Perform win check.
