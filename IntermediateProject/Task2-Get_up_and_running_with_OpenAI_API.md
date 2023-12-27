# **Prompt Engineering**
## **Task 2 :** Get up and running with the OpenAI API
### Step 1: Setup Python

Make sure you have Python installed on your system. You can download Python from the official website: https://www.python.org/. Follow the installation instructions based on your operating system.
#
### Step 2: Setup your API key

If you haven't obtained your OpenAI API key yet, sign up or log in to your OpenAI account and get your API key from the OpenAI Dashboard: https://platform.openai.com/account/api-keys

Once you have your API key, keep it handy as you'll need it to authenticate your requests.
#
### Step 3: Sending your first API request

Create a Python file named `openai-test.py` in your preferred text editor, IDE, or via the terminal. Copy and paste the following code into the `openai-test.py` file:

```python
import openai

# Replace 'YOUR_API_KEY' with your actual OpenAI API key
api_key = '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'
openai.api_key = api_key

def send_first_request():
    prompt_text = "Once upon a time"
    
    response = openai.Completion.create(
        engine="text-davinci-003",  # GPT-3.5 model
        prompt=prompt_text,
        max_tokens=50,  # Maximum length of the completion
    )
    
    return response.choices[0].text.strip()

result = send_first_request()
print("OpenAI API Response:", result)
```

Replace `'YOUR_API_KEY'` with your actual OpenAI API key obtained from the OpenAI Dashboard.
#
### Step 4: Running the file

If you created the `openai-test.py` file in your IDE, simply run the script within your IDE environment.

If you created the file via the terminal, navigate to the directory where `openai-test.py` is located using the terminal, and run the following command:

```bash
python openai-test.py
```

This script sends a request to the OpenAI API using the `text-davinci-003` engine, providing a prompt "Once upon a time" and generating a text completion of maximum 50 tokens. The generated response from the OpenAI API will be printed in the terminal or the IDE's console.

Ensure that your Python environment is correctly set up, and the `openai` library is installed (`pip install openai`) before running the script. Adjust the code or parameters as needed based on your API usage or requirements.
#
# **Output (Screenshot) : **
![Screenshot (68)](https://github.com/abhishakejutur/Prompt-Engineering/assets/91953148/a94087cf-7c12-47d3-9f59-93c5f965acf9)
#
