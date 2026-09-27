# 🤖 GenAI Customer Support Desk

An end-to-end **Generative AI-powered Customer Support Desk** built with **LangChain, FastAPI, Docker, and AWS**.

The application processes customer support transcripts through an AI pipeline that performs **classification, evaluation, aggregation, and reporting**. The application is exposed through a FastAPI API, containerized with Docker, and deployed to AWS using a Docker image stored in Amazon ECR.

---

## 🚀 Project Overview

Customer support teams handle a large volume of conversations that need to be reviewed and evaluated.

This project demonstrates how Generative AI can automate the analysis of customer support transcripts through a modular processing pipeline.

### Processing Flow

```text
Customer Support Transcripts
            │
            ▼
       Data Loading
            │
            ▼
       LLM Initialization
       OpenAI / Gemini
            │
            ▼
       Classification
            │
            ▼
         Evaluation
            │
            ▼
        Aggregation
            │
            ▼
         Reporting
            │
            ▼
       Final Results
```

The application is served using **FastAPI**, packaged as a **Docker container**, and deployed to AWS.

---

## ✨ Key Features

- 🤖 LLM-powered customer support analysis
- 🏷️ Customer support conversation classification
- 📊 AI-based conversation evaluation
- 📈 Result aggregation
- 📑 Automated reporting
- 🔄 Modular GenAI pipeline architecture
- 🔌 Support for OpenAI and Google Gemini
- ⚡ FastAPI REST API
- 🐳 Docker containerization
- ☁️ AWS deployment
- 📦 Docker image storage using Amazon ECR
- 🔐 Environment-based configuration
- 🧩 Separation of components, pipeline, and utility layers

---

## 🛠️ Tech Stack

### Generative AI

- Python
- LangChain
- OpenAI
- Google Gemini
- Prompt Engineering
- Large Language Models

### Backend

- FastAPI
- Uvicorn
- Pydantic
- Python Multipart

### Containerization

- Docker
- Dockerfile
- Docker Image

### Cloud

- Amazon Web Services (AWS)
- Amazon Elastic Container Registry (ECR)
- AWS CLI

### Development

- Git
- GitHub
- VS Code
- Jupyter Notebook
- Python Virtual Environment

---

# 🏗️ Architecture

```text
                         ┌────────────────────────┐
                         │ Customer Support       │
                         │ Transcripts            │
                         └───────────┬────────────┘
                                     │
                                     ▼
                         ┌────────────────────────┐
                         │     Data Loader        │
                         │    data_loader.py      │
                         └───────────┬────────────┘
                                     │
                                     ▼
                         ┌────────────────────────┐
                         │      LLM Loader        │
                         │   OpenAI / Gemini      │
                         └───────────┬────────────┘
                                     │
                                     ▼
                         ┌────────────────────────┐
                         │     Classification     │
                         └───────────┬────────────┘
                                     │
                                     ▼
                         ┌────────────────────────┐
                         │       Evaluation       │
                         └───────────┬────────────┘
                                     │
                                     ▼
                         ┌────────────────────────┐
                         │      Aggregation       │
                         └───────────┬────────────┘
                                     │
                                     ▼
                         ┌────────────────────────┐
                         │       Reporting        │
                         └───────────┬────────────┘
                                     │
                                     ▼
                         ┌────────────────────────┐
                         │     Final Results      │
                         └────────────────────────┘
```

---

# 📂 Project Structure

```text
genai-customer-support-desk/
│
├── config/
│   └── config.json
│
├── data/
│   └── customer support transcripts
│
├── logs/
│
├── src/
│   │
│   ├── components/
│   │   ├── __init__.py
│   │   ├── aggregation.py
│   │   ├── classification.py
│   │   ├── evaluation.py
│   │   ├── reporting.py
│   │   └── router.py
│   │
│   ├── pipeline/
│   │   ├── __init__.py
│   │   ├── inference.py
│   │   └── pipeline.py
│   │
│   └── utils/
│       ├── __init__.py
│       ├── config_loader.py
│       ├── data_loader.py
│       ├── helpers.py
│       └── llm_loader.py
│
├── app.py
├── main.py
├── requirements.txt
├── Dockerfile
├── .dockerignore
├── .gitignore
├── .env
├── deployment-guide.txt
├── projectflow.txt
├── proto.ipynb
├── template.py
└── README.md
```

> `.env`, local virtual environments, logs, and other sensitive/local files should not be committed to GitHub.

---

# 🔄 Application Workflow

## 1. Configuration Loading

The application loads configuration from environment variables and the project configuration file.

```text
.env + config/config.json
             │
             ▼
      config_loader.py
```

This keeps configuration separate from application logic.

---

## 2. Data Loading

Customer support transcripts are loaded using the data loader.

```text
Customer Support Data
          │
          ▼
   data_loader.py
          │
          ▼
      Transcripts
```

---

## 3. LLM Initialization

The application initializes the configured LLM provider.

Supported providers:

- OpenAI
- Google Gemini

```text
             llm_loader.py
                  │
          ┌───────┴───────┐
          ▼               ▼
       OpenAI           Gemini
```

---

## 4. Classification

The classification component uses the LLM to analyze customer support conversations and produce classification results.

```text
Transcript
    │
    ▼
Classification Component
    │
    ▼
Classification Result
```

---

## 5. Evaluation

The evaluation component analyzes the support interaction according to the configured evaluation criteria.

```text
Conversation
     │
     ▼
Evaluation Component
     │
     ▼
Evaluation Result
```

---

## 6. Aggregation

Results generated from individual conversations are aggregated into consolidated results.

```text
Evaluation Results
        │
        ▼
Aggregation Component
        │
        ▼
Aggregated Results
```

---

## 7. Reporting

The reporting component processes the aggregated results and generates structured reports.

```text
Aggregated Results
        │
        ▼
Reporting Component
        │
        ▼
Final Report
```

---

# ⚙️ Configuration

Create a `.env` file in the project root.

For OpenAI:

```env
OPENAI_API_KEY=your_openai_api_key
```

For Google Gemini:

```env
GOOGLE_API_KEY=your_google_api_key
```

The exact environment variables depend on the LLM provider configured in the application.

Application-level configuration can be maintained in:

```text
config/config.json
```

> **Never commit API keys or other sensitive credentials to GitHub.**

---

# 💻 Local Setup

## 1. Clone the Repository

```bash
git clone https://github.com/<your-username>/genai-customer-support-desk.git
```

```bash
cd genai-customer-support-desk
```

---

## 2. Create a Virtual Environment

### Windows

```bash
python -m venv myenv
```

Activate:

```bash
myenv\Scripts\activate
```

### Linux / macOS

```bash
python3 -m venv myenv
```

Activate:

```bash
source myenv/bin/activate
```

---

## 3. Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 4. Configure Environment Variables

Create a `.env` file:

```env
OPENAI_API_KEY=your_api_key
```

or configure the required Google Gemini credentials.

---

# ▶️ Run the Application

Start the FastAPI application using Uvicorn:

```bash
uvicorn app:app --reload
```

The application will be available at:

```text
http://localhost:8000
```

If your project entry point uses `main.py`, use the corresponding module and application name configured in your project.

---

# 📚 API Documentation

FastAPI automatically generates interactive API documentation.

### Swagger UI

```text
http://localhost:8000/docs
```

### ReDoc

```text
http://localhost:8000/redoc
```

Swagger UI can be used to test the available API endpoints directly from the browser.

---

# 🐳 Docker

The application is containerized using Docker to provide a consistent runtime environment.

## Build Docker Image

```bash
docker build -t genai-customer-support-desk .
```

## Run Docker Container

```bash
docker run -p 8000:8000 --env-file .env genai-customer-support-desk
```

The application will be available at:

```text
http://localhost:8000
```

Swagger documentation:

```text
http://localhost:8000/docs
```

---

# ☁️ AWS Deployment

The application is packaged as a Docker image and pushed to **Amazon Elastic Container Registry (ECR)** for cloud deployment.

### Deployment Flow

```text
Source Code
     │
     ▼
Docker Build
     │
     ▼
Docker Image
     │
     ▼
Amazon ECR
     │
     ▼
AWS Deployment
     │
     ▼
Running FastAPI Application
```

---

## 🔐 Configure AWS CLI

Configure AWS credentials using:

```bash
aws configure
```

Provide:

```text
AWS Access Key ID
AWS Secret Access Key
AWS Region
Output Format
```

---

## 🔑 Authenticate Docker with Amazon ECR

```bash
aws ecr get-login-password --region <AWS_REGION> | docker login --username AWS --password-stdin <AWS_ACCOUNT_ID>.dkr.ecr.<AWS_REGION>.amazonaws.com
```

---

## 🏗️ Build Docker Image

```bash
docker build -t genai-customer-support-desk .
```

---

## 🏷️ Tag Docker Image

```bash
docker tag genai-customer-support-desk:latest <AWS_ACCOUNT_ID>.dkr.ecr.<AWS_REGION>.amazonaws.com/<ECR_REPOSITORY>:latest
```

---

## 📤 Push Image to Amazon ECR

```bash
docker push <AWS_ACCOUNT_ID>.dkr.ecr.<AWS_REGION>.amazonaws.com/<ECR_REPOSITORY>:latest
```

The Docker image is then available in Amazon ECR for use by the AWS deployment environment.

---

# 🔒 Security

The project follows basic security practices:

- API keys are stored in environment variables.
- `.env` is excluded from Git.
- AWS credentials are not hardcoded.
- Sensitive configuration is not committed to GitHub.
- Docker images do not contain hardcoded API keys.

Example `.gitignore`:

```gitignore
__pycache__/
*.pyc
*.pyo
*.pyd

.env

.git/
.vscode/

logs/
data/

deployment-guide.txt
```

---

# 📊 Example Use Case

A customer support organization may receive thousands of support conversations.

The system can process these conversations automatically:

```text
Customer Support Conversation
            │
            ▼
      AI Classification
            │
            ▼
       AI Evaluation
            │
            ▼
        Aggregation
            │
            ▼
         Reporting
            │
            ▼
      Structured Results
```

This provides a modular foundation for analyzing customer support interactions at scale.

---

# 🧠 GenAI Concepts Demonstrated

This project demonstrates practical implementation of:

- Large Language Models
- LangChain
- Prompt Engineering
- LLM-based Classification
- LLM-based Evaluation
- Multi-provider LLM integration
- Modular GenAI pipelines
- Structured AI workflows
- Generative AI application development

---

# ☁️ Cloud & Deployment Concepts Demonstrated

- REST API development
- FastAPI application serving
- Docker containerization
- Docker image creation
- Docker image tagging
- Amazon ECR
- AWS CLI
- Container deployment
- Environment-based configuration
- Cloud deployment workflow

---

# 🔮 Future Enhancements

- [ ] Add RAG-based customer support knowledge base
- [ ] Add vector database
- [ ] Add conversation memory
- [ ] Add customer authentication
- [ ] Add ticket management
- [ ] Add sentiment analysis
- [ ] Add human-agent escalation
- [ ] Add frontend dashboard
- [ ] Add database persistence
- [ ] Add automated testing
- [ ] Add CI/CD pipeline
- [ ] Add AWS CloudWatch monitoring
- [ ] Add LLM observability and tracing
- [ ] Add batch transcript processing

---

# 🎯 Learning Outcomes

Through this project, I gained hands-on experience in:

- Building Generative AI applications using LangChain
- Integrating OpenAI and Google Gemini
- Designing modular AI pipelines
- Implementing LLM-based classification
- Implementing LLM-based evaluation
- Aggregating AI-generated results
- Generating structured reports
- Building REST APIs using FastAPI
- Containerizing Python applications using Docker
- Building and tagging Docker images
- Pushing Docker images to Amazon ECR
- Using AWS CLI
- Deploying containerized applications to AWS
- Managing application configuration and secrets

---

# 👩‍💻 Author

**Saloni Malhotra**

Frontend Engineer | Generative AI | LangChain | FastAPI | Docker | AWS

---

## ⭐ Project Highlights

```text
Generative AI
      +
LangChain
      +
Classification
      +
Evaluation
      +
Reporting
      +
FastAPI
      +
Docker
      +
Amazon ECR
      +
AWS Deployment
```

An end-to-end project demonstrating how a **Generative AI application can be developed, exposed through an API, containerized, and deployed to the cloud**.
