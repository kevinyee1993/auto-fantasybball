Can select and click button with:
document.getElementById("{ whatever buttonname }").click()

the buttons inside have names like
pncButtonMove_1006
where the numbers don't increment predictably down the grid

all buttons are contained within a slot called pncEditSlot_0
where the number represents which slot it is
0 is pg
1 is sg
2 is sf
3 is pf
4 is c
5 is G/F
6 is G/F
7 is F/C
8 is F/C

9, 10, 11, and 12 are bench
13 is IR

These numbers can be different depending on the league

can try to select buttons using the pncEditSlot
pncButtonMove

//USE THIS and change pncEditSlot number to get different button
```
document.getElementById("pncEditSlot_0").getElementsByClassName("pncButtonMove")[0].click()
```

After clicking MOVE button, new HERE buttons come up that need to be clicked

//USE THIS to select the position that you want to move the selected player to, change
the number for different positions

```
document.getElementById("pncButtonHere_0").click()
```

the only problem with this is that instead of swapping the players, the person that gets
replaced on the here slot moves to the bench

if you save the buttons as variables before you click them
e.g.
```
let a = document.getElementById("pncEditSlot_0").getElementsByClassName("pncButtonMove")[0]
```

then do
```
a.click()
```
, that player gets clicked even if the player was moved before

so when making a swap, can store 2 players as variables and then swap them eventually
actually wait players don't necessarily have to swap, but this is a good thing to keep in mind

ALSO, players already playing aka 0-8 don't ever need to change out, only people from the bench need to change into the active roster

//After doing all the moves successfully, make sure to call
```
document.getElementById("pncSaveRoster1").click()
```
to save the roster


side note, when choosing between two players for one spot, use the one with the higher own percentage
