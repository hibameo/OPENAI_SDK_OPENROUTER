🌐 What is OpenRouter?

OpenRouter is a service that lets you access multiple AI models (like GPT-4, Claude, Mistral, Gemini, etc.) using a single API key and endpoint.

It’s like a hub that “routes” your prompts to different large language models (LLMs), so you can easily switch between them in one app.

🛠️ How to Use OpenRouter in Python
1. Sign Up & Get API Key
Go to 👉 https://openrouter.ai

Sign in with GitHub

Go to your dashboard to copy your API Key

2. Install OpenAI SDK (works with OpenRouter too)
3. pip install openai

3. Use OpenRouter in Python
4. import openai

openai.api_key = "your-openrouter-api-key"
openai.base_url = "https://openrouter.ai/api/v1"

response = openai.ChatCompletion.create(
    model="mistralai/mistral-7b-instruct",  # Or any supported model
    messages=[
        {"role": "user", "content": "Hello, how are you?"}
    ]
)

print(response.choices[0].message['content'])


💡 Supported Models
You can use many models, such as:

openai/gpt-3.5-turbo

openai/gpt-4-turbo

anthropic/claude-3-opus

mistralai/mistral-7b-instruct

meta/llama-3-70b-instruct

and more…

Find the full list here:
🔗 https://openrouter.ai/models

🌿 Optional: Use .env File
Create a .env file:

.env
OPENAI_API_KEY=your-openrouter-key
OPENAI_API_BASE=https://openrouter.ai/api/v1

Then load it in Python:

python
from dotenv import load_dotenv
load_dotenv()

🧪 Test Endpoint
Use curl to test:

bash
curl https://openrouter.ai/api/v1/models \
  -H "Authorization: Bearer YOUR-API-KEY"
