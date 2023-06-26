# LearningOpenAiExpanding
This repository contains a Python script that generates an email reply to a customer review using the OpenAI GPT-3.5 language model.

# Prerequisites
Python 3.6 or above
OpenAI Python library (openai)

# Installation
1) Clone this repository to your local machine or download the script file.
2) Install the required dependencies by running the following command:
   **pip install openai**

# Usage
Set up your OpenAI API key by replacing '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' with your actual API key in the script.
The get_completion(prompt, model="gpt-3.5-turbo", temperature=0) function generates an email reply. The function takes the following parameters:
prompt: The prompt for generating the email reply.
model (optional): The model to use for generating the response. The default is "gpt-3.5-turbo".
temperature (optional): The degree of randomness in the model's output. Set to 0 for deterministic output. The default is 0.
Customize the prompt variable to include the customer review and sentiment. You can modify the example provided in the script as needed.
Run the script and the generated email reply will be printed to the console.
Example :
import openai

# Set up OpenAI API key
openai.api_key = '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'

# Function to generate email reply
def get_completion(prompt, model="gpt-3.5-turbo", temperature=0):
    messages = [{"role": "user", "content": prompt}]
    response = openai.ChatCompletion.create(
        model=model,
        messages=messages,
        temperature=temperature,
    )
    return response.choices[0].message["content"]

# Customer review and sentiment
sentiment = "negative"
review = '''
So, they still had the 17 piece system on seasonal \
sale for around $49 in the month of November, about \
half off, but for some reason (call it price gouging) \
around the second week of December the prices all went \
up to about anywhere from between $70-$89 for the same \
system. And the 11 piece system went up around $10 or \
so in price also from the earlier sale price of $29. \
So it looks okay, but if you look at the base, the part \
where the blade locks into place doesn’t look as good \
as in previous editions from a few years ago, but I \
plan to be very gentle with it (example, I crush \
very hard items like beans, ice, rice, etc. in the \ 
blender first then pulverize them in the serving size \
I want in the blender then switch to the whipping \
blade for a finer flour, and use the cross cutting blade \
first when making smoothies, then use the flat blade \
if I need them finer/less pulpy). Special tip when making \
smoothies, finely cut and freeze the fruits and \
vegetables (if using spinach-lightly stew soften the \ 
spinach then freeze until ready for use-and if making \
sorbet, use a small to medium sized food processor) \ 
that you plan to use that way you can avoid adding so \
