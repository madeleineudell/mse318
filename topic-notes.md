# LLM alignment

# Model editing and safety interventions

From https://arc.net/l/quote/eqvnkokr:
A common strategy is decoding-time intervention, which redirects the decoding logic of the LLM during
inference, through token distributions (Xu et al., 2024a; Banerjee et al., 2025) or safe prompts (Xie
et al., 2023; Wei et al., 2023b; Zheng et al., 2024). For example, SafeDecoding (Xu et al., 2024a)
adjusts the token distribution toward safe response distributions during decoding, while in-context
defense (ICD) (Wei et al., 2023b) aligns the generation distributions to safe contexts with demonstrations. Such interventions can introduce a trade-off between safety and fluency: altering the
decoding process may degrade the model’s natural performance on benign inputs or increase
inference cost. Meanwhile, post-processing-based defenses apply LLM-as-a-Judge to inspect the
harmfulness of LLMs (Inan et al., 2023; Mazeika et al., 2024). Unfortunately, recent studies have
shown that LLM-based safety judges are often overcautious: they flag many benign prompts as
unsafe (so-called over-refusal) (Panda et al., 2024; Xie et al., 2025). This unreliability, i.e., high
false-positive rates, limits their practical use, as it can render the model unhelpful even on innocuous
tasks.