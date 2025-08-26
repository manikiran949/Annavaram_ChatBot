# Annavaram Temple Chatbot 🏛️

An intelligent AI-powered chatbot that provides information about the Annavaram Temple using Retrieval-Augmented Generation (RAG) technology. The chatbot can answer questions about the temple by searching through a knowledge base PDF and generating contextual responses using OpenAI's language models.

## 🌟 Features

- **Intelligent Q&A**: Ask questions about Annavaram Temple and get accurate, contextual answers
- **RAG Technology**: Combines document search with AI generation for reliable responses
- **Modern Web Interface**: Clean, responsive chat interface with temple-themed design
- **Real-time Interaction**: AJAX-powered chat without page refreshes
- **Vector Search**: Uses FAISS for efficient semantic search through temple information
- **PDF Knowledge Base**: Extracts and processes information from PDF documents

## 🛠️ Technologies Used

- **Backend**: Flask (Python)
- **AI/ML**: LangChain, OpenAI GPT, FAISS Vector Database
- **Frontend**: HTML, CSS, JavaScript (jQuery), Bootstrap
- **Document Processing**: PyPDF2
- **Vector Embeddings**: OpenAI Embeddings

## 📋 Prerequisites

- Python 3.7+
- OpenAI API Key
- Internet connection for API calls

## 🚀 Installation

1. **Clone or Download the Repository**
   ```bash
   git clone <repository-url>
   cd Annavaram_ChatBot
   ```

2. **Create Virtual Environment**
   ```bash
   python -m venv venv
   
   # Activate virtual environment
   # Windows:
   venv\Scripts\activate
   
   # macOS/Linux:
   source venv/bin/activate
   ```

3. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Set Up OpenAI API Key**
   
   Copy the example environment file and add your API key:
   ```bash
   # Windows:
   copy .env.example .env
   
   # macOS/Linux:
   cp .env.example .env
   ```
   
   Then edit the `.env` file and replace `your_openai_api_key_here` with your actual OpenAI API key:
   ```
   OPENAI_API_KEY=your_actual_openai_api_key_here
   ```
   ```bash
   # Windows:
   set OPENAI_API_KEY=your_openai_api_key_here
   
   # macOS/Linux:
   export OPENAI_API_KEY=your_openai_api_key_here
   ```

## 📁 Project Structure

```
Annavaram_ChatBot/
├── app.py                 # Main Flask application
├── annavaram.pdf         # Knowledge base document
├── true_python_file.py   # Testing script
├── templates/
│   └── chat.html         # Chat interface template
├── static/
│   ├── style.css         # Styling for the chat interface
│   └── doctor.jpeg       # Bot avatar image
├── venv/                 # Virtual environment
└── __pycache__/          # Python cache files
```

## 🎯 Usage

1. **Start the Application**
   ```bash
   python app.py
   ```

2. **Access the Chatbot**
   - Open your web browser
   - Navigate to `http://127.0.0.1:8080`
   - Start asking questions about Annavaram Temple!

3. **Example Questions**
   - "What are the different types of darshanas available?"
   - "Tell me about the history of Annavaram Temple"
   - "What are the temple timings?"
   - "How can I reach Annavaram Temple?"
   - "What festivals are celebrated at the temple?"

## 🔧 Configuration

### Changing Port
To run on a different port, modify `app.py`:
```python
if __name__ == '__main__':
    app.run(host="127.0.0.1", port=5000, debug=True)  # Change port here
```

### Using Environment Variables for API Key
For better security, modify `app.py` to use environment variables:
```python
import os
from dotenv import load_dotenv

load_dotenv()
OPENAI_API_KEY = os.environ.get("OPENAI_API_KEY")
```

## 🏗️ How It Works

1. **Document Processing**: The PDF document is processed and split into chunks
2. **Vector Embeddings**: Text chunks are converted to vector embeddings using OpenAI
3. **Vector Storage**: FAISS creates a searchable database of document embeddings
4. **Query Processing**: User questions are converted to embeddings and matched with relevant chunks
5. **Answer Generation**: OpenAI generates contextual answers based on retrieved information

## 🔍 API Endpoints

- `GET /` - Serves the chat interface
- `POST /get` - Processes chat messages and returns AI responses

## 🎨 Customization

### Styling
Modify `static/style.css` to customize:
- Colors and themes
- Chat bubble styles
- Typography
- Responsive breakpoints

### Content
Replace `annavaram.pdf` with your own PDF document to create a chatbot for different topics.

### Bot Avatar
Replace `static/doctor.jpeg` with your preferred bot avatar image.

## 🐛 Troubleshooting

### Common Issues

1. **Import Errors**
   - Ensure virtual environment is activated
   - Verify all dependencies are installed

2. **OpenAI API Key Issues**
   - Check if API key is correctly set
   - Verify API key has sufficient credits
   - Ensure API key has proper permissions

3. **PDF Not Found**
   - Verify `annavaram.pdf` is in the project root
   - Check file permissions

4. **Port Already in Use**
   - Change port in `app.py`
   - Or kill existing processes using the port

## 📝 Development

### Testing
Use `true_python_file.py` to test the RAG functionality without running the web interface:
```bash
python true_python_file.py
```

### Adding New Features
- Modify `app.py` for backend changes
- Update `templates/chat.html` for frontend modifications
- Add new routes as needed

## 🔒 Security Notes

- Never commit API keys to version control
- Use environment variables for sensitive information
- Consider rate limiting for production deployment
- Implement user authentication if needed

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## 📞 Support

For issues and questions:
- Check the troubleshooting section
- Create an issue in the repository
- Verify your OpenAI API setup

## 🙏 Acknowledgments

- OpenAI for the language models
- LangChain for the RAG framework
- FAISS for efficient vector search
- Bootstrap for responsive design components

---

**Note**: Make sure to replace `<repository-url>` with your actual repository URL if you plan to host this on GitHub or similar platforms.