---
title: An Example of Iteration of Strictly Dominated Strategies
layout: post
category: Economics
tags: [Game Theory]
---

Suppose we have a game that has two players, Player 1 and Player 2.
Player 1 has two choices, Up \\((U)\\) or Down \\((D)\\), and Player 2
has three choices: Left \\((L)\\), Center \\((C)\\) and Right \\((R)\\).
This game is represented by the normal form
provided below. We are going to attempt to find the set of rationalizable 
strategies using an iterated-dominance procedure.

![normal form of game](/images/game.png)

## Iteration 1

In the normal form above, notice that if Player 2 chooses 
strategy \\(C\\), they will always receive a lower payoff than if
he or she had chosen strategy \\(L\\). We can say that strategy
\\(C\\) is strictly dominated by \\(L\\) because,

$$\begin{align*}
 u_{2}(U, C) = 4 &< u_{2}(U, L) = 5 \\
 u_{2}(D, C) = 3 &< u_{2}(D, L) = 5.   
 \end{align*}$$
 
Therefore, if Player 2 is rational, he or she will never choose strategy C.
We can show the elimination of this strategy by updating
the normal form of this game.

![normal form after first iteration](/images/game1.png)

## Iteration 2

After we have eliminated strategy C for Player 2. Strategy U is strictly
dominated by D for Player 1 since,

$$\begin{align*}
 u_{1}(U, L) = 6 &< u_{1}(D, L) = 8 \\
 u_{1}(U, R) = 7 &< u_{1}(D, R) = 9.   
\end{align*}$$

So if Player 1 knows that Player 2 is rational, then Player 1 knows
that Player 2 will never choose strategy \\(C\\). Therefore, if Player 1 
is rational, he or she will never choose strategy U\\). 
The normal form for this game now shows that strategies \\(U\\) and \\(C\\) 
have been eliminated.

![normal form after second iteration](/images/game2.png)


## Iteration 3

Once we have eliminated strategy \\(U\\) for Player 1, strategy \\(L\\) is
strictly dominated by strategy \\(R\\) for Player 2 because

$$ u_{2}(D, L) = 5 < u_{2}(D, R) = 6. $$

So if Player 2 knows that Player 1 knows Player 2 is rational, then
Player 2 knows that Player 1 knows Player 2 will never choose strategy
\\(C\\). And if Player 2 knows that Player 1 is rational, then
Player 2 knows that Player 1 will never choose strategy \\(U\\). Therefore,
if Player 2 is rational, he or she will never choose strategy \\(L\\).

The set of rationalizable strategy profiles is 
$$R = \{D \times R\}$$. 

This also represents the equilibrium of this game. The normal form below
shows all eliminated strategies, and the equilibrium
is circled.

![normal form after third iteration](/images/game3.png)
