# Portfolio

Efren Gabriel Aying - AI Portfolio Chatbot
An intelligent AI-powered chatbot integrated into a personal portfolio website, built with Flowise AI and powered by Cohere's language models. The chatbot answers questions about skills, projects, experience, and contact information.

🚀 Features

AI-Powered Conversations - Natural language understanding with Cohere AI
Context-Aware Responses - Retrieval-Augmented Generation (RAG) for accurate answers
Memory Management - Remembers conversation history for better context
Custom Branding - Personalized chatbot design matching portfolio theme
Interactive UI - Smooth animations and modern design
Starter Prompts - Quick questions for easy interaction
Mobile Responsive - Works seamlessly on all devices


🛠️ Tech Stack
Frontend

HTML5
CSS3 (Custom Styling)
JavaScript (ES6+)
Flowise Embed Widget

AI & Backend

Flowise AI - Visual AI workflow builder
Cohere AI - Language model (llama-3.1-8b-instant via Groq)
Cohere Embeddings - Vector embeddings for document search
LangChain - AI orchestration framework
Vector Store - In-Memory Vector Store for RAG

Database (Optional)

MySQL - Record management via XAMPP
phpMyAdmin - Database administration


📋 Prerequisites
Before you begin, ensure you have:

Node.js (v16 or higher)
npm or yarn
Flowise AI installed (npm install -g flowise)
API Keys:

Cohere API Key (for embeddings)
Groq API Key (for LLM) or alternative AI provider


XAMPP (optional, for MySQL Record Manager)


🔧 Installation
1. Clone the Repository
bashgit clone https://github.com/SasayAying/portfolio-ai-chatbot.git
cd portfolio-ai-chatbot
2. Install Flowise
bashnpm install -g flowise
3. Start Flowise
bashnpx flowise start
This will open Flowise at http://localhost:3000
4. Set Up XAMPP (Optional - for MySQL)

Download XAMPP from https://www.apachefriends.org/
Install and start Apache + MySQL services
Open phpMyAdmin at http://localhost/phpmyadmin
Create database: flowise_db


⚙️ Configuration
1. Get API Keys
Cohere API Key:

Go to https://cohere.com/
Sign up for free account
Navigate to API Keys section
Copy your API key

Groq API Key:

Go to https://console.groq.com/
Create account
Generate API key
Copy the key

2. Configure Flowise Chatflow

Open Flowise at http://localhost:3000
Create new chatflow or import Aying AI Chatflow.json
Add credentials:

Cohere Embeddings: Paste Cohere API key
GroqChat: Paste Groq API key


Upload knowledge base: efren_aying_portfolio.txt

3. MySQL Configuration (Optional)
XAMPP Default Credentials:
Host: localhost
Username: root
Password: (leave blank)
Database: flowise_db
Port: 3306

📁 Project Structure
portfolio-ai-chatbot/
│
├── index.html                      # Main portfolio page
├── style.css                       # Portfolio styling
├── efren_aying_portfolio.txt       # AI knowledge base
├── Aying AI Chatflow.json          # Flowise chatflow config
├── README.md                       # This file
│
├── image/
│   └── IMAGE1.jpg                  # Profile image
│
└── flowise-config/
    ├── chatbot-embed.js            # Chatbot integration code
    └── credentials.example.json    # Example API keys (DO NOT COMMIT REAL KEYS)

🎨 Chatbot Customization
Update Chatbot Appearance
Edit the chatbot embed code in index.html:
javascripttheme: {
    button: {
        backgroundColor: '#667eea',  // Change button color
        size: 56,                     // Button size
    },
    chatWindow: {
        title: 'Your Title Here',    // Custom title
        welcomeMessage: 'Your message', // Welcome text
    }
}
Update Knowledge Base
Edit efren_aying_portfolio.txt with your information:

Personal details
Skills and expertise
Projects
Contact information

Then re-upload to Flowise Document Store.

🚀 Deployment
Deploy Flowise
Option 1: Railway (Recommended)

Go to https://railway.app/
Deploy Flowise from template
Add environment variables (API keys)
Update apiHost in chatbot embed code

Option 2: Render

Go to https://render.com/
Create new web service
Deploy Flowise Docker image
Configure environment variables

Option 3: Self-Hosted
bashnpm install -g flowise
flowise start --PORT=3000
Deploy Portfolio Website
Option 1: GitHub Pages
bashgit add .
git commit -m "Deploy portfolio"
git push origin main
Enable GitHub Pages in repository settings.
Option 2: Netlify

Connect GitHub repository
Auto-deploy on push

Option 3: Vercel
bashnpm install -g vercel
vercel

📝 Usage
For Users

Open Portfolio: Visit your portfolio website
Click Chat Button: Bottom-right corner
Ask Questions:

"What are Efren's technical skills?"
"Tell me about his projects"
"How can I contact him?"


Get Instant Answers: AI responds with accurate information

For Developers
Update Content:
bash# 1. Edit knowledge base
nano efren_aying_portfolio.txt

# 2. Re-upload to Flowise Document Store

# 3. Test chatbot
Add New Features:

Open Flowise
Add new nodes to chatflow
Connect and configure
Save and test


🔍 Chatflow Architecture
Text File (Knowledge Base)
    ↓
Recursive Character Text Splitter
    ↓
In-Memory Vector Store ← Cohere Embeddings
    ↓
Conversational Retrieval QA Chain ← GroqChat (LLM)
                                  ← Buffer Memory
Components Explained:

Text File: Loads portfolio information
Text Splitter: Chunks documents for processing
Vector Store: Stores embedded documents
Cohere Embeddings: Converts text to vectors
GroqChat: LLM for generating responses
Buffer Memory: Maintains conversation history
Retrieval QA Chain: Orchestrates RAG workflow


🐛 Troubleshooting
Chatbot Not Loading
Problem: Chat button doesn't appear
Solution:

Check browser console for errors
Verify chatflow ID matches
Ensure Flowise is running
Check API host URL

API Key Errors
Problem: "Unauthorized" or "Invalid API Key"
Solution:
javascript// Verify credentials in Flowise
1. Go to Credentials section
2. Re-enter API keys
3. Test connection
4. Save chatflow
MySQL Connection Failed
Problem: MySQL Record Manager can't connect
Solution:

Start MySQL service in XAMPP
Check credentials (username: root, password: blank)
Verify database exists
Check port 3306 is available

PowerShell Execution Policy Error
Problem: npm install flowise fails with execution policy error
Solution:
powershellSet-ExecutionPolicy -ExecutionPolicy Bypass -Scope Process
npm install -g flowise
Groq API Permission Error
Problem: "Only team owners or users with developer role may create API keys"
Solution:

Create new personal Groq account
Use alternative: Google Gemini or OpenAI
Ask team admin for developer role


🔐 Security Notes
⚠️ IMPORTANT: Never commit API keys to Git!
Protect Your Keys:

Create .gitignore:

gitignore# API Keys and Credentials
credentials.json
.env
config.json

# XAMPP
xampp/

# Node modules
node_modules/

Use Environment Variables:

bashexport COHERE_API_KEY="your-key-here"
export GROQ_API_KEY="your-key-here"

Rotate Keys Regularly: Generate new API keys every 3-6 months


📊 Performance Optimization
Reduce Response Time:

Use smaller embedding models
Limit chunk size (1000 characters)
Reduce Top K to 3-4 results
Enable caching in chatflow

Improve Answer Quality:

Increase chunk overlap (200 characters)
Use higher quality embeddings
Add more detailed information to knowledge base
Fine-tune retrieval parameters


🤝 Contributing
Contributions are welcome! Please follow these steps:

Fork the repository
Create feature branch: git checkout -b feature/amazing-feature
Commit changes: git commit -m 'Add amazing feature'
Push to branch: git push origin feature/amazing-feature
Open Pull Request


📄 License
This project is licensed under the MIT License - see the LICENSE file for details.

👤 Author
Efren Gabriel Aying

Email: ayjesus057@gmail.com
GitHub: @SasayAying
Portfolio: [Your Portfolio URL]


🙏 Acknowledgments

Flowise AI - Visual AI workflow builder
Cohere - AI embeddings and language models
Groq - Fast LLM inference
LangChain - AI orchestration framework
XAMPP - Local development environment


📚 Additional Resources

Flowise Documentation
Cohere API Docs
LangChain Documentation
RAG Tutorial


🗺️ Roadmap

 Add voice input/output
 Multi-language support
 Analytics dashboard
 Admin panel for content updates
 Integration with email notifications
 Mobile app version
 Advanced conversation analytics


💬 Support
If you have questions or need help:

Create an Issue: GitHub Issues
Email: ayjesus057@gmail.com
Discord Community: Join Flowise Discord


⭐ Show Your Support
If this project helped you, please give it a ⭐️!

Built with ❤️ by Efren Gabriel Aying
Last Updated: December 2024
