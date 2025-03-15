Bloodless is a 2-player creature combat trading card game.

## Before A Game
Before starting any games, players must construct a main deck and blood flask deck.

A main deck consists of 50 cards that are not blood flasks nor vestiges. There can't be more than 5 cards with the same name in your deck, unless the cards specify the contrary.

A blood deck consists of 6 cards, 4 of which are regular "Blood Flask". The other two may be any card of Blood Flask type.

## Starting A Game
At the start of a game, both players draw five cards. Both players start with zero blood and 20 points in the health pool.

If a player does not like their starting hand, they can do a mulligan. A mulligan in Bloodless consists of shuffling the hand back into the deck and drawing 5 more cards.

Once both players are satisfied with their hand, they draw one blood flask, and the game starts.

## During A Player's Turn
### The Setup
The Setup phase of a player's turn is where they are allowed to play cards freely. There is also an optional card draw, which is given at the beginning of a player's turn may be performed at any point during the setup phase. Some effects may give the player an additional optional card draw. Optional card draws are consumed when used, or at the end of their setup phase.

An optional card draw allows a player to draw either one card from either their main deck or blood deck.

At any point during this phase, the active player may remove any of their creatures from the board that has zero blood cost if it was played during a previous turn.

At the end of the Setup phase, the Attack phase begins.

Players do not get an optional card draw during their first turn.

### The Attack
The Attack phase is where the active player's creatures attack. Creatures attack from left to right from the perspective of the active player, and if a creature performs multiple attacks simultaneously, they, too, are ordered from left to right.

Any attack on an empty space deals damage to the health pool, and the attacker's controller gains one blood.

An attack on an occupied space deals damage to the creature occupying that space. When a card loses all its health, it dies, and its controller gains one blood. If the card receives more damage than it has health, and the damage received is greater than its health plus its defense, the remaining damage is done to the health pool. This is called Overkill Damage.

At the end of the attack, the turn ends, and the opposing player's turn begins, following the exact same structure.

## Winning A Game
When a player does damage to the health pool and there are less points in it than damage dealt, that player wins the game.

## Playing Cards
To play a card, a player must have an amount of blood equal to or greater than the card's specified blood cost. They lose this amount of blood and the card enters play.

A player may not pay a card's blood cost if the card cannot be played. For example, a player may not choose to give up one blood to play a mosquito if there are no empty spaces on the board.

## Zones
### The Decks
There are two decks for each player. The blood deck and the main deck. When the player is instructed to draw a card, but not from where, the main deck is assumed. The decks are said to be ordered, although, in usual circumstances, their order is unknown.
### The Hand
Each player has a hand, where cards go when they are drawn.

### The Board
The board has six spaces, and four of them belong to each player. They are arranged in a 4x2 grid. A creature that is played is said to be "summoned," while a vestige that enters it is said to be "spawned."

Cards in this zone have state, which is comprised of their current stats as well as any modifications performed to them. This state is lost when they move to a zone where they don't have state.

### The Discard Pile
This is where cards go when they are out of play, not necessarily permanently. Cards entering this zone are said to be discarded.

### The Timeline
The timeline is where commands go when they are played. It is a limited representation of the game's "Abstract Timeline" of events. It serves the purpose of keeping track of the order in which commands happen, in case there are multiple active ones, and previous ones are modifying future ones.

Commands in this zone have state, similar to creatures in the board.

## Card Types
There exist several card types that can go in different zones and have different kinds of abilities.

### Creature
When a Creature is played, it goes on the board. A creature has health, defense, strength and a blood cost. A creature's ability must be Static, and remains active for the time they are on the board.

A creature's "attack" refers specifically to the damage it will deal during the attack phase. Dealing damage at any other time is referred to simply as that: "Dealing Damage"

#### Blood Flask
A Blood Flask is a type of Creature that starts the game in the Blood Deck. When a Blood Flask enters the board, its controller gains one blood.

### Command
When a Command is played, it goes on the timeline. A command has only blood cost. A commands's ability must be an effect.

#### Continuous Command
A Continuous Command is a Command that has a passive ability. They enter the timeline and don't leave it until they are Terminated.

### Vestige
A Vestige is a type which can't exist on its own, and must instead modify another type. For example, there maybe a "Blood Flask Vestige." At the start of the game, no Vestiges are considered to exist. However, they can be created by other cards' abilities.

## Kins
A card may have a Kin. Kins in Bloodless form a parent-child structure. The parent-child structure of kins is shown in [[Kin List]].

## Abilities
There exist two types of abilities: Static abilities, and Eventual abilities.

### Eventual Abilities
Eventual abilities are concrete changes to the state of the game, like drawing a card or giving strength to a creature. Some eventual abilities have defined opposites, like how the opposite of gaining 3 blood is losing 3 blood.

### Passive Abilities
Passive Abilities consist of Events, stretched out or limited under some condition. For example, "whenever a creature enters the board, gain one blood" is a Passive Ability.

Some ways to turn Effects into Passive Abilities will also interact with their defined opposites. For example, the "until" keyword can only be used with static abilities that have defined opposites.

"All creatures gain two health until end of turn" give two health to all creatures, then remove two health at end of turn.

Some of these words can also interact with other passive abilities. Some can *only* interact with passive abilities. For example:

"While this card is on the board, <mark style="background: #FFB86CA6;">you may sacrifice any creature you control at any time during your setup phase</mark>."
"Whenever you draw a Blood Flask, <mark style="background: #FFB86CA6;">once a creature you control dies, draw a card</mark>."

The static ability being modified is highlighted.

## Devouring
Creatures may devour other creatures. When a creature devours another creature, it may not be played unless there is one such creature on the board. In this case, the new creature is played in place of the old one. The old one leaves the board and is discarded.

## Flip Cards
Some cards must begin the game face-down. These cards have a Flip Cost written on them, which is some blood cost to pay or action that must be performed in order to flip the card face-up.

A face-down creature is a 1/1/1 creature with no abilities and no name. Flipping a face-down card counts as the 1/1/1 flip creature ceasing to exist and the face-up card entering the board (but not being played).

## Cumulative Cards
Whenever a second instance of this object is played, it is exiled, and the already-in-play one gains one Cumulative token. This is called "accumulating".

## Syntax
See: [[Syntax]]