## Minimax

Algorithm for predicting the **best next move to make**, assuming the **opponent plays optimally**.
Basically it **looks at all possible outcomes** (with set tree depth) and recursively assignes scores from bottom to top, considering also the opponent's moves.

The algorithm is called minimax because the player (**maximizer**) choses the move that maximizes its score, and the opponent (**minimizer**) chooses the move that minimizes the player's score.

> [!example]
> In this setting, white is the player, black is the opponent. We try to assign a score to each state with a formula that measures "performance" for the white player.
> ![](../z_images/Pasted%20image%2020240603124424.png)
> 
> -1 and 3 are the scores of the leaf states. We now try to assign the best possible score for the white player, which is 3.
> 
> ![](../z_images/Pasted%20image%2020240603124722.png)
> 
> We do this for the other nodes, and now it is black's turn to make a move.
> ![](../z_images/Pasted%20image%2020240603124808.png)
> 
> Black will chose the move that has the lower score for white, so we will assign the lowest score to the black move.
> 
> ![](../z_images/Pasted%20image%2020240603124908.png)
> 
> ![](../z_images/Pasted%20image%2020240603124325.png)
