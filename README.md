# ContentCraft AI - Content Generation App

A full-stack web application for generating and editing content using OpenAI's API.

## Features

- **AI Content Generation**: Generate text and images using OpenAI GPT-4o and DALL-E
- **Manual Content Input**: Add your own text content for editing
- **Text-Based Editing**: Edit any content using natural language instructions
- **Dual Interface**: Tabbed interface for generation vs. manual input
- **Content History**: Track edit history for all content
- **Templates**: Quick-start templates for common content types

## Local Setup

### Prerequisites

- Node.js 18+ installed
- OpenAI API key

### Installation

1. Clone or download this project
2. Install dependencies:
   ```bash
   npm install
   ```

3. Create a `.env` file in the root directory:
   ```
   OPENAI_API_KEY=your_openai_api_key_here
   ```

4. Start the development server:
   ```bash
   npm run dev
   ```

5. Open http://localhost:5000 in your browser

### Building for Production

```bash
npm run build
npm start
```

## Free Hosting Alternatives

Since Replit deployment requires a paid plan, here are free alternatives:

### 1. Vercel (Recommended)
- Fork this project to GitHub
- Connect your GitHub to Vercel
- Deploy with one click
- Add OPENAI_API_KEY in environment variables

### 2. Railway
- Connect GitHub repository
- Deploy automatically
- Free tier available

### 3. Render
- Connect GitHub repository  
- Free tier with some limitations
- Easy environment variable setup

### 4. Netlify + Serverless Functions
- Good for the frontend
- May need modifications for backend

## Usage

1. **Generate Content**: Use the "Generate AI" tab to create new content
2. **Add Content**: Use the "Add Content" tab to input your own text
3. **Edit Content**: Use the editing section to modify any content with natural language instructions
4. **Templates**: Click on template buttons for quick content generation

## API Endpoints

- `POST /api/generate` - Generate new content
- `POST /api/create` - Create content from user input
- `POST /api/edit` - Edit existing content
- `GET /api/content/:id` - Get specific content
- `GET /api/templates` - Get available templates

## Environment Variables

- `OPENAI_API_KEY` - Your OpenAI API key (required)
- `NODE_ENV` - Set to 'production' for production builds

## Cost Considerations

- Hosting: Free on platforms like Vercel, Railway, Render
- OpenAI API: Pay-per-use (typically $0.002-0.06 per request depending on content type)
- No other ongoing costs

## Support

The app includes comprehensive error handling and user guidance for troubleshooting issues.