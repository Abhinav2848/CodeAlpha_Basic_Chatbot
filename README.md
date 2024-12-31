import nltk
from nltk.chat.util import Chat, reflections

# Define a list of patterns and responses
pairs = [
    [
        r"my name is (.*)",
        ["Hello %1, how can I help you today?", ]
    ],
    [
        r"hi|hello|hey",
        ["Hello!", "Hi there!", "Hey! How can I assist you?", ]
    ],
    [
        r"what is your name?",
        ["I am a chatbot created for this example. What's your name?", ]
    ],
    [
        r"how are you?",
        ["I'm just a bunch of code, but thanks for asking! How are you?", ]
    ],
    [
        r"sorry (.*)",
        ["It's okay, no need to apologize!", ]
    ],
    [
        r"thank you|thanks",
        ["You're welcome!", "No problem!", ]
    ],
    [
        r"bye|goodbye",
        ["Goodbye! Have a great day!", ]
    ],
    [
        r"(.*)",
        ["I'm not sure how to respond to that. Can you tell me more?", ]
    ],
]

# Create a chatbot instance
chatbot = Chat(pairs, reflections)

# Start the conversation
def chatbot_conversation():
    print("Hi! I am a chatbot. How can I help you?")
    while True:
        user_input = input("You: ")
        if user_input.lower() in ['bye', 'goodbye']:
            print("Chatbot: Goodbye! Have a great day!")
            break
        else:
            response = chatbot.respond(user_input)
            print(f"Chatbot: {response}")

if __name__ == "__main__":
    chatbot_conversation()
