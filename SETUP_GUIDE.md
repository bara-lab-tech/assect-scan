# Asset Inventory Scanner - Setup Guide

## 🚀 Quick Start

### ⚠️ Camera Access Issue
Browsers block camera access when opening HTML files directly (`file://` protocol). To enable camera scanning, you need to run a local web server.

## Option 1: Using Python (Recommended)

**Windows:**
```bash
python -m http.server 8000
```

**macOS/Linux:**
```bash
python3 -m http.server 8000
```

Then open: **http://localhost:8000**

## Option 2: Using Node.js

```bash
npx http-server
```

Then open the URL shown in the terminal (usually **http://localhost:8080**)

## Option 3: Using VS Code Live Server

1. Install "Live Server" extension in VS Code
2. Right-click on `index.html`
3. Select "Open with Live Server"

---

## 📝 Features

### Scan Mode 📷
- Requires HTTPS or localhost connection
- Scans QR codes and barcodes
- Auto-populates Asset ID

### Manual Entry Mode ✍️
- Works anywhere without camera
- Perfect for quick data entry
- All fields available for editing

### GitHub Integration 🔗
1. Generate Personal Access Token: https://github.com/settings/tokens
   - Select scopes: `repo` (full control of private repositories)
2. Enter credentials in the header:
   - GitHub Personal Access Token
   - GitHub Username
   - Repository Name
3. Click "Sync" to connect

### Data Persistence 💾
- Local storage for offline use
- GitHub sync for backup
- Excel export available

---

## 🔧 GitHub Setup

### Create a Test Repository

1. Go to https://github.com/new
2. Create a new repository (e.g., `asset-inventory`)
3. Generate token at https://github.com/settings/tokens:
   - Click "Generate new token"
   - Select `repo` scope
   - Copy the token immediately (you can't see it again!)

### First Sync

1. Open the app at http://localhost:8000
2. Enter your GitHub credentials in the header
3. Click "Sync"
4. Check your GitHub repo - it will create `data/inventory.json`

---

## ✅ Testing Checklist

- [ ] Camera access works (if running on localhost/HTTPS)
- [ ] Can add assets manually
- [ ] Can edit assets
- [ ] Can delete assets
- [ ] Search/filter works
- [ ] Excel export works
- [ ] GitHub sync works
- [ ] Data persists across page refresh

---

## 🐛 Troubleshooting

### Camera not working?
- Make sure you're on `http://localhost` (not `file://`)
- Check browser permissions (camera icon in address bar)
- Try refreshing the page
- Use Manual Entry mode as fallback

### GitHub sync failing?
- Verify token is valid
- Check username and repo name spelling
- Ensure token has `repo` scope
- Check browser console for errors (F12)

### No data after refresh?
- Check LocalStorage in browser DevTools
- Make sure GitHub sync completed
- Try clicking "Sync" button

---

## 📱 Mobile Testing

For camera access on mobile:
1. Use HTTPS URL (or localhost on same network)
2. Allow camera permissions when prompted
3. App is fully mobile-responsive

---

## 🎯 Next Steps

1. Run local server: `python -m http.server 8000`
2. Open browser: http://localhost:8000
3. Try scanning a QR code or manually add an asset
4. Setup GitHub integration
5. Export to Excel
