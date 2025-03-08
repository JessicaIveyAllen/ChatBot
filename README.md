# AI-Powered IT Troubleshooting Chatbot

![version](https://img.shields.io/badge/version-1.0.0-blue)
![python](https://img.shields.io/badge/python-3.9+-blue)
![flask](https://img.shields.io/badge/flask-2.0.1-green)
![license](https://img.shields.io/badge/license-MIT-orange)

A Flask-based AI chatbot for automated network troubleshooting that integrates with Splunk and system monitoring tools for real-time diagnostics, providing immediate assistance for common networking problems.

## 📋 Overview

This chatbot was designed to reduce the time spent on common IT support issues by providing an intelligent, conversational interface for users to troubleshoot network problems. By leveraging natural language processing and integrating with enterprise monitoring tools, the system can diagnose issues and suggest solutions without human intervention for many common scenarios.

## ✨ Features

- **AI-powered troubleshooting** using OpenAI API for natural language understanding
- **Real-time system diagnostics** through integration with Splunk and monitoring tools
- **Multi-step troubleshooting workflows** for complex networking issues
- **Knowledge base integration** to provide consistent and accurate solutions
- **Escalation pathways** to human support when necessary
- **Detailed logging** of all interactions for continuous improvement
- **Responsive web interface** for easy access from any device
- **Role-based access control** for different user types

## 🛠️ Technology Stack

- **Backend:** Python, Flask
- **AI Integration:** OpenAI API, Custom NLP Pipeline
- **Monitoring Integration:** Splunk API, Custom Adapters
- **Frontend:** HTML/CSS, JavaScript, Bootstrap
- **Database:** SQLite for development, PostgreSQL for production
- **Authentication:** JWT, OAuth2
- **Deployment:** Docker, AWS

## 🖥️ Installation

### Prerequisites
- Python 3.9+
- Docker (optional for containerized deployment)
- OpenAI API key
- Splunk instance with API access

### Local Setup

```bash
# Clone the repository
git clone https://github.com/jessicaiveyallen/ai-troubleshooting-chatbot.git
cd ai-troubleshooting-chatbot

# Create and activate virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Set up environment variables
cp .env.example .env
# Edit .env file with your API keys and configuration

# Initialize the database
flask db init
flask db migrate
flask db upgrade

# Run the application
flask run
```

### Docker Deployment

```bash
# Build the Docker image
docker build -t it-troubleshooting-chatbot .

# Run the container
docker run -p 5000:5000 --env-file .env it-troubleshooting-chatbot
```

## 🔧 Configuration

The application can be configured through environment variables:

```
# API Keys
OPENAI_API_KEY=your-openai-api-key
SPLUNK_API_KEY=your-splunk-api-key

# Service URLs
SPLUNK_URL=https://your-splunk-instance.com
MONITORING_SERVICE_URL=https://your-monitoring-service.com

# Application Settings
LOG_LEVEL=INFO
ENABLE_DEBUGGING=false
MAX_TOKENS=150
```

## 🚀 Usage

1. Access the web interface at `http://localhost:5000` (or your deployed URL)
2. Log in with your credentials
3. Type your networking issue in natural language
4. Follow the chatbot's troubleshooting steps
5. If the issue is resolved, provide feedback on the solution
6. If unresolved, the chatbot will escalate to human support

## 📊 Architecture

```
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│  User Interface │     │  Flask Backend  │     │  OpenAI API     │
│  - HTML/CSS/JS  │────▶│  - Python       │────▶│  - GPT Models   │
│  - Bootstrap    │     │  - REST API     │     │  - Completions  │
└─────────────────┘     └────────┬────────┘     └─────────────────┘
                                 │
                                 ▼
                     ┌─────────────────────────┐
                     │ Integration Layer       │
                     │ - Splunk Connector      │
                     │ - Monitoring Adapters   │
                     └────────────┬────────────┘
                                  │
                     ┌────────────▼────────────┐
                     │ Enterprise Systems      │
                     │ - Splunk                │
                     │ - Network Monitoring    │
                     │ - Ticket System         │
                     └─────────────────────────┘
```

## 🔒 Security Considerations

- All API keys are stored securely and not exposed to clients
- User authentication uses industry-standard practices
- All communications are encrypted using HTTPS
- Information is provided on a need-to-know basis based on user role
- Regular security audits are conducted on the codebase
- Dependency vulnerability scanning is integrated into CI/CD pipeline

## 🧪 Testing

```bash
# Run unit tests
pytest

# Run with coverage report
pytest --cov=app tests/

# Run integration tests
pytest tests/integration/
```

## 📈 Future Enhancements

- [ ] Expand knowledge base to cover more complex scenarios
- [ ] Add support for image-based diagnostics through screenshot analysis
- [ ] Implement proactive issue detection through anomaly detection
- [ ] Develop mobile application for on-the-go support
- [ ] Add multi-language support for global deployment
- [ ] Integrate with additional monitoring and alerting platforms

## 👥 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 📮 Contact

Jessica Ivey Allen - [LinkedIn](https://www.linkedin.com/in/jessicaiveyallen/)

⭐️ From [JessicaIveyAllen](https://github.com/jessicaiveyallen)
