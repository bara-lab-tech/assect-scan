# ⚡ Quick Reference Card

## 🚀 Start App (One Command)
```bash
python -m http.server 8000
```
Then open: **http://localhost:8000**

---

## 📋 File Guide

| File | Purpose |
|------|---------|
| `index.html` | **Main Application** - Complete asset scanner |
| `README.md` | Full documentation & troubleshooting |
| `SETUP_GUIDE.md` | Setup instructions for beginners |
| `test.html` | Diagnostics tool to check system |
| `QUICK_REFERENCE.md` | This file - quick cheat sheet |

---

## 🎯 Main Features

### 📷 **Scan Mode**
- Opens camera and scans QR codes
- Auto-fills Asset ID from scan
- Falls back to manual entry if needed

### ✍️ **Manual Entry Mode**  
- Forms for all asset fields
- Quick data entry without camera
- Works everywhere, no camera needed

### 📊 **Asset Table**
- Shows all assets with full details
- Search by ID, name, or category
- Edit and delete buttons on each row

### 🔗 **GitHub Sync**
- Stores data in your GitHub repo
- Auto-commits on every change
- Pull latest data with Sync button

### 📥 **Excel Export**
- Downloads as `.xlsx` file
- Auto-formatted with headers
- Timestamped filename

---

## 🔑 GitHub Setup (5 min)

### 1. Generate Token
1. Go to: https://github.com/settings/tokens
2. Click "Generate new token"
3. Select `repo` scope
4. Copy token (save it!)

### 2. In App Header
- Paste token in "GitHub Personal Access Token"
- Enter your username
- Enter repository name
- Press Enter to save

### 3. First Sync
- Click "Sync" button
- Check your GitHub repo
- Should see `data/inventory.json`

---

## 🆘 Quick Troubleshooting

| Problem | Fix |
|---------|-----|
| Camera blocked | Use `http://localhost` not `file://` |
| No GitHub sync | Check token & username are correct |
| No data after refresh | Try Sync first, or check LocalStorage |
| App won't load | Refresh (Ctrl+F5) and check console (F12) |

---

## 🔍 Debug Mode (F12)

Press **F12** → Click **Console** tab to see:

- ✅ 🚀 App starting messages
- ✅ 📷 Camera detection
- ✅ 🔄 Sync status
- ❌ Any errors (red text)

---

## ⌨️ Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| **F12** | Open DevTools console |
| **Ctrl+F5** | Hard refresh |
| **Cmd+Shift+R** | Mac hard refresh |
| **Tab** | Jump between form fields |
| **Enter** | Submit form |
| **Escape** | Close modals |

---

## 💡 Pro Tips

1. **Manual Entry First** - Try manual mode before camera
2. **Use Test Page** - Open `test.html` to check system
3. **Watch Console** - F12 shows all debugging info
4. **Allow Permissions** - Browser may ask for camera
5. **Local Server** - Always use `http://localhost`
6. **GitHub Backup** - Sync regularly to backup data
7. **Excel Export** - Download regularly as backup

---

## 🔐 Important

- **GitHub Token**: Only in browser memory, cleared on logout
- **Data**: Stored in YOUR GitHub repo (you own it)
- **Camera**: Only active when Scan Mode is on
- **LocalStorage**: ~5-10MB limit per browser

---

## 📞 Need Help?

1. Check **README.md** for detailed guide
2. Open **test.html** to run diagnostics
3. Press **F12** and check Console tab
4. Read error messages carefully (very descriptive)
5. Try **Manual Entry** if camera fails

---

## ✨ All Features At A Glance

```
📦 Asset Inventory Scanner
├── 📷 QR/Barcode Scanning (with fallback)
├── ✍️  Manual Data Entry
├── 🔍 Real-time Search & Filter
├── ✏️  Edit Assets
├── 🗑️  Delete Assets
├── 📊 Excel Export
├── 🔗 GitHub Auto-Sync
├── 💾 LocalStorage Cache
├── 📱 Mobile Responsive
├── 🎨 Modern UI
└── 🛡️  Error Handling
```

---

**Ready?** → Run `python -m http.server 8000` → Open `http://localhost:8000`

Happy scanning! 📦✨
