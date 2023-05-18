When we train a model, we usually split the dataset in 3 subsets:

![](../z_images/Pasted%20image%2020230518163505.png)


### Motivation for each split:

-   **[Training Set]** Do well on training-set by minimize the loss. (during training)
-   **[Validation Set]** Do well in generalization error. (during training)
-   **[Test Set]** Get an estimate of the generalization error. (post training)


## Problems with this technique

-   It is **biased** on a specific validation partition.
-   It **wastes part of the training data.**
-   There could be possibility of overfitting.
-   Think of each cycle "tune training/valid on validation", the dataset will **get rotten iteration over iteration**


## Solution

The solution is to use cross-validation:

-   A test set should still be held out for final evaluation,
-   Validation set is no longer needed.
-   **K-fold CV**, the training set is **split into k smaller sets** (below K=5).


---

## K-fold Cross-Validation

1. **Split the dataset into k subsets**/folds.
2. **Last fold** = test dataset, **remaining folds** = training dataset.
3. Train the model on the training dataset and validate it on the test dataset.
4. Save the validation score
5. Repeat from step 2, but **use another subset as the test dataset**. Last time was k-1, now it will be k-2, and so on.
6. When we terminate it, we have validated the model on every split/fold, now **we average the validation scores** to summarize the accuracy of the model

![](../z_images/Pasted%20image%2020230518165425.png)


> [!hint] Why bother?
> - The classic method wastes too much training data.
> - This method has no subset-choice related bias.
>
>This thing can be really computationally expensive tho!


---

## What K should we choose?

In general:

-   The larger K is, the **more accurate the error estimation tends to be**
-   but computation time will be greater

Rule of thumb:

-   Typical choices for `K` are `2, 5, 10`.
-   By far the most common is **K = 10: 10-fold cross validation.**
-   Sometimes **5** is used for efficiency reasons.
-   And sometimes **2 is used for subtle statistical reasons, but that is quite rare**

---

## What to do after cross-validation?

After running cross validation, you have **2 choices.**

1.  You can either select **one of the K trained models as your final model** to make predictions
2.  You can train a **new model on all of the data, using the hyperparameters selected by cross-validation.**

*Option 2 is generally preferred.*

![](../z_images/Pasted%20image%2020230518170125.png)


# We fucking bruteforce the research for the optimal hyperparameters.