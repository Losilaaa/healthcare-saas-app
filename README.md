# Healthcare Consultation Assistant 🏥

An AI-powered SaaS application that helps healthcare professionals generate professional consultation summaries, action items, and patient communications from their clinical notes.

<img width="3986" height="1162" alt="architectural-diagram" src="https://github.com/user-attachments/assets/f88c01f3-75ba-413d-96bf-d43f515a5150" />

## 🚀 Features

- **AI-Powered Summaries**: Transforms doctor's notes into structured medical summaries
- **Patient Communications**: Generates patient-friendly email drafts automatically
- **Action Items**: Extracts and formats next steps for healthcare providers
- **Real-time Streaming**: See AI-generated content appear in real-time
- **Enterprise Auth**: Secure authentication with Clerk and JWT verification
- **Subscription Management**: Integrated billing and subscription tiers
- **Production Ready**: Deployed on AWS with monitoring and health checks

## 🛠️ Tech Stack

**Frontend:**
- Next.js 15 (Pages Router)
- TypeScript
- Tailwind CSS
- React Markdown

**Backend:**
- FastAPI (Python)
- OpenAI GPT API
- Pydantic for data validation

**Authentication & Billing:**
- Clerk (Auth, JWT, Subscriptions)

**Infrastructure:**
- Docker (containerization)
- AWS App Runner (hosting)
- Amazon ECR (container registry)
- CloudWatch (logging & monitoring)

**Deployment:**
- Vercel (development)
- AWS (production)

## 📋 Prerequisites

- Node.js 18+
- Python 3.12+
- Docker Desktop
- AWS Account
- Clerk Account
- OpenAI API Key

## 🏃 Quick Start

### 1. Clone the repository
```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
cd YOUR_REPO_NAME
```

### 2. Install dependencies
```bash
# Frontend
npm install

# Backend (optional for local testing)
pip install -r requirements.txt
```

### 3. Set up environment variables
Create `.env.local`:
```bash
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=pk_test_...
CLERK_SECRET_KEY=sk_test_...
CLERK_JWKS_URL=https://...
OPENAI_API_KEY=sk-proj-...
```

### 4. Run development server
```bash
# Using Vercel CLI (recommended - runs both frontend and Python API)
vercel dev

# Or just frontend
npm run dev
```

Visit `http://localhost:3000`

## 🐳 Docker Deployment

### Build the container
```bash
docker build \
  --build-arg NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY="$NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY" \
  -t consultation-app .
```

### Run locally
```bash
docker run -p 8000:8000 \
  -e CLERK_SECRET_KEY="$CLERK_SECRET_KEY" \
  -e CLERK_JWKS_URL="$CLERK_JWKS_URL" \
  -e OPENAI_API_KEY="$OPENAI_API_KEY" \
  consultation-app
```

## ☁️ AWS Deployment

See [deployment guide](./docs/AWS_DEPLOYMENT.md) for detailed instructions.

**Quick steps:**
1. Push image to ECR
2. Create App Runner service
3. Configure environment variables
4. Deploy!

## 📁 Project Structure
