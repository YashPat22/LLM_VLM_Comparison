# Object Detection and Description using Vision Language Models and Large Language Models (Object Detection, Open Source LLMs and VLMs)
This repository is created for the project done for 10623 - Generative AI course offered at CMU (Spring 2024).

This repository contains the code for a novel approach of detecting and generating responses from a LLM and VLM for components from an IoT kit. We create multiple public datasets and deploy Object Detectors, Mistral-7B and LlaVa-7B to achieve this goal.


Permission(s)/License Required:
Access to Mistral through HuggingFace (https://huggingface.co/mistralai/Mistral-7B-Instruct-v0.2)
Access to LlaVa through HuggingFace (https://huggingface.co/liuhaotian/llava-v1.5-7b)

## To setup dependencies:
Install all the requirements using requirements.txt or manually install all packages from requirements.txt

## File Structure
```
📦 LLM-VLM-Comparison
├─ Evaluation
    └─ Evaluation of LLM and VLM approaches
├─ LLM Fine Tuned
    └─ Training and Responses of Mistral
└─ LLM In Context
    └─ In-Context learning notebooks of Mistral
└─ LLM RAG
    └─ RAG Pipeline with Mistral, Langchain and FAISS
└─ LLM Zero Shot
    └─ Baseline Zero shot implementation of Mistral
└─ Object Detector
   └─ Inference from Roboflow API 
└─ VLM Fine Tuned
    └─ Training and Responses of Llava
└─ VLM Zero Shot
    └─ Baseline Zero shot implementation of Llava
└─ Requirements.txt
└─ README.md
└─ Overall Approach.png
```

## Table of Contents

- [Introduction](#introduction)
- [Methodology](#methodology)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [Results](#results)
- [Contribution](#contribution)
- [License](#license)
- [Acknowledgments](#acknowledgments)

## Introduction

Welcome to the Comic Generation project, where we explore the exciting intersection of text prompts and machine learning to create captivating comic illustrations. Leveraging stable diffusion models for visual storytelling consistency\cite{rombach2021highresolution}, our goal is to develop a model that generates comics in a specified style from textual prompts.

## Project Objectives and Questions
- **Objective:** Develop a model for generating comics from text.
- **Questions:**
  1. How do we maintain a consistent style across comic panels?
  2. What methods enable effective comic panel generation from the text prompts?

Encountering challenges, we refined the stable diffusion model by fine-tuning it with images matching the desired comic art style. To address the uniformity across panels, a Similarity Metric was introduced, ensuring content preservation and information transfer.

Explore our results to see a series of comic panels with a consistent art style, showcasing the model's ability to transform text prompts into engaging visual narratives.

## Methodology

For a detailed explanation of the methodology, refer to the Methodology section in the Report.

<img width="895" alt="Overall Approach" src="https://github.com/YashPat22/LLM_VLM_Comparison/assets/111828697/0bc757fa-7631-4800-90e3-66b291160f5b">


## Getting Started

To get started with the project, follow these steps:

1. Clone the repository:
```bash
git clone https://github.com/YashPat22/LLM_VLM_Comparison
```
2. Install required dependencies:
[text](requirements.txt)
```bash
conda install --file requirements.txt
```
or
```bash
pip install -r requirements.txt
```

## Usage

To generate details about an object using the provided pipeline, modify object in the prompt on any of the notebooks mentioned and generate the response.

To use 

## Results

### Evaluation Method 1


### Evaluation Method 2


## Contributions
Our contributions include:
- Creation of datasets for object detector and prompt-response training of LLM and VLM.
- Zero-shot, In-context learning of Mistral and Llava.
- Implementation of RAG document to query responses.
- Fine-tuning LLM and VLM.
- Evaluation of all such methods. 

## License
This project is MIT licensed.

## Acknowledgements
We would like to express our gratitude to the following individuals and resources for their valuable contributions and support during the development of this class project:

- **Prof. Matt Gormley ,Yuanzhi Li and Tiancheng Zhao:** We extend our sincere appreciation to Prof. Matt, Prof. Yuanzhi and the teaching team for their guidance, mentorship, and insightful feedback throughout the project. Their expertise has been instrumental in shaping our understanding and approach.

- **Open Source Community:** We appreciate the broader open-source community for creating and maintaining the tools, libraries, and platforms that supported our project.

This project wouldn't have been possible without the collective efforts and support of everyone mentioned above. Thank you all for being part of this journey!
