# TrialScope AI - Vercel Deployment Guide

## 🚀 Quick Deploy to Vercel

### Option 1: Deploy from GitHub (Recommended)

1. **Connect to Vercel**
   - Go to [vercel.com](https://vercel.com)
   - Sign in with your GitHub account
   - Click "New Project"

2. **Import Repository**
   - Select your `trialscope-ai` repository
   - Vercel will auto-detect it's a static site

3. **Configure Settings**
   - **Framework Preset**: Other
   - **Root Directory**: `./` (leave as default)
   - **Build Command**: Leave empty (not needed for static sites)
   - **Output Directory**: Leave empty (not needed for static sites)

4. **Deploy**
   - Click "Deploy"
   - Your app will be live in minutes!

### Option 2: Deploy via Vercel CLI

```bash
# Install Vercel CLI
npm i -g vercel

# Navigate to project
cd trialscope-ai

# Deploy
vercel

# Follow the prompts
# - Link to existing project or create new
# - Confirm settings
```

## 📁 Project Structure for Vercel

```
trialscope-ai/
├── index.html          # Main app (served at /)
├── demo.html           # Demo version (served at /demo)
├── styles.css          # Styling
├── script.js           # JavaScript functionality
├── vercel.json         # Vercel configuration
├── _headers            # Security headers
├── package.json        # Project metadata
└── README.md          # Documentation
```

## 🔧 Configuration Files

### vercel.json
- Routes `/` to `index.html`
- Routes `/demo` to `demo.html`
- Adds security headers

### _headers
- CORS configuration for API calls
- Security headers for protection

### package.json
- Project metadata
- Build configuration
- Keywords for discoverability

## 🌐 Environment Variables (Optional)

If you need to add API keys later:

```bash
# In Vercel dashboard or CLI
vercel env add CLINICAL_TRIALS_API_KEY
vercel env add PUBMED_API_KEY
```

## 🔍 Testing Your Deployment

1. **Main App**: Visit your Vercel URL
2. **Demo Version**: Visit `your-url.vercel.app/demo`
3. **API Testing**: Try queries like "Compare pembrolizumab vs nivolumab"

## 🛠️ Troubleshooting

### Common Issues:

1. **CORS Errors**
   - Solution: The `_headers` file handles this
   - APIs used are public and CORS-enabled

2. **Build Errors**
   - Solution: Static site, no build required
   - Check `vercel.json` configuration

3. **API Timeouts**
   - Solution: APIs have rate limits
   - App includes fallback to mock data

### Performance Tips:

- **CDN**: Vercel automatically provides global CDN
- **Caching**: Static files are cached automatically
- **Compression**: Enabled by default

## 📊 Monitoring

- **Vercel Analytics**: Built-in performance monitoring
- **Error Tracking**: Automatic error reporting
- **Uptime**: 99.9% uptime guarantee

## 🔄 Updates

To update your deployment:

```bash
# Push changes to GitHub
git push

# Vercel automatically redeploys
# Or manually trigger:
vercel --prod
```

## 🎯 Success Checklist

- [ ] Repository connected to Vercel
- [ ] Main app loads at root URL
- [ ] Demo version accessible at `/demo`
- [ ] API calls work (try a query)
- [ ] Security headers applied
- [ ] Performance optimized

Your TrialScope AI should now be live and fully functional on Vercel! 🎉 