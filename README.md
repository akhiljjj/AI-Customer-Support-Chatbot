🤖 Intelligent Customer Support Chatbot

A Production-Grade Hybrid RAG & Fine-Tuned Assistant
This system combines the specific accuracy of a fine-tuned FLAN-T5 model with the dynamic knowledge retrieval of a FAISS vector database. 



⚡ Key "Vibe" Features

Intent-Aware Retrieval: Unlike standard RAG, this system maps customer queries to specific business intents before searching the vector DB, ensuring the retrieved context is relevant to the policy .


Semantic Reranking: Implemented a Cross-Encoder (ms-marco-MiniLM) to rerank FAISS results, mitigating LLM hallucinations by selecting only the highest-scoring policy matches.


Hard-Coded Guardrails: Integrated logic to handle high-risk queries (legal, escalation, paid subscriptions) instantly, ensuring the system remains safe and reliable.


Fine-Tuning for Tone: Fine-tuned the base flan-t5 model on 3,000 customer service interactions to master specialized intent classification and response formatting.



🛠️ The Tech Stack

Model: google/flan-t5-base (Fine-tuned).


Embeddings: all-MiniLM-L6-v2.


Vector Search: FAISS-GPU for low-latency retrieval.


Reranker: Cross-Encoder for high-precision context filtering.


Frontend: Gradio for real-time interaction and stress-testing.



🏗️ Technical Architecture

Preprocessing: Tokenizes and prepares custom datasets for Seq2Seq training.


Hybrid Retrieval: Maps query keywords to intent-specific FAISS sub-indexes for faster, more accurate context gathering.


Cross-Encoding: Reranks the top 5 documents to find the single best policy "match".


Constrained Generation: Generates responses with a repetition penalty and controlled temperature to maintain a professional support persona.



🚀 Rapid Execution
The script handles all library installations, dataset loading, and model training in one flow.
