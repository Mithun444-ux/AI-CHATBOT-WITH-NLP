COMPANY NAME :CODETECH IT

NAME:Mithun R K

INTERN ID:CT04DG797

DURATION:08-06-2025 TO 08-07-2025

MENTOR:NEELA SANTHOSH KUMAR

Description of the code C: reating a simple AI chatbot using NLP, Pandas, and Matplotlib in Python:

1. Importing Required Libraries

import nltk import pandas as pd import matplotlib.pyplot as plt

nltk: Used for natural language processing (tokenizing and lemmatizing user input).

pandas: For handling and analyzing tabular data.

matplotlib.pyplot: For plotting visual charts (bar chart in this case).

2. Downloading NLTK Resources

nltk.download('punkt') nltk.download('wordnet')

Downloads punkt tokenizer and wordnet lemmatizer dictionary from NLTK.

This is required to break sentences into words and get their base form.

3. Initializing the Lemmatizer

from nltk.stem import WordNetLemmatizer lemmatizer = WordNetLemmatizer()

lemmatizer reduces words to their root form (e.g., "running" → "run").

4. Sample Sales Dataset

data = { 'Day': ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun'], 'Sales': [200, 150, 300, 280, 500, 700, 650] } df = pd.DataFrame(data)


A sample dictionary representing sales for each day of the week.

Converted to a DataFrame for easy analysis and plotting.

5. Predefined User Intent CategorieS

greetings = ["hello", "hi", "hey"] exit_words = ["bye", "exit", "quit"]

Simple keyword-based intent recognition for greetings and exit.

6. Preprocessing Function

def preprocess(text): tokens = nltk.word_tokenize(text.lower()) return [lemmatizer.lemmatize(word) for word in tokens]

Converts user input to lowercase.

Tokenizes the text into words.

Lemmatizes each word to its base form.

7. Chatbot Function

def chatbot(): print("Hi, I'm DataBot! Ask me about sales. Type 'bye' to exit.")

Starts the chatbot interaction.

  Exit Condition

if any(word in tokens for word in exit_words): print("DataBot: Goodbye!") break

Ends chat if user types "bye", "exit", or "quit".

  Greetings Handling

elif any(word in tokens for word in greetings): print("DataBot: Hello! How can I assist you with the data?")

Responds with a friendly greeting.

  Displaying Sales Chart

elif "chart" in tokens or "graph" in tokens: df.plot(x='Day', y='Sales', kind='bar', legend=False) ...

Shows a bar chart of daily sales using Matplotlib.

  Calculating Average Sale

elif "average" in tokens: avg = df['Sales'].mean() print(f"DataBot: The average sale is {avg:.2f}.")

Calculates and displays the mean of sales.

  Displaying Highest Sale

elif "highest" in tokens or "max" in tokens: max_val = df['Sales'].max() ...

Finds the maximum sales value and the corresponding day.

  Summary Statistics

elif "summary" in tokens or "summarize" in tokens: print(df.describe())

Prints summary statistics using pandas.DataFrame.describe() (mean, std, min, max, etc.)

  Default Response

else: print("DataBot: Sorry, I didn't understand that...")

Responds when the input doesn't match any known keyword.

8. Start the Chatbot

chatbot()

Runs the chatbot function in an infinite loop until the user exits.

  Overall Functionality

This chatbot:

Understands basic user input through keyword matching.

Uses NLP (tokenizing + lemmatizing) to process natural language.

Analyzes and visualizes sales data using Pandas and Matplotlib.

OUTPUT

![Image](https://github.com/user-attachments/assets/0484e24d-9bec-488a-a0f8-2732e76c4c53)
