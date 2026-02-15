# RMG Services - Website

Production-ready website for **RMG Services** — tree removal, tree trimming, power washing, and landscaping in Lexington Park, MD.

## Features

- **Working form** — Quote requests are sent via FormSubmit.co to rmgservices301@gmail.com
- **Thank-you page** — Visitors are redirected to `thanks.html` after submitting
- **Responsive** — Mobile, tablet, and desktop
- **Deploy-ready** — Includes Netlify and Vercel configs

## Deployment

### Option 1: Netlify (recommended)

1. Go to [app.netlify.com](https://app.netlify.com)
2. Drag and drop this folder onto the deploy area, or connect your Git repo
3. Deploy — no build step required

### Option 2: Firebase Hosting

See **[DEPLOY-FIREBASE.md](DEPLOY-FIREBASE.md)** for step-by-step instructions.

### Option 3: Vercel

1. Go to [vercel.com](https://vercel.com)
2. Import this project (from Git or upload)
3. Deploy

### Option 4: GitHub Pages

1. Push this folder to a GitHub repo
2. Settings → Pages → Source: Deploy from branch
3. Select the branch and `/` (root)

### Option 5: Any static host

Upload the contents of this folder to your hosting provider (Hostinger, Bluehost, etc.). All paths are relative and will work.

## Form Setup (first-time only)

The form uses [FormSubmit.co](https://formsubmit.co) (free, no signup). **On first submission**, FormSubmit will send a one-time activation email to `rmgservices301@gmail.com`. The recipient must click the link to activate. After that, all submissions go straight to that inbox.

To use a different email, edit the form `action` in `index.html`:

```html
action="https://formsubmit.co/your-email@example.com"
```

## File Structure

```
├── index.html      # Homepage
├── thanks.html     # Post-submit thank-you page
├── styles.css      # Styles
├── script.js       # Nav, smooth scroll
├── images/
│   └── logo.png    # Logo
├── netlify.toml    # Netlify config
├── vercel.json     # Vercel config
└── README.md
```

## Local Development

```bash
# Python
python -m http.server 8000

# Node
npx serve .
```

Then open http://localhost:8000

**Note:** Form redirect to `thanks.html` works when deployed. When testing locally via `file://`, the redirect URL may not resolve correctly—deploy to test the full flow.
