# PLU CODE LOOKUP WEB APP - DEPLOYMENT & USER GUIDE

## OVERVIEW

This is a Progressive Web App (PWA) that runs on any smartphone (iOS/Android) and provides a calculator-style interface for PLU code lookup. It works offline, uses native voice recognition, and costs $0 to deploy.

---

## FEATURES

### ✅ Complete Feature List
- **8-line display** showing PLU codes and product names
- **Search by Code** - numeric input for fast lookup
- **Search by Name** - alphabetic search with partial matching
- **Voice Recognition** - speak product names or codes
- **Text-to-Speech** - hear product names spoken aloud
- **Sort** - toggle between CODE and NAME sorting
- **Delete** - remove items from database
- **CSV Upload** - update database from computer
- **Dark/Light Theme** - adjust for different lighting conditions
- **Offline Support** - works without internet after installation
- **No Hardware Required** - runs on existing smartphones

### 💰 Cost Comparison

| Solution | Cost | Pros | Cons |
|----------|------|------|------|
| **Hardware Device** | $50-75 | Dedicated, durable | Fixed features, development time |
| **This Web App** | **$0** | Free, updateable, better voice | Requires smartphone |

---

## DEPLOYMENT OPTIONS

### OPTION 1: FREE HOSTING (GITHUB PAGES) - RECOMMENDED

**Cost: $0**

1. **Create GitHub Account** (if you don't have one)
   - Go to https://github.com
   - Sign up for free

2. **Create New Repository**
   - Click "New Repository"
   - Name: `plu-lookup`
   - Public repository
   - Initialize with README

3. **Upload Files**
   - Click "Add file" → "Upload files"
   - Upload all these files:
     - index.html
     - styles.css
     - app.js
     - manifest.json
     - sw.js
     - sample_plu_database.csv

4. **Enable GitHub Pages**
   - Go to repository Settings
   - Scroll to "Pages" section
   - Source: Deploy from branch "main"
   - Click "Save"

5. **Access Your App**
   - URL will be: `https://[your-username].github.io/plu-lookup/`
   - Share this URL with employees
   - They can install it as an app on their phones

**Time to Deploy: 10 minutes**

---

### OPTION 2: NETLIFY (ALSO FREE)

**Cost: $0**

1. Go to https://www.netlify.com
2. Sign up with GitHub
3. Click "Add new site" → "Import existing project"
4. Connect to your GitHub repository
5. Click "Deploy site"
6. Your app will be live at: `https://[random-name].netlify.app`

**Benefits:**
- Custom domain support
- Automatic HTTPS
- Automatic deployments when you update files

---

### OPTION 3: YOUR OWN WEB SERVER

If you have a web hosting account or server:

1. Upload all files to a directory
2. Ensure HTTPS is enabled (required for voice recognition)
3. Access via your domain

**Note:** HTTPS is **required** for:
- Voice recognition
- Installable PWA
- Service Worker (offline mode)

---

## INSTALLATION ON SMARTPHONES

### iOS (iPhone/iPad)

1. **Open in Safari** (must use Safari, not Chrome)
   - Navigate to your app URL
   
2. **Add to Home Screen**
   - Tap the Share button (square with up arrow)
   - Scroll down and tap "Add to Home Screen"
   - Name it "PLU Lookup"
   - Tap "Add"

3. **App Icon Created**
   - Find the icon on your home screen
   - Opens in fullscreen mode like a native app
   - Works offline after first load

### Android

1. **Open in Chrome**
   - Navigate to your app URL
   
2. **Install App**
   - Tap the menu (three dots)
   - Tap "Add to Home screen" or "Install app"
   - Or Chrome will show an automatic install prompt
   
3. **App Icon Created**
   - Opens like a native app
   - Works offline

---

## USER GUIDE

### INITIAL SETUP

**Load Your PLU Database:**

1. Prepare your CSV file
   - Format: `CODE,PRODUCT NAME`
   - Example: `4011,BANANAS YELLOW`
   - One item per line
   - All caps recommended for product names

2. Tap **LOAD** button
3. Select your CSV file
4. Database is saved in phone's local storage
5. Works offline from this point

### BASIC OPERATIONS

#### 1. Search by PLU Code
```
1. Tap "BY ID" button
2. Enter number using keypad (e.g., 4011)
3. Tap "SEARCH" or press Enter
4. Item found and spoken aloud
```

#### 2. Search by Product Name
```
1. Tap "BY NAME" button
2. Type partial name (e.g., "BANAN")
3. Tap "SEARCH"
4. All matching items displayed
5. Use ▲ ▼ to navigate
```

#### 3. Voice Search
```
1. Tap "VOICE" button (microphone icon)
2. Say product name or code
   - "Four thousand eleven"
   - "Banana"
   - "Green pepper"
3. App speaks result
```

#### 4. Browse All Items
```
1. Tap "CLEAR" to show all items
2. Use ▲ ▼ to scroll
3. Shows 8 items at a time
4. Page indicator shows current position
```

#### 5. Hear Product Name
```
1. Navigate to item using ▲ ▼
2. Tap "SPEAK" button
3. Or tap "SELECT" to speak
```

#### 6. Delete Item
```
1. Navigate to item
2. Tap "DELETE" button
3. Confirm deletion
4. Item removed from database
```

#### 7. Change Sort Order
```
1. Tap "SORT" button
2. Toggles between:
   - Sort by CODE (default)
   - Sort by NAME (alphabetical)
```

#### 8. Adjust Display Brightness
```
1. Tap "THEME" button
2. Switches between:
   - Dark theme (low light/night)
   - Light theme (bright light/day)
```

---

## VOICE RECOGNITION USAGE

### Supported Commands

**Direct Code Lookup:**
- "Four zero eleven" → finds 4011
- "Nine three five two" → finds 9352

**Product Name Search:**
- "Banana" → finds all bananas
- "Red pepper" → finds red bell peppers
- "Organic apple" → finds organic apples

### Tips for Best Results

1. **Speak Clearly** - normal pace, don't rush
2. **Use Full Names** - "banana yellow" better than "banana"
3. **For Codes** - say each digit: "four-zero-one-one"
4. **Quiet Environment** - background noise affects accuracy
5. **Grant Microphone Permission** - browser will ask on first use

### Language Support
- Currently: English (US)
- To change: Modify `recognition.lang` in app.js
- Examples: 'es-ES' (Spanish), 'fr-FR' (French)

---

## DATABASE MANAGEMENT

### Creating Your CSV Database

**Template:**
```csv
4011,BANANAS YELLOW
4030,KIWI
4040,LIME
4053,LEMON
4065,GREEN PEPPER LG
```

**Rules:**
1. ✅ No headers (start directly with data)
2. ✅ Format: CODE,NAME (comma separated)
3. ✅ Codes must be unique (no duplicates)
4. ✅ Use uppercase for consistency
5. ✅ Keep names under 25 characters for display
6. ✅ Save as .csv or .txt file

**Common Sources:**
- IFPS PLU Database: https://www.ifpsglobal.com
- Your POS system exports
- Manual entry in Excel → Save As CSV

### Updating Database

**Method 1: Replace Entire Database**
1. Tap LOAD button
2. Select new CSV file
3. Replaces all existing data

**Method 2: Manual Editing**
1. Currently not supported in app
2. Edit CSV file on computer
3. Re-upload to app

### Backup Database

**Export Current Data:**
- Currently: No export feature
- Data stored in browser's localStorage
- Workaround: Keep master CSV file on computer

**Future Feature:** 
Add export button to download current database as CSV

---

## CUSTOMIZATION OPTIONS

### Change Colors/Theme

Edit `styles.css`:

```css
:root {
    --text-primary: #00ff00;  /* Change display text color */
    --function-btn: #2c5f8d;  /* Change button colors */
}
```

### Change Voice Language

Edit `app.js`:

```javascript
this.recognition.lang = 'es-ES';  // Spanish
this.recognition.lang = 'fr-FR';  // French
this.recognition.lang = 'de-DE';  // German
```

### Adjust Items Per Page

Edit `app.js`:

```javascript
this.itemsPerPage = 8;  // Change to 4, 6, 10, etc.
```

Then update HTML to match number of lines.

### Add Custom Buttons

Add to `index.html` button section and create handler in `app.js`

---

## TROUBLESHOOTING

### Voice Recognition Not Working

**Problem:** Microphone button doesn't respond

**Solutions:**
1. ✅ Check microphone permission in browser settings
2. ✅ Use HTTPS (not HTTP) - required for security
3. ✅ Ensure Chrome (Android) or Safari (iOS)
4. ✅ Check microphone hardware works in other apps

**iOS Specific:**
- Safari only (Chrome on iOS doesn't support Web Speech API)
- Must be added to Home Screen for full features

### Text-to-Speech Not Speaking

**Problem:** Items selected but no audio

**Solutions:**
1. ✅ Check phone volume (not muted)
2. ✅ Try on different browser
3. ✅ Restart browser/app
4. ✅ Check Do Not Disturb mode

### Database Not Saving

**Problem:** Reloads to sample data

**Solutions:**
1. ✅ Don't use Private/Incognito mode
2. ✅ Check browser storage not full
3. ✅ Don't clear browser data
4. ✅ Ensure localStorage enabled

### App Won't Install

**Problem:** No "Add to Home Screen" option

**Solutions:**
1. ✅ Use Safari (iOS) or Chrome (Android)
2. ✅ Visit over HTTPS
3. ✅ Check manifest.json loaded
4. ✅ Try refreshing page

### CSV Upload Fails

**Problem:** "No valid data found"

**Solutions:**
1. ✅ Check file format (CODE,NAME)
2. ✅ No headers in file
3. ✅ Use comma separator (not semicolon)
4. ✅ Codes must be numbers only
5. ✅ One entry per line

---

## ADVANCED FEATURES

### Keyboard Shortcuts

When using on desktop/tablet with keyboard:

- **↑ Arrow Up** - Navigate up
- **↓ Arrow Down** - Navigate down
- **Enter** - Perform search
- **Delete** - Delete current item
- **Backspace** - Delete last character

### Developer Console

Access for debugging:
- **iOS Safari:** Settings → Safari → Advanced → Web Inspector
- **Android Chrome:** Settings → More Tools → Developer Tools

Logs show:
- Database load status
- Voice recognition transcripts
- Search queries
- Errors

---

## BUSINESS USE CASES

### Training New Cashiers
1. Give trainees smartphone with app installed
2. Let them practice looking up codes
3. Quiz mode: Say product name, trainee finds code
4. Voice mode: Hands-free training

### Quick Reference at Register
1. Mount phone/tablet near register
2. Voice search during checkout
3. No hands needed for lookup
4. Fast verification of unusual items

### Inventory Management
1. Use for quick price checks
2. Voice lookup while stocking shelves
3. Verify product codes match labels
4. Mobile reference tool

### Multi-Store Deployment
1. Create store-specific CSV files
2. Each location loads appropriate database
3. Update via new CSV when products change
4. Zero IT infrastructure needed

---

## COST ANALYSIS

### Traditional Solutions

**Option A: Printed PLU Books**
- Cost: $15-20 per book
- Updates: Must reprint ($15-20 each time)
- Annual: $60-80 (quarterly updates)

**Option B: Hardware Device (From Your Original Request)**
- Initial: $50-75 per unit
- Maintenance: Components can fail
- Updates: Requires technical knowledge
- Per Employee: $50-75

**Option C: Commercial PLU Apps**
- Cost: $5-20 per app license
- Subscriptions: $3-5/month some apps
- Annual: $36-60 per user

### This Solution

**Web App (PWA)**
- Development: $0 (provided free)
- Hosting: $0 (GitHub Pages/Netlify)
- Updates: $0 (just edit CSV)
- Devices: $0 (use existing phones)
- **Total Annual Cost: $0**

**ROI:**
- 5 employees × $60/year = $300/year saved
- Plus: Better features (voice, updates, accessibility)

---

## FUTURE ENHANCEMENTS

### Roadmap Ideas

**Phase 1 (Easy - 1-2 hours):**
- [ ] Export database as CSV
- [ ] Import/merge databases
- [ ] Favorite items marking
- [ ] Recent searches history

**Phase 2 (Medium - 4-6 hours):**
- [ ] Barcode scanner integration
- [ ] Multi-language support
- [ ] Custom categories/departments
- [ ] Statistics (most searched items)

**Phase 3 (Advanced - 8-12 hours):**
- [ ] Cloud sync across devices
- [ ] User accounts
- [ ] Shared store databases
- [ ] Analytics dashboard
- [ ] Admin panel for store managers

**Phase 4 (Expert):**
- [ ] Integration with POS systems
- [ ] Real-time price updates
- [ ] Inventory tracking
- [ ] Photo recognition of produce

---

## SUPPORT & MAINTENANCE

### Regular Maintenance Tasks

**Weekly:**
- Check app still accessible
- Verify voice recognition working

**Monthly:**
- Review and update database
- Remove discontinued items
- Add new products

**Quarterly:**
- Check for browser updates
- Test on new phone models
- Refresh cache (republish if needed)

### Getting Help

**Issues with Code:**
- Check browser console for errors
- Review app.js for logic errors
- Test in different browsers

**Database Issues:**
- Validate CSV format
- Check for duplicate codes
- Verify file encoding (UTF-8)

**Deployment Issues:**
- Ensure HTTPS enabled
- Check manifest.json valid
- Verify service worker registered

---

## LEGAL & COMPLIANCE

### Data Privacy
- All data stored locally on device
- No data sent to external servers
- No tracking or analytics
- GDPR compliant (no personal data)

### PLU Code Usage
- PLU codes are standardized (IFPS)
- Free to use for business purposes
- Verify codes with official IFPS database
- Company-specific codes allowed

### Accessibility
- High contrast themes available
- Voice input for hands-free use
- Keyboard navigation supported
- Screen reader compatible

---

## CONCLUSION

This web-based solution provides all the functionality of the proposed hardware device at zero cost, with the added benefits of:

✅ **Better Voice Recognition** (native OS support)  
✅ **Larger Display** (smartphone screens)  
✅ **Easy Updates** (just upload new CSV)  
✅ **No Hardware Maintenance**  
✅ **Works Offline**  
✅ **Installable as App**  
✅ **Multi-platform** (iOS, Android, Desktop)  

**Total Investment: 0 USD + 30 minutes setup time**

For assistance or questions, consult web development forums or smartphone user guides specific to your device.
