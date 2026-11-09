# GitHub Pages Setup Instructions

This document explains how to enable GitHub Pages for the privacy policy site.

## Automatic Deployment

Once GitHub Pages is enabled, the included GitHub Actions workflow (`.github/workflows/deploy-pages.yml`) will automatically deploy the privacy policy whenever changes are pushed to the `main` branch.

## Manual Setup Steps

Since GitHub Pages cannot be enabled programmatically via API, please follow these steps:

### 1. Enable GitHub Pages

1. Go to repository **Settings**: https://github.com/Vito9972/janitorai-exporter-privacy/settings
2. Navigate to **Pages** in the left sidebar (under "Code and automation")
3. Under **Source**, select: **GitHub Actions**
4. Save the settings

### 2. Verify Deployment

After enabling Pages and merging the PR:

1. The workflow will automatically run
2. Check the **Actions** tab to monitor deployment progress
3. Once complete, the site will be available at:
   ```
   https://vito9972.github.io/janitorai-exporter-privacy/
   ```

### 3. Test the Published Site

Once deployed, verify:

```bash
# Test that the site is publicly accessible
curl -I https://vito9972.github.io/janitorai-exporter-privacy/

# Expected: HTTP 200 OK
```

Open in browser and verify:
- ✅ Both Chinese and English sections are readable
- ✅ Anchor links work (#chinese, #english)
- ✅ No console errors
- ✅ No external resources loading
- ✅ Contact email: vitoscroll@gmail.com
- ✅ Publisher: Vito9972
- ✅ Effective date: 2026-11-10

### 4. Use in Chrome Web Store

After verification, use the published URL in the Chrome Web Store Developer Dashboard:

1. Go to: https://chrome.google.com/webstore/devconsole
2. Open your extension listing
3. Navigate to **Privacy practices** tab
4. Paste the URL: `https://vito9972.github.io/janitorai-exporter-privacy/`
5. Save draft (do not submit yet)

## Alternative: Manual Deployment (Fallback)

If the GitHub Actions workflow encounters issues:

1. In repository Settings → Pages
2. Change **Source** to: **Deploy from a branch**
3. Select branch: **main**
4. Select folder: **/ (root)**
5. Click **Save**

## Workflow Details

The GitHub Actions workflow:
- Triggers on push to `main` branch
- Validates HTML structure
- Checks for external resources
- Verifies required content is present
- Deploys to GitHub Pages
- Provides deployment URL

## Security Notes

The deployed page:
- Contains no JavaScript execution (inline script in test file is for validation only, not deployed)
- Has strict Content Security Policy (CSP)
- Loads no external resources
- Sets no cookies
- Uses no analytics or tracking

## Troubleshooting

### Deployment fails
- Check **Actions** tab for error messages
- Verify Pages is enabled in Settings
- Ensure workflow file is in `.github/workflows/`

### Site not accessible
- Wait 1-2 minutes after first deployment
- Check if DNS has propagated
- Verify repository is public

### Wrong URL
- Standard format: `https://<username>.github.io/<repository-name>/`
- For this repo: `https://vito9972.github.io/janitorai-exporter-privacy/`

## Contact

For questions about this privacy policy page setup:
- Repository: https://github.com/Vito9972/janitorai-exporter-privacy
- Email: vitoscroll@gmail.com (do not send passwords or private chats)
