# Advanced Topics in Machine Learning: Natural Language Processing
Authors: Jonathan Bella, Alessia Berarducci, Jonas Knupp, Tobias Erbacher

This repository contains the codebase for a question-answer system based on the [Medical Meadow Medical Flashcards dataset](https://huggingface.co/datasets/medalpaca/medical_meadow_medical_flashcards), related to the paper "[MedAlpaca - An Open-Source Collection of Medical Conversational AI Models and Training Data](https://arxiv.org/pdf/2304.08247.pdf)". This project was conducted as part of the **Advanced Topics in Machine Learning** course at Università della Svizzera italiana in the autumn semester 2024/2025.

The subsection sections describe the structure of the **nlp.ipynb** notebook. In addition, the directories in this repository include additional work that was not integrated in the final notebook.

The notebook should be exectued in Google Collaboratory using a GPU with sufficient RAM. Before the notebook is run perform the following tasks:
- The folders inside the data repository must be uploaded to the colab instance.
- Set the colab secrets
   - HUGGINGFACE_TOKEN must be a token from Huggingface that allows access to the gated Llama 3.2 repositories.
   - XY @Jonathan

## Dataset investigation
This part was done by Alessia Berarducci.

1. **Initial Cleaning:**
   - Removed duplicate entries from the dataset.
   - Deleted rows where both the input and output were empty, or where either one of them was empty.

2. **Document Length Analysis:**
   - Plotted the distribution of document lengths (number of words) separately for input and output fields.

3. **Vocabulary Size Analysis:**
   - Measured the unique word count for each document and plotted the distribution for both input and output.

4. **Tokenization and Lemmatization with SpaCy:**
   - Used **SpaCy**, a natural language processing library, to tokenize and lemmatize the text in both the input and output.
   - Trained a **Word2Vec** model using this combined list of medical text tokens and test the embeddings using cosine similary. 
   - Word Cloud Analysis of Tokens.
   - Vocabulary Growth Curve. 
   - Top 20 Most Common Words in Inputs and Outputs.

5. **Vector Embedding Using openAI:**
   - Creation of Embeddings
   - Dimensionality Reduction
   - Clustering

The file containing embeddings generated using OpenAI's models is publicly available at the following link: [Google Drive - Embeddings File](https://drive.google.com/drive/folders/19RtsJwWldkp85m0OGLqaFXq1nWQT_y0a?usp=drive_link). 

6. **Indexing and Searching**
   - Used Whoosh

## Training and Evaluation
This part was done by Jonathan Bella and Jonas Knupp.

The fine-tuning of the Llama 3.2 1B and Llama 3.2 3B models on the medical flashcards dataset is implemented in this section. Furthermore, the non-fine-tuned Llama 3.2 1B and Llama 3.2 3B models and the fine-tuned models are evaluated on the USMLE dataset. 

## Voice Interaction
This part was done by Tobias Erbacher.

This part contains the code to implement the speech-to-text and text-to-speech functionality. For the text-to-speech functionality, the Whisper model is used while for the implementation of the text-to-speech functionality the Tacotron 2 and SpeechT5 models are used. In addition, there is code to perform speech-to-text and text-to-spech locally, that is, without extensive hardware resources.

## End-to-End Medical Question Answering
This section contains an end-to-end medical question answering pipeline. The user can input a question verbally and will receive a spoken answer. We also implemented a graphical user-interface using Streamlit.
