# Product Documentation Portal - Technical Implementation Guide

## 📍 Repository Information

**Repository:** `asymblinc.github.io`
**GitHub URL:** https://github.com/asymblinc/asymblinc.github.io
**Branch:** `update/docs-portal-enhancement` (or create new feature branch)

---

## 📁 Files to Modify

Only **ONE** file needs to be updated:

```
/docs-data.json
```

**Location:** Root directory of the repository

---

## 🔧 Changes Required

### 1. Update Product Information (Lines vary by product)

Find your product object in `docs-data.json` and update these fields:

```json
{
  "releaseVersion": "PRODUCT X.X",      // e.g., "ATS 1.45"
  "packageVersion": "v-X.XXX.X",        // e.g., "v-1.146.2"
  "releaseDate": "Month DD, YYYY"       // e.g., "February 3, 2026"
}
```

### 2. Update Documentation Links

Replace `"#"` placeholders with actual Google Docs URLs:

```json
"links": {
  "integrationGuide": {
    "url": "https://docs.google.com/document/d/DOCUMENT_ID/edit",
    "label": "External Integration Guide"
  },
  "preDeployment": {
    "url": "https://docs.google.com/document/d/DOCUMENT_ID/edit",
    "label": "Pre-Deployment Steps"
  },
  "postDeployment": {
    "url": "https://docs.google.com/document/d/DOCUMENT_ID/edit",
    "label": "Post-Deployment Steps"
  },
  "techDoc": {
    "url": "https://docs.google.com/document/d/DOCUMENT_ID/edit",
    "label": "Technical Documentation"
  },
  "userGuide": {
    "url": "https://docs.google.com/document/d/DOCUMENT_ID/edit",
    "label": "User Guide"
  }
}
```

### 3. Add Release History

Populate the `releaseHistory` array with last 10 releases:

```json
"releaseHistory": [
  {
    "releaseVersion": "PRODUCT X.X",
    "packageVersion": "v-X.XXX.X",
    "date": "YYYY-MM-DD",
    "releaseNotesUrl": "https://docs.google.com/document/d/DOCUMENT_ID/edit"
  }
  // Add 9 more releases (newest first)
]
```

---

## 📋 Data Collection Checklist

Before making changes, collect this information:

### Current Release Information
- [ ] Latest release version (e.g., "ATS 1.45")
- [ ] Latest package version (e.g., "v-1.146.2")
- [ ] Latest release date (e.g., "February 3, 2026")

### Documentation URLs
- [ ] Integration Guide URL
- [ ] Pre-Deployment Steps URL
- [ ] Post-Deployment Steps URL
- [ ] Technical Documentation URL
- [ ] User Guide URL

### Release History (Last 10 Releases)
For each release, collect:
- [ ] Release version
- [ ] Package version
- [ ] Release date
- [ ] Release notes URL

**Where to find this data:**
- Slack channel: `#asymbl-{product-name}-release-management`
- Jira releases for the product
- Google Drive documentation folders
- Ask product owner/manager

---

## 🎯 Implementation Summary

**What you're doing:**
Updating a JSON file to add product documentation links and release history so they appear in the documentation portal website.

**Steps:**
1. Clone the repository
2. Open `/docs-data.json`
3. Find your product section
4. Update the 3 version fields
5. Replace 5 documentation link URLs
6. Add 10 release history entries
7. Validate JSON syntax
8. Test locally
9. Commit and push

---

## ✅ Validation Checklist

### Before Committing:

**JSON Syntax:**
- [ ] Validate JSON at https://jsonlint.com/ (paste entire file)
- [ ] No trailing commas after last array/object items
- [ ] All strings use double quotes `"` not single quotes `'`

**Data Format:**
- [ ] Dates in release history use format: `"YYYY-MM-DD"` (e.g., `"2026-02-03"`)
- [ ] Release versions use format: `"PRODUCT X.X"` (e.g., `"ATS 1.45"`)
- [ ] Package versions use format: `"v-X.XXX.X"` (e.g., `"v-1.146.2"`)
- [ ] Release history is ordered newest → oldest

**Links:**
- [ ] All Google Docs URLs are complete (not shortened)
- [ ] All documents have proper sharing permissions
- [ ] Test each link opens in browser

### Testing:

**Local Test:**
```bash
# Navigate to repository
cd /path/to/asymblinc.github.io

# Start local server
python3 -m http.server 8000

# Open in browser
http://localhost:8000
```

**Browser Checks:**
- [ ] Click your product in left sidebar
- [ ] Verify version shows correctly
- [ ] Click all 5 documentation links (should open in new tab)
- [ ] Check release history appears on right sidebar
- [ ] Verify release cards show correct information

---

## 📖 Examples

### Example 1: Complete Product (AIN)
See lines **267-344** in `docs-data.json` for reference

### Example 2: Complete Product (ARA)
See lines **345-432** in `docs-data.json` for reference

### Example 3: Incomplete Product (ASIN)
See lines **433-467** in `docs-data.json` - this needs to be updated

---

## 🚨 Common Mistakes to Avoid

1. **Trailing comma in JSON:**
   ```json
   // ❌ Wrong
   "releaseHistory": [
     { "version": "1.0" },
   ]

   // ✅ Correct
   "releaseHistory": [
     { "version": "1.0" }
   ]
   ```

2. **Wrong date format in JSON:**
   ```json
   // ❌ Wrong
   "date": "Feb 3, 2026"

   // ✅ Correct
   "date": "2026-02-03"
   ```

3. **Wrong version format:**
   ```json
   // ❌ Wrong
   "releaseVersion": "v1.45"

   // ✅ Correct
   "releaseVersion": "ATS 1.45"
   ```

4. **Missing package version prefix:**
   ```json
   // ❌ Wrong
   "packageVersion": "1.146.2"

   // ✅ Correct
   "packageVersion": "v-1.146.2"
   ```

5. **Wrong release order:**
   - ❌ Oldest first
   - ✅ Newest first (latest release at top of array)

---

## 🔗 Quick Reference

| Product ID | Product Name | Current Lines | Status |
|-----------|--------------|---------------|---------|
| ats | ATS | 3-96 | ✅ Complete |
| asm | ASM | 97-190 | ✅ Complete |
| ast | AST | 191-266 | ✅ Complete |
| ain | AIN | 267-344 | ✅ Complete |
| ara | ARA | 345-432 | ✅ Complete |
| asin | ASIN | 433-467 | ❌ Needs Update |

---

## 📞 Need Help?

- **JSON Validation:** https://jsonlint.com/
- **Repository Issues:** Contact repository maintainer
- **Documentation Questions:** Contact product owner
- **Technical Issues:** Reach out to development team lead

---

## 🎯 Expected Outcome

After implementation, the product will display in the portal with:

**Left Sidebar:**
- Product icon and name
- Current release version

**Center Panel:**
- Product details
- Release version and package version badges
- 5 clickable documentation links

**Right Sidebar:**
- Release history cards
- Each showing release version, date, package version, and release notes link

---

**File Format:** Markdown (.md)
**Last Updated:** February 17, 2026
**Version:** 1.0
