# MIDEFICS

## About the project 
<p align="center">
  <img src="MIDEFICS.jpeg" alt="Logo" width="200" height="200" style="display: block; margin: auto;">
</p>


MIDEFICS (**M**edical **I**mage-aware **D**ecoder **E**nhanced à la **F**lamingo with **I**nterleaved **C**ross-attention**S**) is a fine-tuned iteration of the model IDEFICS-9b-instruct, which, in turn, is a refined version of the IDEFICS-9b model, tailored for instruction following.

MIDEFICS has been fine-tuned specifically for medical question answering concerning images. Its capabilities include describing visual content (diagnosing), generating recommendations, or functioning solely as a medical language model without visual inputs.



### Model Details

- **Model type:** Multi-modal model (image+text)
- **Language(s) (NLP):** en
- **License:** MIT
- **Parent Model:** [idefics-9b-instruct](https://huggingface.co/HuggingFaceM4/idefics-9b-instruct)
- **Resources for more information:**
    <!-- - [GitHub Repo](https://github.com/huggingface/m4/) -->
    - Description of [OBELICS](https://huggingface.co/datasets/HuggingFaceM4/OBELICS): [OBELICS: An Open Web-Scale Filtered Dataset of Interleaved Image-Text Documents
](https://huggingface.co/papers/2306.16527)
    - Original Paper: [Flamingo: a Visual Language Model for Few-Shot Learning](https://huggingface.co/papers/2204.14198)

IDEFICS is a substantial multimodal English model designed to process sequences of interleaved images and texts, producing corresponding text outputs. The model exhibits remarkable in-context few-shot learning capabilities, placing it on par with proprietary closed-source models. This positions IDEFICS as a reliable foundation for fine-tuning multimodal models with bespoke data.

IDEFICS leverages two pre-trained unimodal open-access models to facilitate the fusion of visual and textual modalities. Transformer blocks with newly initialized parameters bridge the gap between the vision encoder and the language model. Training data comprises a blend of image-text pairs and unstructured multimodal web documents.

IDEFICS-instruct is derived from further training IDEFICS on Supervised Fine-Tuning and Instruction Fine-Tuning datasets. This refinement notably enhances downstream performance, rendering idefics-9b-instruct a formidable model at its 9-billion parameter scale, while also making it more adept at engaging in conversations.

MIDEFICS emerges from additional training of IDEFICS on Supervised Fine-Tuning and Medical Conversation Fine-Tuning datasets. This refinement substantially bolsters downstream medical performance.



### Data preperation process
The dataset is built from [MURA](https://arxiv.org/abs/1712.06957), [ISIC](https://www.isic-archive.com/) and [ROCO](https://www.semanticscholar.org/paper/Radiology-Objects-in-COntext-(ROCO)%3A-A-Multimodal-Pelka-Koitka/a564fabf130ff6e2742cfba90c7a4018937d764d) which are free open-access online datasets of medical images.
The conversations were generated using GPT-3.5-turbo based on metadata associated to each image.

The graph bellow gives an overview of the data generation process:
![Logo](data_prep.png)
### Model calling
![Logo](model_call.png)

### Before and after finetuning comparision
![results](results.png)

## Usage
You can explore the notebooks for data generration, finetuning and evaluation in this github repo.
You can check the finetuned and quantized model [here](https://huggingface.co/WinterSchool/Midefics) on huggingface and you can also take a look at the different [datasets](https://huggingface.co/WinterSchool) that we created.


