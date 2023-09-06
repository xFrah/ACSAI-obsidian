The attention mechanism, unlike Recurrent Neural Networks and LSTMs, has an infinite reference window, therefore they are able to use the entire contex/history of our data sequence.

> [!tldr] How was it done before?
> We would have used an autoencoder, where the encoder processes the input sequence and encodes/compresses/summarizes the information into a vector/layer (also called as the “latent space”) of a fixed length. 
> 
> ![](../z_images/Pasted%20image%2020230721204516.png)
> 
> This representation is expected to be a good summary of the entire input sequence. The decoder is then initialized with this context vector as inputs, using which it starts generating the transformed output.
> 
> But this is actually shit, because the latent space can only hold so much information, so we can only use so much of the sequence.


For each word in the sentence we generate annotation vectors(hidden states vectors).
Annotation vectors are a representation of the words.