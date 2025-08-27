# AI_Chatbot_Gemini_API
import google.generativeai as genai

api_key = input("Enter your Gemini API key: ")
genai.configure(api_key=api_key)

model = genai.GenerativeModel("gemini-1.5-flash")
chat = model.start_chat()

print("AI Chatbot Ready! Type 'exit' to quit.")
while True:
    user_input = input("You: ")
    if user_input.lower() == "exit":
        break
    response = chat.send_message(user_input)
    print("Bot:", response.text)

