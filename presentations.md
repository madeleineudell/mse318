---
layout: default
title: Presentations
nav_order: 6
---

# Student Presentations
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Presentation Outline

### 1. Intro
- How does this topic relate to the course goal of enabling safe and constrained AI?
- What is the core idea?
- What applications does it target?

### 2. Literature Review
- What are the important papers and ideas?
- Walk us through the intellectual history

### 3. Deep Dive
- Pick one or two papers, and take us through the main idea and results
- Extract some core mathematical insights, and choose one to explain on the board
- Could be a theorem or result from the paper, or some older mathematics that motivates the approach
- Feel free to show how it works on a simple example, like a quadratic objective with linear constraints

### 4. Results
- Summary of numerical results from papers
- Do you think the results are good or bad? Are there obvious omissions?

### 5. Open Directions
- What are the important problems that you think could be addressed with these ideas, but haven't yet been?
- Is there a key challenge that restricts the usefulness of this approach?

**Note:** You might also loop through sections 2-5 several times, one for each of the most important papers in your stack.

---

## An AI-Forward Protocol

Here's the best workflow I've found for producing good presentations on new topics:

### Step 1: Collect Papers
Collect a list of papers and authors whose work you admire on the topic.

### Step 2: Use a Frontier LLM for Research
Use that list to prompt a frontier LLM (GPT5, Gemini) to do deep research on the topic and write a report.

Example prompt:
> Summarize the state of the art in [field], including work by [authors]. Use only published papers or arxiv papers as references in the final report.

You might also inject your own biases and interests here.

### Step 3: Download References
Ask Claude code to download all the references in the report into a folder on your computer.

### Step 4: Read and Verify
Read the report, and skim the papers to check that the understanding you gleaned from the report is correct.

### Step 5: Use NotebookLM
Upload all the papers to NotebookLM.

### Step 6: Deepen Understanding
Have a conversation with NotebookLM to deepen your understanding of the topic and ask more detailed mathematical questions about the papers.

### Step 7: Create Slides
Write a script for a presentation you'd like to give on the topic, noting the high level points you'd want to make, or categories or topics you'd want to hit, or conclusions you'd like to come to. Ask NotebookLM to create a slide deck, using your script as the prompt.

Example prompt:
> Develop a tutorial review of standard ideas in constrained optimization, in particular lagrangian methods and duality, with an eye towards their use in a modern deep learning setting for a PhD audience already familiar with optimization at the level of Boyd and Vandenberghe. Use a plain, latex beamer style slide template with a white background. All numerical results (in particular, tables and figures) must exactly match the source material and reference the source.

### Step 8: Study and Practice
Study the materials and practice your presentation. Be meticulous and make sure you believe and can justify every claim on the slides.

---

## Checklist

In addition to following the above outline (approximately), presentations must include:

- **Quiz:** 2 questions that are easy to answer from the required reading
- **Discussion questions or class activity**

### Before the Presentation

**Monday, 11am:** Email Prof. Udell with:
- Editable draft of slides
- Quiz questions
- Discussion questions

**Tuesday, 1pm:** Submit a PR to the class git repo with your slides

### Bring to Class

- Power adapter
- Anything needed to connect to a USB-C or HDMI cable

### Setup Requirements

- Projector
- Camera
- [Zoom](https://stanford.zoom.us/j/6394072382?pwd=bndKcXBpRFdOb2x5VFhuT0kzN1QvQT09)
- Share screen
