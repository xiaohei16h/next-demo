# OpenAI Chat Demo

A modern, beautiful chat interface powered by OpenAI's GPT-3.5 API, built with Next.js 14, TypeScript, and Tailwind CSS.

## Features

- Modern, responsive UI with gradient backgrounds
- Real-time chat with OpenAI GPT-3.5
- Beautiful message bubbles with smooth animations
- Loading states and error handling
- Dark mode support
- TypeScript for type safety

## Getting Started

### Prerequisites

- Node.js 18+ installed
- An OpenAI API key (get one at https://platform.openai.com/api-keys)

### Installation

1. Clone this repository or navigate to the project directory

2. Install dependencies:
```bash
npm install
```

3. Configure your OpenAI API key:
   - Copy `.env.example` to `.env.local`
   - Add your OpenAI API key to `.env.local`:
```
OPENAI_API_KEY=sk-your-actual-api-key-here
```

4. Run the development server:
```bash
npm run dev
```

5. Open [http://localhost:3000](http://localhost:3000) in your browser

## Project Structure

```
next-demo/
├── app/
│   ├── api/
│   │   └── chat/
│   │       └── route.ts       # OpenAI API endpoint
│   ├── globals.css            # Global styles
│   ├── layout.tsx             # Root layout
│   └── page.tsx               # Main chat page
├── .env.local                 # Environment variables
├── next.config.js             # Next.js configuration
├── tailwind.config.ts         # Tailwind CSS configuration
└── tsconfig.json              # TypeScript configuration
```

## Usage

1. Type your message in the input field at the bottom
2. Click "Send" or press Enter
3. Wait for the AI to respond
4. Continue the conversation!

## Tech Stack

- **Framework**: Next.js 14 (App Router)
- **Language**: TypeScript
- **Styling**: Tailwind CSS
- **AI**: OpenAI GPT-3.5 API
- **Deployment**: Can be deployed to Vercel, Netlify, or any Node.js hosting

## API Endpoints

### POST /api/chat

Sends a message to OpenAI and returns the response.

**Request Body:**
```json
{
  "message": "Your message here"
}
```

**Response:**
```json
{
  "reply": "AI response here"
}
```

## Customization

### Changing the AI Model

Edit `app/api/chat/route.ts` and modify the `model` parameter:

```typescript
const completion = await openai.chat.completions.create({
  model: 'gpt-4', // or 'gpt-3.5-turbo', 'gpt-4-turbo', etc.
  // ...
})
```

### Styling

The app uses Tailwind CSS. Customize colors and styles in:
- `app/page.tsx` - Main chat interface
- `app/globals.css` - Global styles
- `tailwind.config.ts` - Tailwind configuration

## Troubleshooting

### API Key Not Working

Make sure:
- Your `.env.local` file is in the root directory
- The API key starts with `sk-`
- You've restarted the development server after adding the key

### Error: "OpenAI API key is not configured"

Check that your `.env.local` file exists and contains a valid API key.

## License

MIT

## Contributing

Feel free to open issues or submit pull requests!
