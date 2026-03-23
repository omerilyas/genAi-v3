# Understanding Fine-Tuning - Large Language Models

!!! information
    <p align="left"> 👉 <b> The tasks in this section are optional and focus on fine-tuning LLMs. Please note: To run these tasks, you'll need an NVIDIA GPU, or if you're using Google Colab, a Pro subscription is required.</b> </p>

## Fine-Tuning LLMs

The section centers around fine-tuning LLMs, addressing their various aspects and methodologies. As the module progresses, the focus will be given to specialized instruction tuning techniques, namely LoRA. It will examine domain-specific applications (Webex Calling), ensuring a holistic understanding of fine-tuning techniques and their real-world implications.

* **Techniques for Finetuning LLMs:** The lesson highlights the challenges, particularly the resource intensity of traditional approaches. We will introduce instruction tuning methods like LoRA.
* **Deep Dive into LoRA and SFT**: This lesson offers an in-depth exploration of LoRA and SFT techniques. We will uncover the mechanics and underlying principles of these methods.
* **Finetuning using LoRA** : This lesson guides a practical application of LoRA and SFT to finetune an LLM to follow instructions, using data from the “HuggingFace Dataset” .

## Techniques for Finetuning LLMs

### Introduction

In this lesson, we will examine the main techniques for fine-tuning Large Language Models for superior performance on specific tasks. We explore why and how to fine-tune LLMs, the strategic importance of instruction fine-tuning, and several fine-tuning methods, such as  Low-Rank Adaptation (LoRA), Supervised Finetuning (SFT). We also touch upon the benefits of the Parameter-Efficient Fine-tuning (PEFT) approach using Hugging Face's PEFT library, promising both efficiency and performance gains in fine-tuning.

### Why We Finetune LLMs

While pretrained Large Language Models (LLMs) provide a broad understanding of language, it doesn't equip them with the specialized knowledge needed for complex tasks. For instance, a pre-trained LLM may excel at generating text but encounter difficulties when tasked with sentiment analysis or even providing information from your own Knowledge base. This is where fine-tuning comes into play.

Fine-tuning is the process of adapting a pretrained model to a specific task by further training it using task-specific data. For example, if we aim to make an LLM proficient in answering questions about Webex Calling or Webex CC, we would fine-tune it using a dataset comprising Webex question-answer pairs. This process enables the model to recalibrate its internal parameters and representations to align with the intended task, enhancing its capacity to address domain-specific challenges effectively.

However, fine-tuning LLMs conventionally can be resource-intensive and costly. It involves adjusting  the parameters in the pretrained LLM models, which can number in the billions, necessitating significant computational power and time. Consequently, it's crucial to explore more efficient and cost-effective methods for fine-tuning, such as Low-Rank Adaptation (LoRA).

### A Reminder On Instruction and Conversational Finetuning  

In Conversational fine-tuning the model engages in a dialogue with the user, maintaining context over multiple turns.The interaction mimics a natural conversation, with the model responding in a way that feels like a human interlocutor.

Instruction fine-tuning is a specific type of fine-tuning that grants precise control over a model's behavior. The objective is to train a Language Model (LLM) to interpret prompts as instructions rather than simply treating them as text to continue generating. 

### Introduction to Efficient Finetuning with Parameter-Efficient Fine-tuning (PEFT) 

Parameter-Efficient Fine-tuning (PEFT) approaches address the need for computational and storage efficiency in fine-tuning LLMs. Hugging Face developed the PEFT library specifically for this purpose. PEFT leverages architectures that only fine-tune a small number of additional model parameters while freezing most parameters of the pretrained LLMs, significantly reducing computational and storage costs.

PEFT methods offer benefits beyond just efficiency. These methods have been proven to outperform standard fine-tuning methods, particularly in low-data situations, and provide improved generalization for out-of-domain scenarios. Furthermore, they contribute to the portability of models by generating tiny model checkpoints that require substantially less storage space compared to extensive full fine-tuning checkpoints.

The PEFT library supports popular methods such as Low-Rank Adaptation (LoRA) and Prompt Tuning. 

### A Reminder of the Techniques For Finetuning LLMs

There are several techniques to make the finetuning process more efficient and effective:

* **Full Finetuning:** This method involves adjusting all the parameters in the pretrained LLM models to adapt to a specific task. While effective, it is resource-intensive and requires extensive computational power, therefore it’s rarely used. **This is not in the scope of this lab**

* **Low-Rank Adaptation (LoRA):** LoRA is a technique that aims to adapt LLMs to specific tasks and datasets while simultaneously reducing computational resources and costs. By applying low-rank approximations to the downstream layers of LLMs, LoRA significantly reduces the number of parameters to be trained, thereby lowering the GPU memory requirements and training costs. We’ll also see QLoRA, a variant of LoRA that is more optimized and leverages quantization.

With a focus on the number of parameters involved in finetuning, there are multiple methods, such as:

* **Supervised Finetuning (SFT):** SFT involves doing standard supervised finetuning with a pretrained LLM on a small amount of demonstration data. This method is less resource-intensive than full finetuning but still requires significant computational power. **This is within the scope of this lab**

* **Reinforcement Learning from Human Feedback (RLHF):** RLHF is a training methodology where models are trained to follow human feedback over multiple iterations. This method can be more effective than SFT, as it allows for continuous improvement based on human feedback. We’ll also see some alternatives to RLHF, such as Direct Preference Optimization (DPO), and Reinforcement Learning from AI Feedback (RLAIF).**This is not in the scope of this lab**

### Conclusion

In this lesson, we've learned that while pretraining equips LLMs with a broad understanding of language, fine-tuning is necessary to specialize these models for complex tasks. We've looked into various fine-tuning techniques, including Full Finetuning, Low-Rank Adaptation (LoRA), Supervised Finetuning (SFT), and Reinforcement Learning from Human Feedback (RLHF). 