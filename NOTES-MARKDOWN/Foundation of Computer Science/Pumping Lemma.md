The question here is:
Are there "non-regular" languages?

> [!hint]
> A language is regular if and only if there **exists a finite automaton that accepts it**.

> [!important]
> All **finite languages are regular**. We can make a DFA for every string in the language and then unite them all into one.


Assume we have a example of finite automaton (DFA) like this one:

![](../z_images/Pasted%20image%2020241119125349.png)
Is it possible to always guarantee that loop in the middle? 
The answer is **YES**, but we need to prove it.

> [!hint] Why not use NFA's?
> You can't guarantee a loop with NFA, because there is no guaranteed path. Especially considering we can have infinite **ε** paths.
> 
> ![](../z_images/Pasted%20image%2020241119125243.png)


