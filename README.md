# Advanced Topics in Machine Learning: Natural Language Processing
Authors: Jonatan Bella, Alessia Berarducci, Jonas Knupp, Tobias Erbacher

This repository contains the codebase for a question-answer system based on the [Medical Meadow Medical Flashcards dataset](https://huggingface.co/datasets/medalpaca/medical_meadow_medical_flashcards), related to the paper "[MedAlpaca - An Open-Source Collection of Medical Conversational AI Models and Training Data](https://arxiv.org/pdf/2304.08247.pdf)". This project was conducted as part of the **Advanced Topics in Machine Learning** course at Università della Svizzera italiana in the autumn semester 2024/2025.

The subsection sections describe the structure of the **nlp.ipynb** notebook. In addition, the directories in this repository include additional work that was not integrated in the final notebook.

The notebook should be exectued in Google Collaboratory using a GPU with sufficient RAM. Before the notebook is run perform the following tasks:
- The folders inside the data repository must be uploaded to the colab instance.
- Set the colab secrets
   - HUGGINGFACE_TOKEN must be a token from Huggingface that allows access to the gated Llama 3.2 repositories.
   - NGROK_AUTH_TOKEN must be a token from ngrok that allows access to the ngrok service.

## Dataset investigation
This part was done by Alessia Berarducci.

First the dataset was cleaned, followed by the analysis of the document lengths. Then the the vocabulary size using different tokenization approaches was analyzed. Furthermore, a Word2Vec model was trained using the dataset and tested on the semantic similarity task using cosine similarity. Then the documents were embedded using OpenAPI's text-embedding-3-small model. Aftewards, the documents were classified using the obtained embeddings and the obtained clusters were analyzed. Lastly, the documents were indexed using Whoosh, a full-text indexing and searching library and an interactive interface to query the documents was implemented.

## Training and Evaluation
This part was done by Jonatan Bella and Jonas Knupp.

The fine-tuning of the Llama 3.2 1B and Llama 3.2 3B models on the medical flashcards dataset is implemented in this section. Furthermore, the non-fine-tuned Llama 3.2 1B and Llama 3.2 3B models and the fine-tuned models are evaluated on the USMLE dataset. 

## Voice Interaction
This part was done by Tobias Erbacher.

This part contains the code to implement the speech-to-text and text-to-speech functionality. For the text-to-speech functionality, the Whisper model is used while for the implementation of the text-to-speech functionality the Tacotron 2 and SpeechT5 models are used. In addition, there is code to perform speech-to-text and text-to-spech locally, that is, without extensive hardware resources.

## End-to-End Medical Question Answering
This section contains an end-to-end medical question answering pipeline. The user can input a question verbally and will receive a spoken answer. We also implemented a graphical user-interface using Streamlit.
