# Awesome RLAIF
[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
![https://github.com/mengdi-li/awesome-RLAIF/blob/main/LICENSE](https://img.shields.io/badge/License-Apache_2.0-green)

An actively updated list of literature on _**R**einforcement **L**earning from **AI** **F**eedback (RLAIF)_. 


## What is RLAIF? ChatGPT: 
Reinforcement Learning from AI Feedback (RLAIF) is a concept that describes a type of machine learning approach where **an AI agent learns by receiving feedback or guidance from another AI system**. This concept is closely related to the field of Reinforcement Learning (RL), which is a type of machine learning where an agent learns to make a sequence of decisions in an environment to maximize a cumulative reward.

In traditional RL, an agent interacts with an environment and receives feedback in the form of rewards or penalties based on the actions it takes. It learns to improve its decision-making over time to achieve its goals. In the context of Reinforcement Learning from AI Feedback, the AI agent still aims to learn optimal behavior through interactions, but **the feedback comes from another AI system rather than from the environment or human evaluators**. This can be **particularly useful in situations where it may be challenging to define clear reward functions or when it is more efficient to use another AI system to provide guidance**. The feedback from the AI system can take various forms, such as:
- **Demonstrations**: The AI system provides demonstrations of desired behavior, and the learning agent tries to imitate these demonstrations.
- **Comparison Data**: The AI system ranks or compares different actions taken by the learning agent, helping it to understand which actions are better or worse.
- **Reward Shaping**: The AI system provides additional reward signals to guide the learning agent's behavior, supplementing the rewards from the environment.

This approach is often used in scenarios where the RL agent needs to learn from **limited human or expert feedback or when the reward signal from the environment is sparse or unclear**. It can also be used to **accelerate the learning process and make RL more sample-efficient**. Reinforcement Learning from AI Feedback is an area of ongoing research and has applications in various domains, including robotics, autonomous vehicles, and game playing, among others.

## Papers

```
format:
- [title](paper link) | ![](https://img.shields.io/badge/CONFERENCE_'YEAR-blue)
  - Authors: ...
  - <details> <summary>Abstract (click me)</summary> ... </details>
  - Links: [Project website](website link), [Code](code link), [Dataset](dataset link), ...
  - Tags: LLMs / Agents
```

### 2024
- [Self-Rewarding Language Models](https://arxiv.org/abs/2401.10020) | ![](https://img.shields.io/badge/Arxiv-blue)
  - Authors: Weizhe Yuan, Richard Yuanzhe Pang, Kyunghyun Cho, Sainbayar Sukhbaatar, Jing Xu, Jason Weston
  - <details> <summary>Abstract (click me)</summary> We posit that to achieve superhuman agents, future models require superhuman feedback in order to provide an adequate training signal. Current approaches commonly train reward models from human preferences, which may then be bottlenecked by human performance level, and secondly these separate frozen reward models cannot then learn to improve during LLM training. In this work, we study Self-Rewarding Language Models, where the language model itself is used via LLM-as-a-Judge prompting to provide its own rewards during training. We show that during Iterative DPO training that not only does instruction following ability improve, but also the ability to provide high-quality rewards to itself. Fine-tuning Llama 2 70B on three iterations of our approach yields a model that outperforms many existing systems on the AlpacaEval 2.0 leaderboard, including Claude 2, Gemini Pro, and GPT-4 0613. While only a preliminary study, this work opens the door to the possibility of models that can continually improve in both axes. </details>
  - Tags: LLMs

### 2023

- [Beyond Human Data: Scaling Self-Training for Problem-Solving with Language Models](https://arxiv.org/abs/2312.06585) | ![](https://img.shields.io/badge/Arxiv-blue)
  - Authors: Avi Singh, John D. Co-Reyes, Rishabh Agarwal, Ankesh Anand, Piyush Patil, Xavier Garcia, et al.
  - <details> <summary>Abstract (click me)</summary> Fine-tuning language models (LMs) on human-generated data remains a prevalent practice. However, the performance of such models is often limited by the quantity and diversity of high-quality human data. In this paper, we explore whether we can go beyond human data on tasks where we have access to scalar feedback, for example, on math problems where one can verify correctness. To do so, we investigate a simple self-training method based on expectation-maximization, which we call ReSTEM, where we (1) generate samples from the model and filter them using binary feedback, (2) fine-tune the model on these samples, and (3) repeat this process a few times. Testing on advanced MATH reasoning and APPS coding benchmarks using PaLM-2 models, we find that ReSTEM scales favorably with model size and significantly surpasses fine-tuning only on human data. Overall, our findings suggest self-training with feedback can substantially reduce dependence on human-generated data.  </details>
  - Tags: LLMs

- [Reinforced Self-Training (ReST) for Language Modeling](https://arxiv.org/abs/2308.08998) | ![](https://img.shields.io/badge/Arxiv-blue)
  - Authors: Caglar Gulcehre, Tom Le Paine, Srivatsan Srinivasan, Ksenia Konyushkova, Lotte Weerts, et al.
  - <details> <summary>Abstract (click me)</summary> Reinforcement learning from human feedback (RLHF) can improve the quality of large language model's (LLM) outputs by aligning them with human preferences. We propose a simple algorithm for aligning LLMs with human preferences inspired by growing batch reinforcement learning (RL), which we call Reinforced Self-Training (ReST). Given an initial LLM policy, ReST produces a dataset by generating samples from the policy, which are then used to improve the LLM policy using offline RL algorithms. ReST is more efficient than typical online RLHF methods because the training dataset is produced offline, which allows data reuse. While ReST is a general approach applicable to all generative learning settings, we focus on its application to machine translation. Our results show that ReST can substantially improve translation quality, as measured by automated metrics and human evaluation on machine translation benchmarks in a compute and sample-efficient manner. </details>
  - Tags: LLMs


- [Eureka: Human-Level Reward Design via Coding Large Language Models](https://arxiv.org/abs/2310.12931) | ![](https://img.shields.io/badge/Arxiv-blue)
  - Authors: Yecheng Jason Ma, William Liang, Guanzhi Wang, De-An Huang, Osbert Bastani, Dinesh Jayaraman, Yuke Zhu, Linxi Fan, Anima Anandkumar
  - <details> <summary>Abstract (click me)</summary> Large Language Models (LLMs) have excelled as high-level semantic planners for sequential decision-making tasks. However, harnessing them to learn complex low-level manipulation tasks, such as dexterous pen spinning, remains an open problem. We bridge this fundamental gap and present Eureka, a human-level reward design algorithm powered by LLMs. Eureka exploits the remarkable zero-shot generation, code-writing, and in-context improvement capabilities of state-of-the-art LLMs, such as GPT-4, to perform evolutionary optimization over reward code. The resulting rewards can then be used to acquire complex skills via reinforcement learning. Without any task-specific prompting or pre-defined reward templates, Eureka generates reward functions that outperform expert human-engineered rewards. In a diverse suite of 29 open-source RL environments that include 10 distinct robot morphologies, Eureka outperforms human experts on 83% of the tasks, leading to an average normalized improvement of 52%. The generality of Eureka also enables a new gradient-free in-context learning approach to reinforcement learning from human feedback (RLHF), readily incorporating human inputs to improve the quality and the safety of the generated rewards without model updating. Finally, using Eureka rewards in a curriculum learning setting, we demonstrate for the first time, a simulated Shadow Hand capable of performing pen spinning tricks, adeptly manipulating a pen in circles at rapid speed. </details>
  - Links: [Project website](https://eureka-research.github.io/), [Code](https://github.com/eureka-research/Eureka)
  - Tags: Agents

- [Accelerating Reinforcement Learning of Robotic Manipulations via Feedback from Large Language Models](https://arxiv.org/abs/2311.02379) | ![](https://img.shields.io/badge/CoRL_'23_Workshop-blue)
  - Authors: Kun Chu, Xufeng Zhao, Cornelius Weber, Mengdi Li, Stefan Wermter
  - <details> <summary>Abstract (click me)</summary> Reinforcement Learning (RL) plays an important role in the robotic manipulation domain since it allows self-learning from trial-and-error interactions with the environment. Still, sample efficiency and reward specification seriously limit its potential. One possible solution involves learning from expert guidance. However, obtaining a human expert is impractical due to the high cost of supervising an RL agent, and developing an automatic supervisor is a challenging endeavor. Large Language Models (LLMs) demonstrate remarkable abilities to provide human-like feedback on user inputs in natural language. Nevertheless, they are not designed to directly control low-level robotic motions, as their pretraining is based on vast internet data rather than specific robotics data. In this paper, we introduce the Lafite-RL (Language agent feedback interactive Reinforcement Learning) framework, which enables RL agents to learn robotic tasks efficiently by taking advantage of LLMs' timely feedback. Our experiments conducted on RLBench tasks illustrate that, with simple prompt design in natural language, the Lafite-RL agent exhibits improved learning capabilities when guided by an LLM. It outperforms the baseline in terms of both learning efficiency and success rate, underscoring the efficacy of the rewards provided by an LLM. </details>
  - Tags: Agents

- [RAIN: Your Language Models Can Align Themselves without Finetuning](https://arxiv.org/abs/2309.07124) | ![](https://img.shields.io/badge/Arxiv-blue)
  - Authors: Yuhui Li, Fangyun Wei, Jinjing Zhao, Chao Zhang, Hongyang Zhang
  - <details> <summary>Abstract (click me)</summary> Large language models (LLMs) often demonstrate inconsistencies with human preferences. Previous research typically gathered human preference data and then aligned the pre-trained models using reinforcement learning or instruction tuning, a.k.a. the finetuning step. In contrast, aligning frozen LLMs without requiring alignment data is more appealing. This work explores the potential of the latter setting. We discover that by integrating self-evaluation and rewind mechanisms, unaligned LLMs can directly produce responses consistent with human preferences via self-boosting. We introduce a novel inference method, Rewindable Auto-regressive INference (RAIN), that allows pre-trained LLMs to evaluate their own generation and use the evaluation results to guide rewind and generation for AI safety. Notably, RAIN operates without the need of extra data for model alignment and abstains from any training, gradient computation, or parameter updates. Experimental results evaluated by GPT-4 and humans demonstrate the effectiveness of RAIN: on the HH dataset, RAIN improves the harmlessness rate of LLaMA 30B from 82% of vanilla inference to 97%, while maintaining the helpfulness rate. On the TruthfulQA dataset, RAIN improves the truthfulness of the already-well-aligned LLaMA-2-chat 13B model by 5%. </details>
  - Links: [Code](https://github.com/SafeAILab/RAIN)
  - Tags: LLMs

- [Principle-Driven Self-Alignment of Language Models from Scratch with Minimal Human Supervision](https://arxiv.org/abs/2305.03047) | ![](https://img.shields.io/badge/NeurIPS_'23-blue)
  - Authors: Zhiqing Sun, Yikang Shen, Qinhong Zhou, Hongxin Zhang, Zhenfang Chen, David Cox, Yiming Yang, Chuang Gan
  - <details> <summary>Abstract (click me)</summary> Recent AI-assistant agents, such as ChatGPT, predominantly rely on supervised fine-tuning (SFT) with human annotations and reinforcement learning from human feedback (RLHF) to align the output of large language models (LLMs) with human intentions, ensuring they are helpful, ethical, and reliable. However, this dependence can significantly constrain the true potential of AI-assistant agents due to the high cost of obtaining human supervision and the related issues on quality, reliability, diversity, self-consistency, and undesirable biases. To address these challenges, we propose a novel approach called SELF-ALIGN, which combines principle-driven reasoning and the generative power of LLMs for the self-alignment of AI agents with minimal human supervision. Our approach encompasses four stages: first, we use an LLM to generate synthetic prompts, and a topic-guided method to augment the prompt diversity; second, we use a small set of human-written principles for AI models to follow, and guide the LLM through in-context learning from demonstrations (of principles application) to produce helpful, ethical, and reliable responses to user's queries; third, we fine-tune the original LLM with the high-quality self-aligned responses so that the resulting model can generate desirable responses for each query directly without the principle set and the demonstrations anymore; and finally, we offer a refinement step to address the issues of overly-brief or indirect responses. Applying SELF-ALIGN to the LLaMA-65b base language model, we develop an AI assistant named Dromedary. With fewer than 300 lines of human annotations (including < 200 seed prompts, 16 generic principles, and 5 exemplars for in-context learning). Dromedary significantly surpasses the performance of several state-of-the-art AI systems, including Text-Davinci-003 and Alpaca, on benchmark datasets with various settings. </details>
  - Links: [Code & Model Weights & Dataset](https://github.com/IBM/Dromedary)
  - Tags: LLMs

- [Motif: Intrinsic Motivation from Artificial Intelligence Feedback](https://arxiv.org/abs/2310.00166) | ![](https://img.shields.io/badge/Arxiv-blue)
  - Authors: Martin Klissarov, Pierluca D'Oro, Shagun Sodhani, Roberta Raileanu, Pierre-Luc Bacon, Pascal Vincent, Amy Zhang, Mikael Henaff
  - <details> <summary>Abstract (click me)</summary> Exploring rich environments and evaluating one's actions without prior knowledge is immensely challenging. In this paper, we propose Motif, a general method to interface such prior knowledge from a Large Language Model (LLM) with an agent. Motif is based on the idea of grounding LLMs for decision-making without requiring them to interact with the environment: it elicits preferences from an LLM over pairs of captions to construct an intrinsic reward, which is then used to train agents with reinforcement learning. We evaluate Motif's performance and behavior on the challenging, open-ended and procedurally-generated NetHack game. Surprisingly, by only learning to maximize its intrinsic reward, Motif achieves a higher game score than an algorithm directly trained to maximize the score itself. When combining Motif's intrinsic reward with the environment reward, our method significantly outperforms existing approaches and makes progress on tasks where no advancements have ever been made without demonstrations. Finally, we show that Motif mostly generates intuitive human-aligned behaviors which can be steered easily through prompt modifications, while scaling well with the LLM size and the amount of information given in the prompt. </details>
  - Links: [Code](https://github.com/facebookresearch/motif)
  - Tags: Agents

- [RLAIF: Scaling Reinforcement Learning from Human Feedback with AI Feedback](https://arxiv.org/abs/2309.00267) | ![](https://img.shields.io/badge/Arxiv-blue)
  - Authors: Harrison Lee, Samrat Phatale, Hassan Mansoor, Kellie Lu, Thomas Mesnard, Colton Bishop, Victor Carbune, Abhinav Rastogi
  - <details> <summary>Abstract (click me)</summary> Reinforcement learning from human feedback (RLHF) is effective at aligning large language models (LLMs) to human preferences, but gathering high quality human preference labels is a key bottleneck. We conduct a head-to-head comparison of RLHF vs. RL from AI Feedback (RLAIF) - a technique where preferences are labeled by an off-the-shelf LLM in lieu of humans, and we find that they result in similar improvements. On the task of summarization, human evaluators prefer generations from both RLAIF and RLHF over a baseline supervised fine-tuned model in ~70% of cases. Furthermore, when asked to rate RLAIF vs. RLHF summaries, humans prefer both at equal rates. These results suggest that RLAIF can yield human-level performance, offering a potential solution to the scalability limitations of RLHF. </details>
  - Tags: LLMs

- [Language Model Self-improvement by Reinforcement Learning Contemplation](https://arxiv.org/abs/2305.14483) | ![](https://img.shields.io/badge/Arxiv-blue)
  - Authors: Jing-Cheng Pang, Pengyuan Wang, Kaiyuan Li, Xiong-Hui Chen, Jiacheng Xu, Zongzhang Zhang, Yang Yu
  - <details> <summary>Abstract (click me)</summary>Large Language Models (LLMs) have exhibited remarkable performance across various natural language processing (NLP) tasks. However, fine-tuning these models often necessitates substantial supervision, which can be expensive and time-consuming to obtain. This paper introduces a novel unsupervised method called LanguageModel Self-Improvement by Reinforcement Learning Contemplation (SIRLC) that improves LLMs without reliance on external labels. Our approach is grounded in the observation that it is simpler for language models to assess text quality than to generate text. Building on this insight, SIRLC assigns LLMs dual roles as both student and teacher. As a student, the LLM generates answers to unlabeled questions, while as a teacher, it evaluates the generated text and assigns scores accordingly. The model parameters are updated using reinforcement learning to maximize the evaluation score. We demonstrate that SIRLC can be applied to various NLP tasks, such as reasoning problems, text generation, and machine translation. Our experiments show that SIRLC effectively improves LLM performance without external supervision, resulting in a 5.6% increase in answering accuracy for reasoning tasks and a rise in BERTScore from 0.82 to 0.86 for translation tasks. Furthermore, SIRLC can be applied to models of different sizes, showcasing its broad applicability.</details>
  - Tags: LLMs

- [Language to Rewards for Robotic Skill Synthesis](https://arxiv.org/abs/2306.08647) | ![](https://img.shields.io/badge/CoRL_'23-blue)
  - Authors: Wenhao Yu, Nimrod Gileadi, Chuyuan Fu, Sean Kirmani, Kuang-Huei Lee, Montse Gonzalez Arenas, et al.
  - <details> <summary>Abstract (click me)</summary> Large language models (LLMs) have demonstrated exciting progress in acquiring diverse new capabilities through in-context learning, ranging from logical reasoning to code-writing. Robotics researchers have also explored using LLMs to advance the capabilities of robotic control. However, since low-level robot actions are hardware-dependent and underrepresented in LLM training corpora, existing efforts in applying LLMs to robotics have largely treated LLMs as semantic planners or relied on human-engineered control primitives to interface with the robot. On the other hand, reward functions are shown to be flexible representations that can be optimized for control policies to achieve diverse tasks, while their semantic richness makes them suitable to be specified by LLMs. In this work, we introduce a new paradigm that harnesses this realization by utilizing LLMs to define reward parameters that can be optimized and accomplish variety of robotic tasks. Using reward as the intermediate interface generated by LLMs, we can effectively bridge the gap between high-level language instructions or corrections to low-level robot actions. Meanwhile, combining this with a real-time optimizer, MuJoCo MPC, empowers an interactive behavior creation experience where users can immediately observe the results and provide feedback to the system. To systematically evaluate the performance of our proposed method, we designed a total of 17 tasks for a simulated quadruped robot and a dexterous manipulator robot. We demonstrate that our proposed method reliably tackles 90% of the designed tasks, while a baseline using primitive skills as the interface with Code-as-policies achieves 50% of the tasks. We further validated our method on a real robot arm where complex manipulation skills such as non-prehensile pushing emerge through our interactive system. </details>
  - Links: [Project website](https://language-to-reward.github.io/), [Code](https://github.com/google-deepmind/language_to_reward_2023)
  - Tags: Agents

- [Language Instructed Reinforcement Learning for Human-AI Coordination](https://proceedings.mlr.press/v202/hu23e.html) | ![](https://img.shields.io/badge/ICML_'23-blue)
  - Authors: Hengyuan Hu, Dorsa Sadigh
  - <details> <summary>Abstract (click me)</summary> One of the fundamental quests of AI is to produce agents that coordinate well with humans. This problem is challenging, especially in domains that lack high quality human behavioral data, because multi-agent reinforcement learning (RL) often converges to different equilibria from the ones that humans prefer. We propose a novel framework, instructRL, that enables humans to specify what kind of strategies they expect from their AI partners through natural language instructions. We use pretrained large language models to generate a prior policy conditioned on the human instruction and use the prior to regularize the RL objective. This leads to the RL agent converging to equilibria that are aligned with human preferences. We show that instructRL converges to human-like policies that satisfy the given instructions in a proof-of-concept environment as well as the challenging Hanabi benchmark. Finally, we show that knowing the language instruction significantly boosts human-AI coordination performance in human evaluations in Hanabi. </details>
  - Tags: Agents

- [Guiding Pretraining in Reinforcement Learning with Large Language Models](https://proceedings.mlr.press/v202/du23f.html) | ![](https://img.shields.io/badge/ICML_'23-blue)
  - Authors: Yuqing Du, Olivia Watkins, Zihan Wang, Cédric Colas, Trevor Darrell, Pieter Abbeel, Abhishek Gupta, Jacob Andreas
  - <details> <summary>Abstract (click me)</summary> Reinforcement learning algorithms typically struggle in the absence of a dense, well-shaped reward function. Intrinsically motivated exploration methods address this limitation by rewarding agents for visiting novel states or transitions, but these methods offer limited benefits in large environments where most discovered novelty is irrelevant for downstream tasks. We describe a method that uses background knowledge from text corpora to shape exploration. This method, called ELLM (Exploring with LLMs) rewards an agent for achieving goals suggested by a language model prompted with a description of the agent’s current state. By leveraging large-scale language model pretraining, ELLM guides agents toward human-meaningful and plausibly useful behaviors without requiring a human in the loop. We evaluate ELLM in the Crafter game environment and the Housekeep robotic simulator, showing that ELLM-trained agents have better coverage of common-sense behaviors during pretraining and usually match or improve performance on a range of downstream tasks. </details>
  - Links: [Code](https://github.com/yuqingd/ellm)
  - Tags: Agents

- [Reward Design with Language Models](https://arxiv.org/abs/2303.00001) | ![](https://img.shields.io/badge/ICLR_'23-blue)
  - Authors: Minae Kwon, Sang Michael Xie, Kalesha Bullard, Dorsa Sadigh
  - <details> <summary>Abstract (click me)</summary> Reward design in reinforcement learning (RL) is challenging since specifying human notions of desired behavior may be difficult via reward functions or require many expert demonstrations. Can we instead cheaply design rewards using a natural language interface? This paper explores how to simplify reward design by prompting a large language model (LLM) such as GPT-3 as a proxy reward function, where the user provides a textual prompt containing a few examples (few-shot) or a description (zero-shot) of the desired behavior. Our approach leverages this proxy reward function in an RL framework. Specifically, users specify a prompt once at the beginning of training. During training, the LLM evaluates an RL agent's behavior against the desired behavior described by the prompt and outputs a corresponding reward signal. The RL agent then uses this reward to update its behavior. We evaluate whether our approach can train agents aligned with user objectives in the Ultimatum Game, matrix games, and the DealOrNoDeal negotiation task. In all three tasks, we show that RL agents trained with our framework are well-aligned with the user's objectives and outperform RL agents trained with reward functions learned via supervised learning. </details>
  - Links: [Code & Prompts](https://github.com/minaek/reward_design_with_llms)
  - Tags: Agents
 

### 2022
- [Constitutional AI: Harmlessness from AI Feedback](https://arxiv.org/abs/2212.08073) | ![](https://img.shields.io/badge/Arxiv-blue)
  - Authors: Yuntao Bai, Saurav Kadavath, Sandipan Kundu, Amanda Askell, Jackson Kernion, et al.
  - <details> <summary>Abstract (click me)</summary> As AI systems become more capable, we would like to enlist their help to supervise other AIs. We experiment with methods for training a harmless AI assistant through self-improvement, without any human labels identifying harmful outputs. The only human oversight is provided through a list of rules or principles, and so we refer to the method as 'Constitutional AI'. The process involves both a supervised learning and a reinforcement learning phase. In the supervised phase we sample from an initial model, then generate self-critiques and revisions, and then finetune the original model on revised responses. In the RL phase, we sample from the finetuned model, use a model to evaluate which of the two samples is better, and then train a preference model from this dataset of AI preferences. We then train with RL using the preference model as the reward signal, i.e. we use 'RL from AI Feedback' (RLAIF). As a result we are able to train a harmless but non-evasive AI assistant that engages with harmful queries by explaining its objections to them. Both the SL and RL methods can leverage chain-of-thought style reasoning to improve the human-judged performance and transparency of AI decision making. These methods make it possible to control AI behavior more precisely and with far fewer human labels.  </details>
  - Links: [Dataset](https://github.com/anthropics/ConstitutionalHarmlessnessPaper)
  - Tags: LLMs

## Related Awesome Repos
- [awesome-RLHF](https://github.com/opendilab/awesome-RLHF/tree/main)

## Contributing
Let's make the list more comprehensive. 

## 👥 Contributors
<a href="https://github.com/mengdi-li/awesome-RLAIF/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=mengdi-li/awesome-RLAIF"/>
</a>
