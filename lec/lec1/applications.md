# Lecture notes: Introduction

How can we design AI systems that are not only powerful but also provably safe and trustworthy? 
This advanced PhD seminar surveys algorithmic methods to enforce hard constraints in machine learning, reinforcement learning, and generative AI. 
Topics include classical constrained optimization (Lagrangian methods, robust and stochastic programming), 
safe reinforcement learning (trust regions, Lyapunov functions, reachability), 
hybrid ML-optimization methods (projection networks, solver-in-the-loop architectures), 
and alignment strategies for large language models (fine-tuning, model editing, tool use, and interactive alignment). 
We will consider applications to robotics, finance, healthcare, energy, and personal AI assistants. 

---

## 1. Solver-Shortcutting with Guarantees

**Replacing or accelerating classical solvers while preserving feasibility**

![Image](https://upload.wikimedia.org/wikipedia/commons/9/90/Physics-informed_nerural_networks.png)

![Image](https://raw.githubusercontent.com/amazon-science/co-with-gnns-example/955489d90df286ed9a29e939f364a7cad3706dd1/media/fig3_flowchart_v2.png)

![Image](https://dyh28w2y3a9av.cloudfront.net/public/SGWEB0164/SGWEB0164.jpg)

![Image](https://www.frontiersin.org/files/Articles/549457/fenrg-08-00161-HTML/image_m/fenrg-08-00161-g001.jpg)

### 1.1 PDEs and Scientific Computing

**Applications**

* Fluid dynamics, climate models, materials science, battery modeling
* Inverse problems in physics and biology

**Constraints**

* Physical laws (PDEs, conservation, boundary conditions)
* Stability and long-time accuracy

**Methods**

* PINNs, SciML, Deep Operator Networks, neural Galerkin methods
* Differentiable solvers, unrolled optimization

**Key lesson**

> Approximate *solutions* are easy; approximate *physics* is dangerous. Constraint violations may be subtle but catastrophic.

---

### 1.2 Combinatorial Optimization & OR (Modernized)

**Applications**

* Disaster relief logistics, airline crew scheduling, hospital resource allocation
* Cloud computing (job placement, power-aware scheduling), supply chains

**Constraints**

* Precedence, capacity, integrality, fairness, regulatory constraints
* Feasibility often NP-hard; infeasible solutions are useless

**Methods**

* Graph neural networks, learning-to-branch, learning heuristics
* Neural warm starts for MILPs, solver-in-the-loop systems

**Cautionary note**

> Beware benchmarks where feasibility is trivial (e.g., TSP). Real systems fail because *constraints interact*, not because objectives are hard.

---

### 1.3 Energy Systems (Hybrid Continuous–Discrete)

**Applications**

* Unit commitment, grid reconfiguration, demand response
* Resilience under faults or attacks

**Constraints**

* AC power flow equations (nonconvex PDEs)
* Binary on/off decisions, safety margins, N-1 reliability

**Methods**

* SDP relaxations, learned surrogates with feasibility recovery
* Projection networks, unrolled OPF solvers

**Why it matters**

> Energy systems make explicit that *feasibility dominates optimality*: violating physics or safety constraints is unacceptable, even briefly.

---

## 2. Safe Reinforcement Learning & Autonomous Systems

**Learning to act without violating constraints during learning or deployment**

![Image](https://www.mdpi.com/sensors/sensors-24-03139/article_deploy/html/images/sensors-24-03139-g005.png)

![Image](https://cdn.shopify.com/s/files/1/0567/9582/4198/files/Screenshot_2025-04-07_at_12.34.22_PM.png?v=1744043828)

![Image](https://www.autelpilot.com/cdn/shop/articles/liteplus-obstacle-avoidance_1274x578.png?v=1677575610)

![Image](https://www.researchgate.net/publication/348294271/figure/fig1/AS%3A977180502786048%401609989395771/Forward-Reachability-Analysis-The-objective-is-to-compute-the-blue-sets-RtX-0-to.png)

### 2.1 Robotics & Autonomous Vehicles

**Applications**

* Self-driving cars, drones, bipedal and humanoid robots

**Constraints**

* Collision avoidance (especially humans)
* Actuator limits, balance, thermal constraints
* Traffic laws and social norms

**Methods**

* Trust-region methods (TRPO-style)
* Lyapunov-based constraints, control barrier functions
* Reachability and Hamilton–Jacobi safety analysis

**Anecdote**

* A Waymo vehicle blocking train tracks illustrates *constraint mis-specification*: the system obeyed a red light constraint that was irrelevant to its context.

**Key insight**

> 99% accuracy is failure. Safety-critical systems demand error rates closer to hardware fault tolerances.

---

## 3. LLMs, Generative Models, and Alignment

**When the “optimization problem” is implicit, ambiguous, or adversarial**

![Image](https://miro.medium.com/1%2AwHBCLbrP9pwgAkU5kO3j0Q.png)

![Image](https://substackcdn.com/image/fetch/%24s_%212xQG%21%2Cf_auto%2Cq_auto%3Agood%2Cfl_progressive%3Asteep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fa7192a6e-1f78-4a7f-9390-155462166248_1400x1000.png)

![Image](https://cdn.sanity.io/images/7m9jw85w/production/51fec5920633a3007410529f10af91223e39f371-3343x1465.png?w=3343)

![Image](https://www.spectrumlabsai.com/hs-fs/hubfs/Pillar%20Pages/ai-based%20content%20moderation.jpg)

### 3.1 Personal and Professional AI Assistants

**Applications**

* Email drafting, reports, search, planning, coding, decision support

**Constraints**

* Factuality (except where disclosure is unsafe)
* Style, tone, politeness, legal compliance
* Non-generation of harmful or manipulative content

**Why this is hard**

* Inputs are natural language → objectives and constraints are latent
* Tradeoffs are implicit, user-dependent, and often underspecified

**Methods**

* Fine-tuning with constraints, RLHF variants
* Model editing, tool use, verification and retrieval
* Interactive alignment (user-in-the-loop constraints)

**Core research question**

> How do we specify, enforce, and *verify* constraints when the task itself is ill-posed?

---

## 4. Cross-Cutting Themes for the Course

These unify the applications above and motivate the technical content.

### Feasibility > Optimality

* In safety-critical systems, infeasible ≡ unacceptable
* Many ML benchmarks invert this priority

### Specification Is the Bottleneck

* Most failures are not optimization failures, but *constraint modeling failures*

### Learning + Optimization Is Inevitable

* Pure ML struggles with hard constraints
* Pure optimization struggles with scale and uncertainty
  → Hybrid architectures are needed for real-world deployment

### Verification and Guarantees Matter

* As autonomy increases, post-hoc evaluation is insufficient
* Provable bounds, certificates, and reachability analysis become central