# Project Name ?? MediChat Pro - Medical Document Intelligence Assistant

## 📖 Overview
MediChat Pro is an intelligent medical document analysis system that combines AI-powered chat capabilities with secure document storage and email reporting. 
The application allows healthcare professionals to upload medical documents, ask questions about their content, and receive AI-generated insights with comprehensive analytics.


## 🚀 Key Features

📄 Document Processing: Upload and process multiple PDF medical documents

🤖 AI-Powered Chat: Ask questions about your medical documents using self-hosted LLMs

☁️ Secure Storage: Automatic document storage in AWS S3 with deduplication

🔍 Vector Search: ChromaDB-powered semantic search for relevant document retrieval

📧 Email Analytics: Send comprehensive medical analysis reports via email

🎫 Support System: Automated support ticket generation

📊 Session Management: Save and manage chat sessions with analytics


## 🏗️ Architecture & Workflow

User Interface (Streamlit)
        ?
Document Upload & Processing
        ?
S3 Storage + ChromaDB Vector Storage
        ?
AI Chat Interface (Self-hosted LLM)
        ?
Medical Insights & Analytics
        ?
Email Reports & Support Tickets


## 📁 Project Structure

medibot/
├── app/
│   ├── __init__.py
│   ├── chat_utils.py          # AI chat functionality
│   ├── config.py              # Configuration & environment variables
│   ├── email_utils.py         # Email & reporting system
│   ├── pdf_utils.py           # PDF text extraction
│   ├── s3_utils.py            # AWS S3 document storage
│   ├── ui.py                  # Streamlit UI components
│   └── vectorstore_utils.py   # ChromaDB vector storage
├── main.py                    # Main Streamlit application
└── requirements.txt           # Python dependencies


## 📁 Project Structure

```
medipro/
├── app/
│   ├── __init__.py
│   ├── chat_utils.py          # AI chat functionality
│   ├── config.py              # Configuration & environment variables
│   ├── email_utils.py         # Email & reporting system
│   ├── pdf_utils.py           # PDF text extraction
│   ├── s3_utils.py            # AWS S3 document storage
│   ├── ui.py                  # Streamlit UI components
│   └── vectorstore_utils.py   # ChromaDB vector storage
├── main.py                    # Main Streamlit application
└── requirements.txt           # Python dependencies
```

## 🔧 Core Components

1. Chat System (chat_utils.py)
 - Self-hosted LLM integration with OpenAI-compatible API

 - Medical terminology detection and analysis

 - Response enhancement with medical context

 - Configurable temperature and model settings

2. Document Processing (pdf_utils.py + s3_utils.py)
 - PDF text extraction with cleaning and normalization

 - AWS S3 integration for secure document storage

 - Automatic deduplication using content hashing

 - Batch processing for multiple documents

3. Vector Storage (vectorstore_utils.py)
 - ChromaDB cloud integration for semantic search

 - Self-hosted embedding models for text vectorization

 - Batch processing for efficient document indexing

 - Relevance-based document retrieval

 4. Email & Reporting (email_utils.py)
 - Comprehensive medical analytics reports
 
 - Support ticket generation system

 - HTML and plain text email templates

 - SMTP integration with configurable providers

5. Configuration (config.py)
 - Centralized environment variable management

 - Model configuration for both chat and embeddings

 - Email and storage service configurations

## 🛠️ Installation & Setup
### Prerequisites

 - Python 3.8+

 - AWS S3 bucket (for document storage)

 - ChromaDB cloud account

 - Self-hosted LLM API endpoint

 - SMTP email service

 1. Clone and Install Dependencies

    > git clone <repository-url>
    > cd medipro
    > pip install -r requirements.txt

2. Environment Configuration

### Create a .env file with the following variables:
# Self-hosted Model Configuration
OPENAI_API_BASE=http://your-llm-api-endpoint/v1
OPENAI_API_KEY=your-api-key-or-not-needed
OPENAI_EMBEDDING_BASE=http://your-embedding-api-endpoint/v1
OPENAI_EMBEDDING_KEY=your-embedding-key
LLM_MODEL=your-llm-model-name
EMBEDDING_MODEL=your-embedding-model

# ChromaDB Configuration
CHROMA_API_KEY=your-chroma-api-key
CHROMA_TENANT=your-tenant
CHROMA_DATABASE=medibot
CHROMA_COLLECTION=medical_documents

# AWS S3 Configuration
S3_ACCESS_KEY=your-aws-access-key
S3_SECRET_KEY=your-aws-secret-key
S3_BUCKET_NAME=your-bucket-name
S3_REGION=ap-south-1

# Email Configuration
EMAIL_SMTP_SERVER=smtp.gmail.com
EMAIL_SMTP_PORT=587
EMAIL_SENDER=your-email@gmail.com
EMAIL_PASSWORD=your-app-password
EMAIL_RECEIVER=default-receiver@example.com

3. Run the Application

    > streamlit run main.

## 💻 Usage Guide

1. Document Upload
 - Use the sidebar to upload PDF medical documents

 - Documents are automatically processed and stored in S3

 - Text is extracted, cleaned, and indexed in ChromaDB


 2. Chat Interface
 - Ask questions about your medical documents

 - The AI searches through all uploaded documents

 - Responses include medical insights and relevant context

3. Email Features
 - Configure recipient email in the sidebar

 - Send analysis reports with chat history and document insights

 - Generate support tickets for assistance

4. Session Management
 - Save current session state

 - View analytics on documents processed and messages exchanged
 
 - Clear vector storage when needed



 ## 🔄 Workflow Details


## Document Processing Flow
1 - Upload: User uploads PDF files through Streamlit interface

2 - Extraction: Text is extracted and cleaned from PDFs

3 - Storage: Documents are stored in AWS S3 with unique keys

4 - Vectorization: Text is split into chunks and embedded

5 - Indexing: Embeddings are stored in ChromaDB for search

## Chat Interaction Flow

1 - Query: User asks a medical question

2 - Retrieval: Relevant document chunks are found using semantic search

3 - Context: Retrieved documents are formatted as context
 
4 - Generation: LLM generates response based on context

5 - Enhancement: Response is enhanced with medical insights

## Email Reporting Flow

1 - Trigger: User requests email report or support ticket

2 - Analytics: Session data and document insights are compiled

3 - Formatting: HTML and plain text email content is generated

4 - Delivery: Email is sent via configured SMTP server

## 🎯 Command Features

## Chat Commands 

 - "send report to email@example.com" - Send analysis report

 - "create support ticket" - Generate support request

 - "process s3 documents" - Process all S3 stored documents

 - "save session" - Save current session state

 ## Email Templates

 - Medical Analytics Report: Comprehensive session summary with document insights

 - Support Ticket: Technical support request with chat context

 - Session Save: Session backup with analytics

## 🔒 Security Features
 - Document Deduplication: Prevents duplicate document storage

 - Secure Storage: AWS S3 with proper access controls

 - Email Validation: Ensures valid email addresses for reporting

 - Environment Variables: Sensitive data stored securely

 ## 📊 Analytics & Insights
### The system provides:

  - Document processing statistics

  - Chat session analytics

 - Medical keyword detection

 - Response confidence scoring

 - Query complexity analysis

## 🚨 Medical Disclaimer
### ⚠️ Important: MediChat Pro is designed for educational and informational purposes only. It should not be used as a substitute for professional medical advice, diagnosis, or treatment. Always consult with qualified healthcare professionals for medical concerns.
 

 ## 🛠️ Technical Stack
 - Frontend: Streamlit

 - AI/ML: Self-hosted LLMs, ChromaDB, Sentence Transformers

 - Storage: AWS S3, ChromaDB Cloud

 - Email: SMTP with HTML templates

 - PDF Processing: PyPDF, Text Extraction

 - Configuration: Python-dotenv

 ## 📞 Support

For technical support or questions:

 - Use the "Create Support Ticket" feature in the application

 - Email: shewan.dagne1@gmail.com




 ## 🔄 Development
## Adding New Features

 1 - Follow the modular architecture pattern

 2 - Add configuration in config.py

 3 - Implement utilities in appropriate module files

 4 - Update main application logic in main.py

## Testing

 - Test document upload and processing

 - Verify email functionality with test emails

 - Validate chat responses with medical documents

 - Check S3 integration and ChromaDB connectivity


 MediChat Pro - Empowering healthcare professionals with intelligent document analysis and AI-powered insights. ???

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
