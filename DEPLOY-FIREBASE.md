# Deploy RMG Services Website to Firebase Hosting

Firebase Hosting is free for static sites and includes a global CDN, custom domains, and SSL certificates.

## Prerequisites

- A [Google account](https://accounts.google.com)
- [Node.js](https://nodejs.org) installed (v14 or higher)

## Step 1: Install Firebase CLI

Open a terminal and run:

```bash
npm install -g firebase-tools
```

Or, if you prefer not to install globally:

```bash
npx firebase-tools
```

## Step 2: Log in to Firebase

```bash
firebase login
```

A browser window will open. Sign in with your Google account and authorize the CLI.

## Step 3: Initialize Firebase in Your Project

Navigate to your project folder:

```bash
cd c:\Users\Amber\PortfolioObjects
```

Initialize Firebase:

```bash
firebase init hosting
```

When prompted:

1. **Use an existing project or create a new project?**  
   - Choose **Create a new project** or **Use an existing project** (select one)
   - If creating new: enter a project ID (e.g. `rmg-services-lexington-park`)

2. **What do you want to use as your public directory?**  
   - Enter `.` (a single dot) — your project root contains `index.html`, `thanks.html`, etc.

3. **Configure as a single-page app (rewrite all urls to /index.html)?**  
   - Choose **No** — you have multiple pages (`index.html`, `thanks.html`)

4. **Set up automatic builds and deploys with GitHub?**  
   - Choose **No** unless you want GitHub integration

5. **Overwrite index.html?**  
   - Choose **No** if asked — you already have an `index.html`

## Step 4: Deploy

```bash
firebase deploy
```

After deployment, you’ll see output like:

```
Hosting URL: https://your-project-id.web.app
```

Your site is live at that URL.

---

## Optional: Configure for Your Project

If `firebase init` created a `firebase.json` file, it should look like:

```json
{
  "hosting": {
    "public": ".",
    "ignore": [
      "firebase.json",
      "**/.*",
      "**/node_modules/**"
    ]
  }
}
```

If `public` is not `.`, edit `firebase.json` so the `public` folder is the project root (where `index.html` lives).

---

## Custom Domain

1. In the [Firebase Console](https://console.firebase.google.com), open your project.
2. Go to **Hosting** → **Add custom domain**.
3. Enter your domain (e.g. `rmgservices.com`).
4. Follow the instructions to add the DNS records Firebase provides.

---

## Future Deployments

After setup, deploy updates with:

```bash
firebase deploy
```

Or deploy only hosting:

```bash
firebase deploy --only hosting
```

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| `firebase: command not found` | Run `npm install -g firebase-tools` again or use `npx firebase-tools` |
| "Permission denied" | Run `firebase login` again |
| Form redirect goes to wrong URL | The form uses `window.location.origin`; on Firebase Hosting this will be correct |
| 404 on `thanks.html` | Ensure `thanks.html` is in the same folder as `index.html` and `public` is set to `.` |
