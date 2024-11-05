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

```shipping_status.csv``` database used for query

* order_id: order identification number of order and used to track which order customer want to ask.
* customer_name: the name of the person receive the order
* status: the current order status, is the order being shipped, delivered, pending or cancellled?
* order_date: the date that the order is ordered
* delivery_date: the date that the order is or will be expected to be shipped or done.
* shipping_date: the date that the seller transfer the order to shipper, and the order move.
* shipping_adress: the order is shipped to this adress
* carrier: shipping unit which is responsible for delivery
* tracking_number: the unique number that the admin use for tracking more details of the order if there is any problem.
* item_description: one of the information on the contents of the package. It is the name of item the customer ordered.
* quantity: one of the information on the contents of the package. It express the number of item in the package ordered.
* shipping_cost: the cost of the order or the price of the package that the customer must pay.
* shipper_name: the name of the person deliver your order or the shipper/carrier
* shipper_phone_number: the phone number of your shipper, you can contact with the shipper by this.
* current_location: the location of the order in realtime, if the order was shipped, this location will be the shipping address.


```shipping_status_chatbot.ipynb``` my code for setting chatbot



<p align="center">
<img width="550" src="https://github.com/user-attachments/assets/95f214a6-5aec-47e4-ba2e-444586c1bad4">
</p>





