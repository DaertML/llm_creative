# llm_creative
Repo for studying the mechanisms to improve LLMs for creative writing. Trying to discover the magic behind GPT4.5

# Introduction
LLMs have emerged as useful tools thanks to multiple advancements:
- ULM-Fit approach: training the LLM on a general corpus in an unsupervised manner by next token prediction
- RLAIF/RLHF: for instruction/chat based models
- GPRO like: for training the LLM in easy verifiable domains

The main goal of this repo is to cover all mechanisms to improve in the field of creative writing, in which, it is hard to eval how the LLM made a better/worse response. It is good to highlight that RLHF shouldnt be considered to cover this; as the main goal is to find a way to scale it beyond human tagging, with something like GRPO.

# Main mechanisms
It is an open secret, that as the proprietory LLMs improved in the STEM branches, as well as covering improved reasoning and planning; the community won at the creative writing since day one: multiple fine tuned models, token schedulers, inference hyperparameters and prompts have been the basis for solving such problem:
- Frankenmerges: creativeness can be augmented by merging models that have been trained on creative domains.
- Token samplers: this field is still in its infancy; remarkable is the Mirostat sampler that aids in creating novel and creative content.
- Inference Hyperparameters: this is dependent on each LLM, but an increase in the temperature and top_k seems like a great place to start experimenting and finding a source of generating samples for later comparison.

# Proposed novel mechanisms
This document covers an attempt to cover the classic and new potential mechanisms to enhance the creative writing of an LLM:
- GRPO RL Like method: having an annotated dataset on different trajectories for how to complete a joke/creative piece may help in the process of leaving the LLM freedom to learn the intermediate paths towards such resolutions. Reward hacking could be an issue as the intermediate steps are hard to evaluate (mainly we could consider the use of an LLM as a judge to achieve it).
- Formalization of the creative writing: letting an LLM to write a critic of the creative writing in the shape of a Chain of Thought and then asking another to eval it and provide feedback to enhance it, may lead to a flywheel towards achieving improvements in the same manner as we have seen in STEM, in which the measuring of both intermediate and final solutions is easier.
- Chain of Thought Reasoning: finetuning may not be necessary at all, as soon as the model is capable of reasoning about the problem using CoT, and using that CoT to evaluate as the different solutions are generated. This depends on the capabilities that the model already knows; as it is kind of an open problem to control the way the model reasons... at least with the same controlability as you get when you prompt a model that is not meant for reasoning (the thing is, if the model doesnt know about a new kind of jokes, or how you want it to eval the jokes, or whatever... it may be hard to give leave In Context Learning as the way to achieve it).

## GRPO RL Like method:
This mechanism can use the result from a formalization of the creative writing; as well as use learning signals from DPO datasets or similar on the expected results from the model.

In this case, instead of having a definite answer, the LLM has a valid answer that it needs to reason to get there. It may try to do reward hacking in the process, thus the value of an LLM evaluating the intermediate steps CoT that are produced. It is very likely that there is a need of a big model to work on this topics as a judge.

## Formalization of the creative writing
In this case, the LLm is asked to "reason" about different paths that the creative writing could take; the LLM is given a topic, and certain guidelines to follow during the creative writing process. Once such creative work is done, the LLM is asked to create a logic formalization of the writing; something that can be introduced in a logic engine to be scored and validated.

This is nothing new, but the use of classic Aristotles Logic and evaluation of propositional logic; this may be extended: some research has given ideas in the field of logic like introducing "Time" in the resolution of the logic proposition, in a similar manner as how a finite automata is executed.

As potential frameworks to achieve it: PyReason and Prolog. Other alternatives are viable as soon as similar capabilities are provided.

# Experiments
With this being said; the preliminary experiments go in hand with trying to make the LLM reason about the intermediate steps towards the expected result; even though, there is no mathematical/formal way of proving that each step is valid, an LLM or human in the loop can evaluate such steps from the chain of thought. At this stage, I have to say that the involved process seems to be like the classic way of doing RLHF, somehow, the difficulty comes from the used mechanisms to evaluate the validity of each step of the model.

One could argue that one of the best ways of exploiting all these mechanisms is the use of all techniques together, to see how the results are improved; somehow, things get hard pretty fast, and there is a need to introduce new mechanisms to the mix iteratively.

Two examples on how the thing with CoT in the prompt works are provided: one to validate the validity of a philosophical argument, another to create funny jokes. The QwQ:32b model isnt prompted with anything fancy but a simple query to do the thing; it is expected that we can get better with clever prompting.

# Motivation
The motivation here is to push the capabilities of the LLMs in fields that are hard to eval, or that at least are hard to get a common solution for; that is: anything outside of STEM, or for which you know the answer. The main motivation for this is to try mechanisms that have been attempted before and are in use in STEM fields, to solve problems out of STEM. Seeing how greatly such mechanisms perform in STEM, it is to be expected that we can push the boundaries.

# New avenues
It is very likely that finding a flywheel in these fields may bring us way closer to AGI; as novel research works are only verifiable at the end of the work, something that takes a lot of out gambles from the researchers doing the work: hypothesis proposal, experimenting, reporting, validating...

If one thinks about it even in STEM there is a need for "wording", much more than for writing logical statements and proofs; such wording needs a mechanism that analyzes different paths of resolution and ways for evaluating such paths without the use of a solution comparison at the end of the process.

Determining that something is funny or not brings the need of different evaluation methods to validate the solution; something that is not needed in STEM as experiments are easy to evaluate for correctness.
