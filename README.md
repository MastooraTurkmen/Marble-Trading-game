# Marble-Trading-Game

A simple marble trading project made by Python 

***Console log***

using indexedDB for stdlib modules cache

> You start the game with 1000 gold pieces
> 
> purse: 3000, last result: (black): 2000
> 
> purse: 3200, last result: (green): 200
> 
> purse: 3000, last result: (red): -200
> 
> starting/ ending purse: 1000 / 3000
> 
> gain/loss: 200.0 %

------



## Cods has been used

```py

import random
#create a bag with 10 marbles
bag = ('green','green','green','green','green','black','red','red','red','white')
#starting amount of money
start_purse = 1000
# current money amount
purse = start_purse
#result of last round
result = 0
#how many rounds
rounds = 3
#last marble
marble = 'none'
# welcome user to game
print(f'You start the game with {start_purse} gold pieces')
# loop drawing marbles
for draw in range(1,rounds+1):
    #how much was bet
    bet = int(input(f'Current Purse: {purse} Last draw: {marble} \nRound {draw} - How much do you want to bet?: '))
    #draw marble
    marble = random.choice(bag)
    # win or loss
    if marble == 'green':
        result = bet
    elif marble == 'black':
        result = 10 * bet
    elif marble == 'white':
        result = -5 * bet
    else:
        result = -bet
    #calc win or loss/ result and new amount/purse
    purse += result
    #lose game if lose half of money
    if purse < 0.5 * start_purse:
        print(f'Game over! You lost to much gold!!!')
        break
    #print results
    print(f'purse: {purse}, last result: ({marble}): {result}')
    print('')
# print final results
print('starting/ ending purse: ', start_purse, '/',purse)
print('gain/loss: ', ((purse-start_purse)/start_purse *100),'%')

```
