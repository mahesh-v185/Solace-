# Deployment Guide for Solace AI Companion

## Prerequisites
- Your `GEMINI_API_KEY` from Google AI Studio
- A GitHub account (for most options)

## Option 1: Vercel (Recommended - Easiest)

### Steps:
1. **Install Vercel CLI**:
   ```bash
   npm install -g vercel
   ```

2. **Deploy**:
   ```bash
   npx vercel --prod
   ```

3. **Set Environment Variables**:
   - Go to your Vercel dashboard
   - Navigate to your project → Settings → Environment Variables
   - Add: `GEMINI_API_KEY` = your API key

4. **Your app will be live at**: `https://your-project-name.vercel.app`

## Option 2: Netlify

### Steps:
1. **Install Netlify CLI**:
   ```bash
   npm install -g netlify-cli
   ```

2. **Build your app**:
   ```bash
   npm run build
   ```

3. **Deploy**:
   ```bash
   netlify deploy --prod --dir=dist
   ```

4. **Set Environment Variables**:
   - Go to Netlify dashboard → Site settings → Environment variables
   - Add: `GEMINI_API_KEY` = your API key

## Option 3: GitHub Pages

### Steps:
1. **Push your code to GitHub**:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/yourusername/your-repo-name.git
   git push -u origin main
   ```

2. **Set up GitHub Secrets**:
   - Go to your GitHub repo → Settings → Secrets and variables → Actions
   - Add: `GEMINI_API_KEY` = your API key

3. **Enable GitHub Pages**:
   - Go to Settings → Pages
   - Source: Deploy from a branch
   - Branch: gh-pages

4. **Your app will be live at**: `https://yourusername.github.io/your-repo-name`

## Option 4: Firebase Hosting

### Steps:
1. **Install Firebase CLI**:
   ```bash
   npm install -g firebase-tools
   ```

2. **Login to Firebase**:
   ```bash
   firebase login
   ```

3. **Initialize Firebase**:
   ```bash
   firebase init hosting
   ```

4. **Build and Deploy**:
   ```bash
   npm run build
   firebase deploy
   ```

5. **Set Environment Variables**:
   - Go to Firebase Console → Functions → Environment variables
   - Add: `GEMINI_API_KEY` = your API key

## Option 5: Static File Hosting

You can also upload the `dist` folder to any static hosting service:

- **Surge.sh**: `npx surge dist`
- **Cloudflare Pages**: Drag and drop the `dist` folder
- **AWS S3**: Upload the `dist` folder to an S3 bucket

## Important Notes:

1. **Environment Variables**: Make sure to set your `GEMINI_API_KEY` in your hosting platform's environment variables.

2. **CORS Issues**: If you encounter CORS issues, you might need to configure your hosting platform to handle API requests properly.

3. **API Key Security**: Never commit your API key to version control. Always use environment variables.

4. **Custom Domain**: Most platforms allow you to set up a custom domain for your app.

## Quick Test:

After deployment, test that your app works by:
1. Opening the deployed URL
2. Sending a message to Solace
3. Verifying the AI responds correctly

## Troubleshooting:

- **Build Errors**: Make sure all dependencies are installed (`npm install`)
- **API Errors**: Verify your `GEMINI_API_KEY` is correctly set
- **404 Errors**: Ensure your hosting platform is configured for SPA routing 