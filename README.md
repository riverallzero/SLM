# SLM
- **S**mall **L**anguage **M**odel
- Microsoft - [3 bit Ai trends to watch in 2024](https://news.microsoft.com/three-big-ai-trends-to-watch-in-2024/?ocid=FY24_soc_omc_br_li_Trends)
  
    > SLMs are still quite large with several billion parameters(7B) in contrast to hundreds of billions of parameters(175B-GPT) in LLMs. 
    > But they're small enough to run on a phone offline. 
    > Parameters are variables, or adjustable elements, that determine a model's behavior.
    > "Small language models can make AI more accessible due to their size and affordability" says ```Sebastien Budeck```, who leads the Machine Learning Foundations group at Microsoft Research.
    > "At the same time, we're discovering new ways to make them as powerful as large language models."

## | Model
### Alpaca-LLaMa
- Stanford University(alpaca [[about]](https://crfm.stanford.edu/2023/03/13/alpaca.html)), Meta(llama [[about]](https://llama.meta.com/))

#### Alpaca

a model fine-tuned from the LLaMA 7B model on 52K instruction-following demonstrations

#### LLaMa

large language model has ```7B```, ```13B```, ```33B```, and ```65B``` of parameter

### Orca
- Microsoft([about](https://www.microsoft.com/en-us/research/blog/orca-2-teaching-small-language-models-how-to-reason/))

achieve enhanced reasoning abilities, which are typically found only in much larger language models

```orca: 13B```, ```orca 2: 7B, 13B```

### Phi
- Microsoft([about](https://www.microsoft.com/en-us/research/blog/phi-2-the-surprising-power-of-small-language-models/))

demonstrates outstanding reasoning and language understanding capabilities, showcasing state-of-the-art performance among base language models with less than 13 billion parameters

```phi-1: 1.3B```, ```phi-1.5: 1.3B```, ```phi-2: 2.7B```

## | About
### library
- ```transformers``` provides APIs and tools to easily download and train state-of-the-art pretrained models
- ```accelerate``` enables the same PyTorch code to be run across any distributed configuration
- ```sentencepiece``` unsupervised text tokenizer and detokenizer mainly for Neural Network-based text generation systems where the vocabulary size is predetermined prior to the neural model training
- ```protobuf``` Google’s language-neutral, platform-neutral, extensible mechanism for serializing structured data – think XML, but smaller, faster, and simpler
- ```bitsandbytes``` brings quantization to your model. You can now load any pytorch model in 8-bit or 4-bit with a few lines of code

### parameter
- ```device_map='auto'``` suggests that the code should automatically handle device placement, likely selecting the available GPU if one is present
- ```load_in_8bit=True``` indicates that the model should be loaded using 8-bit quantization, which is a technique to reduce the memory and computational requirements of the model by using lower precision for certain calculations
- ```use_fast=False``` not to use the fast tokenizer implementation, since fast and slow tokenizers produce different tokens
- ```return_tensors='pt'``` specifies that the output should be PyTorch tensors
- ```add_special_tokens``` which defaults to **True**, adds the BOS (beginning of a sentence) token at the beginning and the EOS (end of a sentence) token at the end. If you do not want to use these symbols, you can set **False**
