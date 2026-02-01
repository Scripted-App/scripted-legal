# Legal Documents Hosting Instructions

This folder contains HTML versions of the Privacy Policy and Terms & Conditions for the Scripted iOS app.

## Files
- `privacy.html` - Privacy Policy
- `terms.html` - Terms and Conditions

## Hosting Options

### Option 1: GitHub Pages (Recommended - Free and Easy)

1. Create a new public GitHub repository (e.g., `scripted-legal`)
2. Upload both HTML files to the repository
3. Go to Settings > Pages
4. Select "Deploy from a branch" and choose `main` branch
5. Save and wait for deployment
6. Your URLs will be:
   - Privacy: `https://[your-username].github.io/scripted-legal/privacy.html`
   - Terms: `https://[your-username].github.io/scripted-legal/terms.html`

### Option 2: Firebase Hosting (Free)

```bash
# Install Firebase CLI if not already installed
npm install -g firebase-tools

# Login to Firebase
firebase login

# Initialize Firebase Hosting in this directory
cd /Users/elizabeth2.0/Desktop/Scripted/legal-docs
firebase init hosting

# Select your Firebase project
# Choose this directory as public directory
# Configure as single-page app: No
# Don't overwrite files

# Deploy
firebase deploy --only hosting
```

Your URLs will be:
- Privacy: `https://[your-project-id].web.app/privacy.html`
- Terms: `https://[your-project-id].web.app/terms.html`

### Option 3: Custom Domain

If you have a domain (e.g., `scripted.app`):
1. Upload files to your web hosting
2. Access at:
   - `https://scripted.app/privacy.html`
   - `https://scripted.app/terms.html`

## Next Steps

After hosting:

1. **Update the iOS app** (`SocialAuthView.swift` line 161):
```swift
Link("Privacy Policy", destination: URL(string: "YOUR_PRIVACY_URL_HERE")!)
Link("Terms & Conditions", destination: URL(string: "YOUR_TERMS_URL_HERE")!)
```

2. **Test the links** in the app to make sure they open correctly

3. **Add URLs to App Store Connect** when submitting:
   - Privacy Policy URL (required field)
   - Terms & Conditions URL (optional but recommended)

## Notes

- **IMPORTANT**: The Terms & Conditions file contains placeholder text `[Your State]` and `[Your County]` in the "Dispute Resolution" section. Update these with your actual state and county before hosting.

- Both files are styled with purple branding (#734D80) matching the Scripted app design

- Files are mobile-responsive and will display properly on iPhone screens

- No external dependencies - pure HTML/CSS for fast loading

## Domain Email Setup

Once you have a domain, set up these email addresses:
- `support@scripted.app` (used in Terms & Conditions)
- `privacy@scripted.app` (used in Privacy Policy)

Forward both to your personal email.
