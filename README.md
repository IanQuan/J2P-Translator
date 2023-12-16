# Jyutping to Chinese Character Transliteration

## Project Overview

This project focuses on leveraging a Transformer model for the transliteration task from Jyutping to Chinese Characters. Transliteration is a critical component in natural language applications, aiding information retrieval and machine translation, particularly for proper nouns and technical terms. The Transformer model, renowned for its success in natural language processing tasks, serves as the core architecture for this sequence-to-sequence attention-based model.

## Significance and Applications

- **Enhancing Language Applications:**
  - The project addresses the scarcity of research on Jyutping to Chinese Characters transliteration, vital for applications like information retrieval, machine translation, speech-to-text (STT), and automatic speech recognition (ASR).

- **Cultural and Societal Impact:**
  - Beyond technical challenges, the project contributes to the preservation of heritage languages, particularly in Cantonese-speaking communities, empowering speakers to actively document their linguistic heritage.

## Datasets

- **Hambaanglaang Storybooks:**
  - Provides foundational Cantonese learning resources with 235 storybooks for learners of all ages.
  
- **CantoMap:**
  - A corpus of contemporary spoken Hong Kong Cantonese, offering additional resources for the study of modern Cantonese.

- **Hong Kong Cantonese Corpus (HKCanCor):**
  - Collected from transcribed conversations recorded between March 1997 and August 1998, including spontaneous speech and radio programs.

- **words.hk(粵典):**
  - A large-scale Cantonese lexicon project aiming to create an extensive and sustainable Cantonese dictionary.

## Model Architecture

- **Word Embedding:**
  - **Jyutping Embedding:** No publicly available pre-trained word embeddings for Jyutping were found. Therefore, a custom word embedding model was built and trained from one-hot encodings prepared for Jyutping in this project.

  - **Chinese Character Embedding:** Leveraged a pre-trained word embedding model, ayaka14732/bert-tokenizer-cantonese, [https://github.com/ayaka14732/bert-tokenizer-cantonese]. This model performs second-stage pre-training with Cantonese data on the BART base Chinese model.

- **Transformer Model:**
  - Implemented a customized variant of the sequence-to-sequence attention-based Transformer model augmented with a Homophones Weighting Layer.
  
- **Homophones Weighting (HW):**
  - Introduced to emphasize predictions corresponding to homophones, enhancing the model's performance in capturing homophonic relationships.
![Model Architecture](url)
## Performance Evaluation

- **Hyperparameter Tuning:**
  - Systematically refined the model through homophone weighting and hyperparameter tuning using Ray Tune.

- **Accuracy Improvement:**
  - Achieved a remarkable 94% testing accuracy, surpassing baseline models, demonstrating the effectiveness of the Transformer model with Homophones Weighting.

## Comparative Analysis

- **Transformer vs. Vanilla RNN:**
  - Compared the Transformer model's performance with a vanilla Recurrent Neural Network (RNN), showcasing the Transformer's superiority in addressing challenges related to Homophone Ambiguity.

## Limitations

- **Specific Terms and Lexicons:**
  - Acknowledged difficulty in transliterating specific terms, names, and phrases due to the nuances of Cantonese pronunciation and variability in representing specific terms in Jyutping.

- **Data Insufficiency:**
  - Highlighted challenges related to data scarcity for Cantonese and Jyutping, affecting the model's generalization, especially for uncommon words, names, or phrases.

This project not only contributes to the advancement of NLP applications but also aligns with cultural preservation goals, addressing practical challenges in Cantonese transcription and promoting linguistic heritage documentation.
