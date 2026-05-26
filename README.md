# College Problem Reporting Portal

A modern, responsive single-page application for anonymous campus issue reporting with tiered admin management.

## Features

### Anonymous Student/User
- Submit problems anonymously (no login required)
- View public feed of reported issues
- Filter by category, status, and search

### Standard Admin
- Login with admin credentials
- View dashboard with statistics and analytics
- Update problem status
- Soft delete problems (move to Recycle Bin)
- View Recycle Bin (read-only)

### Main Admin (Super Admin)
- All Standard Admin privileges
- Restore soft-deleted problems
- Permanently delete problems from Recycle Bin
- Manage admin users (add, revoke, change roles)

## Tech Stack

- React 18
- Vite
- Tailwind CSS
- Lucide React Icons

## Getting Started

### Installation
```bash
npm install
```

### Development
```bash
npm run dev
```

### Build for Production
```bash
npm run build
```

### Preview Production Build
```bash
npm run preview
```

## Admin Credentials

### Main Admin (Super Admin)
- Email: `mainadmin@college.edu`
- Password: `MainAdmin2026!`

### Standard Admin
- Email: `admin@college.edu`
- Password: `Admin123!`

## Deployment

### Cloudflare Pages (Recommended)
1. Push code to GitHub repository
2. Go to Cloudflare Dashboard → Pages → Create a project
3. Connect to your GitHub repository
4. Build settings:
   - Build command: `npm run build`
   - Build output directory: `dist`
5. Click "Save and Deploy"

Or use Wrangler CLI:
```bash
npm install -g wrangler
wrangler pages project create college-problem-portal
wrangler pages deploy dist
```

### Vercel
```bash
npm install -g vercel
vercel
```

### Netlify
```bash
npm install -g netlify-cli
netlify deploy --prod --dir=dist
```

### GitHub Pages
1. Push code to GitHub repository
2. Go to repository Settings → Pages
3. Set source to deploy from `dist` folder

### Static Hosting
Upload the contents of the `dist` folder to any static hosting service.

## Project Structure

```
college-problem-portal/
├── src/
│   ├── App.jsx          # Main application component
│   ├── main.jsx         # Entry point
│   └── index.css        # Tailwind CSS
├── dist/                # Production build output
├── index.html           # HTML template
├── package.json         # Dependencies
├── vite.config.js       # Vite configuration
├── tailwind.config.js   # Tailwind configuration
└── postcss.config.js    # PostCSS configuration
```

## State Management

The application uses React's `useState` hook for state management with mock data. The data structure is designed to be easily connected to a backend database:

```javascript
interface Problem {
  id: string;
  title: string;
  category: string;
  description: string;
  urgency: 'Low' | 'Medium' | 'High';
  status: 'Pending' | 'In Progress' | 'Resolved';
  timestamp: string;
  isDeleted: boolean;
  deletedBy?: string;
}
```

## License

MIT
