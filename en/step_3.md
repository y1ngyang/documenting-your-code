## Getting started

Imagine you've created a software masterpiece that will make countless coders' lives a little easier, and you've made it available, but nobody is using it because they don't know how to! Creating documentation is key when you share your code.

In this project, you will be documenting some example code based on our [Deck of cards](https://projects.raspberrypi.org/en/projects/deck-of-cards){:target="_blank"} project. It's not essential for you to have worked through this project, but it would be useful, because it would help you understand what the code you'll document does.

--- task ---

Download the [project code](resources/card.py) called `card.py`.

--- /task ---

--- task ---

Open the downloaded `card.py` program using Python 3 IDLE.

--- /task ---

--- collapse ---

---
title: card.py
---

```python

import random

class Card:

    def __init__(self, suit, number):
        self._suit = suit
        self._number = number

    def __repr__(self):
        return self._number + " of " + self._suit

    @property
    def suit(self):
        return self._suit

    @suit.setter
    def suit(self, suit):
           if suit in ["hearts", "clubs", "diamonds", "spades"]:
               self._suit = suit
           else:
               print("That's not a suit!")

    @property
    def number(self):
        return self._number

    @number.setter
    def number(self, number):
        valid = [str(n) for n in range(2,11)] + ["J", "Q", "K", "A"]
        if number in valid:
            self._number = number
        else:
            print("That's not a valid number")


class Deck:

    def __init__(self):
        self._cards = []
        self.populate()

    def populate(self):
        suits = ["hearts", "clubs", "diamonds", "spades"]
        numbers = [str(n) for n in range(2,11)] + ["J", "Q", "K", "A"]
        self._cards = [ Card(s, n) for s in suits for n in numbers ]

    def shuffle(self):
        random.shuffle(self._cards)

    def deal(self, no_of_cards):
        dealt_cards = []
        for i in range(no_of_cards):
            dealt_card = self._cards.pop(0)
            dealt_cards.append(dealt_card)
        return dealt_cards

    def __repr__(self):
        cards_in_deck = len(self._cards)
        return "Deck of " + str(cards_in_deck) + " cards"
        
deck = Deck()
print(deck)

```

--- /collapse ---

--- task ---

Look over the code. You will see that there are two classes: `Card` and `Deck`. `Card` represents a single playing card, while `Deck` is a collection of `Cards` stacked in order.

At the bottom of the program, a `deck` object is created from `Deck`, and a description is printed to the screen.

--- /task ---

--- task ---

Run the `card.py` program.

You should see a message describing the deck of cards printed to the screen.

![deck of 52 cards](images/deckofcards.png)

--- /task ---
