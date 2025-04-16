# YouTube Research Agent

A full-stack application that helps analyze YouTube channels and videos using AI.

## Project Structure

- `frontend/`: Next.js frontend application
- `agent/`: Python backend with FastAPI
- `main.py`: FastAPI server entry point

## Deployment Instructions

### Frontend (Vercel)

1. Install Vercel CLI:
   ```bash
   npm install -g vercel
   ```

2. Navigate to the frontend directory:
   ```bash
   cd frontend
   ```

3. Deploy to Vercel:
   ```bash
   vercel
   ```

4. Set environment variables in Vercel dashboard:
   - `NEXT_PUBLIC_API_URL`: Your backend API URL

### Backend (Python)

The backend needs to be deployed separately. You can use services like:
- Railway
- Render
- Heroku
- DigitalOcean App Platform

#### Environment Variables

Create a `.env` file with the following variables:
```
GEMINI_API_KEY=your_gemini_api_key
YOUTUBE_API_KEY=your_youtube_api_key
PINECONE_API_KEY=your_pinecone_api_key
PINECONE_INDEX=your_pinecone_index
PINECONE_CLOUD=aws
PINECONE_REGION=your_region
```

## Local Development

1. Install Python dependencies:
   ```bash
   python -m venv venv
   source venv/bin/activate  # or .\venv\Scripts\activate on Windows
   pip install -r requirements.txt
   ```

2. Install Node.js dependencies:
   ```bash
   cd frontend
   npm install
   ```

3. Start the backend server:
   ```bash
   uvicorn main:app --reload
   ```

4. Start the frontend development server:
   ```bash
   cd frontend
   npm run dev
   ```

## API Endpoints

- `POST /youtube`: Process YouTube-related questions
- `POST /chat`: Process general chat questions
- `GET /test-youtube`: Test YouTube API connection 