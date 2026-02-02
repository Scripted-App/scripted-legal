# How to Publish Legal Documents to GitHub Pages

## Quick Start (5 minutes)

### Step 1: Create GitHub Repository

1. Go to https://github.com/new
2. Repository name: `scripted-legal`
3. Description: "Legal documents for Scripted iOS app"
4. Set to **Public** (required for free GitHub Pages)
5. Do NOT initialize with README (we already have files)
6. Click "Create repository"

### Step 2: Push Your Code

```bash
cd /Users/elizabeth2.0/Desktop/Scripted/legal-docs

# Add your GitHub remote (replace YOUR-USERNAME with your GitHub username)
git remote add origin https://github.com/YOUR-USERNAME/scripted-legal.git

# Push to GitHub
git branch -M main
git push -u origin main
```

### Step 3: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click "Settings" tab
3. Click "Pages" in the left sidebar
4. Under "Source", select "Deploy from a branch"
5. Select branch: **main**
6. Select folder: **/ (root)**
7. Click "Save"
8. Wait 1-2 minutes for deployment

### Step 4: Get Your URLs

Your site will be live at:
- **Homepage**: `https://YOUR-USERNAME.github.io/scripted-legal/`
- **Privacy Policy**: `https://YOUR-USERNAME.github.io/scripted-legal/privacy.html`
- **Terms & Conditions**: `https://YOUR-USERNAME.github.io/scripted-legal/terms.html`

GitHub will show you the exact URL in Settings > Pages.

### Step 5: Update the iOS App

Once you have your URLs, update `SocialAuthView.swift` (line 161):

```swift
Link("Privacy Policy", destination: URL(string: "https://YOUR-USERNAME.github.io/scripted-legal/privacy.html")!)
Link("Terms & Conditions", destination: URL(string: "https://YOUR-USERNAME.github.io/scripted-legal/terms.html")!)
```

### Step 6: Test

1. Open the URLs in your browser to verify they work
2. Build and run the iOS app
3. Tap on the Privacy Policy and Terms links to make sure they open correctly

## Alternative: Use a Custom Domain

If you own `scripted.app`, you can point GitHub Pages to your custom domain:

1. In GitHub repository Settings > Pages
2. Enter `legal.scripted.app` in "Custom domain"
3. Add a CNAME record in your domain DNS settings:
   - Type: CNAME
   - Name: legal
   - Value: YOUR-USERNAME.github.io
4. Wait for DNS propagation (can take up to 24 hours)

Then your URLs become:
- Privacy: `https://legal.scripted.app/privacy.html`
- Terms: `https://legal.scripted.app/terms.html`

## Updating Documents Later

To update the legal documents:

```bash
cd /Users/elizabeth2.0/Desktop/Scripted/legal-docs

# Edit the HTML files
# Then commit and push changes

git add .
git commit -m "Update Privacy Policy"
git push

# Changes go live in 1-2 minutes automatically
```

## Important Notes

- **Before publishing**: Update the placeholder text in `terms.html`:
  - Find and replace `[Your State]` with your actual state
  - Find and replace `[Your County]` with your actual county
  - These are in the "Dispute Resolution" section

- These documents are PUBLIC - anyone can access them via the URL

- GitHub Pages is completely free for public repositories

- No build process or server needed - just pure HTML/CSS

## Troubleshooting

**If pages don't load after 2 minutes:**
1. Check that the repository is Public (not Private)
2. Verify GitHub Pages is enabled in Settings > Pages
3. Make sure branch is set to `main` and folder is `/ (root)`
4. Check the Actions tab for any deployment errors

**If styling looks broken:**
1. All CSS is inline in the HTML files - no external dependencies
2. Should work on any browser including mobile Safari

## Contact Setup

Don't forget to set up these email addresses:
- `support@scripted.app`
- `privacy@scripted.app`

These are referenced in the legal documents and should forward to your personal email.
