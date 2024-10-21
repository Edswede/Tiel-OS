# Tiel-OS
pip install tensorflow numpy
import random

# Define some simple rules for responses
responses = {
    "hello": ["Hi there!", "Hello!", "Greetings!", "How can I help you today?"],
    "how are you?": ["I'm just a bot, but thanks for asking!", "Doing well, how about you?", "I'm here to assist you!"],
    "what is your name?": ["I'm a simple AI chatbot.", "You can call me Chatbot!", "Just a bot without a name."],
    "bye": ["Goodbye!", "See you later!", "Take care!"],
}

# Function to get a response based on user input
def get_response(user_input):
    # Normalize the input
    user_input = user_input.lower()
    # Check for matching responses
    for key in responses:
        if key in user_input:
            return random.choice(responses[key])
    return "I'm sorry, I don't understand that."

# Chat loop
print("Chatbot: Hi! I'm a chatbot. Type 'bye' to exit.")
while True:
    user_input = input("You: ")
    if user_input.lower() == 'bye':
        print("Chatbot: Goodbye!")
        break
    response = get_response(user_input)
    print("Chatbot:", response)
