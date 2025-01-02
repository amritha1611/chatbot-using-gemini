# Gemini AI Chatbot

## Overview

This repository demonstrates the implementation of a conversational AI chatbot using Google Gemini AI. The chatbot, named **Chitti the Robot**, is tailored to assist students in the Data Science domain by answering their queries and providing detailed explanations.

---

## Features
- **Conversational AI**: Powered by Google Gemini AI, offering natural and insightful interactions.
- **Customizable Chat Model**: Based on the `gemini-1.5-flash` model with personalized instructions.
- **Real-time Interaction**: Users can engage in dynamic conversations with Chitti.
- **Data Science Expertise**: Specialized to resolve queries related to Data Science, Machine Learning, and related topics.

---

## Getting Started

### Prerequisites
1. Python 3.7+
2. Google Gemini AI Python SDK (`google-generativeai`)
3. A valid Gemini AI API Key

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/gemini-ai-chatbot.git
   cd gemini-ai-chatbot
   ```

2. Install dependencies:
   ```bash
   pip install google-generativeai
   ```

3. Set up the API key:
   - Place your API key in a file at `keys/.gemini_api_key.txt`.

---

## Usage

### Basic Interaction

Run the chatbot script:
```python
import google.generativeai as genai

# Set up the API Key
with open("keys/.gemini_api_key.txt") as f:
    key = f.read()

genai.configure(api_key=key)

# Initialize the model
model = genai.GenerativeModel('gemini-1.5-flash')
chat = model.start_chat(history=[])

# Chat Loop
while True:
    prompt = input("Enter your prompt:")
    if prompt.lower() in ['exit', 'bye']:
        break
    response = chat.send_message(prompt)
    print(f"Chitti: {response.text}")
```

### Custom Instructions
The chatbot is pre-configured with a persona:
- Name: Chitti the Robot
- Description: Helpful AI assistant specializing in Data Science.

To modify the instructions:
```python
model = genai.GenerativeModel(
    'gemini-1.5-flash',
    system_instruction="""You are a helpful AI assistant.
    You resolve the doubts of students from the Data Science domain.
    Your name is 'Chitti the Robot'."""
)
```

---

## Supported Models
List of available Gemini AI models:
- `gemini-1.5-flash`
- `gemini-1.5-pro`
- `gemini-2.0-flash-exp`
- And more...

To list all models:
```python
for model in genai.list_models():
    print(model.name)
```

---

## Contributions
Contributions are welcome! Feel free to open an issue or submit a pull request.

---

## License
This project is licensed under the MIT License. See the LICENSE file for details.

---

## Acknowledgments
- **Google Gemini AI**: For the powerful generative models.
- **Chitti the Robot**: For being the inspiration behind this project.
