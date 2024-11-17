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

For Installation of PyTorch see [official website](https://pytorch.org/).

You also need `nltk`:
 ```console
pip install nltk
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
      "patterns": ["Hi", "Hello", "Hey", "Good day"],
      "responses": [
        "Hello! How can I assist with your flight booking?",
        "Hi there! Ready to book your flight?",
        "Hello! Need help with airline tickets?"
      ]
    },
    {
      "tag": "goodbye",
      "patterns": ["Goodbye", "Bye", "See you later"],
      "responses": [
        "Goodbye! Safe travels!",
        "Bye! Happy to help with your next flight!",
        "See you soon, enjoy your journey!"
      ]
    },
    {
      "tag": "thanks",
      "patterns": ["Thank you", "Thanks", "Much appreciated"],
      "responses": ["You're welcome!", "Glad to help!", "My pleasure!"]
    },
    {
      "tag": "flight_booking",
      "patterns": [
        "I want to book an airplane ticket",
        "Can you help me book a flight?",
        "I need an airplane ticket for my trip"
      ],
      "responses": [
        "Sure, I can help with that. Please provide your destination and travel date.",
        "Absolutely! Where would you like to fly to, and when would you like to travel?"
      ]
    },
    {
      "tag": "destination",
      "patterns": [
        "I want to go to New York",
        "Flying to Los Angeles",
        "My destination is Tokyo"
      ],
      "responses": [
        "Got it! How many seats will you need?",
        "Noted. How many passengers will be traveling?"
      ]
    },
    {
      "tag": "travel_date",
      "patterns": [
        "On 15th October",
        "Flying on 1st November",
        "I need a ticket for 20th December"
      ],
      "responses": [
        "Noted! Would you prefer Economy, Business, or First Class?",
        "Date set. Do you have a preferred class for the flight?"
      ]
    },
    {
      "tag": "class_preference",
      "patterns": [
        "Economy class",
        "Business class",
        "First Class"
      ],
      "responses": [
        "Great choice! Let me check available flights for you.",
        "Class selected. Finding the best flight options..."
      ]
    },
    {
      "tag": "payment",
      "patterns": [
        "Can I pay with credit card?",
        "Do you accept PayPal?",
        "Is UPI payment available?"
      ],
      "responses": [
        "We accept all major credit cards, PayPal, and UPI payments.",
        "Yes, you can pay via credit card, PayPal, or UPI."
      ]
    },
    {
      "tag": "baggage_allowance",
      "patterns": [
        "What's the baggage allowance?",
        "How much baggage can I take?",
        "Is there a limit on checked baggage?"
      ],
      "responses": [
        "The baggage allowance varies by airline and class. I can provide specific details for your selected flight.",
        "For most flights, Economy class allows 20-30 kg, Business and First class allow more. I'll check for your chosen airline."
      ]
    },
    {
      "tag": "seating",
      "patterns": [
        "Can I select my seat?",
        "I want a window seat",
        "Do I have to pay for seat selection?"
      ],
      "responses": [
        "Yes, you can select your seat during booking. Window and aisle seats may have an additional charge depending on the airline.",
        "Seat selection is available! Some seats may have an extra fee, depending on the airline."
      ]
    }
  ]
}
