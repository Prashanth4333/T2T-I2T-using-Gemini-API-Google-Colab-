# T2T-I2T-using-Gemini-API-Google-Colab-

📄 README.md Content
markdown
Copy
Edit
# 🤖 Gemini AI - Text & Vision Model Explorer (Google Generative AI SDK)

This project demonstrates how to interact with both text and multimodal (image+text) Gemini models using Google's `google-generativeai` SDK in Google Colab.

> Built with 💡 Python + Google Colab + Gemini API (Generative AI)

---

## 🚀 Features

- ✅ Access Gemini API securely using API key  
- 🧠 Chat with `gemini-1.5-pro` (Text-to-Text)  
- 🖼️ Use `gemini-1.0-pro-vision` for Image-to-Text generation  
- 📜 List all available Gemini models  
- 💬 Handle multi-turn conversations (chat mode)  

---

## 🧰 Requirements

- Google Colab or Jupyter Notebook  
- A valid Gemini API key from [Google AI Studio](https://makersuite.google.com/app)  
- Python 3.7+  

---

## 📦 Installation

```bash
pip install -U google-generativeai
🔐 API Key Setup
python
Copy
Edit
from google.colab import userdata
import google.generativeai as genai

genai.configure(api_key=userdata.get("GOOGLE_API_KEY"))
📜 List Available Gemini Models
python
Copy
Edit
for model in genai.list_models():
    print(model.name)
💬 Text-to-Text Chat using gemini-1.5-pro
python
Copy
Edit
model = genai.GenerativeModel(model_name="gemini-1.5-pro")
chat = model.start_chat()

response = chat.send_message("Explain the difference between AI and ML.")
print(response.text)
✅ Sample Output:
AI is a broad concept involving machines that can perform tasks that typically require human intelligence. ML is a subset of AI focused on systems that learn from data.

🖼️ Image-to-Text with gemini-1.0-pro-vision
python
Copy
Edit
model = genai.GenerativeModel("gemini-1.0-pro-vision")

from PIL import Image
img = Image.open("your_image.jpg")

response = model.generate_content(["Describe this image", img])
print(response.text)
✅ Sample Output:
The image shows a modern smartwatch with a black strap placed on a wooden table.

📂 Project Files
vbnet
Copy
Edit
📁 gemini-ai-demo/
├── README.md
├── gemini_text_chat.ipynb         # Text chat using gemini-1.5-pro
├── gemini_image_chat.ipynb        # Image + text using gemini-1.0-pro-vision
🧠 Author
Prashanth 4333
🌐 GitHub: github.com/prashanth4333

📄 License
This project is licensed under the MIT License.

🙌 Acknowledgements
Google Generative AI SDK

Google AI Studio

yaml
Copy
Edit
