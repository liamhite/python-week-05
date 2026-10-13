import random

def createDeck():

   suit = ['C', 'S', 'D', 'H']
   value = ["A", '2', '3', '4', '5', '6', '7', '8', '9', '10', 'J', 'Q', 'K']
   deck = []

   for number in value:
     for item in suit:
      card = number + item
      deck.append(card)

   return deck


def shuffleDeck(deck):
   hopper1 = []
   hopper2 = []
   hopper3 = []
   shuffledDeck = []

   for card in deck:
     num = random.randint(1, 3)
     if num == 1:
       hopper1.append(card)
     elif num == 2:
       hopper2.append(card) 
     else :
       hopper3.append(card)

   shuffledDeck.extend(hopper1)
   shuffledDeck.extend(hopper2)
   shuffledDeck.extend(hopper3)
      
   return shuffledDeck


def promptUser(deckCount):
     try:
       yesNo = input("Would you like to draw cards? (y/n) ")
       if yesNo.lower() == "y":
          numOfCards = int(input("How many cards? "))
          if numOfCards > deckCount:
             print(f"Unable to draw {numOfCards} cards. Deck only has {deckCount} cards")
             # recursion  :)
             return promptUser(deckCount)
          else:
             return numOfCards
       else:
          return 0
     except ValueError:
      print("You did not enter a valid number. Your Done")
      return 0


def drawCards(numOfCards, deck, hand):
    newCards = []
    for i in range(numOfCards):
      pop = (deck.pop(0))
      newCards.append(pop)
     
    hand.extend(newCards)  

    return deck, newCards, hand



# MAIN CODE

cardDeck = createDeck()
cardDeck = shuffleDeck(shuffleDeck(shuffleDeck(shuffleDeck(cardDeck))))

yourHand = []
count = len(cardDeck)

while count > 0:
        numOfCards = promptUser(count)
        newCards = []
        cardDeck, newCards, yourHand = drawCards(numOfCards, cardDeck, yourHand)    

        count = len(cardDeck)
        

        print(f"New cards {newCards}")  
        print(f"Your hand {yourHand}")
        print(f"Cards left {count}")
        print("")

        if numOfCards == 0:
           break

print("Don't forget to tip the dealer!")