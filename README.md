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
- [Dataset](#dataset)
- [Usage](#usage)
- [Results](#results)
- [Contribution](#contribution)
- [License](#license)
- [Acknowledgments](#acknowledgments)

## Introduction

In this project we leveraged the current advancements in the field of computer vision and natural language processing to a specific task of identifying and describing components of an IoT kit to be used by a beginner to get started with using the IoT kit.

## Project Objectives and Questions
- Objective: Develop a tool to identify and describe all IoT kit component
- Questions:
What kind of methods did we explore?

We investigated two distinct approaches: 
1) an independent Visual Language Model (VLM) and 
2) a combination of an Object Detector with a Language Model (either LLM or VLM). Our findings indicated that the integration of an object detector with a language model yielded superior outcomes. We proceeded to carry out additional experiments involving in-context learning, fine-tuning, and Retrieval Augmented Generation (RAG) to identify the most effective model.

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

## Dataset

The dataset created for this task are shown as below:
- Image Dataset (Object Detection): https://www.kaggle.com/datasets/yashpatawarijain/iot-components-images
- Text Dataset (Prompt Response): https://www.kaggle.com/datasets/yashpatawarijain/iot-component-images

## Usage

To replicate these results, use the Kaggle image dataset as mentioned above and train/fine-tune your object detector to detect your images for this task. Use the class output as text and feed it into the prompts into the notebooks according to the tree mentioned above.
Few pointers:

1. Inference and RAG pipeline can be run on a T4 GPU with 4 bit quantization.
2. For fine-tuning LLM and VLM, we recommend using A100 GPU with atleast 2 hours of training compute.
3. Make sure you have access to HuggingFace models in case you choose a gated model, for example, LlaMa-2 or LlaMa-3.

## Results
We assess the effectiveness of various methods using established large language models (LLMs) such as ChatGPT, Gemini, and c4 AI command R+.
Our evaluation process is as follows: 
For each of our proposed LLM/VLM methods, we test with five examples (HiLetgo GY-521 module, RC522 RFID Module, Servo Motor SG90, Stepper Motor and Water Level Detection Sensor Module) and compute the mean scores from the evaluation LLMs. We then aggregate these average scores to create a single score for each method.
We also conduct qualitative human evaluations and find that LLM-assisted scoring with ground truth (evaluation method 2) aligns closely with human judgment. We summarize the results of each of our proposed LLM/VLM methods as follows:
**VLM No Object Detector:** Vague answers output, with almost no utility.
**With Object Detector:** 

1) LLM/VLM ICL: Description is useful, however sometimes incorrect information on applications and specifications,
2) LLM/VLM Fine tuning: Significant improvement in utility of answer to the user,
3) RAG: The best results for our task. 

### Evaluation Method 1
Method 1: score the answers generated by each of the methods based on the prompt. 
![Eval_no_context](https://github.com/YashPat22/LLM_VLM_Comparison/assets/111828697/f46148d6-188f-4f21-b9c0-e949aa075ecc)


### Evaluation Method 2
Method 2: score them again after providing ground truth data to mitigate any bias of the evaluation LLMs.
![Eval_context](https://github.com/YashPat22/LLM_VLM_Comparison/assets/111828697/c1fd3139-0bfd-42e5-a21a-baf72c2c7fa9)



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
