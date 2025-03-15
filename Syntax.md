This document does not define a bloodless parser, nor fully determines the syntax and grammar for a bloodless card. It merely stands as a guideline for rules that one such parser would need to uphold.

The objective of defining a bloodless syntax is to ensure that every effect is perfectly and unambiguously derivable from the text in the cards.

Special cases (e.g. entire sentences without internal structure) are discouraged, but allowed.

Syntax sugar is allowed and welcome wherever it makes an effect easier to read.

## Numbers
### Integers
Any integer.

### Letters
Any letter from the Latin or Greek alphabets.

### Bound Variable References
These are valid stand-ins for a number, and refer to a previously bound number. Each of these words restricts the possible referent.
`amount`
`quantity`
`number`

## Card Identities
### Type
`creature | command | continuous command | [type] vestige`

### Controller
`[player]'s [rooted card identity]`

### Keywords
`[card identity] with [keyword]`
`[card identity] without [keyword]`
`[card identity] with [num]x [cumulative keyword]`
`[keyword] [card identity]`

### Stats
`[card identity] with [num stat] [comparison] [num]`

### Text
`[card identity] with text containing "[raw text]"`
`[card identity] with text containing "[raw text]"`

### Kin
`[kin] kin [card identity]`
e.g. "Insect kin creature with Bifurcated Strike"

`[card identity] of [kin] kin`

`[card identity] not of [kin] kin`

## Players
`you`
`this [card identity]'s controller`
The controller of the card that the text is on.

`your opponent`
`the opposing player
The card's controller's opponent.

### Or
`[card identity] or [card identity]`

## Targets
### Chosen Target
`target [card identity]`
`target player`

### Card
`a [card identity]`
`some [card identity]`
`this [card identity]`
`that [card identity]`
`all [card identity]`
`[num] [card identity]`

## Zones
### Decks
`[player]'s deck`
`[player]'s main deck`
A player's main deck.

`[player]'s blood deck
A player's blood deck.

### Hands
`[player]'s hand`
A player's hand.

### Discard Pile
`[player]'s discard pile`
`[player]'s graveyard`
A player's discard pile.

## Effects
### Drawing Cards
`[target player] draws a card (from [deck])?`
Specified player draws a card from the specified deck, or main deck if none is specified.

`[target target player] draws [num] cards (from [deck])?`
Specified player draws a number of cards from the specified deck, or main deck if none is specified.

`draw a card (from [deck])?`
Card's controller draws a card from the specified deck, or main deck if none is specified.

`draw [num] cards (from [deck])?`
Card's controller draws a number of cards from the specified deck, or main deck if none is specified.

### Gaining Keywords
`[target object] gains [keyword]`
Gives a keyword to a target. Opposite of losing the keyword.

`[target object] gains [num]x [keyword]`
Only works if the keyword can accumulate. Gives multiple instances of a keyword. Opposite of losing the keyword that many times.

### Losing Keywords
`[target object] loses [keyword]` 
Target loses keyword. Opposite to gaining the keyword.

`[target object] loses [num]x [keyword]`
Target loses keyword multiple times. Opposite to gaining the keyword.

`[target object] loses all [keyword]`
Target loses all of the given keyword. Opposite to regaining the lost keywords.

`[target object] loses all keywords`
Target loses all keywords. Opposite to regaining the lost keywords.

### Gaining Blood
`[target player] gains [num] blood`
`[target player] gains +[num] blood`
e.g. "Opposing player gains +4 blood."

Gives a specified number of blood to the specified player.

`gain [num] blood`
`gain +[num] blood`
e.g. "Opposing player gains +4 blood."

Gives a specified number of blood to the card's controller.

### Losing Blood
`[target player] loses [num] blood`
e.g. "Opposing player loses +4 blood."

Removes a specified number of blood from the specified player.

`lose [num] blood`
e.g. "Opposing player loses +4 blood."

Removes a specified number of blood from the card's controller.

### Playing Cards
`play [target card] for free`
`play [target card] for [num] blood`
`[target player] plays [target card] for free`
`[target player] plays [target card] for [num] blood`

#### Damaging
`[target] damages [target]`
e.g. "A creature you control damages its opposing space"
`[target] deal damage`
e.g. "All creatures deal damage"

#### Sacrificing
`[target player] sacrifices [target creature controlled by player]`
`sacrifice [target creature controlled by you]`
`[target creature controlled by you] is sacrificed`

#### Destroying
`[target player] destroys [target creature]`
`destroy [target creature]`
`[target creature] is destroyed`

#### Terminating
`terminate [target command]`
`terminate`
`[target command] is terminated`

#### Accumulating
`[target in play with 'accumulating'] accumulates`
`[target in play with 'accumulating'] disaccumulates
`accumulate`
`disaccumulate`

#### Counters
`[target] gains a [counter name] counter`
`[target] lose a [counter name] counter`
`[target] gain [num] [counter name] counters`
`[target] lose [num] [counter name] counters`

### Changing Attack
`[target object] attacks [target space]`
e.g. "This creature attacks the spaces adjacent to the opposing space"

#### Stats
TODO

## Repetitions
### For Each
`for each [target], [event]`
Repeat event every time. Binds "that X" during the iteration.

`for each blood [player] has, [event]`


## Passivifiers
Ways to turn effects into static ones.

### When
`when [moment|situation], [effect]`
`[eventual effect] when [moment|situation]`

`once [moment|situation], [effect]`
`[eventual effect] once [moment|situation]`
Waits until something happens, causes an effect, then terminates.

### Until
`until [moment|situation], [effect]`
`[static effect] until [moment|situation]`
Executes an effect, waits until something happens, then executes the opposite effect, then terminates.

### While
`while [moment|situation], [static effect]`
A static effect happens until the specified something happens, then terminates.

### Whenever
`whenever [moment|situation], [effect]`
An effect happens whenever another event happens.

`whenever [eventive effect], [effect] instead`
`whenever [eventive effect], instead [effect]`
An effect overrides every instance of another effect.

## Allowances
Any action with a `may` as an auxiliary is an Allowance. These cannot exist on their own, but need a specified time.

`[allowance] at any time`
Before and after any other event, the event has a chance to happen.

`[allowance] at any time during [phase/turn]`
`[allowance] after [phase/turn]`
`[allowance] before [phase/turn]`
`[allowance] after [event]`
`[allowance] before [event]`


## Resolution Of Bindings
### Personal Pronouns
| Pronoun | Binding |
| - | - |
| you | The card's controller |
| he, she | Referrent matching gender and number |
| they | Animate singular referrent or plural referrent |
| it | Inanimate singular referrent |

### Demonstratives
| Pronoun | Binding |
| - | - |
| this X | The card the text is on. It is presupposed that X matches the card, otherwise the rule is invalid |
| that X | Referrent that matches X and is singular |
| those X | Referrent that matches X and is plural |
| the X | Referrent that matches X. If X is plural, treat constituents of plural referrents as singular |
| one of those X | Singular member of referrent that matches X and is plural |
| some of those X | Referrents of the controller's choice that match X and is plural |

### Other Restrictions
Demonstrative pronouns are also bound by the predicate they are found in. If a referrent cannot satisfy the relation specified by the predicate, then another referrent is searched for.

Some predicates (like "searching" or "drawing") are failable, and "if X fails" adds a restriction upon X's binding.
