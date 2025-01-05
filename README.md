# Advanced Topics in Machine Learning: Natural Language Processing
Authors: Jonathan Bella, Alessia Berarducci, Jonas Knupp, Tobias Erbacher

This repository contains the codebase for a question-answer system based on the [Medical Meadow Medical Flashcards dataset](https://huggingface.co/datasets/medalpaca/medical_meadow_medical_flashcards), related to the paper "[MedAlpaca - An Open-Source Collection of Medical Conversational AI Models and Training Data](https://arxiv.org/pdf/2304.08247.pdf)". This project was conducted as part of the **Advanced Topics in Machine Learning** course at Università della Svizzera italiana in the autumn semester 2024/2025.

The codebase is structured in the following sections:
* **dataset_investigation**:

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
   - Vocabulary Grouwth Curve. 
   - Top 20 Most Common Words in Inputs and Outputs.

5. **Vector Embedding Using openAI:**
   - Creation of Embeddings
   - Dimensionality Reduction
   - Clustering

The file containing embeddings generated using OpenAI's models is publicly available at the following link: [Google Drive - Embeddings File](https://drive.google.com/drive/folders/19RtsJwWldkp85m0OGLqaFXq1nWQT_y0a?usp=drive_link). 

6. **Indexing and Searching**
   - Used Whoosh


* **training_and_evaluation**: @Jonas, Jonatan
* **voice_interaction**: Contains the code for voice interactivity of the system, as well as some experimentation with different libraries and models.
- **nlp.ipynb**: The clean master notebook with all relevant code elements to run the system, without additional details.
