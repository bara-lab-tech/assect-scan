# 📸 QR Scanner - Complete User Guide

## 🎯 Overview

Your Asset Inventory Scanner now has an **improved QR scanning system** with:
- ✅ Manual capture control
- ✅ One-time detection (no alerts spam)
- ✅ Instant LocalStorage save
- ✅ Auto-fill functionality
- ✅ Stop camera button

---

## 🚀 Quick Start (5 Steps)

### Step 1: Open Scan Mode
Click **"📷 Scan Mode"** button at the top left

### Step 2: Point Camera
Point your device camera at a QR code and hold steady

### Step 3: Wait for Detection
Wait 1-2 seconds for automatic detection

### Step 4: See Confirmation
You'll get: **"✅ QR Code captured!"** notification (appears only once!)

### Step 5: Use the Data
- Scanned data shows in text field
- Click **"✅ Use This Data"** button
- Asset ID auto-filled
- Data saved to LocalStorage
- Auto-switches to Manual Entry form
- Complete remaining fields
- Click "Add Asset"

---

## 📱 Scanner Interface

```
┌─────────────────────────────────────┐
│    Asset Inventory Scanner          │
├─────────────────────────────────────┤
│  📷 Scan Mode   │   📝 Manual Entry │ ← Mode Toggle
├─────────────────────────────────────┤
│                                     │
│   [CAMERA PREVIEW - LIVE FEED]      │
│                                     │
│    Shows real-time camera           │
│    Keep QR code in frame            │
│                                     │
├─────────────────────────────────────┤
│  [📸 Capture]    [⏹️ Stop]          │ ← Control Buttons
├─────────────────────────────────────┤
│ Scanned Data                        │
│ [ASSET123_______________________]   │ ← Shows captured code
├─────────────────────────────────────┤
│  [✅ Use This Data]                 │ ← Click after scan
└─────────────────────────────────────┘
```

---

## 🎛️ Control Buttons

### 📸 Capture Button
- **Purpose**: Show camera is ready
- **When to Use**: After pointing at QR code
- **Action**: Click when ready to capture
- **Note**: Detection happens automatically

### ⏹️ Stop Button
- **Purpose**: Turn off camera
- **When to Use**: When done scanning
- **Action**: Stops camera feed and releases resource
- **Benefit**: Saves battery, frees camera for other apps

### ✅ Use This Data Button
- **Purpose**: Confirm and use scanned data
- **When to Use**: After QR code is detected
- **Action**: Saves to LocalStorage, auto-fills Asset ID
- **Next**: Automatically switches to Manual Entry mode

---

## 💾 How Data is Stored

### 1. **Immediate Save** (On Capture)
```javascript
// When you click "Use This Data":
localStorage.setItem('lastScannedQR', {
    id: "ASSET123",
    timestamp: "2025-06-17T10:30:00.000Z",
    source: "qr_scan"
})
```

### 2. **Asset Storage** (On Add)
```javascript
// When you click "Add Asset":
localStorage.setItem('assetInventory', [
    {
        id: "ASSET123",
        name: "Laptop",
        category: "Electronics",
        // ... more fields
    }
])
```

### 3. **GitHub Sync** (Optional)
```javascript
// Automatically committed to GitHub
data/inventory.json
{
    "assets": [
        { /* asset data */ }
    ]
}
```

---

## 📝 Complete Workflow

```
START
 ↓
[Click 📷 Scan Mode]
 ↓
[Point camera at QR code]
 ↓
[Wait 1-2 seconds]
 ↓
[QR detected automatically]
 ↓
[See "✅ QR Code captured!" - ONE TIME ONLY]
 ↓
[Data appears in "Scanned Data" field]
 ↓
[Click ✅ Use This Data]
 ↓
[Data saved to localStorage]
 ↓
[Asset ID auto-filled]
 ↓
[Auto-switch to Manual Entry mode]
 ↓
[Fill in remaining fields]
 ↓
[Click "Add Asset"]
 ↓
[Asset appears in table]
 ↓
[Data also synced to GitHub (if configured)]
 ↓
END
```

---

## 🧪 Testing Guide

### Test 1: Capture and Notification
1. Go to https://www.qr-code-generator.com
2. Generate a test QR code
3. Open app in Scan Mode
4. Point camera at QR
5. Wait for "✅ QR Code captured!" notification
6. **Check**: Notification appears **ONLY ONCE** (no spam)

### Test 2: LocalStorage Save
1. After QR captured, click "Use This Data"
2. Open browser DevTools (F12)
3. Go to **Storage** → **LocalStorage**
4. Look for `lastScannedQR`
5. **Check**: Should see your scanned data

### Test 3: Data Persistence
1. Scan QR code and click "Use This Data"
2. Refresh page (F5)
3. Open DevTools (F12)
4. Check LocalStorage again
5. **Check**: Data still there after refresh

### Test 4: Complete Workflow
1. Capture QR code
2. Click "Use This Data"
3. Complete the form (Name, Category, Location)
4. Click "Add Asset"
5. **Check**: Asset appears in table

### Test 5: Multiple Scans
1. Scan different QR codes
2. Each one should detect once per scan
3. **Check**: No repeated alerts for same QR

---

## 🔍 Debugging

### View Scanned Data
```javascript
// Open browser console (F12)
localStorage.getItem('lastScannedQR')
```

### View All Assets
```javascript
localStorage.getItem('assetInventory')
```

### Clear All Data
```javascript
localStorage.clear()
```

### Check Console Logs
```
F12 → Console tab
Look for: 📸 QR Code detected: ASSET123
```

---

## ⚠️ Common Issues

### Issue: Notification Shows Multiple Times
**Status**: ✅ **FIXED** - Each QR now triggers only once
**Solution**: Already built into the app

### Issue: Camera Not Opening
**Cause**: Running from `file://` instead of `http://localhost`
**Solution**: Use local server:
```bash
python -m http.server 8000
# Then visit: http://localhost:8000
```

### Issue: QR Code Not Detected
**Causes**:
- Poor lighting
- QR code too far away
- QR code partially obscured
- Camera out of focus

**Solutions**:
- Better lighting
- Move camera closer
- Ensure full QR code is visible
- Keep camera steady
- Try different QR code

### Issue: No Data After "Use This Data"
**Solution**: Open DevTools and check:
```javascript
localStorage.getItem('lastScannedQR')
```

### Issue: Can't See "Use This Data" Button
**Cause**: QR code not detected yet
**Solution**: 
- Check camera is on
- Point at valid QR code
- Wait for detection

---

## 📱 Mobile Usage

### On iPhone/iPad
1. Use Safari or Chrome
2. Grant camera permission
3. Point at QR code
4. All features work the same
5. Data saved locally

### On Android
1. Use Chrome or Firefox
2. Grant camera permission
3. Point at QR code
4. Works exactly like desktop
5. All data synced

### Best Practices
- Good lighting conditions
- Hold camera steady
- QR code in center of screen
- Move slowly if needed
- Try different angles

---

## 🔐 Privacy & Security

✅ **Data Storage**
- Only in browser (LocalStorage)
- Optional GitHub backup (if you set it up)
- No external servers

✅ **Camera**
- Only accessed when in Scan Mode
- Explicit permission required
- Can stop anytime with Stop button
- Turned off when not scanning

✅ **QR Codes**
- Not sent anywhere
- Only used locally
- Can scan sensitive codes safely
- No logging of QR content

---

## 📚 Related Features

### Manual Entry Mode
If camera isn't available, use Manual Entry:
1. Click "📝 Manual Entry"
2. Fill in all fields manually
3. Click "Add Asset"
4. Same result, no QR needed

### Excel Export
After adding assets:
1. Click "📊 Download Excel"
2. Get `.xlsx` file with all assets
3. Open in Excel/Sheets

### GitHub Sync
Optional cloud backup:
1. Enter GitHub credentials
2. Click "Sync"
3. All assets backed up online
4. Auto-sync on changes

---

## 💡 Pro Tips

1. **Generate Test QR Codes**
   - https://www.qr-code-generator.com
   - Free, easy, fast

2. **Batch Scanning**
   - Scan multiple items quickly
   - Each one saves separately
   - Complete forms later if needed

3. **Offline Mode**
   - App works completely offline
   - Data saved locally
   - Sync to GitHub when online

4. **Mobile Scanning**
   - Phone camera works great
   - Touch-friendly buttons
   - Perfect for inventory work

5. **Asset ID Tips**
   - Use short, memorable codes
   - Include asset type (LAP, CHR, etc)
   - Example: LAP001, CHR002, etc

---

## ✅ Feature Checklist

- ✅ QR code detection
- ✅ One-time notification
- ✅ Manual capture control
- ✅ Stop button
- ✅ Use This Data button
- ✅ LocalStorage save
- ✅ Auto-fill Asset ID
- ✅ Mode switching
- ✅ No repeated alerts
- ✅ Mobile friendly
- ✅ Offline capable
- ✅ GitHub optional sync

---

## 📞 Support

### Quick Answers
1. **How do I...?** → Read QR_SCANNER_GUIDE.md
2. **Something broken?** → Check console (F12)
3. **Need help?** → See README.md
4. **Quick tips?** → See QUICK_REFERENCE.md

### Console Debugging
```javascript
// Everything logged here
F12 → Console → Look for 📸 messages
```

---

## 🎉 Ready to Scan!

Your QR scanner is now ready with all improvements:
1. ✅ One-time detection
2. ✅ Manual control buttons
3. ✅ Instant LocalStorage save
4. ✅ No notification spam
5. ✅ Auto-fill functionality

**Start scanning! 📸✨**
