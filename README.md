# 🤖 AI Chatbot Education Platform

An AI-powered educational chatbot system combining a **Python/TensorFlow NLP chatbot** backend with a **modern web frontend** featuring user authentication, voice input/output, and real-time chat.

---

## 📸 Screenshots

> Add your screenshots here by placing images in the repo and linking them:
> `![Home Page](screenshots/home.png)`

---

## 🌟 Features

- 🧠 **NLP-based Chatbot** — Trained neural network model using TensorFlow/Keras for intent classification
- 🎓 **Education-focused** — College inquiry bot with intents for courses, admissions, schedules, and FAQs
- 🌐 **Web Interface** — Responsive landing page built with Bootstrap 5 and AOS animations
- 🔐 **User Authentication** — Register and login system with localStorage-based session management
- 🎤 **Voice Input** — Speech-to-text support using the Web Speech Recognition API
- 🔊 **Voice Output** — Text-to-speech AI responses using the SpeechSynthesis API
- 📡 **REST API Backend** — Node.js + Express server with MongoDB for chat history persistence
- 💬 **Floating Chatbox** — Toggle-able chat widget embedded on the main landing page

---

## 🗂️ Project Structure

```
ai-chatbot-education/
│
├── 📄 index.html           # Landing page with embedded chatbox widget
├── 📄 chatbot.html         # Full-screen AI chat interface
├── 📄 login.html           # User login page
├── 📄 register.html        # User registration page
├── 📄 styles.css           # Global styles
├── 📄 script.js            # Frontend logic (auth, chat, voice I/O)
├── 📄 server.js            # Node.js/Express backend server
├── 📄 user.js              # Mongoose User schema
│
├── 🐍 main.py              # Python chatbot inference engine
├── 🐍 trainingData.py      # Model training script
├── 📄 intents.json         # Intent definitions (patterns & responses)
├── 📦 chatbotmodel.h5      # Pre-trained Keras model
├── 📦 words.pkl            # Pickled vocabulary
└── 📦 classes.pkl          # Pickled intent classes
```

---

## 🛠️ Tech Stack

### Frontend
| Technology | Purpose |
|---|---|
| HTML5 / CSS3 | Structure & styling |
| Bootstrap 5 | Responsive UI components |
| Font Awesome 6 | Icons |
| AOS (Animate On Scroll) | Page animations |
| Web Speech API | Voice input & output |

### Backend (Node.js)
| Technology | Purpose |
|---|---|
| Node.js + Express | REST API server |
| MongoDB + Mongoose | Chat history storage |
| Axios | OpenAI API requests |
| CORS | Cross-origin support |

### AI / Python
| Technology | Purpose |
|---|---|
| Python 3.x | Core language |
| TensorFlow / Keras | Neural network model |
| NLTK | Natural language tokenization & lemmatization |
| NumPy | Numerical computation |

---

## 🚀 Getting Started

### Prerequisites

- Node.js v14+ and npm
- Python 3.8+
- MongoDB (local or Atlas)
- OpenAI API key (for GPT responses in the web frontend)

---

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/your-username/ai-chatbot-education.git
cd ai-chatbot-education
```

---

### 2️⃣ Run the Python Chatbot (Terminal)

Install dependencies:

```bash
pip install tensorflow nltk numpy
```

Download NLTK data (run once):

```python
import nltk
nltk.download('punkt')
nltk.download('wordnet')
```

**(Optional) Retrain the model:**

```bash
python trainingData.py
```

**Run the chatbot:**

```bash
python main.py
```

---

### 3️⃣ Run the Node.js Backend Server

Install dependencies:

```bash
npm install express body-parser mongoose axios cors
```

Add your OpenAI API key in `server.js`:

```js
const OPENAI_API_KEY = 'your_openai_api_key_here';
```

Start the server:

```bash
node server.js
```

Server runs at: `http://localhost:5000`

---

### 4️⃣ Open the Web Frontend

Simply open `index.html` in your browser, or serve it with a static server:

```bash
npx serve .
```

Then visit `http://localhost:3000`.

---

## 🔌 API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/api/messages` | Send a user message, get AI response |
| `GET` | `/api/messages` | Retrieve full chat history |

### Example Request

```json
POST /api/messages
{
  "userMessage": "What courses are available?"
}
```

### Example Response

```json
{
  "botMessage": "Informatics College Pokhara offers BSc (Hons) Computing and several BBA specializations..."
}
```

---

## 🧠 How the Python Chatbot Works

1. **Training** (`trainingData.py`): Tokenizes and lemmatizes patterns from `intents.json`, builds a bag-of-words representation, and trains a 3-layer neural network (Dense → Dropout → Dense → Dropout → Softmax).

2. **Inference** (`main.py`): Takes user input, converts it to a bag-of-words vector, runs it through the trained Keras model, and returns the highest-probability response from the matching intent.

3. **Intents** (`intents.json`): Defines tags, example patterns, and possible responses for topics like greetings, courses, admission requirements, class schedules, and more.

---

## 🎤 Voice Features

- **Voice Input**: Click the 🎤 microphone button to speak your question. The Web Speech Recognition API transcribes it and sends it automatically.
- **Voice Output**: The AI's response is read aloud using the browser's built-in SpeechSynthesis API.

---

## ⚙️ Configuration

| File | What to configure |
|---|---|
| `server.js` | `OPENAI_API_KEY`, MongoDB connection URI |
| `script.js` | API base URL (`http://localhost:5000`) |
| `intents.json` | Add/modify chatbot intents, patterns, and responses |

---

## 📦 Dependencies

### Python
```
tensorflow
nltk
numpy
```

### Node.js
```
express
body-parser
mongoose
axios
cors
```

---

## 🤝 Contributing

1. Fork the project
2. Create your feature branch: `git checkout -b feature/AmazingFeature`
3. Commit your changes: `git commit -m 'Add some AmazingFeature'`
4. Push to the branch: `git push origin feature/AmazingFeature`
5. Open a Pull Request

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

## 🙏 Acknowledgements

- Original Python chatbot model by **Riya Nakarmi** (college project)
- [TensorFlow](https://www.tensorflow.org/) & [Keras](https://keras.io/)
- [NLTK](https://www.nltk.org/)
- [Bootstrap](https://getbootstrap.com/)
- [OpenAI](https://openai.com/)

---

> Made with ❤️ for AI-powered education
