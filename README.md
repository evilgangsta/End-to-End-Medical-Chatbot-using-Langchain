This Medical Chatbot uses the latest MoE model Qwen2 1.5B model and levrages LORA and RAG to deliver results far better than the base model. We have used the Gale Encyclopedia of Medicine through Qudrant vector database to levrage RAG and add "memory" to our model. 
The model can be downloaded from here "[Irathernotsay/qwen2-1.5B-medical_qa-Finetune](https://huggingface.co/Irathernotsay/qwen2-1.5B-medical_qa-Finetune)" or "https://huggingface.co/Irathernotsay/qwen2-1.5B-medical_qa-Finetune-Q4_K_M-GGUF" if you want inference on CPU.
We have used 4 bit quantization to be able to run the model on CPU using the llama.cpp. 
