---
layout: post
comments: true
name: playability
title: Playability in Polish Scrabble
---

Strategy plays a prominent role in Scrabble. However, after playing for a while, you realise that only knowing more words can improve your results. When I used to play regularly, I was wondering how to optimise word-learning. Some people simply read the OSPS (Official Dictionary of Polish Scrabble Players), but I don't know anyone who was persistent enough to go through all of the words. It seems you have to know most of the dictionary if you aspire to win major English tournaments, but the level in Polish Scrabble is, understandably, slightly lower. Others learn the most probable bingos, such as OCEANIT/OCTANIE, IZATYNO, AZTECKI, RILSANY etc. — it is quite easy to generate such lists. But the intuition suggests it is still not the optimal way: many of the words on the list will have a letter order that does not fit on a typical board or they won't give us enough advantage to justify the amount of time spent learning them.

### Playability

An American Scrabble player, John O'Laughlin, published his [playability list](http://pages.cs.wisc.edu/~o-laughl/collins/) in 2007. In order to generate it, you need a self-playing program that can generate millions of games. At the moment (February 2015), [Elise](http://www.codehappy.net/elise/) is the best Scrabble AI. Unfortunately, it can't be currently adapted to play with the Polish dictionary. We are left with good old [Quackle](http://people.csail.mit.edu/jasonkb/quackle/), which allows us to play in Polish since recently. I didn't find the exact algorithm that olaugh used to generate his list, so I based my procedure on various hints scattered around the Internet. The main rule is **the playability of a word is the number of points that we wouldn't have scored in a move, hadn't we known this word, but only the next best one**.

First we need to generate the best moves. Quackle is very efficient at this and it takes him a split of a second.


    Speedy Player B: Turn 1
       A B C D E F G H I J K L M N O      Speedy Player A          ĆŁNÓPŚY 74  
      ------------------------------  -> Speedy Player B          EEIKRSY   0   
     1|=     '       =       '     =| --Static Player's choices (your play: 1)-----
     2|  -       "       "       -  | best *H7 S(I)EKIERY 61 
     3|    -       '   '       -    | best  H4 SIEK(I)ERY 61 
     4|'     -       '       -     '|  25.2 E5 ESK(A)ERY  36 I
     5|        -           -        |  39.9 C7 K(A)ISERY  24 E
     6|  "       "       "       "  |  40.0 C7 K(A)RESIE  22 Y
     7|    '       '   '       '    |  41.6 D8 (G)RYSIE   18 EK
     8|=   A G A D z I E     '     =|  41.6 D8 (G)ISERY   18 EK
     9|    '       '   '       '    |  43.0 D8 (G)IEREK   18 SY
    10|  "       "       "       "  |  44.0 D8 (G)RESY    16 EIK
    11|        -           -        |  44.9 D8 (G)REKI    16 ESY
    12|'     -       '       -     '| --Tracking-----------------------------------
    13|    -       '   '       -    | ?AAAAAAAĄBBCCCĆDDEEEEĘFGHHIIIIIIJJKKLLLŁŁMMM
    14|  -       "       "       -  | NNNNNŃOOOOOOÓPPPRRRSSSŚTTTUUWWWWYYYZZZZZŹŻ  86
    15|=     '       =       '     =|
      ------------------------------


We note the best word and its value and go down the list. Between the two different positions of `SIEKIERY` (H7 and H4) there is no difference in points. The next move, `ESK(A)ERY`, is worth less, so we note the difference. To be exact, we note the **equity**, not the value. The equity is the combined score for the move and the leave (the letters that stay on our rack), which I will explain elsewhere. In this case we assign 25.2 points to `SIEKIERY` and continue the game.


    Speedy Player A: Turn 4
       A B C D E F G H I J K L M N O   -> Speedy Player A          BFLPRSY   132 
       ------------------------------     Speedy Player B          ?ACGLTW   114 
     1|=     '       W       '     =| --Static Player's choices (your play: 1)-----
     2|  -       "   A   "       -  | best *B2  FL(O)PY  32 BRS
     3|    -       ' Z '       -    |  2.51 12G B(E)LFRY 28 PS
     4|B O T K I     K       -     '|  2.51 11G F(I)BRYL 28 PS
     5|        N A P A Ś Ć -        |  3.00 B2  FL(O)RY  30 BPS
     6|  "       " Ł     "       "  |  4.36 B2  SF(O)RY  28 BLP
     7|    '       Ó S '       '    |  6.96 11G F(I)BRY  24 LPS
     8|=   A G A D z I E     '     =|  6.96 E7  F(A)RBY  24 LPS
     9|    '       ' E '       '    |  7.02 B2  SP(O)RY  22 BFL
    10|  "       "   K   "       "  |  7.02 B2  PS(O)RY  22 BFL
    11|        -     I     -        |  7.03 2G  B(A)SF   20 LPRY
    12|'     -       E       -     '| --Tracking-----------------------------------
    13|    -       ' R '       -    | ?AAAAĄCCCDDEEEEĘGHHIIIIIJJLLŁMMMNNNNŃOOOOOPR
    14|  -       "   Y   "       -  | RSSTTUUWWWYYZZZZŹŻ  62
    15|=     '       =       '     =|
       ------------------------------

Here knowing `FLOPY` is not as advantageous, because the next best move (`BELFRY`) is only 2.51 points worse (actually 4 points, but it is better to leave `PS` on the rack than `BRS`). 

Yet another case:


    Speedy Player B: Turn 11
       A B C D E F G H I J K L M N O      Speedy Player A          AEIŁNSZ  380 
       ------------------------------  -> Speedy Player B          ?AKNNOO   286 
     1|=     '       =       F O T O| --Static Player's choices (your play: 1)-----
     2|  -       "       " C I   R  | best *A2 pOKONAN(A) 80 
     3|    -       '   S K U L N Y M| best  A2 dOKONAN(A) 80 
     4|'     -       ' P   M I   B E|  3.00 A2 KANONOw(A) 77 
     5|        -       I   O J   A S|  10.0 C2 pOKONAN(Y) 70 
     6|  "       T R Z E J       C  |  10.0 C2 dOKONAN(Y) 70 
     7|    '       '   Ś       ' H I|  10.0 C2 KsOANON(Y) 70 
     8|=     '   G Z I Ć     '     G|  10.0 C2 KANONOw(Y) 70 
     9|A R Y       A   '       '   Ł|  11.0 L7 NAKOp(A)NO 69 
    10|  Ó   B U Ź C E   "       W Y|  12.0 L7 KANON(A)dO 68 
    11|  D Ż E T   H       -     E  |  78.8 8A KuNO       35 ANO
    12|'     -     L ' K   P A M P Ę| --Tracking-----------------------------------
    13|    z E Z N A W A Ń     A R  | AEIŁNSZ  7
    14|  -       " L   D "     S Ą  |
    15|=   W Y D Z I W I     ' O   =|
       ------------------------------

Here, only `POKONANA` and `DOKONANA` will be included in our ranking as the best moves from this rack, but their _playability_ is 78.8, which is the difference between them and **the next move from the list that requires playing different letters from the rack**. It would be unfair if we assigned them only 3 points only because there are more bingos from this rack. The current solution is not ideal, but at the moment I don't have a better idea how to deal with this.

I generated 90 million games and analysed them for playability. The list is available [here](../downloads/playability-pl.txt). The number beside is the sum of points that we would have gained from knowing a word in all the simulated games. The dominance of short words with Ź, Ń and Ś (worth 9, 7 and 5 respectively) is not a surprise, since playing such a letter on a triple letter tile is often better than playing any other word from the rack. Quite obvious but still good to have verified: OFF, PFF and UFF are virtually useless.

I encourage you to analyse the list and draw interesting conclusions, but also to criticise my methodology — I am willing to create a better ranking if I know how to. A slightly modified Quackle source code that I used to generate the list is on my [github](https://github.com/alkamid/quackle/blob/master/test/testharness.cpp). In the future I'd like to make a "hookability list", check how many simulations we need to reach convergence (it seems that 90M is excessive), compress the above list to lemmas (something English players don't have to worry about), find interesting patterns hidden in the list, and so on. If you are interested, I have 20GB of raw data — you can, for example, look at playability depending on the phase of the game.