# 🎯 Raynor Planning Intelligence v3.5

**Smart Planning with Pre-loaded Historical Intelligence**

Version 3.5 introduces a major workflow improvement: historical PO intelligence is now **pre-loaded and persistent**, so you only need to upload your buying sheet for daily planning work.

## 🆕 What's New in v3.5

### Pre-loaded Intelligence Architecture
- **Historical data persists** in browser storage (localStorage)
- **Upload buying sheet only** for daily/weekly planning
- **Update intelligence quarterly** (every 3-6 months) as needed
- **Export/Import intelligence** to share across devices or backup

### Key Benefits
✅ **Faster workflow** - No need to upload Past POs every time
✅ **Consistent intelligence** - Same historical context for all planning sessions
✅ **Easy updates** - Refresh intelligence on your schedule
✅ **Portable** - Export intelligence to use on different computers

## 📋 Daily Workflow (Simple!)

1. Open the tool → Historical intelligence automatically loads
2. Upload your current **Buying Sheet** (the only file you need daily)
3. Click **Generate Planning Dashboard**
4. Review items with intelligent suggestions:
   - Average order quantities from history
   - Typical ship-to plants
   - Last order dates
5. Make decisions, add notes, mark actions
6. Export your work

**That's it!** No need to upload Past POs every time.

## 🔄 Updating Intelligence (Every 3-6 Months)

When you want to refresh the historical intelligence with newer data:

### Method 1: Upload New Past POs
1. Export fresh F4311 (Past POs) data from JDE
2. In the tool, click the **"Update Intelligence (Optional)"** upload box
3. Select your new Past POs file
4. Intelligence automatically rebuilds and saves
5. Export the intelligence file for backup

### Method 2: Import Pre-built Intelligence
1. Click **"Import Intelligence Data"**
2. Select a `.json` intelligence file
3. Intelligence loads and saves automatically

## 💾 Intelligence Data Management

### Export Intelligence
- Click **"Export Intelligence Data"**
- Saves as `raynor-intelligence-YYYY-MM-DD.json`
- Use this to:
  - Backup your intelligence data
  - Share with team members
  - Use on different computers/browsers

### Import Intelligence
- Click **"Import Intelligence Data"**
- Select a previously exported `.json` file
- Instantly loads all historical intelligence

### Where is Intelligence Stored?
- **Browser localStorage** - Persists between sessions
- Stored locally in your browser only
- No data sent to any server
- Survives page refreshes and browser restarts
- Clear browser data = intelligence is lost (export first!)

## 📊 Intelligence Data Format

The intelligence JSON file contains:

```json
{
  "version": "3.5",
  "lastUpdated": "2026-02-16",
  "itemCount": 1523,
  "intelligence": {
    "12345_ITEM001": {
      "avgQty": 500,
      "typicalShipTo": "Plant A",
      "lastOrderDate": "2026-01-15",
      "orderCount": 12
    }
  }
}
```

**Key Format:** `SUPPLIER_ITEM`
- Supplier = Address Number (AN8)
- Item = Short Item Number

## 🚀 Deployment to GitHub Pages

### Option 1: GitHub Web Interface (Easiest)
1. Go to https://github.com/new
2. Repository name: `raynor-planning-intelligence`
3. Make it **Public**
4. Create repository
5. Upload `index_v3.5.html` (rename to `index.html`)
6. Go to Settings → Pages
7. Source: "main" branch → Save
8. Your tool will be live at: `https://[username].github.io/raynor-planning-intelligence/`

### Option 2: Git Command Line
```bash
# Create and navigate to directory
mkdir raynor-planning-intelligence
cd raynor-planning-intelligence

# Copy your file and rename
cp index_v3.5.html index.html

# Initialize git
git init
git add index.html
git commit -m "Deploy Raynor Planning Intelligence v3.5"

# Connect to GitHub (create repo first at github.com)
git remote add origin https://github.com/[username]/raynor-planning-intelligence.git
git branch -M main
git push -u origin main

# Enable GitHub Pages in repository Settings → Pages
```

## 📝 Column Mapping Reference

### Buying Sheet (Required File)
The tool automatically detects these columns:

| Data | Column Names (flexible matching) |
|------|----------------------------------|
| **Item Number** | 'Item Number', 'Item', 'Short Item', 'ITM', 'Short Item No' |
| **Description** | 'Description', 'Desc', 'Item Description', 'DSC' |
| **Supplier** | 'Alpha Name', 'Supplier', 'Supplier Name', 'AN8', 'Address Number' |
| **Ship To** | 'Ship To Numbers', 'Ship To', 'SHAN', 'Ship To Number' |
| **On Hand** | 'Total On Hand', 'On Hand', 'TRQT', 'Quantity On Hand' |
| **On PO** | 'Quantity On P.O.', 'On PO', 'QTOR', 'Open PO' |
| **Cushion** | 'CUSHION OH+OO-commits-dmdlt', 'Cushion', 'CUSH' |

### Past POs / F4311 (Optional - For Updating Intelligence)
| Data | Column Names |
|------|-------------|
| **Item** | 'Short Item No', 'Item Number', 'Item' |
| **Supplier** | 'Address Number', 'Supp No', 'AN8' |
| **Ship To** | 'Ship To Number', 'Ship To' |
| **Quantity Ordered** | 'Quantity Ordered' |
| **Quantity Received** | 'Quantity Received' |
| **Order Date** | 'Order Date' |

## 🔧 Maintenance Schedule

### Recommended Update Frequency
- **Buying Sheet**: Daily or weekly (as needed for planning)
- **Intelligence Data**: Every 3-6 months
- **Full Intelligence Rebuild**: Quarterly or when you notice stale data

### Best Practices
1. **Export intelligence after each update** - Create backup files
2. **Date your intelligence exports** - Track which quarter's data you have
3. **Share intelligence with team** - Everyone uses same historical context
4. **Keep backups** - Intelligence files are small, keep archives

## 🎯 Features

### Dashboard Features
- ✅ Pre-loaded historical intelligence
- ✅ Real-time filtering by supplier, ship-to, history status
- ✅ Search by item number or description
- ✅ Sortable columns
- ✅ Bulk actions (Mark Ordered, Skip)
- ✅ Notes for each item
- ✅ Export to Excel with all intelligence data

### Intelligence Insights
- 📊 **Average Order Quantity** - Based on completed POs
- 📍 **Typical Ship-To Plant** - Most frequently used location
- 📅 **Last Order Date** - When item was last ordered
- 🔢 **Order Count** - Number of historical orders analyzed

## 🔒 Privacy & Security

- **100% Client-side** - All processing happens in your browser
- **No server uploads** - Your data never leaves your computer
- **No tracking** - No analytics or data collection
- **No account required** - Just open and use
- **Secure** - Can be used on company networks (no external data transfer)

## 🆘 Troubleshooting

### Intelligence Not Loading
- Check browser console for errors
- Try exporting and re-importing intelligence
- Clear browser cache (but export intelligence first!)

### Columns Not Detected
- Verify your Excel/CSV column headers match expected names
- Try renaming columns to match the reference table above
- Ensure data is in the first sheet of Excel files

### Intelligence Not Saving
- Check browser localStorage is enabled
- Try exporting intelligence manually after each update
- Some browsers in private/incognito mode don't persist localStorage

### Can't Access on Different Computer
- Export intelligence file on computer A
- Import intelligence file on computer B
- Intelligence is stored per-browser, not per-account

## 📞 Support

For questions or issues:
1. Check this README
2. Review the browser console for error messages
3. Export your intelligence data before troubleshooting
4. Try in a different browser if issues persist

## 🗺️ Roadmap

Potential future enhancements:
- Cloud sync for intelligence data
- Multi-user collaboration
- Advanced forecasting algorithms
- Supplier performance metrics
- Lead time analysis
- Automated reorder suggestions

---

**Version**: 3.5
**Last Updated**: February 2026
**Compatible With**: Chrome, Edge, Firefox, Safari (modern versions)
