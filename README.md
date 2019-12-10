# Counterweight
## What is it?
Despite having access to more information than ever before in history, we live in a world of divided ideologies and narrowed perspectives. <br />

Whether attributed to social network algorithms which suggest only news reinforcing certain perspectives, targeted ads by agencies to continuously feed their ideological bases, or simply user habit that cause recurring visits to the same news sources, internet users easily fall into dangerous echo-chambers, which at scale, cause the sharding and deterioration of communities. <br />

This is why we want to introduce Counterweight, a Google Chrome extension to help remedy these issues. 
Based on an article the user is currently reading, Counterweight can present other perspectives on the topic by suggesting articles from different news sources across the political spectrum covering the same event. <br />

![image](https://user-images.githubusercontent.com/25347517/70572654-0fd4dd00-1b55-11ea-87cc-4736be87fc02.png)
## Demo

![DEMO!](https://media.giphy.com/media/KFhQn4LjcRnlICXM73/giphy.gif)

## How to run?
1. Clone the repository onto your local machine
2. Run the first cell in the HCI.ipynb to start the FLASK Server that establishes the connection between the Javascript on the chrome extension and Python script that scrapes for relevant news articles
3. To load counterweight, Go to Chrome extensions -> chrome://extensions/ -> Load Unpacked and select the folder for this repository 
4. Refresh the Counterweight extension 
5. Open the news article you wish to browse
6. Click on the Counterweight extension at the top right corner of the browser to see other relevant articles ranked by news source bias and similarity to the currently read news article
7. If you wish to not display the bias, you can change this by right clicking on the extension and toggling the bias to YES/NO
8. Return to the news article to view the new interactive result 

The approach is detailed below: 

Upon wishing to see other perspectives of a news article,the user clicks on the chrome extension icon. This triggers counterweight to extract keywords relevant to article and use them to search for other relevant articles that are made available by the newsapi. The model assigns a similarity ranking using Gensim to achieve this.   
The ranked articles are then categorized and displayed across of a spectrum of news source biases.  
The element of interactivity comes into play when the user can choose to slide along the bias spectrum to sort the results by bias or just get a plain search engine ~esque ranked result for relevant articles.

![image](https://user-images.githubusercontent.com/25347517/70573378-b1a8f980-1b56-11ea-96cd-1506b78be810.png)

### References:
The Gensim similarity ranking has been implemented using this approach:https://radimrehurek.com/gensim/auto_examples/core/run_similarity_queries.html 
This is the news API that we used to scrape the web for relevant news articles: https://newsapi.org/
