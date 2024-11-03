# Chatbot

*Design a system that can respond to any user query regarding the shipping status of their order for an e-commerce company, for example*

At a very high level, here’s the architecture for our chatbot:


<p align="center">
<img width="748" alt="{0AD0D917-05DA-4A3A-864C-29819C91B825}" src="https://github.com/user-attachments/assets/d8c910c1-ee82-44b1-b8a9-ff565c3b6d2b">
</p>

There are three main components: The chatbot, the indexer and the Pinecone index.

* The indexer crawls the source of truth, generates vector embeddings for the retrieved documents and writes those embeddings to Pinecone
* A user makes a query to the chatbot
* The chatbot queries Pinecone for the source of true
* The chatbot responds to the user.
* Let’s take a deeper look at the Indexer:

```shipping_data.csv``` database used for query
```shipping_status_chatbot.ipynb``` my code for setting chatbot



