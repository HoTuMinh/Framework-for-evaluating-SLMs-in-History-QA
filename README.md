# Comprehensive Assessment of SLM Performance on Vietnamese High School History Tasks
A benchmarking framework for evaluating Small Language Models (SLMs) on Vietnamese history education tasks, with comprehensive datasets and evaluation protocols for both multiple-choice and essay questions.
# Overview
This project introduces the first standardized benchmark for assessing Small Language Models (≤9B parameters) on Vietnamese high school history tasks. The framework evaluates models across multiple prompting strategies and question types, providing insights for educational technology applications in Vietnam.
# Key Features

Comprehensive Dataset: 560 multiple-choice questions from official Vietnamese National High School examinations (2020-2024)
Essay Question Framework: Extended dataset with context passages and reference answers for reasoning evaluation
Multi-Model Evaluation: Testing of 25 SLMs across various model families (Qwen, Gemma, Vietnamese-specific models)
Advanced Prompting Strategies: Baseline, Zero-shot CoT, One-shot CoT, and Few-shot CoT evaluation
LLM-as-a-Judge: Automated evaluation system for essay responses with human validation
Difficulty Classification: Questions categorized by cognitive demand (Knowledge, Comprehension, Application, Advanced Application)

# Dataset Structure
## Multiple-Choice Dataset

Size: 560 unique questions
Source: Official Vietnamese high school graduation exams (2020-2024)
Fields: id, question, options, answer
Annotations: Difficulty levels and question types
Categories: Comparison, Multiple-Choice, Evaluation, Outcome, Event, Context

## Essay Dataset
Extended from multiple-choice with additional fields:

Context: Historical passages providing necessary background information
Reference Answer: Model solutions with explanations
Focus: Reasoning-intensive categories (causal-background, consequence-impact, evaluative, comparative)

# Evaluation Metrics
## Multiple-Choice Tasks

Primary Metric: Accuracy (correct answers / total questions)
Breakdown Analysis: Performance by difficulty level and question type
Format: Models must output answers in [A], [B], [C], or [D] format

## Essay Tasks
4-Criteria Likert Scale (1-5 points each):

Correctness: Historical accuracy and factual precision
Response Structure: Logical organization and coherence
Response Format: Language use, grammar, and presentation
Comprehensibility: Clarity and effective communication

# Models Evaluated
Model Families

Qwen Series: Qwen2, Qwen2.5, Qwen3 (various sizes)
Gemma Series: Gemma 1.0, 1.1, Gemma2, Gemma3
Vietnamese-Oriented: VinaLLaMA, Vistral
Comparison: GPT-OSS-20B (outlier for reference)

Parameter Range

Primary Focus: 0.5B - 9B parameters
Total Models: 25 SLMs + 1 larger model for comparison

# Key Findings
## Multiple-Choice Performance

Top Performers: Gemma-2-9b-it (82.14%) and Qwen2.5-7B-Instruct (80.36%)
Difficulty Impact: Significant accuracy decline from Knowledge → Advanced Application
Question Type: Lower performance on Comparison and Evaluation questions
Vietnamese Models: Did not achieve top results despite Vietnamese fine-tuning

### Prompting Strategy Results

Baseline: Best for larger, well-trained models
Zero-shot CoT: Limited improvement for most models; significant gains for Qwen3-4B (+27.3%)
Few-shot CoT: Best overall performance but caused failures in some models
Context Window: Longer prompts sometimes degraded performance near context limits

## Essay Evaluation Insights

LLM Judge Performance: Mixed results compared to human evaluators
Strongest Agreement: Correctness assessment (LLM more consistent than humans)
Weakest Agreement: Response format and structure evaluation
Correlation: Human-human (0.7) vs. Human-LLM (0.46-0.47)

# Technical Implementation
Hardware Requirements

Cloud GPUs: 2× NVIDIA T4 (32GB) or 1× NVIDIA L4 (24GB)
Platforms: Kaggle, Google Colab
Optimization: Model-specific configurations for efficient inference

# Reproducibility

Standardized evaluation protocols
Consistent GPU environments
Open-source code and configurations
Detailed experimental parameters
