# PLU Code Lookup - Web App

A free, offline-capable Progressive Web App for grocery store PLU code lookup. Works on any smartphone (iOS/Android) with voice recognition and text-to-speech.

## ✨ Features

- 🔢 **Search by PLU Code** - Fast numeric lookup
- 📝 **Search by Name** - Partial text matching
- 🎤 **Voice Recognition** - Speak to search hands-free
- 🔊 **Text-to-Speech** - Hear product names
- ⚡ **8-Line Display** - Calculator-style interface
- 🌓 **Dark/Light Themes** - Adjust for any lighting
- 💾 **Offline Support** - Works without internet
- 📂 **CSV Import** - Easy database updates
- 🗑️ **Delete Items** - Manage your database
- ⇅ **Sort by Code/Name** - Flexible organization

## 🚀 Quick Start

### Deploy (5 minutes)

1. **Upload to GitHub Pages**
   - Create repository
   - Upload all files
   - Enable GitHub Pages in Settings

2. **Access on Smartphone**
   - Visit: `https://[username].github.io/[repo-name]/`
   - Install as app on home screen

### Use (30 seconds)

1. **Load Database**
   - Tap "LOAD" button
   - Select your CSV file
   - Database saved locally

2. **Search**
   - By Code: Tap "BY ID" → Enter number → "SEARCH"
   - By Name: Tap "BY NAME" → Type letters → "SEARCH"
   - By Voice: Tap "VOICE" → Speak product or code

## 📁 Files Included

```
index.html          - Main app interface
styles.css          - Calculator-style design
app.js              - Application logic
manifest.json       - PWA configuration
sw.js              - Service worker (offline mode)
sample_plu_database.csv - Example data
DEPLOYMENT_GUIDE.md - Full documentation
```

## 💰 Cost

**Total: $0**
- Free hosting (GitHub Pages/Netlify)
- No server required
- No monthly fees
- Uses existing smartphones

## 🎯 Use Cases

- Training new cashiers
- Quick reference at register
- Voice lookup during checkout
- Mobile price verification
- Inventory management

## 📱 Browser Support

| Platform | Browser | Voice | TTS | PWA |
|----------|---------|-------|-----|-----|
| iOS      | Safari  | ✅    | ✅  | ✅  |
| Android  | Chrome  | ✅    | ✅  | ✅  |
| Desktop  | Chrome  | ✅    | ✅  | ✅  |
| Desktop  | Firefox | ❌    | ✅  | ✅  |

## 🔒 Privacy

- All data stored locally on device
- No external servers
- No tracking
- No data collection
- GDPR compliant

## 📝 CSV Format

```csv
4011,BANANAS YELLOW
4030,KIWI
4040,LIME
4053,LEMON
```

- No headers
- Format: `CODE,NAME`
- Unique codes only
- Uppercase recommended

## 🛠️ Customization

**Change Theme Colors** → Edit `styles.css`  
**Change Voice Language** → Edit `app.js` (line ~252)  
**Adjust Display Lines** → Edit `itemsPerPage` in `app.js`

## 📚 Documentation

See `DEPLOYMENT_GUIDE.md` for:
- Complete installation instructions
- User guide
- Troubleshooting
- Advanced features
- Customization options

## 🆚 Comparison

| Feature | Hardware Device | This Web App |
|---------|----------------|--------------|
| Cost | $50-75 | **$0** |
| Voice Quality | Limited vocabulary | **Native OS** |
| Display | 8 lines LCD | **Full smartphone** |
| Updates | Requires reprogramming | **Upload CSV** |
| Offline | ✅ | ✅ |
| Maintenance | Hardware can fail | **No hardware** |

## 🤝 Contributing

Feel free to:
- Report bugs
- Suggest features
- Submit improvements
- Share customizations

## 📄 License

Free to use for commercial and personal purposes.

## 🏪 Perfect For

- Grocery stores
- Produce markets
- Retail checkouts
- Training facilities
- Any PLU code use case

---

**Get started in 5 minutes. Zero cost. Works offline. No installation required beyond a web browser.**

For detailed setup, see `DEPLOYMENT_GUIDE.md`
