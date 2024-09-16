# INTRODUCTION

This Medical Chatbot uses the latest MoE model Qwen2 1.5B model and levrages LORA and RAG to deliver results far better than the base model. We have used the Gale Encyclopedia of Medicine through Qudrant vector database to levrage RAG and add "memory" to our model. The model can be downloaded from here "Irathernotsay/qwen2-1.5B-medical_qa-Finetune" or "https://huggingface.co/Irathernotsay/qwen2-1.5B-medical_qa-Finetune-Q4_K_M-GGUF" if you want inference on CPU. We have used 4 bit quantization to be able to run the model on CPU using the llama.cpp.


## SETUP

Clone the project from github and create a virtual environment using conda
```bash
    conda create -n myenv python=3.9
```
Move to the project directory using cd and install all the project requirements using your anaconda prompt.
```bash
    pip install -r requirement.txt --use-deprecated=legacy-resolver
```
Use docker to initialize the vector database.
```bash
    conda env config vars set pwd=[present working directory]
    E.g. if the current workign directory is “C:\Users\JohnDoe\Work\ChatBot”, then the above command should be conda env config vars set pwd=C:/Users/JohnDoe/Work/ChatBot
    docker pull qdrant/qdrant
    docker run -p 6333:6333 -p 6334:6334 -v $(pwd)/qdrant_storage:/qdrant/storage:z
    qdrant/qdrant
```
More details regarding Qdrant can be found [here](https://qdrant.tech/documentation/).
Run the ingest.py file to fill the vector database with the data. You can add any amount of data you want for vector database. Run the app.py file to run the chatbot web application locally.


## TODO

- [X]   Select the appropriate model
- [X]   Finetune the model on https://huggingface.co/datasets/ruslanmv/ai-medical-chatbot dataset
- [X]   Integrate RAG with the chatbot
- [X]   Build a website for the chatbot
- [X]   Improve the UI
- [ ]   Deploy the model on huggingface spaces
