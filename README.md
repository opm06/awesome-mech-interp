# Awesome Mechanistic Interpretability [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

I've curated this list for two readers: the grad student or researcher who wants a complete map of the field, and the newcomer who needs an on-ramp from "what is a transformer?" to running their first activation patching experiment. If you're in the latter camp, begin with the [Start Here](#start-here) section. Every section after that opens with foundational reading and builds outward.

I've tried to keep this list narrow, covering work that engages with model internals: circuits, features, sparse decompositions, causal interventions, and activation steering grounded in features. Post-hoc XAI methods, behavioral evaluation, and probing that doesn't connect to internals are out of scope.

## Contents

- [Start Here](#start-here)
- [Prerequisites: Transformers from Scratch](#prerequisites-transformers-from-scratch)
- [Field Guides, Glossaries, and Career](#field-guides-glossaries-and-career)
- [Courses and Curricula](#courses-and-curricula)
- [Foundations: Distill Circuits Thread](#foundations-distill-circuits-thread)
- [Foundations: Transformer Circuits](#foundations-transformer-circuits)
- [Case Studies](#case-studies)
- [Lens Methods](#lens-methods)
- [Causal Methods](#causal-methods)
- [Model Editing and Localization](#model-editing-and-localization)
- [Sparse Autoencoders and Dictionary Learning](#sparse-autoencoders-and-dictionary-learning)
- [Transcoders, Crosscoders, and Beyond SAEs](#transcoders-crosscoders-and-beyond-saes)
- [Circuit Tracing and Attribution Graphs](#circuit-tracing-and-attribution-graphs)
- [Sparse-by-Design and Architecture-Level Interpretability](#sparse-by-design-and-architecture-level-interpretability)
- [Toy Models and Synthetic Tasks](#toy-models-and-synthetic-tasks)
- [Reasoning Interpretability](#reasoning-interpretability)
- [Representations and Linear Structure](#representations-and-linear-structure)
- [Activation Steering](#activation-steering)
- [Vision and Multimodal Mechanistic Interpretability](#vision-and-multimodal-mechanistic-interpretability)
- [Tools and Libraries](#tools-and-libraries)
- [Benchmarks and Datasets](#benchmarks-and-datasets)
- [Surveys and Reviews](#surveys-and-reviews)
- [Open Problems and Research Agendas](#open-problems-and-research-agendas)
- [Talks and Podcasts](#talks-and-podcasts)
- [Contributing](#contributing)
- [License](#license)

## Start Here

A short ordered reading path for people new to the field. Work through these and you will be able to read the rest of this list.

1. [The Illustrated Transformer](https://jalammar.github.io/illustrated-transformer/). Visual introduction to attention and transformer structure. Read this before any math.
2. [Mechanistic Interpretability Quickstart Guide](https://www.neelnanda.io/mechanistic-interpretability/quickstart-old). Neel Nanda's compressed orientation to the field, written so a confused beginner can leave with a working mental model.
3. [A Barebones Guide to Mechanistic Interpretability Prerequisites](https://www.neelnanda.io/mechanistic-interpretability/prereqs). Practical checklist of skills you need: ML basics, transformers, coding, research habits.
4. [Learn Mechanistic Interpretability](https://learnmechinterp.com/). Open-source textbook covering transformer internals, interpretability techniques, and frontier research. The single best linear spine for the field.
5. [ARENA Chapter 1: Transformers and Mechanistic Interpretability](https://www.arena.education/chapter1). Hands-on curriculum that pairs each technique with code. Treat this as a coding sprint, not passive reading.
6. [Mechanistic Interpretability Glossary](https://www.neelnanda.io/mechanistic-interpretability/glossary). Reference for residual stream, induction heads, logit lens, path patching, superposition, and other terms you will hit repeatedly.
7. [Concrete Steps to Get Started in Transformer Mechanistic Interpretability](https://www.neelnanda.io/mechanistic-interpretability/getting-started). What to actually do after the quickstart, biased toward writing code and reading papers in the right order.

## Prerequisites: Transformers from Scratch

If transformers themselves are still fuzzy, build mechanical intuition here first.

- [The Illustrated GPT-2](https://jalammar.github.io/illustrated-gpt2/). Visual explanation of decoder-only language models and token prediction.
- [The Annotated Transformer](https://nlp.seas.harvard.edu/annotated-transformer/). Line-by-line transformer implementation. Read when you want the math and the code to connect.
- [The Annotated Transformer (GitHub)](https://github.com/harvardnlp/annotated-transformer). Code companion you can clone and run.
- [minGPT](https://github.com/karpathy/minGPT). Karpathy's compact PyTorch GPT implementation. Useful for building a felt sense of how a GPT is put together.
- [microgpt](https://karpathy.github.io/2026/02/12/microgpt/). Single-file GPT and autograd system for a truly minimal end-to-end stack.
- [But what is a GPT? Visual intro to transformers](https://youtu.be/wjZofJX0v4M). 3Blue1Brown video introducing transformer mechanics.
- [Attention in transformers, visually explained](https://youtu.be/eMlx5fFNoYc). 3Blue1Brown visual explanation of attention.
- [How might LLMs store facts](https://youtu.be/9-Jl0dxWQs8). 3Blue1Brown video on MLP-based fact storage.

## Field Guides, Glossaries, and Career

Maps of the field, opinionated reading lists, and guidance on becoming a researcher.

- [An Extremely Opinionated Annotated List of My Favourite Mechanistic Interpretability Papers](https://www.neelnanda.io/mechanistic-interpretability/favourite-papers). Neel Nanda's annotated canon. See also the [v2 update](https://www.alignmentforum.org/posts/NfFST5Mio7BCAQHPA/an-extremely-opinionated-annotated-list-of-my-favourite-1).
- [How to Become a Mechanistic Interpretability Researcher](https://www.alignmentforum.org/posts/jP9KDyMkchuv6tHwm/how-to-become-a-mechanistic-interpretability-researcher). Practical guide to building the skills and portfolio you actually need.
- [A Pragmatic Vision for Interpretability](https://www.lesswrong.com/posts/StENzDcD3kpfGJssR/a-pragmatic-vision-for-interpretability). Strategic essay on what interpretability research should prioritize. Cross-posted on the [EA Forum](https://forum.effectivealtruism.org/posts/Tm2vqRZ6YMpiftCs4/a-pragmatic-vision-for-interpretability).
- ["Mechanistic?"](https://arxiv.org/abs/2410.09087). Position paper clarifying the different uses of the word "mechanistic" in interpretability and which one this list cares about.
- [ML Alignment and Theory Scholars (MATS)](https://www.matsprogram.org/). Research and education program that places scholars with alignment and interpretability mentors. Common entry point for new researchers.

## Courses and Curricula

Structured programs and university-style courses.

- [ARENA Chapter 1: Transformers and Mechanistic Interpretability](https://www.arena.education/chapter1). Serious hands-on curriculum. Use this as a main coding sprint.
- [ARENA Intro to Mechanistic Interpretability](https://learn.arena.education/chapter1_transformer_interp/02_intro_mech_interp/). Exercise-based introduction using TransformerLens.
- [ARENA 3.0 GitHub](https://github.com/callummcdougall/ARENA_3.0). Source curriculum repository.
- [Understanding LLMs: Mechanistic Interpretability Lecture](https://cogsciprag.github.io/Understanding-LLMs-course/lectures/10-mechanistic-interpretability.html). University lecture covering logit lens, residual stream analysis, activation patching, circuit analysis, and SAEs.
- [BlueDot AI Safety: Unit 6, Mechanistic Interpretability](https://bluedot.org/courses/alignment/6). AI-safety-oriented introduction with curated readings, including introductory essays and classic circuits material.
- [Introduction to Mechanistic Interpretability, Johns Hopkins](https://ep.jhu.edu/courses/705771-introduction-to-mechanistic-interpretability/). Formal course page. Useful for seeing how the field is taught in a university setting.
- [EACL 2024: Transformer-specific Interpretability](https://projects.illc.uva.nl/indeep/tutorial/). EACL tutorial on transformer-specific interpretability methods and case studies.
- [Mechanistic Interpretability Workshop ICML 2024](https://icml2024mi.pages.dev/). Recorded talks from the field's main workshop.
- [BlackboxNLP](https://blackboxnlp.github.io/). Long-running EMNLP workshop on analyzing and interpreting neural networks. The internals-focused subset is in scope here.

## Foundations: Distill Circuits Thread

The classic visual-circuits work in convnets. Slow, beautiful, and still load-bearing for how the field thinks about features.

- [Feature Visualization](https://distill.pub/2017/feature-visualization). How to generate examples that reveal what neurons, channels, or layers respond to.
- [The Building Blocks of Interpretability](https://distill.pub/2018/building-blocks). Feature visualization, activation atlases, and how to inspect internal representations.
- [Activation Atlas](https://distill.pub/2019/activation-atlas). Large-scale feature visualization for mapping neural network activation space.
- [Circuits Thread](https://distill.pub/2020/circuits). The foundational thread treating neural networks as collections of interpretable circuits.
- [Zoom In: An Introduction to Circuits](https://distill.pub/2020/circuits/zoom-in). The best conceptual bridge from neuron visualization to circuit-level analysis.
- [Early Vision](https://distill.pub/2020/circuits/early-vision). Case studies in early vision circuits and how low-level features compose.
- [Curve Detectors](https://distill.pub/2020/circuits/curve-detectors). Detailed reverse engineering of curve-detecting circuits.
- [Naturally Occurring Equivariance](https://distill.pub/2020/circuits/equivariance). How networks represent transformed versions of features.
- [Visualizing Weights](https://distill.pub/2020/circuits/visualizing-weights). What you can learn by inspecting weights directly.
- [Branch Specialization](https://distill.pub/2020/circuits/branch-specialization). Large-scale specialization in network branches.
- [Weight Banding](https://distill.pub/2020/circuits/weight-banding). A specific structural phenomenon in network weights.

## Foundations: Transformer Circuits

The Anthropic transformer circuits canon. Read these in order if you read nothing else.

- [Transformer Circuits Thread](https://transformer-circuits.pub/). The hub. Bookmark it.
- [A Mathematical Framework for Transformer Circuits](https://transformer-circuits.pub/2021/framework/index.html). Attention-only transformer framework, residual stream thinking, path decomposition. The single most cited paper in this list.
- [In-context Learning and Induction Heads](https://transformer-circuits.pub/2022/in-context-learning-and-induction-heads/index.html). Identifies induction heads and connects them to in-context learning.
- [Induction Heads Illustrated](https://www.lesswrong.com/posts/TvrfY4c9eaGLeyDkE/induction-heads-illustrated). Accessible visual explanation of induction heads, copying behavior, and the AB...AB pattern.
- [How Transformers Implement Induction Heads](https://arxiv.org/html/2410.11474v1). Later technical analysis of induction-head implementation. Read after the original.
- [Toy Models of Superposition](https://transformer-circuits.pub/2022/toy_model/index.html). Foundational paper on superposition, polysemanticity, and why neurons are often not clean units of meaning.
- [Mechanistic Interpretability, Variables, and the Importance of Interpretable Bases](https://www.transformer-circuits.pub/2022/mech-interp-essay). Conceptual essay on reverse engineering, variables, and why basis choice matters.
- [Softmax Linear Units](https://transformer-circuits.pub/2022/solu/index.html). Architectural experiment to make MLP neurons more interpretable.
- [Privileged Bases in the Transformer Residual Stream](https://transformer-circuits.pub/2023/privileged-basis/index.html). When residual-stream bases are or are not meaningful.
- [Superposition, Memorization, and Double Descent](https://transformer-circuits.pub/2023/toy-double-descent/index.html). Connects superposition, memorization, and double descent in toy models.
- [Polysemanticity and Superposition in Large Language Models](https://arxiv.org/abs/2210.01892). Polysemanticity and superposition as explanations of neuron behavior in LLMs.
- [Thinking Like Transformers](https://arxiv.org/abs/2106.06981). Introduces RASP, a programming language for the kinds of computations transformers can perform.
- [Transformer Circuits Updates: March 2024](https://transformer-circuits.pub/2024/march-update/index.html), [July 2024](https://transformer-circuits.pub/2024/july-update/index.html), [April 2025](https://transformer-circuits.pub/2025/april-update/index.html). Research updates worth scanning to see where the team is pointing.

## Case Studies

End-to-end reverse engineering of specific behaviors. Treat these as worked examples of the methodology.

- [Interpretability in the Wild: A Circuit for Indirect Object Identification in GPT-2 Small](https://arxiv.org/abs/2211.00593). The landmark IOI paper. Required reading.
- [Walkthrough of A Circuit for Indirect Object Identification](https://www.neelnanda.io/mechanistic-interpretability/walkthrough-ioi). Explanatory walkthrough if the paper feels dense.
- [Progress Measures for Grokking via Mechanistic Interpretability](https://arxiv.org/abs/2301.05217). Reverse engineers modular addition in a grokking setting and shows how structure changes before test loss improves.
- [Grokking Paper Companion](https://www.neelnanda.io/grokking-paper). Companion explanation for the grokking work.
- [Reverse Engineering Modular Addition Walkthrough](https://www.neelnanda.io/mechanistic-interpretability/modular-addition-walkthrough). Practical walkthrough of the modular-addition circuit.
- [The Clock and the Pizza: Two Stories in Mechanistic Explanation of Neural Networks](https://arxiv.org/abs/2306.17844). Two contrasting mechanistic explanations of how networks solve modular addition.
- [Emergent World Representations: Exploring a Sequence Model Trained on a Synthetic Task](https://arxiv.org/abs/2210.13382). The Othello-GPT paper. Does a sequence model learn an internal board state?
- [Actually, Othello-GPT Has a Linear Emergent World Representation](https://www.neelnanda.io/mechanistic-interpretability/othello). Follow-up arguing for a linear world representation.
- [Othello World GitHub](https://github.com/likenneth/othello_world). Codebase for the Othello-GPT experiments.
- [How does GPT-2 Compute Greater-Than? Interpreting Mathematical Abilities in a Pre-trained Language Model](https://arxiv.org/abs/2305.00586). Reverse engineers the greater-than circuit.
- [Copy Suppression: Comprehensively Understanding an Attention Head](https://arxiv.org/abs/2310.04625). End-to-end reverse engineering of a copy-suppression head.
- [Successor Heads: Recurring, Interpretable Attention Heads In The Wild](https://arxiv.org/abs/2312.09230). Attention heads that compute next-element-in-ordinal-sequence operations.
- [Circuit Component Reuse Across Tasks in Transformer Language Models](https://arxiv.org/html/2310.08744v3). Are circuit components reused across tasks, or task-specific?
- [Universal Neurons in GPT2 Language Models](https://arxiv.org/abs/2401.12181). Identifies universal neurons that recur across independently trained GPT-2 models.
- [Fine-Tuning Enhances Existing Mechanisms: A Case Study on Entity Tracking](https://arxiv.org/abs/2402.14811). Fine-tuning amplifies pre-existing circuits rather than building new ones.
- [Identifying Semantic Induction Heads to Understand In-Context Learning](https://arxiv.org/abs/2402.13055). Induction heads that operate over semantic relations.
- [Forbidden Facts: An Investigation of Competing Objectives in Llama-2](https://arxiv.org/abs/2312.08793). Internal mechanisms of competing objectives under forbidden-fact prompts.
- [Competition of Mechanisms: Tracing How Language Models Handle Facts and Counterfactuals](https://arxiv.org/abs/2402.11655). Competing internal mechanisms for facts versus counterfactuals.
- [Talking Heads: Understanding Inter-layer Communication in Transformer Language Models](https://arxiv.org/abs/2406.09519). How attention heads communicate across layers via the residual stream.
- [Confidence Regulation Neurons in Language Models](https://arxiv.org/abs/2406.16254). Neurons that regulate output confidence.
- [Context versus Prior Knowledge in Language Models](https://arxiv.org/abs/2404.04633). Mechanistic balance between context and parametric prior knowledge.
- [Mechanistic Understanding and Mitigation of Language Model Non-Factual Hallucinations](https://arxiv.org/abs/2403.18167). Where non-factual hallucinations originate inside LMs.
- [Finding Neurons in a Haystack: Case Studies with Sparse Probing](https://arxiv.org/abs/2305.01610). Sparse probing to find feature-encoding neurons.
- [INSIDE: LLMs' Internal States Retain the Power of Hallucination Detection](https://arxiv.org/abs/2402.03744). Internal hidden states as a signal for hallucination detection.
- [How Alignment and Jailbreak Work: Explain LLM Safety through Intermediate Hidden States](https://arxiv.org/abs/2406.05644). Mechanistic study of alignment and jailbreaks via intermediate states.
- [What Makes and Breaks Safety Fine-tuning? Mechanistic Study](https://arxiv.org/abs/2407.10264). How safety fine-tuning reshapes internal representations.
- [A Mechanistic Understanding of Alignment Algorithms: A Case Study on DPO and Toxicity](https://arxiv.org/abs/2401.01967). How DPO reshapes toxicity-related internals.

## Lens Methods

Techniques for reading information out of intermediate model states. Useful diagnostics, weaker as causal claims.

- [Interpreting GPT: The Logit Lens](https://www.lesswrong.com/posts/AcKRB8wDpdaN6v6ru/interpreting-gpt-the-logit-lens). The classic. Projects intermediate residual-stream states into vocabulary space.
- [Eliciting Latent Predictions from Transformers with the Tuned Lens](https://arxiv.org/abs/2303.08112). Improves on logit lens by training translators from intermediate representations to output distributions.
- [LearnMechInterp: Logit Lens and Tuned Lens](https://learnmechinterp.com/topics/logit-lens-and-tuned-lens/). Practical explanation of both lens methods and their limitations.
- [Logit Prisms](https://neuralblog.github.io/logit-prisms/). Decomposes logits into interpretable additive contributions.
- [Patchscopes: A Unifying Framework for Inspecting Hidden Representations of Language Models](https://arxiv.org/abs/2401.06102). Decodes hidden representations by patching them into prompt-driven inspections.
- [Backward Lens: Projecting Language Model Gradients into the Vocabulary Space](https://arxiv.org/abs/2402.12865). Projects gradients into vocabulary space to interpret learning signals.
- [Interpreting Neural Networks through the Polytope Lens](https://arxiv.org/abs/2211.12312). Reframes interpretation through polytopes induced by piecewise-linear activations.

## Causal Methods

Interventions that establish what model components actually compute, rather than what they correlate with.

- [Attribution Patching](https://www.neelnanda.io/mechanistic-interpretability/attribution-patching). Gradient-based approximation of activation patching. Makes circuit discovery cheap.
- [LearnMechInterp: Attribution Patching](https://learnmechinterp.com/topics/attribution-patching/). Practical treatment of attribution patching and how to use it responsibly.
- [Towards Automated Circuit Discovery for Mechanistic Interpretability](https://arxiv.org/abs/2304.14997). Introduces ACDC, an automated approach to candidate circuits.
- [Attribution Patching Outperforms Automated Circuit Discovery](https://arxiv.org/abs/2310.10348). Empirical comparison.
- [AtP*: An Efficient and Scalable Method for Localizing LLM Behaviour to Components](https://arxiv.org/abs/2403.00745). Reliability and scalability improvements on attribution patching.
- [Localizing Model Behavior with Path Patching](https://arxiv.org/abs/2304.05969). Path patching as a way to localize behavior to specific computational paths.
- [Towards Best Practices of Activation Patching in Language Models: Metrics and Methods](https://arxiv.org/abs/2309.16042). Methodological study of how to do patching well.
- [Causal Scrubbing: A Method for Rigorously Testing Interpretability Hypotheses](https://www.alignmentforum.org/posts/JvZhhzycHu2Yd57RN/causal-scrubbing-a-method-for-rigorously-testing). Rigorously tests whether a proposed model of computation matches the real network.
- [Causal Scrubbing Results on Induction Heads](https://www.lesswrong.com/posts/j6s9H9SHrEhEfuJnq/causal-scrubbing-results-on-induction-heads). Applies causal scrubbing to induction-head hypotheses.
- [Causal Abstraction for Faithful Model Interpretation](https://arxiv.org/abs/2301.04709). Theoretical foundation connecting causal abstraction to patching and scrubbing. Journal version: [JMLR](https://jmlr.org/papers/v26/23-0058.html).
- [Causal Mediation Analysis for Interpreting Neural NLP](https://arxiv.org/abs/2004.12265). Earlier causal mediation work used in causal tracing traditions.
- [Interpretability at Scale: Identifying Causal Mechanisms in Alpaca](https://arxiv.org/abs/2305.08809). Boundless DAS for identifying causal mechanisms at scale.
- [Hypothesis Testing the Circuit Hypothesis in LLMs](https://arxiv.org/abs/2410.13032). Formal tests of the circuit hypothesis.
- [Information Flow Routes: Automatically Interpreting Language Models at Scale](https://arxiv.org/abs/2403.00824). Automatically traces information flow routes through transformer components.
- [Have Faith in Faithfulness: Going Beyond Circuit Overlap When Finding Model Mechanisms](https://arxiv.org/abs/2403.17806). Improves circuit-finding faithfulness beyond simple overlap metrics.
- [Functional Faithfulness in the Wild: Circuit Discovery with Differentiable Computation Graph Pruning](https://arxiv.org/abs/2407.03779). Differentiable pruning over computation graphs to find circuits.
- [Is This the Subspace You Are Looking For? An Interpretability Illusion for Subspace Activation Patching](https://arxiv.org/abs/2311.17030). A cautionary illusion that can arise from subspace activation patching.
- [Interpretability Illusions in the Generalization of Simplified Models](https://arxiv.org/abs/2312.03656). Simplified interpretability models can produce misleading conclusions.
- [Missed Causes and Ambiguous Effects: Counterfactuals Pose Challenges for Interpreting Neural Networks](https://arxiv.org/abs/2407.04690). Critique of counterfactual-based interpretability methods.
- [Language Models Can Explain Neurons in Language Models](https://openai.com/index/language-models-can-explain-neurons-in-language-models/). Using LLMs to generate and score natural-language explanations of neurons.
- [N2G: A Scalable Approach for Quantifying Interpretable Neuron Representations in Large Language Models](https://arxiv.org/abs/2304.12918). Quantifying interpretable neuron representations as graphs.
- [InversionView: A General-Purpose Method for Reading Information from Neural Activations](https://arxiv.org/abs/2405.17653). Inverts and reads information out of neural activations.
- [The Quest for the Right Mediator: Surveying Mechanistic Interpretability Through the Lens of Causal Mediation Analysis](https://arxiv.org/abs/2408.01416). Reframes the methodology landscape through causal mediation.

## Model Editing and Localization

Localization-as-interpretability, knowledge editing, and the limits of both.

- [Locating and Editing Factual Associations in GPT](https://arxiv.org/abs/2202.05262). The ROME paper. Causal localization plus rank-one editing of factual recall.
- [ROME Project Page](https://rome.baulab.info/). Interactive project page with examples.
- [Dissecting Recall of Factual Associations in Auto-Regressive Language Models](https://arxiv.org/abs/2304.14767). How factual associations are stored and extracted internally.
- [Does Localization Inform Editing? Surprising Differences in Causality-Based Localization vs. Knowledge Editing in Language Models](https://arxiv.org/abs/2301.04213). Localization of facts does not predict where edits succeed.
- [What Does the Knowledge Neuron Thesis Have to Do with Knowledge?](https://arxiv.org/abs/2405.02421). Critical examination of the knowledge neuron thesis.
- [Robust Knowledge Unlearning via Mechanistic Localizations](https://arxiv.org/abs/2405.12856). Uses mechanistic localization for robust unlearning.
- [What Do the Circuits Mean? A Knowledge Edit View](https://arxiv.org/abs/2406.17241). Interprets discovered circuits through the lens of knowledge editing.
- [Model Editing Harms General Abilities of Large Language Models: Regularization to the Rescue](https://arxiv.org/abs/2401.04700). Side effects of ROME-style edits on internal abilities.

## Sparse Autoencoders and Dictionary Learning

The dominant decomposition method of the 2023 to 2025 wave. Read these in order.

- [Towards Monosemanticity: Decomposing Language Models with Dictionary Learning](https://transformer-circuits.pub/2023/monosemantic-features). The paper that put SAEs at the center of the field.
- [Scaling Monosemanticity: Extracting Interpretable Features from Claude 3 Sonnet](https://transformer-circuits.pub/2024/scaling-monosemanticity/). Scales SAEs to a production-scale model.
- [Mapping the Mind of a Large Language Model](https://www.anthropic.com/research/mapping-mind-language-model). Anthropic's accessible overview of scaling monosemanticity.
- [Extracting Concepts from GPT-4](https://openai.com/index/extracting-concepts-from-gpt-4/). OpenAI work on scalable SAEs and concept extraction at GPT-4 scale.
- [Scaling and Evaluating Sparse Autoencoders](https://arxiv.org/abs/2406.04093). OpenAI k-sparse SAE paper with scaling laws and evaluation. PDF: [openai.com](https://cdn.openai.com/papers/sparse-autoencoders.pdf).
- [Gemma Scope: Helping the Safety Community Shed Light on the Inner Workings of Language Models](https://deepmind.google/blog/gemma-scope-helping-the-safety-community-shed-light-on-the-inner-workings-of-language-models/). DeepMind release of open SAEs across Gemma.
- [Gemma Scope: Open Sparse Autoencoders Everywhere All At Once on Gemma 2](https://arxiv.org/abs/2408.05147). Technical paper on JumpReLU SAEs across Gemma sizes and layers.
- [Gemma Scope Documentation](https://ai.google.dev/gemma/docs/gemma_scope). Practical docs for using Gemma Scope.
- [Improving Dictionary Learning with Gated Sparse Autoencoders](https://arxiv.org/abs/2404.16014). Gated SAEs that improve the reconstruction-sparsity tradeoff.
- [Sparse Autoencoders Find Highly Interpretable Features in Language Models](https://arxiv.org/abs/2309.08600). Early result that dictionary learning recovers interpretable features.
- [Interpreting Attention Layer Outputs with Sparse Autoencoders](https://arxiv.org/abs/2406.17759). Trains SAEs on attention layer outputs.
- [Identifying Functionally Important Features with End-to-End Sparse Dictionary Learning](https://arxiv.org/abs/2405.12241). End-to-end training that prioritizes functionally important features.
- [Towards Principled Evaluations of Sparse Autoencoders for Interpretability and Control](https://arxiv.org/abs/2405.08366). Principled evaluation protocols for SAEs.
- [Sparse Autoencoders Match Supervised Features for Model Steering on the IOI Task](https://openreview.net/forum?id=JdrVuEQih5). SAE features match supervised features for steering.
- [Measuring Progress in Dictionary Learning for Language Model Interpretability with Board Game Models](https://arxiv.org/abs/2408.00113). Uses OthelloGPT-style models to benchmark dictionary learning.
- [Understanding and Steering Llama 3 with Sparse Autoencoders](https://www.goodfire.ai/research/understanding-and-steering-llama-3). Goodfire's applied SAE work on Llama 3 with feature interpretation and steering.
- [Mapping the Latent Space of Llama 3.3 70B](https://www.goodfire.ai/research/mapping-latent-spaces-llama). SAE-based feature mapping at larger open-model scale.
- [Goodfire Open Source SAE Announcement](https://www.goodfire.ai/blog/sae-open-source-announcement). Open-source SAE releases.
- [SAE Reconstruction Errors Are (Empirically) Pathological](https://www.lesswrong.com/posts/rZPiuFxESMxCDHe4B/sae-reconstruction-errors-are-empirically-pathological). Empirical study showing SAE errors have pathological downstream effects.
- [Sparse Autoencoders Find Composed Features in Small Toy Models](https://www.lesswrong.com/posts/a5wwqza2cY3W7L9cj/sparse-autoencoders-find-composed-features-in-small-toy). SAEs trained on toy models recover composed rather than atomic features.
- [Research Report: Sparse Autoencoders Find Only 9 of 180 Board State Features in OthelloGPT](https://www.lesswrong.com/posts/BaEQoxHhWPrkinmxd/research-report-sparse-autoencoders-find-only-9-180-board). SAEs recover only a small fraction of ground-truth features.
- [Do Sparse Autoencoders Find "True Features"?](https://www.lesswrong.com/posts/QoR8noAB3Mp2KBA4B/do-sparse-autoencoders-find-true-features). Conceptual investigation of whether SAEs recover the model's true features.
- [Sparse Autoencoders Can Interpret Randomly Initialized Transformers](https://arxiv.org/abs/2501.17727). SAE interpretability can produce convincing-looking features even in random models. Evaluation matters.
- [An Intuitive Explanation of Sparse Autoencoders for Mechanistic Interpretability](https://www.lesswrong.com/posts/CJPqwXoFtgkKPRay8/an-intuitive-explanation-of-sparse-autoencoders-for). Beginner-friendly conceptual explanation.
- [LearnMechInterp: SAELens and Neuronpedia](https://learnmechinterp.com/topics/saelens-and-neuronpedia/). Practical guide to using SAELens and Neuronpedia together.
- [Announcing Neuronpedia](https://www.lesswrong.com/posts/BaEQoxHhWPrkinmxd/announcing-neuronpedia-platform-for-accelerating-research). Motivation and research use for the SAE feature browser.

## Transcoders, Crosscoders, and Beyond SAEs

The next wave of decomposition methods that go past plain SAEs on individual sites.

- [Transcoders Beat Sparse Autoencoders for Interpretability](https://arxiv.org/html/2501.18823v1). Argues transcoders can outperform SAEs for some interpretability objectives.
- [Transcoders Find Interpretable LLM Feature Circuits](https://arxiv.org/abs/2406.11944). Uses transcoders to discover interpretable feature circuits.
- [Cross-Layer Transcoders Collection](https://huggingface.co/collections/mntss/cross-layer-transcoders). Hugging Face collection for cross-layer transcoder models.
- [CLT-Forge](https://arxiv.org/html/2603.21014v1). Tooling and training for cross-layer transcoders.
- [open_cross_layer_transcoder](https://github.com/etredal/open_cross_layer_transcoder). Open implementation for cross-layer transcoder experiments.
- [Sparse Crosscoders for Cross-Layer Features and Model Diffing](https://transformer-circuits.pub/2024/crosscoders/index.html). Anthropic work using sparse crosscoders to study cross-layer features and model differences.
- [Natural Language Autoencoders](https://www.anthropic.com/research/natural-language-autoencoders). Translates model activations into natural-language descriptions. Full paper: [transformer-circuits.pub](https://transformer-circuits.pub/2026/nla/).
- [The Local Interaction Basis: Identifying Computationally-Relevant and Sparsely Interacting Features in Neural Networks](https://arxiv.org/abs/2405.10928). A basis of sparsely interacting, computationally relevant features.

## Circuit Tracing and Attribution Graphs

Frontier methods (2024 to 2026) for tracing computations end to end through attribution graphs.

- [Circuit Tracing: Revealing Computational Graphs in Language Models](https://transformer-circuits.pub/2025/attribution-graphs/methods.html). The Anthropic circuit tracing methodology using attribution graphs and replacement models.
- [On the Biology of a Large Language Model](https://transformer-circuits.pub/2025/attribution-graphs/biology.html). Large-scale case studies applying circuit tracing to Claude 3.5 Haiku.
- [Tracing the Thoughts of a Large Language Model](https://www.anthropic.com/research/tracing-thoughts-language-model). Accessible Anthropic overview of the 2025 circuit-tracing work.
- [Open-Source Circuit Tracing](https://www.anthropic.com/research/open-source-circuit-tracing). Anthropic's open-source release.
- [circuit-tracer](https://github.com/decoderesearch/circuit-tracer). Library for circuit tracing workflows.
- [LearnMechInterp: Circuit Tracing](https://learnmechinterp.com/topics/circuit-tracing/). Practical explanation of the approach.
- [Replicating Circuit Tracing for a Simple Mechanism](https://www.goodfire.ai/research/replicating-circuit-tracing-for-a-simple-mechanism). Goodfire walkthrough that makes circuit tracing concrete.
- [Sparse Feature Circuits: Discovering and Editing Interpretable Causal Graphs in Language Models](https://arxiv.org/abs/2403.19647). Builds interpretable causal graphs over SAE features and uses them for editing.
- [Sparse Autoencoders Enable Scalable and Reliable Circuit Identification in Language Models](https://arxiv.org/abs/2405.12522). SAE-based scalable circuit identification.
- [Automatically Identifying Local and Global Circuits with Linear Computation Graphs](https://arxiv.org/abs/2405.13868). Linear computation graphs over SAE features for local and global circuits.

## Sparse-by-Design and Architecture-Level Interpretability

Train models to be interpretable from the start, rather than decomposing after the fact.

- [Understanding Neural Networks Through Sparse Circuits](https://openai.com/index/understanding-neural-networks-through-sparse-circuits/). OpenAI work on training sparse networks to make circuits legible.
- [Weight-Sparse Transformers](https://arxiv.org/abs/2511.13653). The technical paper behind the sparse-circuits direction.
- [Bilinear MLPs Enable Weight-Based Mechanistic Interpretability](https://arxiv.org/abs/2410.08417). Replacing standard MLPs with bilinear MLPs makes weight inspection tractable.

## Toy Models and Synthetic Tasks

Controlled settings where ground truth is available and methods can be evaluated cleanly.

- [Tracr: Compiled Transformers as a Laboratory for Interpretability](https://arxiv.org/abs/2301.05062). Compiles RASP programs into transformer weights for ground-truth circuits.
- [Learning Transformer Programs](https://arxiv.org/abs/2306.01128). Trains transformers to be mechanically interpretable as discrete programs.
- [A Toy Model of Universality: Reverse Engineering How Networks Learn Group Operations](https://arxiv.org/abs/2302.03025). Reverse engineers how small networks learn group operations.
- [Feature Emergence via Margin Maximization: Case Studies in Algebraic Tasks](https://arxiv.org/abs/2311.07568). How interpretable features emerge through margin maximization.
- [Generating Interpretable Networks Using Hypernetworks](https://arxiv.org/abs/2312.03051). Hypernetworks that generate networks with more interpretable structure.

## Reasoning Interpretability

Mechanistic accounts of multi-step reasoning, chain-of-thought, and planning. The new frontier.

- [Mechanistic Interpretation of Multistep Reasoning](https://arxiv.org/abs/2310.14491). Mechanistic interpretation of how LMs perform multi-step reasoning.
- [A Mechanistic Analysis of a Transformer Trained on a Symbolic Multi-Step Reasoning Task](https://arxiv.org/abs/2402.11917). Reverse engineering of a transformer on symbolic multi-step reasoning.
- [Chain-of-Thought Mechanistic Interpretability with Sparse Autoencoding](https://arxiv.org/abs/2507.22928). SAE-based study of chain-of-thought reasoning.
- [Iteration Head: A Mechanistic Study of Chain-of-Thought](https://arxiv.org/abs/2406.02128). Identifies iteration heads underlying chain-of-thought.
- [Chain of Thought May Be Highly Informative Despite Its "Unfaithfulness"](https://metr.org/blog/2025-08-08-cot-may-be-highly-informative-despite-unfaithfulness/). METR post on interpreting chain-of-thought reliability.
- [FaithCoT-Bench](https://openreview.net/forum?id=lN3yKqqzF1). Benchmark for chain-of-thought faithfulness.
- [Thought Anchors: Which LLM Reasoning Steps Matter?](https://www.alignmentforum.org/posts/iLHe3vLur3NgrFPFy/thought-anchors-which-llm-reasoning-steps-matter). Which reasoning steps are causally important. Bridges chain-of-thought analysis and causal intervention.
- [Unlocking the Future: Exploring Look-Ahead Planning Mechanistic Interpretability in Large Language Models](https://arxiv.org/abs/2406.16033). Mechanistic study of look-ahead planning behavior.
- [Calibrating Reasoning in Language Models with Internal Consistency](https://arxiv.org/abs/2405.18711). Uses internal consistency signals to calibrate reasoning.

## Representations and Linear Structure

Linear representation hypothesis, geometry-of-truth, and what is encoded as a direction in activation space.

- [The Geometry of Truth: Emergent Linear Structure in Large Language Model Representations of True and False Datasets](https://arxiv.org/abs/2310.06824). Truth and falsity as a linear direction in LLM representations.
- [Language Models Linearly Represent Sentiment](https://arxiv.org/abs/2310.15154). Sentiment as a linear direction.
- [Language Models Represent Space and Time](https://arxiv.org/abs/2310.02207). Linear representations of spatial and temporal coordinates.
- [The Geometry of Categorical and Hierarchical Concepts in Large Language Models](https://arxiv.org/abs/2406.01506). Geometric structure of categorical and hierarchical concepts.
- [Function Vectors in Large Language Models](https://arxiv.org/abs/2310.15213). Compact activation vectors that encode in-context functions.
- [Observable Propagation: Uncovering Feature Vectors in Transformers](https://arxiv.org/abs/2406.16291). Method for uncovering feature vectors propagating through transformer layers.
- [Emergent Linear Representations in World Models of Self-Supervised Sequence Models](https://arxiv.org/abs/2309.00941). Linear world-model representations in sequence models.
- [Learned Feature Representations Are Biased by Complexity, Learning Order, Position, and More](https://arxiv.org/abs/2405.05847). Empirical study of biases in learned internal representations.

## Activation Steering

Behavioral control by adding or modifying directions in activation space. Included when the work connects to features or circuits.

- [Activation Addition: Steering Language Models Without Optimization](https://arxiv.org/abs/2308.10248). Steers LM behavior by adding activation vectors derived from contrastive prompts.
- [Steering Llama 2 via Contrastive Activation Addition](https://arxiv.org/abs/2312.06681). Steers Llama 2 by adding contrastive activation directions.
- [Inference-Time Intervention: Eliciting Truthful Answers from a Language Model](https://arxiv.org/abs/2306.03341). Steers LM outputs toward truthful answers via targeted activation interventions.
- [A Language Model's Guide Through Latent Space](https://arxiv.org/abs/2402.14433). Steers and analyzes LM behavior by navigating directions in latent activation space.
- [Multi-property Steering of Large Language Models with Dynamic Activation Composition](https://arxiv.org/abs/2406.17563). Dynamic steering that composes multiple property directions.
- [Activation Steering with SAEs](https://www.lesswrong.com/posts/C5KAZQib3bzzpeyrg/full-post-progress-update-1-from-the-gdm-mech-interp-team). Steers behavior by intervening on individual SAE features.

## Vision and Multimodal Mechanistic Interpretability

Circuits and features in vision transformers, CLIP, VLMs, and diffusion models.

- [Prisma: An Open Source Toolkit for Mechanistic Interpretability in Vision and Video](https://arxiv.org/abs/2504.19475). Toolkit covering vision transformers, SAEs, and many model families.
- [Laying the Foundations for Vision and Multimodal Mechanistic Interpretability](https://www.lesswrong.com/posts/kobJymvvcvhbjWFKe/laying-the-foundations-for-vision-and-multimodal-mechanistic). Motivation and open problems for the area.
- [Towards Multimodal Interpretability: Learning Sparse Interpretable Features in Vision Transformers](https://www.lesswrong.com/posts/bCtbuWraqYTDtuARg/towards-multimodal-interpretability-learning-sparse-2). Trains SAEs on vision transformer activations.
- [A Survey on Mechanistic Interpretability for Multi-Modal Foundation Models](https://arxiv.org/abs/2502.17516). Survey of the subfield.
- [SAELens-V](https://github.com/PKU-Alignment/SAELens-V). SAE tooling for vision and multimodal model interpretability.
- [Llamascopium](https://github.com/OpenMOSS/Llamascopium). Framework for SAEs and frontier variants on Llama-family models.
- [Bridging the VLM and Mech Interp Communities for Multimodal Interpretability](https://www.lesswrong.com/posts/aa5fzGr8JA3pqvhYC/bridging-the-vlm-and-mech-interp-communities-for-multimodal). Community bridge post and reading list.
- [Case Study: Interpreting, Manipulating, and Controlling CLIP with Sparse Autoencoders](https://www.lesswrong.com/posts/iYFuZo9BMvr6GgMs5/case-study-interpreting-manipulating-and-controlling-clip). Worked case study on CLIP with SAEs.
- [Interpreting CLIP's Image Representation via Text-Based Decomposition](https://arxiv.org/abs/2310.05916). Text-based decomposition of CLIP's image representation.
- [Interpreting CLIP with Sparse Linear Concept Embeddings](https://arxiv.org/abs/2402.10376). SpLiCE: sparse linear decomposition of CLIP.
- [Decomposing and Interpreting Image Representations via Text in ViTs Beyond CLIP](https://arxiv.org/abs/2406.01583). Extends text-based decomposition beyond CLIP.
- [Interpreting the Second-Order Effects of Neurons in CLIP](https://arxiv.org/abs/2406.04341). Second-order neuron analysis in CLIP.
- [Sparse Autoencoders Learn Monosemantic Features in Vision-Language Models](https://arxiv.org/abs/2504.02821). SAEs find monosemantic features in VLMs.
- [How Visual Representations Map to Language Feature Space in Multimodal LLMs](https://arxiv.org/pdf/2506.11976). Feature-level mapping from vision to language inside MLLMs.
- [Causal Interpretation of Sparse Autoencoder Features in Vision](https://arxiv.org/abs/2509.00749). Causal interventions on SAE features in vision models.
- [Sparse Autoencoders for Scientifically Rigorous Interpretation of Vision Models](https://arxiv.org/abs/2502.06755). Principled evaluation protocols for SAEs on vision.
- [Analyzing Hierarchical Structure in Vision Models with Sparse Autoencoders](https://arxiv.org/abs/2505.15970). Hierarchical SAE analysis of vision models.
- [Large Multi-modal Models Can Interpret Features in Large Multi-modal Models](https://arxiv.org/abs/2411.14982). LMMs explain LMM features.
- [SAE-V: Interpreting Multimodal Models for Enhanced Alignment](https://arxiv.org/abs/2502.17514). Multimodal SAE work.
- [Universal Sparse Autoencoders: Interpretable Cross-Model Concept Alignment](https://arxiv.org/pdf/2502.03714). SAEs for cross-model concept alignment.
- [Diffusion Lens: Interpreting Text Encoders in Text-to-Image Pipelines](https://arxiv.org/abs/2403.05846). Diffusion-specific lens for text encoders in T2I pipelines.
- [Decoding Vision Transformers: The Diffusion Steering Lens](https://arxiv.org/abs/2504.13763). Steering lens for decoding ViTs.
- [Beyond Logit Lens: Contextual Embeddings for Robust Hallucination Detection and Grounding in VLMs](https://arxiv.org/abs/2411.19187). Better lens methods for VLM hallucinations.
- [Devils in Middle Layers of Large Vision-Language Models: Interpreting, Detecting, and Mitigating Object Hallucinations via Attention Lens](https://www.arxiv.org/abs/2411.16724). Attention-lens analysis of VLM hallucinations.
- [Understanding Multimodal LLMs: The Mechanistic Interpretability of LLaVA in Visual Question Answering](https://arxiv.org/abs/2411.10950). Mechanistic study of LLaVA on VQA.
- [Understanding Information Storage and Transfer in Multi-modal Large Language Models](https://arxiv.org/abs/2406.04236). Where and how MLLMs store and transfer information.
- [Towards Vision-Language Mechanistic Interpretability: A Causal Tracing Tool for BLIP](https://arxiv.org/abs/2308.14179). Causal tracing tool for BLIP.
- [Investigating Mechanisms for In-Context Vision Language Binding](https://arxiv.org/abs/2505.22200). How VLMs bind visual and linguistic information in context.
- [Finding and Editing Multi-Modal Neurons in Pre-Trained Transformers](https://arxiv.org/abs/2311.07470). Multi-modal neurons in pretrained transformers.
- [Multimodal Neurons in Pretrained Text-Only Transformers](https://arxiv.org/abs/2308.01544). Multimodal neurons that emerge even in text-only models.
- [MINER: Mining the Underlying Pattern of Modality-Specific Neurons in Multimodal Large Language Models](https://arxiv.org/abs/2410.04819). Modality-specific neurons in MLLMs.
- [Deciphering Functions of Neurons in Vision-Language Models](https://arxiv.org/abs/2502.18485). Neuron-level interpretation in VLMs.
- [MMNeuron: Discovering Neuron-Level Domain-Specific Interpretation in Multimodal Large Language Model](https://arxiv.org/abs/2406.11193). Domain-specific neurons in MLLMs.
- [What Do VLMs NOTICE? A Mechanistic Interpretability Pipeline for Gaussian-Noise-free Text-Image Corruption and Evaluation](https://arxiv.org/abs/2406.16320). Mechanistic pipeline for VLM corruption evaluation.
- [Mechanistic Interpretability for Steering Vision-Language-Action Models](https://arxiv.org/pdf/2509.00328). Steering VLA models via internals.
- [Textual Steering Vectors Can Improve Visual Understanding in Multimodal Large Language Models](https://arxiv.org/abs/2505.14071). Steering MLLMs via textual steering vectors.
- [Reducing Hallucinations in Vision-Language Models via Latent Space Steering](https://arxiv.org/abs/2410.15778). Latent-space steering to reduce VLM hallucinations.
- [Interpreting and Editing Vision-Language Representations to Mitigate Hallucinations](https://arxiv.org/abs/2410.02762). Editing VLR for hallucination mitigation.
- [Dissecting and Mitigating Diffusion Bias via Mechanistic Interpretability](https://arxiv.org/abs/2503.20483). Mechanistic analysis and editing of diffusion model bias.
- [Sparse Autoencoders Reveal Selective Remapping of Visual Concepts During Adaptation](https://arxiv.org/abs/2412.05276). How visual concepts remap during model adaptation.
- [From What to How: Attributing CLIP's Latent Components Reveals Unexpected Semantic Reliance](https://arxiv.org/abs/2505.20229). SAE attribution of CLIP's latent components.

## Tools and Libraries

Alphabetical within sub-areas. If you do not know where to start, install TransformerLens.

### Core libraries

- [Baukit](https://github.com/davidbau/baukit). PyTorch toolkit for probing, editing, and instrumenting networks.
- [CircuitsVis](https://github.com/TransformerLensOrg/CircuitsVis). Visualization library for attention patterns and circuits views. Installable via [PyPI](https://pypi.org/project/circuitsvis/).
- [NNsight](https://nnsight.net/). Tracing and intervening on internals, including larger models. Source on [GitHub](https://github.com/ndif-team/nnsight). Practical orientation at [LearnMechInterp](https://learnmechinterp.com/topics/nnsight-and-nnterp/).
- [nnterp](https://arxiv.org/abs/2511.14465). Standardized interface for mechanistic interpretability of transformers, focused on clean composable interventions.
- [Penzai](https://github.com/google-deepmind/penzai). JAX library for writing models as legible pytree data structures to support inspection and intervention.
- [pyreft](https://github.com/stanfordnlp/pyreft). Representation finetuning library that edits a small set of internal representations to steer behavior.
- [pyvene](https://stanfordnlp.github.io/pyvene/). Intervention library for PyTorch models. Paper: [arxiv.org](https://arxiv.org/abs/2403.07809).
- [TransformerLens](https://github.com/TransformerLensOrg/TransformerLens). The core Python library for MI of transformer language models. Learn this early. [Docs](https://transformerlensorg.github.io/TransformerLens/), [Tutorials](https://transformerlensorg.github.io/TransformerLens/content/tutorials.html), [Main Demo](https://transformerlensorg.github.io/TransformerLens/generated/demos/Main_Demo.html), [Main Demo on Colab](https://colab.research.google.com/github/neelnanda-io/TransformerLens/blob/main/demos/Main_Demo.ipynb), [intro tutorials](https://github.com/callummcdougall/TransformerLens-intro).

### SAEs and feature browsing

- [Neuronpedia](https://www.neuronpedia.org/). Open platform for browsing, visualizing, and steering features. Essential SAE exploration tool.
- [SAELens](https://github.com/decoderesearch/SAELens). Library for training, loading, and analyzing SAEs. [Tutorial notebook](https://github.com/jbloomAus/SAELens/blob/main/tutorials/tutorial_2_0.ipynb), [training notebook](https://github.com/jbloomAus/SAELens/blob/main/tutorials/training_a_sparse_autoencoder.ipynb), [training docs](https://github.com/jbloomAus/SAELens/blob/main/docs/training_saes.md).
- [sae_vis](https://github.com/callummcdougall/sae_vis). Tool to replicate Anthropic-style SAE feature visualizations.
- [sparse_autoencoder](https://github.com/ai-safety-foundation/sparse_autoencoder). AI Safety Foundation library for SAE experiments.
- [EleutherAI sae](https://github.com/EleutherAI/sae). Top-k SAE implementation following the OpenAI methodology.

### Circuit discovery and tracing

- [Automatic Circuit Discovery (ACDC)](https://github.com/ArthurConmy/Automatic-Circuit-Discovery). Reference implementation of ACDC.
- [circuit-tracer](https://github.com/decoderesearch/circuit-tracer). Library for circuit tracing workflows.

### Lenses, debuggers, and visualizers

- [LLM Transparency Tool](https://github.com/facebookresearch/llm-transparency-tool). Interactive tool for tracing information flow and component contributions inside LLMs.
- [Transformer Debugger](https://github.com/openai/transformer-debugger). OpenAI tool combining automated interpretability with SAEs for inspecting small LM behaviors.
- [Tuned Lens](https://github.com/AlignmentResearch/tuned-lens). Implementation of the tuned lens method.
- [Comgra](https://github.com/FlorianDietz/comgra). Inspect internal tensors of PyTorch networks over training.

### Vision and multimodal

- [ViT-Prisma](https://github.com/Prisma-Multimodal/ViT-Prisma). Mechanistic interpretability for vision and video transformers.
- [SAELens-V](https://github.com/PKU-Alignment/SAELens-V). SAE tooling for vision and multimodal models.
- [LVLM-Interpret](https://arxiv.org/abs/2404.03118). Interpretability tool for large vision-language models.
- [MAIA: Multimodal Automated Interpretability Agent](https://arxiv.org/abs/2404.14394). Automated multimodal interpretability agent.

### Steering libraries

- [repeng](https://github.com/vgel/repeng). Library for generating representation-engineering control vectors.
- [pyreft](https://github.com/stanfordnlp/pyreft). Also listed above. Useful for steering by representation finetuning.

## Benchmarks and Datasets

Datasets and benchmarks designed for evaluating mechanistic interpretability methods themselves.

- [MIB: A Mechanistic Interpretability Benchmark](https://arxiv.org/abs/2504.13151). Benchmark for circuit localization and causal variable identification.
- [InterpBench: Semi-Synthetic Transformers for Evaluating Mechanistic Interpretability Techniques](https://arxiv.org/abs/2407.14494). Semi-synthetic transformers with known ground truth.
- [TinySQL: A Progressive Text-to-SQL Dataset for Mechanistic Interpretability Research](https://arxiv.org/abs/2503.12730). Progressive text-to-SQL dataset designed for MI work.
- [FaithCoT-Bench](https://openreview.net/forum?id=lN3yKqqzF1). Benchmark for chain-of-thought faithfulness.

## Surveys and Reviews

Field-level maps. Read these once you can read papers in the rest of this list.

- [A Practical Review of Mechanistic Interpretability for Transformer-Based Language Models](https://arxiv.org/abs/2407.02646). Broad practical review of transformer MI methods and applications.
- [Mechanistic Interpretability for AI Safety: A Review](https://arxiv.org/abs/2404.14082). Review focused on the AI-safety motivation. Accessible [blog version](https://leonardbereska.github.io/blog/2024/mechinterpreview/).
- [A Survey on Mechanistic Interpretability in AI](https://dl.acm.org/doi/10.1145/3787104). ACM Computing Surveys treatment of the field.
- [A Survey on Sparse Autoencoders for Interpretability](https://arxiv.org/abs/2503.05613). Survey of SAE methods, evaluations, and applications. Published version: [ACL Anthology](https://aclanthology.org/2025.findings-emnlp.89/).
- [A Survey on Mechanistic Interpretability for Multi-Modal Foundation Models](https://arxiv.org/abs/2502.17516). Multimodal MI survey.
- [A Primer on the Inner Workings of Transformer-based Language Models](https://arxiv.org/abs/2405.00208). Internals-focused primer for transformer LMs.
- [Attention Heads of Large Language Models: A Survey](https://arxiv.org/abs/2409.03752). Survey of attention head functions and circuit-relevant findings.
- [Knowledge Mechanisms in Large Language Models: A Survey and Perspective](https://arxiv.org/abs/2407.15017). Survey of how knowledge is stored and retrieved internally.
- [Relational Composition in Neural Networks: A Survey and Call to Action](https://arxiv.org/abs/2407.14662). Survey on relational composition framed as an interpretability agenda.
- [Toward Transparent AI: A Survey on Interpreting the Inner Structures of Deep Neural Networks](https://arxiv.org/abs/2207.13243). Broader survey of methods for interpreting internal structure.
- [Locate, Steer, and Improve: A Practical Survey of Actionable Mechanistic Interpretability in Large Language Models](https://arxiv.org/abs/2601.14004). Survey biased toward actionable MI techniques.

## Open Problems and Research Agendas

What is still unsolved and worth working on.

- [Open Problems in Mechanistic Interpretability](https://arxiv.org/abs/2501.16496). The major open-problems paper. A research map, not beginner material.
- [Open Problems in Mechanistic Interpretability (FAR AI page)](https://far.ai/research/open-problems-in-mechanistic-interpretability). FAR AI write-up.
- [200 Concrete Open Problems in Mechanistic Interpretability](https://www.alignmentforum.org/posts/LbrPTJ4fmABEdEnLf/200-concrete-open-problems-in-mechanistic-interpretability). Large list of concrete project ideas. Use after you have completed at least one replication. Also as a [sequence](https://www.alignmentforum.org/s/yivyHaCAmMJ3CqSyj) and a navigable [Coda doc](https://coda.io/@firstuserhere/open-problems-in-mechanistic-interpretability).
- [Position: An Inner Interpretability Framework for AI Inspired by Lessons from Cognitive Neuroscience](https://arxiv.org/abs/2406.01352). Position paper proposing a neuroscience-informed framework.
- [Interpretability Needs a New Paradigm](https://arxiv.org/abs/2405.05386). Argues for a new paradigm bridging behavioral and mechanistic interpretability.
- [Toward New Frameworks for Studying Model Representations](https://arxiv.org/abs/2402.03855). Position paper on new representation-study frameworks.
- [Black-Box Access Is Insufficient for Rigorous AI Audits](https://arxiv.org/abs/2401.14446). Argues rigorous audits require white-box access to model internals.

## Talks and Podcasts

Conversations and recorded talks worth your time.

- [What Matters Right Now in Mechanistic Interpretability](https://www.youtube.com/watch?v=XZX_CFfVgIc). Neel Nanda's October 2025 talk on current priorities and taste in the field.
- [Neel Nanda on Mechanistic Interpretability (80,000 Hours Podcast)](https://80000hours.org/podcast/episodes/neel-nanda-mechanistic-interpretability/). Long-form conversation on the field, recommended papers, ARENA, and research paths.
- [A Walkthrough of A Mathematical Framework for Transformer Circuits](https://www.youtube.com/watch?v=KV5gbOmHbjU). Neel Nanda walks through the framework paper.
- [A Walkthrough of Toy Models of Superposition (with Jess Smith)](https://youtu.be/R3nbXgMnVqQ). Walkthrough of the superposition paper.
- [A Walkthrough of In-Context Learning and Induction Heads, Part 1 of 2 (with Charles Frye)](https://youtu.be/dCkQQYwPxdM). Walkthrough of the induction-heads paper.

## Contributing

See [contributing.md](contributing.md) for the entry format, quality bar, and PR checklist. New entries are welcome. Removals are also welcome when an entry no longer earns its slot.

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, the maintainers have waived all copyright and related or neighboring rights to this work. See [LICENSE](LICENSE).
