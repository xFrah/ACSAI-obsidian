## Title: Multi-scale Concept Detection?

Below each title there is an explanation of what the section should contain (roughly).

## Existing works

Existing works in semantic search are usually based on:
- **Splitting documents in fixed-size chunks** and storing the chunk embeddings for later search
- **Embeddings of whole documents** and storing them for later search
- **Generating textual descriptions** of chunks or documents and storing them for later search

## Motivation for this work

The aim of this approach, is to create a more flexible semantic search, more **akin to something like object detection**, **but for concepts** in a source of information (document, audio, video).

This approach would solve and change the following:
- **Fixed-size chunking**: the problems of under-representation (requested concept doesn't fit in a single chunk) and imprecise representation (chunk is off, or much bigger than the requested concept).
- **Further processing needed for precise information retrieval**: The need for further processing from a human or LLM when a classical semantic search approach returns the "general" position of the highest-scoring result.

Under this title I could also include why I made some choices instead of others.

## General idea

We embed documents with **rolling windows of different sizes**, so that at each point of the document concepts of different sizes can be captured.

We treat those **sequences of vectors** as **curves** in the embedding space.

When a search is performed, we combine the curves to create a **new single curve** (still a sequence of vectors) that captures the **features that matter the most to the query**, at each point of the document.

We perform **signal analysis** on this new curve, and its **peaks**, along with their **boundaries**, will be the result of our process (after some refinement).

## The Process (all points are a detailed explanation of the step)

### 1. File pre-processing / Rolling-window curves creation

### 2. Best-features curve computation

### 3. Signal processing for finding peaks

### 4. Peak boundaries refinement

### 5. Outputting bounding boxes on the document


## Experiments

Experiments we made with different sources, possible even audio or video, along with parameters we found to be good.

## Improvements that can be made

I already know of a lot of improvements that could be made with more time spent on researching this topic. Even though I couldn't achieve them.