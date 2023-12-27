```python
import openai
```




```python
# openai.api_key = "your secret API Key"
openai.api_key = "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"
```


```python
# this loop will let us ask questions continuously

while True:
    
    # Set up the model and prompt
    model_engine = "text-davinci-003"
    
    prompt = input('Enter new prompt: ')

    if 'exit' in prompt or 'quit' in prompt:
        break

    # Generate a response
    # given the most recent context (4096 characters)
    # continue the text up to 2048 tokens ~ 8192 charaters
    completion = openai.Completion.create(
        engine=model_engine,
        prompt=prompt,
        max_tokens=1024,
        n=1,
        stop=None,
        temperature=0.5,
    )
    
    # extracting useful part of response
    response = completion.choices[0].text
    
    # printing response
    print(response)
```
**Output :**
```
    
    Enter new prompt: Which is the largest country by area in the world?
    
    
    Russia is the largest country in the world by area, with a total landmass of 17,098,242 square kilometers (6,601,668 square miles).
    Enter new prompt: population to top 5 countries
    
    
    1. China - 1.4 billion
    2. India - 1.3 billion
    3. United States - 330 million
    4. Indonesia - 270 million
    5. Brazil - 210 million
    Enter new prompt: top 5 football players in the world
    
    
    1. Lionel Messi
    2. Cristiano Ronaldo
    3. Neymar Jr.
    4. Robert Lewandowski
    5. Kylian Mbappe
    Enter new prompt: exit
    
