# Python Screening Task 3: Evaluating Open Source Models for Student Competence Analysis

This document presents a research plan and reasoning for evaluating open-source AI models for their use in analyzing student competence in Python, as per the screening task requirements.

---

## Research Plan

Our research approach focuses on evaluating open-source, code-specialized Large Language Models (LLMs) for their pedagogical potential. The initial evaluation will center on **Meta's Code Llama**, selected for its domain-specific training on source code and its proven instruction-following capabilities. The primary criteria for assessing its suitability will be: **1) Code Comprehension**, the model's ability to accurately identify not just syntactic bugs but also conceptual errors in a student's logic; **2) Instruction Adherence**, its reliability in following a complex "Socratic tutor" meta-prompt that strictly forbids revealing direct solutions; and **3) Prompt Quality**, the clarity and pedagogical effectiveness of the Socratic questions it generates to guide students toward self-discovery.

To validate the model's applicability, we will test it against a curated dataset of Python snippets containing common beginner errors. We will then perform a qualitative analysis where a human expert scores the model's generated prompts against a rubric measuring relevance, clarity, and educational value. This expert-in-the-loop methodology is a core part of our reasoning; we chose this approach because standard accuracy metrics are insufficient for evaluating educational nuance. The decision-making process prioritizes the practical, real-world effectiveness of the model as a teaching aid over simplistic quantitative measures, ensuring our evaluation is directly aligned with the goal of fostering deeper student understanding.

---

## Reasoning

### What makes a model suitable for high-level competence analysis?

A suitable model requires more than just bug detection. It must possess:
1.  **Semantic Understanding:** The ability to infer the student's *intent* behind the code to understand their specific misconception.
2.  **Abstract Reasoning:** The capacity to identify the *category* of error (e.g., misunderstanding scope vs. a simple typo) to inform the line of questioning.
3.  **Controlled Generation:** Exceptional instruction-following to adopt a tutor persona and strictly adhere to negative constraints like "do not provide the solution."

### How would you test whether a model generates meaningful prompts?

Meaningful prompts must be tested qualitatively by a human expert. The process involves:
1.  **Defining a Rubric:** Creating a scorecard with criteria like "Relevance to Error," "Encourages Critical Thinking," and "Clarity for a Novice."
2.  **Using a Test Set:** Feeding the model a standardized set of buggy code samples.
3.  **Expert Scoring:** Having an experienced educator or developer score each generated prompt against the rubric to determine its pedagogical value.

### What trade-offs might exist between accuracy, interpretability, and cost?

These three factors are in constant tension in any AI project:
* **Accuracy vs. Cost:** Larger, more accurate models (e.g., 70B parameters) produce better prompts but have significantly higher computational and financial costs, potentially making them impractical for a free educational tool.
* **Accuracy vs. Interpretability:** The most powerful models are "black boxes." We can verify their output is good, but we cannot easily interpret *why* they chose a specific question, which introduces a level of unpredictability.
* **Cost vs. Interpretability:** Simpler, interpretable systems are cheap but lack the nuance needed to generate high-quality, human-like educational prompts, making them unsuitable for this task.

### Why did you choose the model you evaluated, and what are its strengths or limitations?

The chosen model for initial evaluation is **Meta's Code Llama**.

**Reason for Choice:**
It is a logical and efficient choice because it is an open-source model specifically fine-tuned on a massive corpus of code. Unlike a general-purpose model, it is already an expert in the domain of programming.

**Strengths:**
* **Domain-Specific:** It has a deep, built-in understanding of code syntax, patterns, and logic.
* **Instruction-Tuned:** It has variants specifically trained to follow complex commands, which is essential for our "Socratic tutor" prompt.
* **Scalable:** It is available in various sizes, allowing for a practical trade-off between performance and resource requirements.

**Limitations:**
* **Not a Trained Educator:** It understands code, but not pedagogy. Its ability to teach is entirely dependent on the quality of our prompting, not on any innate understanding of how students learn.
* **Potential for Error:** Like any LLM, it can be confidently wrong or misinterpret novel student solutions, requiring human oversight in a real-world application.
