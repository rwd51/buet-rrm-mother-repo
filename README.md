# buet-rrm-mother-repo

Backend Repo: https://github.com/rwd51/bitfest-onsite-backend-buet-rrm

Frontend Repo: https://github.com/azraihan/bitfest-hackathon-2025-team-apex_bytes-frontend 


# Banglish to Bangla Conversion Platform

## 🌟 Project Overview
A comprehensive platform that enables seamless conversion of Banglish (Bengali written in English alphabet) to proper Bangla text, featuring advanced AI capabilities, content management, and interactive learning features.

### Repository Links
- Backend Repository: [buet-rrm-backend](https://github.com/rwd51/bitfest-onsite-backend-buet-rrm)
- Frontend Repository: [buet-rrm-frontend](https://github.com/azraihan/bitfest-hackathon-2025-team-apex_bytes-frontend)

## 🏗️ Architecture

### Tech Stack
- **Backend**: FastAPI
- **Database**: PostgreSQL, Redis
- **AI/ML**: 
  - LangChain Pipeline Agent (LLM-in-loop)
  - OpenAI API
  - Google Cloud Translation API (Gemini)
  - Custom Pretrained Model

### System Components
```mermaid
graph TD
    A[Client] --> B[FastAPI Backend]
    B --> C[PostgreSQL]
    B --> D[Redis Cache]
    B --> E[LangChain Pipeline]
    E --> F[OpenAI]
    E --> G[Gemini]
    E --> H[Custom Model]
    B --> I[Authentication]
```

### Banglish to Bangla Inference Pipeline Overview
<img width="604" alt="Screenshot 2025-01-04 at 9 20 12 AM" src="https://github.com/user-attachments/assets/ecb26e36-3a63-4529-9c6c-b815c9aaa00a" />


## 🚀 Features

### Core Functionality
1. **Advanced Translation System**
   - Banglish to Bangla conversion using hybrid approach
   - LangChain pipeline with multiple LLM integration
   - Custom pretrained model for specialized translations

2. **Content Management**
   - PDF generation and export
   - Public/Private content sharing
   - AI-powered caption generation

3. **Interactive Chatbot**
   - Multilingual support (Banglish/Bangla)
   - Context-aware responses
   - PDF content reference capability

4. **User System**
   - Secure authentication
   - Profile management
   - Content privacy controls

5. **Performance Optimization**
   - Redis caching for frequently accessed data
   - Efficient database queries
   - Scalable architecture

## 🛠️ Setup and Installation

### Prerequisites
```bash
# Python 3.8+
python --version

# PostgreSQL
postgresql --version

# Redis
redis-server --version
```

### Environment Setup
1. Clone the repositories
```bash
git clone https://github.com/rwd51/bitfest-onsite-backend-buet-rrm
git clone https://github.com/azraihan/bitfest-hackathon-2025-team-apex_bytes-frontend
```

2. Backend Setup
```bash
cd bitfest-onsite-backend-buet-rrm
python -m venv venv
source venv/bin/activate  # or `venv\Scripts\activate` on Windows
pip install -r requirements.txt
```

3. Configure Environment Variables
```env
# .env file
DATABASE_URL=postgresql://user:password@localhost:5432/db_name
REDIS_URL=redis://localhost:6379
OPENAI_API_KEY=your_openai_key
GOOGLE_CLOUD_API_KEY=your_google_cloud_key
```

4. Initialize Database
```bash
alembic upgrade head
```

5. Frontend Setup
```bash
cd ../bitfest-hackathon-2025-team-apex_bytes-frontend
npm install
```

### Running the Application
1. Start Backend Server
```bash
uvicorn app.main:app --reload
```

2. Start Frontend Development Server
```bash
npm run dev
```

## 📚 API Documentation

### Translation Endpoints
```python
POST /api/v1/translate
    Request Body:
        - text: str (Banglish text)
        - mode: str (quick/accurate)
    Response:
        - translated_text: str
        - confidence: float

POST /api/v1/pdf/generate
    Request Body:
        - content: str
        - title: str
        - visibility: str (public/private)
    Response:
        - pdf_url: str
        - caption: str
```

### Authentication Endpoints
```python
POST /api/v1/auth/register
POST /api/v1/auth/login
GET /api/v1/auth/profile
```

## 🔐 Security

- JWT-based authentication
- Rate limiting on API endpoints
- Input sanitization and validation
- Secure file handling
- API key encryption

## 🎯 Performance Optimizations

1. **Caching Strategy**
   - Redis for frequent translations
   - Session management
   - API response caching

2. **Database Optimization**
   - Indexed queries
   - Connection pooling
   - Efficient data modeling

3. **API Performance**
   - Batch processing
   - Async operations
   - Response compression

## 📊 Monitoring and Analytics

- Request/Response timing
- Error tracking
- User engagement metrics
- Translation accuracy monitoring
- System resource utilization

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🌟 Acknowledgments

- OpenAI for their powerful LLM API
- Google Cloud for Gemini Translation API
- The FastAPI team for the excellent framework
- Contributors and testers who helped improve the system
