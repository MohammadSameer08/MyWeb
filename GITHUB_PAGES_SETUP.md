# GitHub Pages Deployment Setup

Your Next.js portfolio is now configured for GitHub Pages deployment on `username.github.io`.

## Setup Steps

### 1. Create GitHub Repository
- Create a new repository named `username.github.io` (replace `username` with your actual GitHub username)
- Push your code to this repository

### 2. Build and Deploy

Run the following command to build your site and deploy to GitHub Pages:

```bash
npm run deploy
```

This command will:
- Build your Next.js application
- Export it as static HTML files
- Push the files to the `gh-pages` branch on GitHub
- GitHub Pages will automatically serve from `https://username.github.io`

### 3. Alternative: Manual Build

If you prefer to build manually first:

```bash
# Build and export to the 'out' directory
npm run export

# Then deploy using gh-pages
npm run deploy
```

## Generated Files

After building, you'll find:
- `out/index.html` - Your main portfolio page
- `out/blog/index.html` - Blog page
- All other pages exported as static HTML

## Important Notes

⚠️ **API Routes Limitation**: Your Next.js project includes API routes:
- `/api/contact/route.js`
- `/api/data/route.js`
- `/api/google/route.js`

These API routes **will NOT work on GitHub Pages** because GitHub Pages only serves static files. 

**Solutions:**
1. **Option A**: Move API functionality to an external service (Firebase, Vercel, AWS Lambda, etc.)
2. **Option B**: Remove API routes and integrate services differently (e.g., client-side contact form with email service)
3. **Option C**: Consider using Vercel instead of GitHub Pages for full Next.js support

## Verify Deployment

1. After running `npm run deploy`, wait a few minutes for GitHub Pages to build
2. Visit `https://username.github.io` in your browser
3. Your portfolio should be live!

## Troubleshooting

- Check Repository Settings → Pages → Source is set to "Deploy from a branch" and branch is `gh-pages`
- Clear browser cache if changes aren't showing
- Check GitHub Actions in the repository for deployment status
