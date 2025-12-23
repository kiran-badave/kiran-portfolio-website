# 📊 Data Management Guide

This guide explains how to manage your portfolio content using the centralized data system.

## 🎯 Overview

All portfolio content is stored in a single file: **`data.js`**

This ensures:
- ✅ **Consistency**: Same data across portfolio and CV
- ✅ **Easy Updates**: Change once, update everywhere
- ✅ **No Duplication**: Single source of truth
- ✅ **Version Control**: Track all changes in one place

## 📁 Data Structure

The `data.js` file contains the following sections:

### 1. Personal Information
```javascript
personal: {
    name: "Your Name",
    title: "Your Job Title",
    subtitle: "Your Subtitle",
    location: "City, State, Country",
    email: "your.email@example.com",
    phone: ["+1 234 567 8900", "+1 098 765 4321"],
    linkedin: "https://www.linkedin.com/in/yourprofile",
    linkedinDisplay: "linkedin.com/in/yourprofile",
    address: "Full Address",
    profileImage: "assets/profile_picture.png"
}
```

### 2. Professional Summary
```javascript
summary: "Your professional summary text here..."
```

### 3. Statistics
```javascript
stats: [
    { number: 7, label: "Years Experience" },
    { number: 50, label: "Projects Completed" },
    { number: 15, label: "Technologies" }
]
```

### 4. Work Experience
```javascript
experience: [
    {
        company: "Company Name",
        location: "City, Country",
        role: "Your Role",
        duration: "Start Date - End Date",
        durationYears: "X years",
        logo: "assets/images/company-logo.png",
        responsibilities: [
            "Responsibility 1",
            "Responsibility 2"
        ],
        technologies: {
            "Category 1": "Tech stack 1",
            "Category 2": "Tech stack 2"
        }
    }
]
```

### 5. Skills
```javascript
skills: [
    {
        icon: "💻",
        title: "Skill Category",
        description: "Description of skills"
    }
]
```

### 6. Education
```javascript
education: [
    {
        icon: "🎓",
        degree: "Degree Name",
        field: "Field of Study",
        institution: "University Name",
        duration: "Start - End",
        logo: "assets/images/university-logo.png"
    }
]
```

## 🔄 How to Update Content

### Step 1: Open data.js
```bash
# Using VS Code
code data.js

# Or any text editor
nano data.js
```

### Step 2: Find the Section to Update
Use Ctrl+F (Cmd+F on Mac) to search for the section you want to update.

### Step 3: Make Your Changes
Edit the values within the quotes or arrays.

### Step 4: Save the File
Press Ctrl+S (Cmd+S on Mac) to save.

### Step 5: Refresh Your Browser
The changes will automatically appear in:
- Main portfolio (`index.html`)
- Printable CV (`cv-print.html`)

## 📝 Common Update Scenarios

### Updating Email Address
```javascript
personal: {
    email: "newemail@example.com",  // ← Change here
    // ... rest of personal info
}
```

### Adding New Work Experience
```javascript
experience: [
    {
        company: "New Company",
        location: "New City, Country",
        role: "New Role",
        duration: "Jan 2024 - Present",
        durationYears: "1 year",
        logo: "assets/images/new-company-logo.png",
        responsibilities: [
            "New responsibility 1",
            "New responsibility 2"
        ],
        technologies: {
            "Front-end": "React, TypeScript",
            "Back-end": "Node.js, Express"
        }
    },
    // ... existing experiences below
]
```

### Updating Statistics
```javascript
stats: [
    { number: 8, label: "Years Experience" },  // ← Updated from 7 to 8
    { number: 60, label: "Projects Completed" },  // ← Updated from 50 to 60
    { number: 20, label: "Technologies" }  // ← Updated from 15 to 20
]
```

### Adding New Skill
```javascript
skills: [
    {
        icon: "🚀",
        title: "New Skill Category",
        description: "Description of new skills"
    },
    // ... existing skills
]
```

### Updating Profile Picture
1. Add new image to `assets/` folder
2. Update the path:
```javascript
personal: {
    profileImage: "assets/new_profile_picture.png"  // ← Update path
}
```

## ⚠️ Important Notes

### 1. Maintain JSON Structure
- Keep all commas, brackets, and quotes
- Don't remove any required fields
- Use proper JavaScript syntax

### 2. HTML in Text
You can use HTML tags in text fields:
```javascript
responsibilities: [
    "Developed <strong>React</strong> applications"  // Bold text
]
```

### 3. Special Characters
Escape special characters:
```javascript
summary: "I'm a developer"  // Use \' for apostrophes if needed
```

### 4. Arrays
Maintain array structure with square brackets:
```javascript
phone: ["+1 234 567 8900", "+1 098 765 4321"]  // Multiple items
```

## 🧪 Testing Your Changes

After updating `data.js`:

1. **Open in Browser**
   ```bash
   open index.html
   ```

2. **Check Portfolio**
   - Verify all sections display correctly
   - Check for any missing data

3. **Check Printable CV**
   ```bash
   open cv-print.html
   ```
   - Verify CV formatting
   - Test print preview (Ctrl/Cmd + P)

4. **Validate JavaScript**
   - Open browser console (F12)
   - Check for any errors

## 🐛 Troubleshooting

### Data Not Showing?
1. Check browser console for errors (F12)
2. Verify JSON syntax in `data.js`
3. Ensure all quotes and commas are correct
4. Hard refresh browser (Ctrl+Shift+R)

### Syntax Error?
Common issues:
- Missing comma between items
- Unclosed quotes or brackets
- Extra comma at end of array

### Profile Picture Not Loading?
1. Verify image exists in `assets/` folder
2. Check file path is correct
3. Ensure image format is supported (PNG, JPG, JPEG)

## 📋 Validation Checklist

Before deploying changes:

- [ ] All personal information is current
- [ ] Work experience is up to date
- [ ] Skills reflect current expertise
- [ ] Education information is accurate
- [ ] Contact details are correct
- [ ] Profile picture loads properly
- [ ] No JavaScript errors in console
- [ ] Portfolio displays correctly
- [ ] Printable CV formats properly
- [ ] All links work correctly

## 🔐 Version Control

Track your changes with Git:

```bash
# After updating data.js
git add data.js
git commit -m "Update: [describe your changes]"
git push origin main
```

Examples:
```bash
git commit -m "Update: Added new work experience at Company X"
git commit -m "Update: Changed email address"
git commit -m "Update: Updated skills section"
```

## 💡 Best Practices

1. **Regular Updates**: Keep your data current
2. **Backup**: Commit changes to Git regularly
3. **Test Locally**: Always test before deploying
4. **Consistent Formatting**: Maintain consistent style
5. **Professional Tone**: Keep content professional
6. **Proofread**: Check for typos and errors

## 📞 Need Help?

If you encounter issues:
1. Check this guide
2. Review the example data in `data.js`
3. Check browser console for errors
4. Validate JSON syntax online
5. Refer to README.md for more information

---

**Remember**: `data.js` is your single source of truth. All changes made here automatically reflect in both your portfolio website and printable CV! 🎉