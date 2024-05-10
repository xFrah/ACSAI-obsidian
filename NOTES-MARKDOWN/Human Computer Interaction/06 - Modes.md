Modes are different situations from which the same gesture can produce different outcomes.

> [!example]
> A button can switch on or off the engine depending on the state of the engine.


## Modal interface

A modal interface means that gesture != action.

The user must check the system state before executing actions.

> [!example]
> ![](../z_images/Pasted%20image%2020240510104020.png)

> [!quote] Definition
> A UI is modal regarding a gesture when:
> - The state of the UI is not the locus of attention of the user
> - The UI will react to the gesture with N possible replies, depending on the state.
>   
>   
>   > [!hint] What the fuck does the first point mean
>   > The UI element in question might be active or awaiting interaction, but it isn't what the user is currently focused on.
>   > 
>   > - **Modal Interaction**: Occurs when a UI element, not initially the focus, requires interaction to proceed, thereby interrupting the flow of the primary task.
>>- **Non-modal Interaction**: Involves elements that are already the focus of the user's attention, where interactions proceed without shifting focus or interrupting other tasks.
> 


## Mode errors

A mode error happens when you take an action that was not intended simply because the system state was not in the locus of attention.

> [!example]
> You want to go to a new line, but you submit the form.

> [!tip] How to minimize mode errors?
> Don't have modes. Or make sure they are evident.
>




