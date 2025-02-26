1. Text -> Keyword -> ML algo -> Spam
2. Link -> 

## Vectorisation
It is the process of coverting data like images and text into mathematical format, for machine to understand.

## Feature Extraction
It is process of identifying & extracting relevant data from raw data.
It is important for tasks such as NLP and image recognition.
-> Since data is measured in different scales and categories, normalisation is important to convert it into machine learning langauge

## Common Extraction Techniques:
1. **Autoencoders:** can identify key data features. The autoencoder concept hinges on learning from the coding of the original data sets to derive new, more potent features. It achieves this by training a neural network to recreate its input, which forces it to discover and exploit structures in the data.
2. **Principle Component Analysis:** This feature extraction method reduces the dimensionality of large data sets while preserving the maximum amount of information.
3. **Bag of Words**: it is a effective technique to extract high usuage frequency words.
4. **Term Frequency-Inverse Doucment Frequency**: Extension of BoW, it determines how important a word is in corpus or collection. It considers word across all documents
5. **Image Processing**: It involves raw data analysis to identify and isolate significant patterns in an image.

---
# Compeititors

TG-Spam's spam detection algorithm is multifaceted, incorporating several criteria to ensure high accuracy and efficiency:

- **Message Analysis**: It evaluates messages for similarities to known spam, flagging those that match typical spam characteristics.
- **Integration with Combot Anti-Spam System (CAS)**: It cross-references users with the Combot Anti-Spam System, a reputable external anti-spam database.
- **Spam Message Similarity Check**: TG-Spam assesses the overall resemblance of each message to known spam patterns.
- **Stop Words Comparison**: Messages are compared against a curated list of stop words commonly found in spam.
- **OpenAI Integration**: TG-Spam may optionally use OpenAI's GPT models to analyze messages for spam patterns.
- **Emoji Count**: Messages with an excessive number of emojis are scrutinized, as this is a common trait in spam messages.
- **Meta checks**: TG-Spam can optionally check the message for the number of links and the presence of images. If the number of links is greater than the specified limit, or if the message contains images but no text, it will be marked as spam.
- **Automated Action**: If a message is flagged as spam, TG-Spam takes immediate action by deleting the message and banning the responsible user.
---
## Why Web-hooks and not polling

The API integration should be efficient enough that sharing of data between apps provides great value to the user. In the polling method, we send a request for new events (specifically, Create, Retrieve, and Delete events, which signal changes in data) at a predetermined frequency and wait for the endpoint to respond. If the endpoint doesn’t respond, there are no new events to share. Similar to polling, webhooks provide your application a way of consuming new event data from an endpoint. However, instead of sending repeated requests for new events, you provide the endpoint with a URL, usually within the endpoint UI, which your application monitors. Whenever a new event occurs within the endpoint app, it posts the event data to your specified URL, updating your application in real-time.

  

Initially, this bot was created with a polling method then later it was changed to a web-hook method as they are more efficient. In polling, the data is always out-of-date for example if the frequency of polling is set as every 6 hrs then the returned event could have happened any time in this 6-hour gap whereas in web-hook the event is posted immediately to the monitored URL, and the app is updated with new data instantly. Zapier found that over 98.5% of polls are wasted. In contrast, webhooks only transfer data when there is new data to send, making them 100% efficient. That means that polling creates, on average, 66x more server load than webhooks. That’s a lot of wasted time, and if you’re paying per API call, a whole lot of wasted money. To save us from all the losses web-hook method has been used NaradaFakeBuster.

---

Fake news detection- NaradaFakeBuster