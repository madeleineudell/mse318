# lec1 agenda

Applications and challenges
- What kinds of AI systems?
- What kinds of constraints

Course design
- overview of proposed topics
- grading and format

Foundational concepts (mathematical review)
- Lagrangian methods
- Proximal/Projection based methods (prototypical example: HardNet)
- Stochastic optimization and chance constraints

Small group discussion

By Friday: sign up for topic
Next week's class: meet with team to discuss papers

# Applications and challenges
- What kinds of AI systems?
- What kinds of constraints

AI systems are being used for all sorts of important applications!

* Deep learning techniques are being used to shortcut traditional solvers and produce faster solutions
    - solving PDEs
        - methods: mostly multilayer perceptrons and variants. keywords: PINNs, SciML, Deep Operator Learning, ...
    - solving large-scale combinatorial optimization problems (which might be encoded as constraint programming problems, or MILPs)
        - classic OR problems (scheduling, routing, supply chain, ...) but make it sound modern, eg with applications in disaster relief, cloud computing, hospital systems, airlines ...
        - methods: mostly graph neural networks
    - solving problems in energy systems, which involve both PDEs (physical laws, like AC-OPF) *and* binary variables (which generators to turn on, or which subsystems to disconnect)
        - methods: all of the above and more, also semidefinite programming relaxations and unrolled optimization loops
    These problems often involve hard constraints that may be difficult to satisfy (physical laws, precedence constraints). Feasibility is often much harder than optimality
    * Beware of papers that test only on "easy" NP-hard problems (eg TSP, where there are good approximation algorithms, and feasibility is easy)

* LLMs are being used to generate emails, reports, summaries, responses to internet searches, cyber attacks, plans for wars, recipes, tariff rates, suicides, etc
    - how can we make sure the LLM responses are 
        - factual --- except where that reveals dangerous information
        - polite --- or at least, meets the style requirements the user intends
        - optimal --- but what even is the objective, or constraints? the problem input is natural language!
        - ...?

* Robotics:
    applications: self-driving cars, drones, bipedal robots, ...
    constraints:
    - avoid obstacles, especially people
    - remain in safe operating regime
    - don't break laws
anecdote: my in-law's Waymo sat on the Embarcadero train tracks in SF and blocked a train because it could see a red light (that wasn't for it)

As we've seen in the context of self-driving cars, getting from 99% accuracy to 99.99999999999% accuracy is critical for 
systems that will be allowed to operate autonomously. And extremely hard!

# Course design
- overview of proposed topics
- grading and format

# Foundational concepts (mathematical review)
- Lagrangian methods
- Proximal/Projection based methods (prototypical example: HardNet)
- Stochastic optimization and chance constraints

# Small group discussion

* What aspects of constrained and safe AI interest you? Could be an application area or a technique you want to learn more about?
* Pick an application of AI where safety or constraints matter.

# Applications and challenges

From Van Henteryk: (dichotomy is not clear to me)
(1) constrained optimization problems, which are characterized by constraints modeling relations among features of each data sample, and 
- physics: Ohm's law, Kirchoff's law, Navier Stokes
(2) problems that require specific properties to hold on the predictor itself, called constrained predictor problems
- monotonicity (eg, price increases with demand)
- fairness (eg, no disparate impact)

From ICLR submission ADVANCING LLM SAFE ALIGNMENT
Recent large language models (LLMs) have achieved remarkable capabilities across a wide range of
tasks. However, this power comes with serious safety and alignment concerns (Wang et al., 2024b; Ji
et al., 2023; Anwar et al., 2024). Trained over massive pretrained corpora, LLMs have the potential
to generate biased, toxic, or harmful content, and adversarial jailbreak prompts can coax an LLM
into violating its own content guidelines (Liu et al., 2023; Wei et al., 2023a; Zou et al., 2023b).
These vulnerabilities persist despite extensive alignment efforts during pre-training and post-training
phases (Bai et al., 2022; Dai et al., 2024; Korbak et al., 2023). In practice, the potential for harmful
outputs and the ability to bypass built-in safeguards raise significant concerns for deploying LLMs in
real-world applications.

OPF:
The Optimal Power Flow (OPF) problem determines the best generator
dispatch of minimal cost that meets the demands while satisfying the physical and engineering constraints  of the power system [11].
Typical constraints include the non-linear non-convex AC power flow equations, Kirchhoff’s current
laws, voltage bounds, and thermal limits. The OPF problem is a fundamental building bock of
many applications, including security-constrained OPFs [31]), optimal transmission switching [19],
capacitor placement [6], and expansion planning [33] which are of fundamental importance for
ensuring a reliable and efficient behavior of the energy system.

LLMs:
- polite
- "brand-safe" consistent with brand identity
- no sycophantism
- casual / detailed
- refuse to provide instructions for weapons, self-harm
- don't contribute to anxiety, depression, delusional spirals



# Prompts 

Develop a tutorial on AI methods to guarantee satisfaction of hard constraints, in particular lagrangian methods and repair methods.
The Van Henteryk paper provides a high level roadmap to the field.
You can use the Fioretto paper as an example of lagrangian methods, and the HardNet paper as an example of repair methods.
The presentation should target for a PhD audience already familiar with optimization at the level of Boyd and Vandenberghe,
and follow Boyd and Vandenberghe notation when possible.
Walk us through the mathematics necessary to understand the strategy,
and when it succeeds or fails.
Use a plain, latex beamer style slide template with a white background. 
All numerical results (in particular, tables and figures) must exactly match the source material and reference the source.
