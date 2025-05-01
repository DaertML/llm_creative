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

# 
