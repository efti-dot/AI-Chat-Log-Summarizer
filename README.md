Project name: AI Chat Log Summarizer

Project description: A simple Python program that takes in user-AI chat logs, processes, and summarizes them based on basic Natural Language Processing (NLP) principles using TF-IDF for keyword extraction.

Project explaination: Firstly, the program take a input .txt file and Parses chat logs line by line. In Chat Log Parsing step, it separates messages by User and AI using startswith() function. Secondly, count the total message, user message and AI message. Thirdly, extracts the top five keywords using TF-IDF (ignores stopwords). TF-IDF is a numerical statistic used in Natural Language Processing (NLP) to reflect how important a word is in a document. In this step, i use use sklearn for this and removes common stopwords. Transforms the messages into a matrix of TF-IDF scores. Then converts the result into a simple 1D array. And pairs each word with its score. Then selects the top five keywords based on the highest scores. Finally, calculate total number of exchange messages, nature of the conversation and Most common keywords. In nature of conversation step, i use priority-based approch. Pick the top most meaningful keywords and checks if a phrase formed by combining the top two (e.g., "machine learning") exists in the actual chat text. If ture then add this to the main topic. Otherwise, the top individual keyword is selected as the main topic (top keyword must be unmatched with skip words like "hi", "hello", "can" etc. because Words like "hi", "hello", "can", etc. do not represent meaningful topics.).

How to run:
  1. Clone or download the repository.
  2. Add your .txt chat log.
  3. Chat file should be formatted like:
      User: Hello!
      AI: Hi! How can I assist you today?
      User: Can you explain what machine learning is?
      AI: Sure! Machine learning is a field of AI that allows systems to learn from data.
  4. Update the file path.

Sample outputs: For this given chat log, the output is --> Summary:
                                                           - The conversation had 4 exchanges.
                                                           - The user asked mainly about machine learning and related topics.
                                                           - Most common keywords: hello,learning,machine,explain,assist
