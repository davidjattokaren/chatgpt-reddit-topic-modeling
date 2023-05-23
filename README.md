# chatgpt-reddit-topic-modeling
Topic Modeling of ChatGPT SubReddits using LDA

## Business Context
The Artificial Intelligence space has seen a recent boom, with ChatGPT gaining high popularity. The public sentiment is mixed, with critics finding issues with ethical AI, political responses, and how this tool may lead to redundancy in roles.

## Goal
To understand the primary topics being discussed around ChatGPT and provide insights to management on potential topics of interest. Simultaneously, understanding the sentiment around ChatGPT and potential ways OpenAI could improve it.

## Landscape of Industry
Taking into consideration the Top 4 competitors of ChatGPT, we find that on Reddit the # of members is highest for ChatGPT (1.3 million) by a high margin – this indicates that there are many conversations around this tool, and it is relevant to deep dive further to understand – 

What is being spoken about? 
What is the perception of members around various topics?

## Understanding the Purpose
ChatGPT is an extremely popular tool. While chatbots have existed for many years, the accuracy, speed, and amount of knowledge that ChatGPT provides users has resulted in a massive boom in the number of users, as well as the number of opinions on the tool (and AI in general).

The public sentiment is mixed, with critics finding issues with ethical AI, political responses, and how this tool may lead to redundancy in roles. Proponents of the tool argue for its capability to provide an answer to virtually question, in a matter of seconds. 

This variance in sentiment brings about a need to understand what the public is speaking about (on social media) and understand how the product offering (and perceived value) can be improved.

## Significance to the Industry
- Product Improvement: OpenAI would benefit by being able to understand the areas (topics) where ChatGPT does well, and where it can improve (e.g., accuracy of responses, breach of trust and safety layer, etc.) This will ensure public sentiment towards ChatGPT is positive.
- Competitor Analysis: Understand how competitors are doing vs. ChatGPT, and if there are topics that indicate this type of a comparison. Ideally, we would want ChatGPT to be preferred more vs. competitors.
  - Competitors
    - Google's BERT
    - Microsoft's Turing NLG
- Customer Preferences: Understanding the preferences of customers involves identifying topics that talk about feature requests, “wish lists”, as well as customer opinions on AI as a whole. This is important as an AI that behaves the way humans want it to behave would be more accepted.
- Planning Strategy: As ChatGPT continues to evolve (ChatGPT Plus, GPT4 / 5, etc.), we would like to advise OpenAI management on the road ahead – insights that would enable them to tailor their product offerings towards a broader customer base, enabling wider acceptance.

## Data Collection & Related Issues
We scrape data using PRAW (multiple instances of PRAW for various ChatGPT subreddits - ChatGPT, OpenAI, ChatGPTPro, ChatGPTCoding, WeirdGPT).

### General Data Cleaning
- Converting to lower case, removing html tags, special characters, punctuations, single characters, multiple spaces.
- Removing stop words

### Specific Data Cleaning
- Removing links from comments (searching for https://)
- Removing bot / AutoModerator comments
- Removing empty comments and comments where Author is NA
- Removing comments with less than 5 words

## Solution to Identified Data Issues
- To ensure that we have representative data, we scraped from multiple subreddits that reveal diverse viewpoints. For example, we observe that weirdGPT contains primarily negative viewpoints. ChatGPT, ChatGPTPro, and OpenAI contain mixed viewpoints. ChatGPTCoding contains neutral viewpoints.
- For the appropriate sample size, we aim to have at least 1,000 documents. For this reason, we decided to scrape multiple subreddits instead of just one as we can have more representative data & have a greater sample size by running multiple instances of PRAW.
- Scraped over multiple months to avoid short term topic bias.
- We could potentially scrape sources other than Reddit to ensure more representativeness of the data (e.g., Twitter).

## Analytical Methods Taken
### Data Pre-Processing
- General + Specific Data Cleaning
- Stop words
- Lemmatization
- Dictionary
- Bag of Words Corpus

### Topic Modeling
- Latent Dirichlet Allocation
  - Identify topics within a collection of text (common words, grouping)

### Sentiment Analysis
- Lexicon based sentiment analysis (VADER Sentiment)
  - Determine the emotional tone of text
  - Useful for understanding customer feedback on topic
  - Fine-tuned for social media sentiments

## Topic Modeling - LDA
- Topic Modeling using LDA has proven useful in identifying trendy topics within the ChatGPT subreddit.
- Extract k topics for each subreddit, combination of subreddits, or the entire dataset, facilitating deeper analysis of the data.
- Provide valuable insights into the factors that contribute to the user experience for members, potentially informing developers on areas of improvement.
- Using LDA to analyze user discussions on the ChatGPT subreddit has the potential to help product developers better understand user needs and concerns.

## Insights Summary
- The primary sentiment towards ChatGPT is negative-neutral, with most topics indicating a negative sentiment
- The primary usage requirement for most consumers is as a “digital assistant”. Users feed in their personal information / work and expect ChatGPT to help them. (Helping humans reduce work time)
- OpenAI should focus on these strengths – Helping job applicants (during interviews, during job search), Text writing (prompts, resumes, etc.), Assignment assistant (guidance, not answers)
- OpenAI should work on these weaknesses – Inaccuracy of calculations (assignments, etc), Fear of ChatGPT replacing humans, Political answers / bias
### Future Steps
- Create a subset of ChatGPT solely focused on being a “personal digital assistant” – helping users with their personal tasks (such as job hunt, assignments, etc) – this will improve sentiment massively
- Upgrade the trust and safety layer to avoid biased answers around sensitive topics, such as politics (these are personal to users and hence have the tendency to cause negative sentiment if not aligned)
- Work on accuracy of calculations and answers – many users complain about the inaccuracy / malleability of ChatGPT with it’s answers, and this raises doubts on how much it can be trusted.

## Limitations
- Need to scrape for longer and periodically to ensure we can track both short- and long-term trends
- There may be posts made with an image, which our current model cannot track
- Language is a constraint. We have primarily scraped and worked with English comments in this project
- Ethical considerations. Need to consider if it is fair to use human sentiments about AI to modify / upgrade our AI tools

## Conclusion
- Customer Feedback: There is a general negative sentiment towards ChatGPT. Some topics are positive, but it is primarily negative.
- Identifying Key Topics: The most discussed topic regarding ChatGPT is about its promptness, access, and ability to aid humans in reducing the amount of work time. 
- Future Strategy: Faster and easy access to be provided. Focus on the strengths that were identified and offer a subset of ChatGPT.
- Emerging Trends: It has a skill for writing resumes, letter, articles, and job prompts. Users also tend to use it for assignment assistance.
