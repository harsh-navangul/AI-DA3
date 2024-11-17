# Implementation of a Chatbot in PyTorch.  

## Installation

### Create an environment
Whatever you prefer (e.g. `conda` or `venv`)
```console
mkdir myproject
$ cd myproject
$ python3 -m venv venv
```

```console
venv\Scripts\activate
```
### Install PyTorch and dependencies



You also need `nltk`:
 ```console
pip install nltk torch
 ```

If you get an error during the first run, you also need to install `nltk.tokenize.punkt`:
Run this once in your terminal:
 ```console
$ python
>>> import nltk
>>> nltk.download('punkt')
```

## Usage
Run
```console
python train.py
```
This will dump `data.pth` file. And then run
```console
python chat.py
```
## Customize
Have a look at [intents.json](intents.json). You can customize it according to your own use case. Just define a new `tag`, possible `patterns`, and possible `responses` for the chat bot. You have to re-run the training whenever this file is modified.
```console
{
  "intents": [
    {
      "tag": "greeting",
      "patterns": [
        "Hi",
        "Hey",
        "How are you",
        "Is anyone there?",
        "Hello",
        "Good day"
      ],
      "responses": [
        "Hey :-), How can I help for your next Trip?",
        "Hello, How can I help for your next Trip?",
        "Hi there, what can I do for your next Trip?",
        "Hi there, how can I help for your next Trip?"
      ]
    },
    {
      "tag": "goodbye",
      "patterns": ["Bye", "See you later", "Goodbye"],
      "responses": [
        "See you later, Happy Journey",
        "Have a Safe Trip",
        "Bye! Come back again soon."
      ]
    },
    {
      "tag": "thanks",
      "patterns": ["Thanks", "Thank you", "That's helpful", "Thank's a lot!"],
      "responses": ["Happy to help!", "Any time!", "My pleasure"]
    },
    {
      "tag": "trip",
      "patterns": [
        "I wanted a package for my trip to Manali",
        "I am planning for a trip to Manali",
        "Do you plan a trip to Manali?"
      ],
      "responses": [
        "Yes, for a Trip to Manali. May I know for How many days' package you need?"
      ]
    },
    {
      "tag": "payments",
      "patterns": [
        "Do you take credit cards?",
        "Do you accept Mastercard?",
        "Can I pay with Paypal?",
        "Are you cash only?"
      ],
      "responses": [
        "We accept VISA, Mastercard and Paypal",
        "We accept most major credit cards, and Paypal"
      ]
    },
    {
      "tag": "days",
      "patterns": [
        "1 Day",
        "2 Days",
        "3 Days",
		"4 Days",
		"5 Days",
		"6 Days",
		"7 Days",
		"8 Days",
		"9 Days",
		"10 Days"
		
      ],
      "responses": [
        "Sure, We have! May I know in which Month are you planning for the trip?",
        "Sure, Please enter your journey Month"
      ]
    },
    {
      "tag": "Month",
      "patterns": [
        "Janurary",
        "February",
		"March",
		"April",
		"December",
        "May"
		
      ],
      "responses": [
        "Sure, You can have a stay at Hotel Mount View",
        "Sure, You can have a stay at Hotel Harsh Paradise"
      ]
    }
  ]
}
