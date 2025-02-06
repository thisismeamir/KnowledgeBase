---
undefined: ""
File: Knowledge Center/Journals/Xavier Documentation/Introduction.md
sticker: lucide//newspaper
---
Large language models are statistical models that can practice text-generation given an initial prompt. These models are being used as in 2024 in very much many places, leading to considerations about their potentials in more areas. On the other hand LLMs lack the ability to interact with computers since they are only means of producing text:

$$
F: \text{text} \longrightarrow \text{text}
$$
This has led me to consider an alternative use of these models. A more dynamic use which has multiple agents (chat threads) each acquired with an additional prompt explaining the instruction they have to do given a prompt. Each of this instructions would lead to a probabilistic accuracy of returned prompt which can be then interpreted using a pipeline into actions in local computer. 

$$
F: \text{prompt} \longrightarrow \text{instruction-prompt} + \text{prompt} \longrightarrow \text{action}
$$
This simple modeling can lead to an enormous potential of LLMs as prompt makers. Leading to an artificial intelligent integration with computers to do actions.

# Introducing [[xavier]]
Xavier is a personal assistant uses this idea. It is personalized for Kid A (aka Amir H. Ebrahimnezhad). The main concept in Xavier is not to train Ai from scratch, but using abstractions, instruction-prompts, layers of interactions, and apis to enhance interactions with LLMs to a more dynamic and self-reflecting interaction, making the LLMs work beside the evaluation of the text of the user (talking to themselves, making plans, writing and reading stuff, providing large analysis).

## Defining the Goals
The goals of creating Xavier is 
1. To make automation in general and specific tasks, specific to the needs of the user (Kid A).
2. Faster research and reviews
3. Easier project management, development and debugging
4. Processing large amount of data and providing insight.
5. Doing small to large (future) projects (development).

## General Structure of Xavier
The structure that I adapted and am developing Xavier by is similar to that of a human brain. But we should not forget that whatever the human brain is capable of is not necessary for a computer. 

The overall structure of Xavier divides into four categories.
1. *Xavier Grey Matter*: The core of thoughts, memory, executions and response generations. 
2. *Xavier Axon*: Channels and APIs for interactions with me and the environment (right now only the local computer and some websites).
3. *Xavier Continuum*: Making Xavier aware everywhere. This module should be very efficient and small to be ran in the background.
4. Xavier Routine
### Xavier Grey Matter