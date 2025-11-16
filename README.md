# Did You Know? 🧠

A modern, responsive web application for sharing and discovering interesting facts across various categories. Built with TypeScript and Supabase, this project demonstrates clean architecture, type safety, and serverless API design.

## ✨ Features

- **Category Filtering**: Browse facts by categories (Science, Technology, History, Health, Entertainment, Finance, Society, News)
- **Interactive Voting**: Upvote or downvote facts with vote tracking via localStorage
- **Fact Submission**: Share your own facts with trustworthy sources through an elegant modal form
- **Sorting Options**: Sort facts by newest or most popular
- **Responsive Design**: Fully responsive UI that works seamlessly on desktop and mobile devices
- **Real-time Updates**: Live data synchronization with Supabase backend
- **Toast Notifications**: User-friendly feedback for actions like duplicate voting
- **Smooth Animations**: Polished UI with fade-in effects and hover transitions

## 🚀 Technologies Used

### Frontend
- **TypeScript** - Type-safe JavaScript for better development experience
- **HTML5 & CSS3** - Modern semantic markup and styling
- **Vite** - Fast build tool and development server
- **Lucide Icons** - Lightweight SVG icons for better performance

### Backend
- **Supabase** - Backend as a Service (PostgreSQL database)
- **Vercel Serverless Functions** - API endpoints for CRUD operations

### Package Manager
- **pnpm** - Fast, disk space efficient package manager

## 📁 Project Structure

```
didyouknow-ts/
├── api/                        # Serverless API endpoints
│   ├── create-fact.ts         # POST endpoint to create new facts
│   ├── facts.ts               # GET endpoint for getting the facts
│   └── vote.ts                # POST endpoint for voting
├── public/                     # Static assets
│   ├── favicon.ico
│   └── knowledge_icon.svg     # App icon with dark mode support
├── src/                        # Source code
│   ├── types/                 # TypeScript type definitions
│   │   ├── supabase.ts       # Auto-generated Supabase types
│   │   └── utils.ts          # Custom type definitions
│   ├── main.ts               # Main application logic
│   ├── modal.ts              # Modal dialog functionality
│   └── styles.css            # Application styles
├── index.html                 # Entry point
├── package.json              # Dependencies and scripts
├── tsconfig.json             # TypeScript configuration
├── pnpm-lock.yaml           # Lock file for dependencies
└── .gitignore               # Git ignore rules
```

## 🛠️ Installation

### Prerequisites
- Node.js (v18 or higher)
- pnpm (or npm/yarn)
- Supabase account

### Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/Drave18/didYouKnow-TS.git
   cd didYouKnow-TS
   ```

2. **Install dependencies**
   ```bash
   pnpm install
   # or
   npm install
   ```

3. **Set up environment variables**
   Create a `.env` file in the root directory:
   ```env
   VITE_SUPABASE_URL=your_supabase_project_url
   VITE_SUPABASE_ANON_KEY=your_supabase_anon_key
   ```

4. **Set up Supabase Database**
   
   Create a table named `facts` with the following schema:
   ```sql
   CREATE TABLE facts (
     id BIGSERIAL PRIMARY KEY,
     created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW(),
     text TEXT NOT NULL,
     source TEXT NOT NULL,
     category TEXT NOT NULL,
     votes_positive INTEGER DEFAULT 0,
     votes_negative INTEGER DEFAULT 0
   );
   ```

5. **Run development server**
   ```bash
   pnpm dev
   # or
   npm run dev
   ```

6. **Open in browser**
   Navigate to `http://localhost:5173`

## 🏗️ Build for Production

```bash
pnpm build
# or
npm run build
```

The built files will be in the `dist/` directory.


## 🎯 Key Features Explained

### Event Delegation
Efficient event handling using event delegation pattern to manage clicks on dynamically generated fact cards.

### Local Storage Voting
Vote tracking persists in browser localStorage to prevent duplicate voting on the same fact.

### Serverless API
Three Vercel serverless functions handle:
- **GET /api/facts** - Fetch paginated facts
- **POST /api/create-fact** - Create new fact entries
- **POST /api/vote** - Update vote counts



## 🌐 Deployment

This project is configured for deployment on **Vercel**:

1. Connect your GitHub repository to Vercel
2. Add environment variables in Vercel dashboard
3. Deploy automatically on every push to main branch


## 🤝 Contributing
Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is open source and available under the MIT License.

## 👨‍💻 Author

**Drave18**
- GitHub: [@Drave18](https://github.com/Drave18)

## 🙏 Acknowledgments

- Icons by [Lucide](https://lucide.dev/)
- Backend by [Supabase](https://supabase.com/)
- Hosted on [Vercel](https://vercel.com/)
