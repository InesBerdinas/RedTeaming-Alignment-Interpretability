# Red Teaming, Alignment and Interpretability of Large Language Models
AI Safety University project

## Overview

This project investigates the behavior of aligned Large Language Models (LLMs) under adversarial prompting conditions. The study combines Red Teaming methodologies, alignment evaluation, and interpretability techniques to analyze how safety mechanisms respond to jailbreak attacks, roleplay-based prompt injections, and contextual manipulation strategies.

The project also explores the use of Integrated Gradients (Captum) to identify which prompt tokens contribute most strongly to model refusal or compliance behaviors.

## Research Objectives

The main goals of this project were:

- Evaluate the robustness of an aligned LLM against adversarial prompts.
- Compare manually crafted jailbreak attacks with benchmark attacks from HarmBench HumanJailbreaks.
- Analyze model behavior through logits, hidden representations, and generation trajectories.
- Investigate the applicability and limitations of Integrated Gradients for LLM interpretability.
- Study the relationship between prompt structure and model safety responses.

## Methodology
### Red Teaming Evaluation

Two prompt datasets were evaluated:

- Custom handcrafted adversarial prompts designed specifically for this study.
- Randomly sampled prompts from the HarmBench HumanJailbreaks benchmark.

Attack Success Rate (ASR) was measured as the primary metric.

### Additional statistical analyses included:

- Wald confidence intervals for binomial proportions.
- Two-proportion z-test.
- Relative Risk estimation and confidence intervals.
- Interpretability Analysis

### The project implemented a custom analysis framework using:

PyTorch
Hugging Face Transformers
Captum

### Integrated Gradients was applied to:

- Identify influential prompt tokens.
- Compare benign and adversarial prompts.
- Analyze jailbreak, roleplay, and prompt injection strategies.
- Study attribution patterns associated with alignment behaviors.

### Additional analyses included:

- Next-token logits inspection.
- Hidden-state extraction.
- Representation similarity.
- Layer-wise representation drift.
- Generation trajectory analysis.
- Entropy and KL divergence measurements.

## Key Findings
### Red Teaming
Handcrafted attacks achieved a higher Attack Success Rate than sampled HarmBench attacks.
The observed difference was statistically significant under the experimental conditions.
Results suggest that manually designed prompts can exploit vulnerabilities not always captured by standardized benchmarks.
Interpretability

### Integrated Gradients revealed that:

High-attribution tokens were often associated with instruction-overriding phrases.
Roleplay jailbreaks shifted attribution toward meta-instructions such as "ignore", "previous", "all", and "directly".
Attribution scores reflected the model's internal decision process for the selected target token rather than the full generated response.

The study also discusses several methodological limitations of attribution-based analyses in autoregressive language models.

## Main Technologies
- Python
- PyTorch
- Hugging Face Transformers
- Captum
- NumPy
- Statistical hypothesis testing

## References

Key references that informed this work include:

- Axiomatic Attribution for Deep Networks (Sundararajan et al., 2017)
- Four Axiomatic Characterizations of the Integrated Gradients Attribution Method
- Introduction to LLM Red Teaming
- Understanding the Prompt Sensitivity of Large Language Models
- Attention is not Explanation (Jain & Wallace, 2019)

## Limitations

This work represents an exploratory study rather than a definitive benchmark evaluation.

#### Results are subject to limitations including:

- Small handcrafted prompt dataset.
- Sampling variability within HarmBench.
- Dependence of attribution scores on target-token selection.
- Interpretability limitations inherent to gradient-based attribution methods.

## Technical Report

A complete description of the methodology, experimental setup, statistical analysis, red teaming evaluation, and interpretability experiments is available in the full technical report (pdf)

## Author

María Inés Berdiñas

Artificial Intelligence Engineering Student

