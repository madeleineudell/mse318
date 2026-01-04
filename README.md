# **MS&E 318: Constrained and Safe AI**

How can we design AI systems that are not only powerful but also provably safe and trustworthy? This advanced PhD seminar surveys algorithmic methods to enforce hard constraints in machine learning, reinforcement learning, and generative AI. 
Topics include classical constrained optimization (Lagrangian methods, robust and stochastic programming), 
safe reinforcement learning (trust regions, Lyapunov functions, reachability), 
hybrid ML-optimization methods (projection networks, solver-in-the-loop architectures), 
and alignment strategies for large language models (fine-tuning, model editing, tool use, and interactive alignment). 
We will consider applications to robotics, finance, healthcare, energy, and personal AI assistants. 
Topics may change according to student interest.
Prerequisites: optimization at the level of CME 307 or EE 364a.

For each topic, we will begin with a foundational mini-lecture,
followed by student-led discussion on modern research papers.
The course will culminate in a final research project
which will constitute a majority of the grade.

# Logistics

* **When:** 1:30-4:20pm Tuesdays Jan 9-March 10
* **Where:** [McCullough 122](https://campus-map.stanford.edu/?srch=McCullough+122) or on [Zoom](https://stanford.zoom.us/j/6394072382?pwd=bndKcXBpRFdOb2x5VFhuT0kzN1QvQT09) by prior arrangement with the instructor
* You can schedule [Office hours](https://calendar.app.google/sCu1wpZXkUdAXdA59) on this calendar or chat with Prof. Udell after class.

# Learning goals

Students who complete the course should be able to:

* Formulate AI problems with explicit hard constraints and identify appropriate enforcement mechanisms.
* Compare Lagrangian, projection-based, and solver-in-the-loop approaches theoretically and empirically.
* Critically evaluate safety and alignment claims in modern ML papers.
* Design a constrained AI system with provable guarantees or well-justified approximations.
* Contribute to the research literature on constrained and safe AI, at the level of a workshop or conference submission to ICML, NeurIPS, or ICLR.

# Course format and requirements

Students are required to attend class, with at most one absence.
(Any student may also attend up to one class remotely via [Zoom](https://stanford.zoom.us/j/6394072382?pwd=bndKcXBpRFdOb2x5VFhuT0kzN1QvQT09),
or more by prior arrangement with the instructor.)

Course grades have three components:

* **Quiz** (.1): Most classes will begin with a short quiz to reinforce the main ideas of the reading.
Your lowest quiz score will be dropped.
* **Present a paper** (.3): Students will each lead a discussion on a paper twice (or so), likely in teams
depending on course enrollment.
The student leading the discussion will prepare a 30 minute presentation using slides,
two quiz questions on the paper,
and a class activity or questions for discussion.
* **Research project** (.6):
The final research project should explore a new idea for safe and constrained AI.
Projects can be in teams of up to three students except by
special advance permission from the instructor.
Students will prepare an initial project proposal, midterm report, and final report
on the project, and may make an in-class presentation.
Research projects can (and should!) advance your PhD research.

<!-- Students taking the class for 1 credit will be required
to write fewer reviews,
present only one paper,
and will not be required to complete the research project.
The quiz requirement will be the same. -->

# Schedule

[This google doc serves as our schedule.](https://docs.google.com/spreadsheets/d/1qYS6aMa5TyBz1OmN1CT787XdBiAisVg9pACr-XSaN9A/edit?gid=0#gid=0)
A tentative schedule follows.
We may spend more or less time on a topic depending on student interest.

| Date          | Topic                                                   | Required Paper 1                                                                                                          | Required Paper 2                                                                                                                                                                      | Optional / Further Reading                                                                                                                                                                                                                                                               |
| ------------- | ------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1/6/2026**  | Intro: importance of constraints + classical approaches | **Adopt Constraints Over Penalties in Deep Learning** (Ramirez et al., 2025) [[arXiv](https://arxiv.org/abs/2505.20628)]  | **Optimization Learning** (Van Hentenryck, 2025) [[arXiv](https://arxiv.org/abs/2501.03443)]                                                                                          | Chance-constrained optimization notes (Boyd) [[PDF](https://web.stanford.edu/class/ee364a/lectures/chance_constr.pdf)]; Douglas–Rachford splitting perspective [[arXiv](https://arxiv.org/abs/2303.16394)]; Fioretto & Van Hentenryck (2020) [[arXiv](https://arxiv.org/abs/2001.09394)] |
| **1/13/2026** | No class; read ahead                                    | —                                                                                                                         | —                                                                                                                                                                                     | Students select ≥2 papers from Weeks 3–9 for short presentation proposals                                                                                                                                                                                                                |
| **1/20/2026** | Differentiable projections & feasibility layers         | **HardNet: Hard-Constrained Neural Networks** (Min & Azizan, 2025) [[arXiv](https://arxiv.org/abs/2410.10807)]            | **OptNet: Differentiable Optimization as a Layer** (Amos & Kolter, 2017) [[arXiv](https://arxiv.org/abs/1703.00443)]                                                                  | CVXPYLayers [[arXiv](https://arxiv.org/abs/1910.12430)]; DC3; Enforcing Hard Linear Constraints with Decision Rules (Constante-Flores et al., 2025) [[arXiv](https://arxiv.org/abs/2505.13858)]                                                                                          |
| **1/27/2026** | Reinforcement learning with constraints                 | **Trust Region Policy Optimization** (Schulman et al., 2015) [[arXiv](https://arxiv.org/abs/1502.05477)]                  | **Constrained Policy Optimization** (Achiam et al., 2017) [[arXiv](https://arxiv.org/abs/1705.10528)]                                                                                 | Projection-Based CPO (PCPO) [[arXiv](https://arxiv.org/abs/2010.03152)]; FOCOPS [[arXiv](https://arxiv.org/abs/2002.06506)]; Distributionally Robust Constrained RL (Zhang et al., 2024) [[arXiv](https://arxiv.org/abs/2406.15788)]                                                     |
| **2/3/2026**  | Safe RL: Lyapunov & reachability                        | **Lyapunov-based Safe RL** (Chow et al., 2018) [[arXiv](https://arxiv.org/abs/1801.08757)]                                | **Reachability-Based Safety for Learning Systems** (Bansal et al., survey) [[arXiv](https://arxiv.org/abs/2108.06266)]                                                                | Control barrier functions; MPC + learning; robust RL formulations                                                                                                                                                                                                                        |
| **2/10/2026** | LLM alignment                                           | **Training Language Models with Human Feedback (RLHF)** (Ouyang et al., 2022) [[arXiv](https://arxiv.org/abs/2203.02155)] | **Constitutional AI** (Bai et al., 2022) [[arXiv](https://arxiv.org/abs/2212.08073)]                                                                                                  | Safety Representation Ranking (SRR) [[OpenReview](https://openreview.net/forum?id=A3DELRfrKO)]; critiques of reward modeling                                                                                                                                                             |
| **2/17/2026** | Post-training interventions & steering                  | **Constrained Decoding** (Hokamp & Liu, 2017) [[arXiv](https://arxiv.org/abs/1704.07138)]                                 | **Persona Vectors** (Chen et al., 2025) [[arXiv](https://arxiv.org/abs/2507.21509)]                                                                                                   | AlphaEdit [[arXiv](https://arxiv.org/abs/2410.02355)]; Guiding LLMs the Right Way [[arXiv](https://arxiv.org/html/2403.06988v1)]; Surjectivity of Neural Networks [[arXiv](https://arxiv.org/abs/2508.19445)]                                                                            |
| **2/24/2026** | Formal verification                                     | **Vericoding / Verified Code Generation** [[survey](https://arxiv.org/abs/2306.15626)]                                    | **Hilbert: Informal + Formal Proofs** (Varambally et al., 2025) [[arXiv](https://arxiv.org/abs/2509.22819)]                                                                           | Lean-guided LLMs; proof-carrying code; formal methods for agents                                                                                                                                                                                                                         |
| **3/3/2026**  | Declarative programming & tool use                      | **OptiMUS-0.3** (AhmadiTeshnizi et al., 2025) [[arXiv](https://arxiv.org/abs/2407.19633)]                                 | **OptiMind: Teaching LLMs Optimization** (Chen et al., 2025) [[MSR](https://www.microsoft.com/en-us/research/publication/optimind-teaching-llms-to-think-like-optimization-experts/)] | OptiChat [[arXiv](https://arxiv.org/abs/2501.08406)]; LLMs for supply chain decisions [[arXiv](https://arxiv.org/abs/2507.21502)]; Democratizing Optimization with GenAI                                                                                                                 |
| **3/10/2026** | Synthesis & future directions                           | **On Surjectivity of Neural Networks** (Jiang & Haghtalab, 2025) [[arXiv](https://arxiv.org/abs/2508.19445)]              | **GDPval: Economically Grounded Evaluation** (Patwardhan et al., 2025) [[arXiv](https://arxiv.org/abs/2510.04374)]                                                                    | SWE-bench [[arXiv](https://arxiv.org/abs/2310.06770)]; agent configuration constraints [[arXiv](https://arxiv.org/abs/2511.09268)]                                                                                                                                                       |
| **3/18/2026** | (No class; exam period)                                 | —                                                                                                                         | —                                                                                                                                                                                     | —                                                                                                                                                                                                                                                                                        |


<!-- Sign up for presentation slots on the google doc
by adding your name and a link to the paper you'll present.
(Make sure not to choose a paper someone else has already picked!)
We may spend more or less time on a topic depending on student interest. -->

# Presentations

## Outline

1. Intro
    - how does this topic relate to the course goal of enabling safe and constrained AI?
    - what is the core idea?
    - what applications does it target?
2. Literature review
    - what are the important papers and ideas?
    - walk us through the intellectual history
3. Deep dive
    - pick one or two papers, and take us through the main idea and results
    - extract some core mathematical insights, and choose one to explain on the board. could be a theorem or result from the paper, or some older mathematics that motivates the approach. feel free to show how it works on a simple example, like a quadratic objective with linear constraints.
4. Results
    - summary of numerical results from papers
    - do you think the results are good or bad? Are there obvious omissions?
5. Open directions
    - what are the important problems that you think could be addressed with these ideas, but haven't yet been?
    - is there a key challenge that restricts the usefulness of this approach?

You might also loop through 2-5 several times, one for each of the most important papers in your stack.

## An AI-forward protocol

Here's the best workflow I've found for producing good presentations on new topics.

1. Collect a list of papers and authors whose work you admire on the topic.
2. Use that list to prompt a frontier LLM (GPT5, Gemini) to do deep research on the topic and write a report. A prompt might be, 

> Summarize the state of the art in <field>, including work by <authors>. Use only published papers or arxiv papers as references in the final report. 

You might also inject your own biases and interests here.

3. Ask Claude code to download all the references in the report into a folder on your computer. 
4. Read the report, and skim the papers to check that the understanding you gleaned from the report is correct.
5. Upload all the papers to NotebookLM. 
6. Have a conversation with NotebookLM to deepen your understanding of the topic and ask more detailed mathematical questions about the papers.
7. Write a script for a presentation you'd like to give on the topic, noting the high level points you'd want to make, or categories or topics you'd want to hit, or conclusions you'd like to come to. Ask NotebookLM to create a slide deck, using your script as the prompt. Here's a prompt I've used:

> Develop a tutorial review of standard ideas in constrained optimization, in particular lagrangian methods and duality, with an eye towards their use in a modern deep learning setting for a PhD audience already familiar with optimization at the level of Boyd and Vandenberghe. Use a plain, latex beamer style slide template with a white background. All numerical results (in particular, tables and figures) must exactly match the source material and reference the source.

8. Study the materials and practice your presentation. Be meticulous and make sure you believe and can justify every claim on the slides.

## Checklist

In addition to following the above outline (approximately), presentations must include
* quiz (2 questions that are easy to answer from the required reading)
* discussion questions or class activity

before the presentation
* (Monday 11am) email Prof. Udell with an editable draft of slides, quiz questions, and discussion questions
* (Tuesday 1pm) submit a PR to the class git repo with your slides

bring
* power
* anything needed for you to connect to a USB-C or HDMI cable

setup
* projector
* camera
* [zoom](https://stanford.zoom.us/j/6394072382?pwd=bndKcXBpRFdOb2x5VFhuT0kzN1QvQT09)
* share screen
