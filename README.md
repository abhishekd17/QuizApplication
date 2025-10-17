# Quiz Master - Interactive Quiz Application

## Overview

Quiz Master is a professional, production-ready quiz application built with Next.js and React. It provides an engaging and interactive way to take quizzes with real-time feedback, progress tracking, and detailed result analysis.

### Key Features
- **Email Verification**: Users submit their email before starting the quiz
- **15 Dynamic Questions**: Questions fetched from the Open Trivia Database API
- **30-Minute Timer**: Countdown timer with auto-submit functionality
- **Question Navigation**: Jump to any question with visual status indicators
- **Progress Tracking**: Overview panel showing visited, attempted, and unanswered questions
- **Detailed Results**: Comprehensive report comparing user answers with correct answers
- **Responsive Design**: Fully optimized for mobile, tablet, and desktop devices
- **Smooth Animations**: Elegant transitions and visual feedback throughout the app
- **Dark Mode Support**: Built-in dark mode compatibility

## Tech Stack

- **Framework**: Next.js 15+ with App Router
- **Language**: TypeScript
- **Styling**: Tailwind CSS v4
- **UI Components**: shadcn/ui
- **API**: Open Trivia Database (https://opentdb.com/api.php)
- **State Management**: React Hooks (useState, useEffect, useCallback)

## Installation & Setup

### Prerequisites
- Node.js 18+ installed
- npm or yarn package manager

### Steps

1. **Clone the repository**
   \`\`\`bash
   git clone <repository-url>
   cd quiz-app
   \`\`\`

2. **Install dependencies**
   \`\`\`bash
   npm install
   \`\`\`

3. **Run the development server**
   \`\`\`bash
   npm run dev
   \`\`\`

4. **Open in browser**
   - Navigate to `http://localhost:3000`
   - The app will automatically reload on code changes

### Build for Production
\`\`\`bash
npm run build
npm start
\`\`\`

## Project Structure

\`\`\`
quiz-app/
├── app/
│   ├── layout.tsx          # Root layout with metadata
│   ├── page.tsx            # Main app component with page routing
│   └── globals.css         # Global styles and Tailwind config
├── components/
│   ├── start-page.tsx      # Email submission page
│   ├── quiz-page.tsx       # Main quiz interface
│   ├── results-page.tsx    # Results and detailed report
│   ├── question-display.tsx # Individual question component
│   ├── question-navigation.tsx # Question overview panel
│   ├── timer.tsx           # Countdown timer component
│   └── ui/                 # shadcn/ui components
├── lib/
│   └── utils.ts            # Utility functions (cn for className merging)
└── README.md               # This file
\`\`\`

## Component Architecture

### Page Components
- **StartPage**: Collects user email with validation
- **QuizPage**: Main quiz interface with timer and navigation
- **ResultsPage**: Displays results with expandable question details

### Feature Components
- **QuestionDisplay**: Renders individual questions with answer options
- **QuestionNavigation**: Shows overview of all questions with status
- **Timer**: Countdown timer with visual progress indicator

## Key Features Explained

### 1. Email Validation
- Validates email format before allowing quiz start
- Stores email for the final report

### 2. Timer System
- 30-minute countdown timer
- Visual warning when time is running low (< 5 minutes)
- Auto-submits quiz when timer reaches zero
- Circular progress indicator showing remaining time

### 3. Question Navigation
- Jump to any question directly
- Visual indicators for:
  - **Blue**: Current question
  - **Green**: Answered questions
  - **Yellow**: Visited but not answered
  - **Gray**: Not visited
- Summary statistics showing answered/visited/remaining counts

### 4. Results Report
- Score display with percentage
- Performance level assessment
- Expandable question details showing:
  - User's answer
  - Correct answer
  - All available options
- Print-friendly format
- Option to retake the quiz

## API Integration

The app fetches questions from the Open Trivia Database:
\`\`\`
https://opentdb.com/api.php?amount=15
\`\`\`

### Data Processing
- Decodes HTML entities in questions and answers
- Shuffles answer options for randomization
- Validates API response before rendering

## Responsive Design

The application is fully responsive with breakpoints:
- **Mobile**: < 768px (single column layout)
- **Tablet**: 768px - 1024px (optimized spacing)
- **Desktop**: > 1024px (multi-column layout with sidebar)

## Browser Compatibility

Tested and compatible with:
- ✅ Chrome 90+
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ Edge 90+

## Assumptions

1. **Internet Connection**: App requires internet to fetch questions from the API
2. **Modern Browser**: Uses modern JavaScript features (ES6+)
3. **Email Validity**: Email validation is client-side; no backend verification
4. **Timer Accuracy**: Timer accuracy depends on browser performance
5. **Local State**: Quiz data is stored in component state (not persisted)

## Challenges & Solutions

### Challenge 1: HTML Entity Decoding
**Problem**: API returns HTML-encoded characters (e.g., `&quot;`, `&amp;`)
**Solution**: Created `decodeHTML` function using textarea element to parse entities

### Challenge 2: Answer Randomization
**Problem**: Correct answer always appeared in the same position
**Solution**: Implemented `shuffleArray` function to randomize answer order

### Challenge 3: Timer Auto-Submit
**Problem**: Needed to auto-submit when timer reaches zero
**Solution**: Used `useCallback` to trigger submission without infinite loops

### Challenge 4: Responsive Navigation Panel
**Problem**: Navigation panel was too large on mobile
**Solution**: Used CSS Grid with responsive columns and sticky positioning

### Challenge 5: State Management Across Pages
**Problem**: Needed to maintain quiz state across page transitions
**Solution**: Lifted state to main component and passed callbacks to child components

## Performance Optimizations

1. **Lazy Loading**: Components load only when needed
2. **Memoization**: Used `useCallback` for event handlers
3. **CSS Animations**: Hardware-accelerated transitions
4. **Efficient Re-renders**: Minimal state updates
5. **Image Optimization**: No unnecessary images

## Accessibility Features

- ✅ Semantic HTML elements
- ✅ ARIA labels and roles
- ✅ Keyboard navigation support
- ✅ Color contrast compliance (WCAG AA)
- ✅ Screen reader friendly
- ✅ Focus indicators on interactive elements

## Future Enhancements

1. **Backend Integration**: Save results to database
2. **User Authentication**: Login system for tracking progress
3. **Question Categories**: Filter questions by category
4. **Difficulty Levels**: Select quiz difficulty
5. **Leaderboard**: Compare scores with other users
6. **Analytics**: Track user performance over time
7. **Offline Mode**: Cache questions for offline use
8. **Mobile App**: React Native version

## Deployment

### Deploy to Vercel (Recommended)
\`\`\`bash
npm install -g vercel
vercel
\`\`\`

### Deploy to Netlify
\`\`\`bash
npm run build
# Connect your GitHub repo to Netlify
\`\`\`

### Deploy to GitHub Pages
\`\`\`bash
npm run build
# Push to gh-pages branch
\`\`\`

## License

This project is open source and available under the MIT License.

## Support

For issues or questions:
1. Check the troubleshooting section
2. Review the code comments
3. Open an issue on GitHub

---

**Built with ❤️ for CausalFunnel Internship Program**
