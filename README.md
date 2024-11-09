import openai
# Setup API key for ChatGPT
openai.api_key = 'YOUR_API_KEY_HERE'

def get_explanation(prompt):
    response = openai.ChatCompletion.create(
        model="gpt-3.5-turbo",
        messages=[{"role": "user", "content": prompt}]
    )
    return response.choices[0].message['content']

# Example prompt
user_prompt = "Explain Newton's First Law in simple terms"
explanation = get_explanation(user_prompt)
print("Explanation:", explanation)
