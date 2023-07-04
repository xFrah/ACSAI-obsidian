---
alias: Random forest, Random forests, Decision tree
---

## How to build a tree

-   Resort to a **greedy heuristic**:
    1.  Start from an empty decision tree
	    
    2.  **[Greedy Step]** Choose:
	    A) a dimension among axes 
	    B) **BEST** splitting value that minimize the Impurity function on the chosen axes
	    When Impurity is Entropy we **minimize the entropy** also known as **maximizing the [Information Gain](Information%20Gain.md).**
	    
    3.  Once A) and B) are chosen save them as "parameters" of the model
	    
    4.  Apply **recursion to the ramifications**.


-   **Termination**:
    1.  if no examples – return **majority** from parent (Voting such as in k-NN).
	    
    2.  else if all examples in same class – return the class **(pure node)**.
	    
    3.  else we are not in a termination node (keep recursing)
	    
    4.  **[Optional]** we could also terminate for some **regularization** parameters


> [!example] Exercise
> 
> | Person ID (training example) | Overcooked pasta? | Waiting Time | Rude Waiter? | Satisfied y | 
> |--- |--- |--- |--- |--- | 
> | $x_1$ | Yes | Long | No | 1 (yes) | 
> | $x_2$ | No | Short | Yes | 1 (yes) | 
> | $x_3$ | Yes | Long | Yes | 0 (no) | 
> | $x_4$ | No | Long | Yes | 1 (yes) |
> | $x_5$ | Yes | Short | Yes | 0 (no) |
> 
> 1. Using the training data, construct **a decision tree** for the **binary classification** of customers into ‘Satisfied (1)’ or ‘Unsatisfied (0)’. 
> 2. Use the **[Information Gain](Information%20Gain.md) (IG)** as the decision criterion to select which attribute to split on. Show your calculations for the IG for all possible attributes for every split.
> 
> 
> ### How to approach this
> 
> 
> ##### First, Analysis:
> 
> - The features $x$ are **categorical variables** in 3 dimensions.
>     -   Feature 1 is *{Yes, No}*
>     -   Feature 2 is *{Long, Short}*
>     -   Feature 3 is *{Yes, No}*
>     
> - the target $y$ is **binary categorical variable** *{Satisfied (yes), UnSatisfied (no)}*
> 
> 
> ##### What is the Entropy of the $y$ with **no split taken**?
> 
> **Over 5 samples** we have **3 yes and 2 no**, so:
> $$\large H(S)= -\frac{3}{5}\log_2(\frac{3}{5})-\frac{2}{5}\log_2(\frac{2}{5}) \approx 0.971$$
> 
> 
> ##### Bruteforce all possible splits
> 
> Now we have to just "brute force" all the possible splits (3) as if we took the split and compute the weighted entropy after.
> 
> > [!note]
> > We compute the entropy of a split as:
> > 
> > $$\large \text{weight} \cdot H(y~|~\texttt{Splitted x value})$$
> > 
> > Where:
> > - $\text{weight} = \Large\frac{|\text{samples in the split}|}{|\text{Samples in the parent}|}$
> > - Splitted x is one of the two possible values that the attribute we split can now take.
> 
> 
> Split on **Overcooked pasta** and compute the new Entropy. We have two cases:
> 
> -   A) $\texttt{Ov. pasta==Yes}$ 
> 	I have 3 samples over the "parent" 5 so i have to weight this as $\frac{3}{5}$:
> 	
> 	$\large\frac{3}{5}H(y~|~\texttt{Ov. pasta==Yes}) = -\sum_{y \in \{yes,no\}} p(y|x)\log_2(p(y|x))$
> 	
> 	we have **2 No Satisfaction and 1 Yes,Satisfaction , over 3 samples after chosing**:
> 	
> 	$\large\frac{3}{5}H(y~|~\texttt{Ov. pasta==Yes}) =\frac{3}{5}\cdot \big[ \underbracket{-\frac{1}{3}\log_2(\frac{1}{3})}_{yes}-\underbracket{\frac{2}{3}\log_2(\frac{2}{3})}_{no}\big] \approx 0.551$
> 	
> 	![](../z_images/Pasted%20image%2020230519113628.png)
> 	
> -   B) $\texttt{Ov. pasta==No}$ 
> 	I have 2 samples over the "parent" 5 so i have to weight this as $\frac{2}{5}$
> 	
> 	$\large\frac{2}{5}H(y~|~\texttt{Ov. pasta==No}) = -\sum_{y \in \{yes,no\}} p(y|x)\log_2(p(y|x))$
> 	
> 	we have **0 UnSatisfaction and 2 Yes, Satisfaction , over 2 samples after chosing**:
> 	
> 	$\large\frac{2}{5}H(y~|~\texttt{Ov. pasta==No}) =\frac{2}{5}\cdot \big[ -\frac{0}{2}\log_2(\frac{0}{2})-\frac{2}{2}\log_2(\frac{2}{2}) \big] = 0$
> 	
> 	![](../z_images/Pasted%20image%2020230519113651.png)
> 
> 
> [Information Gain](Information%20Gain.md) for split on $\texttt{Overcooked pasta}$:
> $$IG(Y~|~\texttt{Ov. pasta}) \doteq \frac{5}{5}H(S) - \Big[ \frac{2}{5}H(y~|~\texttt{Ov. pasta==No}) + \frac{3}{5}H(y~|~\texttt{Ov. pasta==Yes}) \Big]$$
> 
> 
> ### So now we are here:
> 
> ##### Split Over. Cooked pasta == Yes
> 
> | Person ID (training example) | ~~[Feat. 1] Overcooked pasta?~~ | [Feat. 2] Waiting Time | [Feat. 3] Rude Waiter? | Satisfied y� | 
> |--- |--- |--- |--- |--- | 
> | $x_1$ | ~~Yes~~ | Long | No | 1 (yes) | 
> | $x_3$ | ~~Yes~~ | Long | Yes | 0 (no) | 
> | $x_5$ | ~~Yes~~ | Short | Yes | 0 (no) |
> 
> ##### Split Over. Cooked pasta == No
> 
> | Person ID (training example) | ~~[Feat. 1] Overcooked pasta?~~ | [Feat. 2] Waiting Time | [Feat. 3] Rude Waiter? | Satisfied y� | 
> |--- |--- |--- |--- |--- | 
> | $x_2$ | ~~No~~ | Short | Yes | 1 (yes) | 
> | $x_4$ | ~~No~~ | Long | Yes | 1 (yes) |
> 
> 
> ### And the tree is:
> 
> ![](../z_images/Pasted%20image%2020230518181627.png)
> 
> 
> ### We are done only for 1/3 of the features.
> 
> Now we have to keep repeating this for the other 2 features and then split on the feature with the maximum IG.
> 
> | Split Feature | IG | 
> |--- |--- | 
> | Overcooked Pasta | 0.42 | 
> | Waiting Time | ? | 
> | Rude Waiter | ? |
> 
> 
> ### Fast forward
> 
> | Split Feature | IG | 
> |--- |--- | 
> | **Overcooked Pasta** | **0.42** | 
> | Waiting Time | 0.020 | 
> | Rude Waiter | 0.171 |
> 
> So we split on `Overcooked Pasta over Yes` with a gain of 0.42
> 
> -   Note that `Overcooked Pasta` is a binary variabile so splitting over Yes or Not does not matter.
> -   If `Overcooked Pasta` were {Yes, No, Maybe} we should have splitted taking note of the treshold. -i.e. if we binary split on **Yes**, the other split is ¬¬ `Yes` (which means it could be `No` or `Maybe`).
> 
> 

---


## How to reduce overfitting

1. **Minimum Leaf Size:** We can setup a minimum number of leaf "size". The minimum number of samples required to be at a leaf node.
    
2. **Maximum Depth:** We can also set the threshold value on the tree depth.
    
3. **Relative Impurity Decrease:** A node will be split if this split induces a decrease of the impurity greater than or equal to this value.


However, even if we have these,, it is **still hard to train a decision tree to perform well generally**. 

Decision trees are high-variance models. It means a slight change in the training data, will lead to an entirely different model. Decision trees usually overfit. To overcome this situation, ensemble technique — bagging can be used, which leads to a random forest.

---

## Bagging and Ensamble -> Random Forest

Bagging means **Bootstrap Aggregation**. 
In Bagging we build different models using sample subset and then aggregate the predictions of the different models to reduce variance.

> [!hint]
> The problem with variance is that we try to fit the data too much(or too much data?).
> If we average the set of observations, the variance will be reduced.


Basically we split the dataset, then train a decision tree for each single split.
Then, in order to make inference, we forward the input to all the decision trees and we return the average output.

To average the results of different classifiers/trees:

$$\large h(\mathbf{x}) = \frac{1}{M}\sum_{j=1}^M h(\mathbf{x})_{\mathbf{D}_j}$$