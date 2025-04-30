Bloodless' runtime is based on Events.

## Definitions
**Text**: Text on a card describing what the card does, when it does it and how it interacts with other things.

**Event**: An imaginary object that represents the a change in the state of the game.

**Executing an Event:** To perform the changes represented by the event.

**Triggered Ability / TA**: Ability that reacts to events, often resulting in the creation of another one.

**Event Modifying Triggered Ability / EMTA:** An ability that reacts to events, modifying them without creating another. They have higher precedence than regular TAs.

**Event Creating Triggered Ability / EMTA:** An ability that reacts to events, creating events. They have low precedence.

## The State
The state of the game contains:
- Player states
- Health pool value
- Event modifiers
- Effect queue
- Event history
- Current phase

### The Initial State
The initial state consists of the following:
- The two player states, with the decks they've brought to the game, empty discard piles and empty hands.
- The two 

## Triggered Abilities
Events are an intent to modify the game. They have unique identities and may contain internal structure.

Triggered abilities are objects that represent a reaction to events. They also contain information about the origin of the event. Different types of abilities have a level of precedence.

When events are queued, the first one is popped from the queue and begins to be modified.

First, relevant EMTAs are triggered, modifying the event and possibly denying its execution and further modification.

Second, the event is executed.

Finally, Triggered Abilities are run on it, possibly creating new events.

### Event Matching
Events can be matched for certain patterns. For example, considering that a Draw effect contains the player that draws and the deck that is drawn from, a Draw match contains information about which players count as a match, which decks count as a match, and which are excluded. This information is called an Event Pattern.
An ability's trigger is an event pattern.

### Reactions and Binding
When a TA is successfuly matched, the reaction may depend on objects that only come into relevance after the event is executed. However, the reaction is defined *before* any triggering happens. Consider the following example:

You play a creature with the following text: `Whenever you draw a card, play it.` At this time, there is no relevant card draw - the reaction doesn't know what will be played, but the trigger is capable of supplying that information the moment it happens. This happens through a process called **binding**.

When a TA is triggered, it binds all objects found by the event pattern. The objects are bound to a pattern of their own, which, for the previous example, would contain the fact that the object has been drawn, but it would also contain the fact that the object can be played and is a card.

These bindings are passed down to the reaction. The reaction searches through the bindings, looking for the latest "playable" match.

### A Complete Overview
With this, the complete life of an event is the following:

- Events are queued.
- An event is popped.
- EMTAs are run on it.
  - The EMTAs' triggers check for a match in the event. The ones that match it, modify it.
- The resulting event is executed.
- ECTAs are run on it.
  - The ECTAs' triggers check for a match in the event. The ones that match it:
    - Bind any relevant object matches
    - Provide the object matches to the reaction
    - The reaction is pushed to the front of the event queue if all the objects it needs are present in the list of bindings.
