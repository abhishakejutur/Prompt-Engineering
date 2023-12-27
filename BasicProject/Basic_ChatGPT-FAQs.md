## **Requirements :**

- python==3.9.7
- pip==21.3.1
- numpy==1.21.2
- transformers==4.11.3

## **Chatbot Project Setup Instructions for Beginners :**

1. **Python Installation:**
   - Download and install Python 3.9.7 from the official Python website: https://www.python.org/downloads/.

2. **Update pip (Python Package Manager):**
   - Open your command line or terminal and run the following command to update `pip` to the latest version:
     ```
     pip install --upgrade pip
     ```

3. **Create a Project Folder:**
   - Create a folder for your project. You can name it whatever you like, e.g., "ChatbotProject."

4. **Create a Virtual Environment (Optional but Recommended):**
   - To create a virtual environment, run the following commands in your project folder:
     ```
     python -m venv venv
     ```
   - Activate the virtual environment:
     - On Windows:
       ```
       venv\Scripts\activate
       ```
     - On macOS and Linux:
       ```
       source venv/bin/activate
       ```

5. **Install Required Libraries:**
   - Create a `requirements.txt` file in your project folder and add the following lines:
     ```
     python==3.9.7
     pip==21.3.1
     numpy==1.21.2
     transformers==4.11.3
     # Add any other project-specific libraries here
     ```
   - Install the libraries using the following command:
     ```
     pip install -r requirements.txt
     ```

6. **Install Visual Studio Code (VS Code):**
   - Download and install Visual Studio Code from the official website: https://code.visualstudio.com/.

7. **Install VS Code Extensions (Optional):**
   - Open VS Code and go to the Extensions view (click on the square icon on the left sidebar).
   - Search for and install any VS Code extensions you find useful for your development, such as Python extensions or code formatting extensions.

8. **Create a Chatbot Script:**
   - Create a Python file for your chatbot code in the project folder. Name it, e.g., "chatbot.py."

9. **Add Chatbot Code:**
   - Copy and paste your chatbot code into the "chatbot.py" file. You can use the provided sample code as a starting point.

10. **Run Your Chatbot:**
    - Open a terminal within VS Code or use your system's command line to navigate to the project folder.
    - Activate the virtual environment if you created one.
    - Run your chatbot script using the following command:
      ```
      python chatbot.py
      ```

11. **Interact with Your Chatbot:**
    - Your chatbot will now be running in the terminal or command line. You can interact with it by typing input, and it will respond based on the rules and FAQs you defined.

12. **Exit Your Chatbot:**
    - To exit your chatbot, type 'bye' in the terminal, and it will respond with a goodbye message.

That's it! You've successfully set up your chatbot project with all the required instructions in a single `setup_instructions.txt` file.


# **Code :**


```python
import random
```


```python
# Define a dictionary of ChatGPT-related questions and their answers
chatgpt_faqs = {
    "what is chatgpt?": "ChatGPT is a language model developed by OpenAI that is designed for natural language conversation. It can answer questions, generate text, and have interactive discussions with users.",
    "how does chatgpt work?": "ChatGPT is powered by a deep learning model called GPT (Generative Pre-trained Transformer). It's trained on a large corpus of text from the internet and uses that knowledge to generate human-like text based on input.",
    "what can i do with chatgpt?": "You can use ChatGPT for a variety of tasks, such as answering questions, generating text, creating content, providing recommendations, and much more.",
    "is chatgpt free to use?": "OpenAI offers both free and paid access to ChatGPT. There may be usage limitations on the free tier, and you can check OpenAI's pricing for more details.",
    "what is prompt engineering?": "Prompt engineering is the process of designing specific instructions or questions to obtain desired responses from a language model like ChatGPT. It involves crafting prompts to be clear and effective in conveying your intent.",
    # Add more FAQs as needed...
    "What can I use ChatGPT for?": "ChatGPT can be used for various purposes such as generating text for conversations, answering questions, assisting in writing tasks, creating content, and more.",
    "Is ChatGPT powered by machine learning?": "Yes, ChatGPT is powered by machine learning, specifically a type of deep learning model called a transformer.",
    "What versions of GPT are available in ChatGPT?": "ChatGPT currently uses GPT-3, the third iteration of the Generative Pre-trained Transformer developed by OpenAI.",
    "How accurate is ChatGPT in generating responses?": "ChatGPT aims to generate contextually relevant and coherent responses. However, its accuracy may vary depending on the input and complexity of the query.",
    "Can ChatGPT understand context in conversations?": "Yes, ChatGPT is designed to understand context in conversations and generate responses based on the preceding dialogue.",
    "Are there limitations to what ChatGPT can understand or answer?": "While ChatGPT is proficient in generating text, it may not always provide accurate or complete information. Its responses are based on the patterns in the data it was trained on.",
    "Can ChatGPT perform tasks other than generating text?": "ChatGPT is primarily designed for text generation but can be fine-tuned for specific tasks such as translation, summarization, and more.",
    "Is ChatGPT capable of learning from new information or updates?": "ChatGPT does not learn or update in real-time. It generates responses based on its pre-existing knowledge learned during training.",
    "How can I improve the accuracy of ChatGPT's responses?": "Providing clear and specific inputs can help improve the accuracy of ChatGPT's responses. Additionally, fine-tuning the model for specific tasks may enhance performance.",
    "Is ChatGPT's usage limited by any terms or policies?": "Yes, the usage of ChatGPT is subject to OpenAI's use case policy and terms of service. It should be used responsibly and in compliance with these policies.",
    "Where can I find more information about ChatGPT and its capabilities?": "You can find detailed information about ChatGPT, its capabilities, and best practices on the OpenAI website and documentation.",
    "What is your product?": "Our product is a multi-purpose tool designed to...",
    "How can I contact support?": "You can reach our support team via email at support@example.com.",
    # Add more FAQ pairs here
    "Is there a free trial available?": "Yes, we offer a 14-day free trial for new users.",
    "What payment methods do you accept?": "We accept major credit cards such as Visa, Mastercard, and American Express.",
    "Can I upgrade my plan later?": "Certainly! You can upgrade your plan at any time from your account settings.",
    "Do you offer refunds?": "We have a 30-day refund policy for our subscriptions. Please refer to our terms of service for details."
}
```


```python
# Define some sample rules for the chatbot
rules = {
    "hello": ["Hi there!", "Hello!", "How can I help you today?"],
    "how are you": ["I'm just a computer program, so I don't have feelings, but thanks for asking! How can I assist you?", "I'm here to help. What can I do for you?"],
    "bye": ["Goodbye!", "Have a great day!", "See you later!"],
    "help": ["You can ask me questions or say hello. If you want to exit, just type 'bye'."],
}
```


```python
def chatbot_response(user_input):
    user_input_lower = user_input.lower().strip()
    
    if user_input_lower in chatgpt_faqs:
        return chatgpt_faqs[user_input_lower]
    elif user_input_lower in rules:
        return random.choice(rules[user_input_lower])
    else:
        return "I'm not sure I understand. Can you please rephrase your question or greeting?"
```


```python
# Main chat loop
print("Chatbot: Hi! I'm your friendly chatbot. You can start a conversation with me or type 'bye' to exit.")
while True:
    user_input = input("You: ")
    if user_input.lower() == "bye":
        print("Chatbot: Goodbye!")
        break
    response = chatbot_response(user_input)
    print("Chatbot:", response)
```

# **Output :**
![Screenshot (61)](https://github.com/abhishakejutur/Prompt-Engineering/assets/91953148/00363752-43fd-4894-aef8-39646b8aa5eb)



