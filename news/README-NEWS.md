# Mach50 News Management System

## Overview
The Mach50 website now features a dynamic news swiper that loads content from a JSON file. This makes it easy to update news without editing the HTML code.

## How It Works

The news swiper automatically:
- Loads news articles from `news.json`
- Displays them in a scrolling ticker at the bottom of the video
- Loops infinitely for continuous display
- Pauses on hover for easy reading

## Updating News

### Method 1: Edit the JSON File Directly

1. Open `news.json` in any text editor
2. Add, edit, or remove news items
3. Save the file
4. Refresh the website to see changes

### JSON Structure

Each news item has the following fields:

```json
{
    "id": 1,                    // Unique identifier (number)
    "title": "Article Title",   // The headline (string)
    "date": "2025-11-21",      // Publication date (YYYY-MM-DD format)
    "url": "/news/article",    // Link to full article (string)
    "category": "News"         // Category label (string)
}
```

### Example: Adding a New News Item

```json
[
    {
        "id": 6,
        "title": "Mach50 Expands to European Market",
        "date": "2025-11-25",
        "url": "/news/european-expansion",
        "category": "News"
    },
    // ... existing items
]
```

### Best Practices

1. **Keep it Recent**: Display your 5-7 most recent news items
2. **Consistent Format**: Use the same date format (YYYY-MM-DD)
3. **Clear Titles**: Keep headlines under 80 characters for best display
4. **Valid JSON**: Always validate your JSON (use jsonlint.com if needed)
5. **Order**: List items from newest to oldest

## File Locations

```
/
├── index.html          # Main website file
├── news.json          # News data file (edit this to update news)
└── README-NEWS.md     # This file
```

## Troubleshooting

### News Not Loading?

1. **Check the console**: Open browser DevTools (F12) and look for errors
2. **Verify JSON syntax**: Make sure your JSON is valid
3. **Check file path**: Ensure `news.json` is in the same directory as `index.html`
4. **CORS issues**: If testing locally, use a local server (not file://)

### JSON Syntax Errors

Common mistakes:
- Missing commas between items
- Trailing comma after last item (remove it)
- Unescaped quotes in text (use \" for quotes inside strings)
- Missing closing brackets

### Testing Locally

To test locally, use a simple HTTP server:

```bash
# Using Python 3
python -m http.server 8000

# Using Node.js
npx serve

# Using PHP
php -S localhost:8000
```

Then visit: `http://localhost:8000`

## Advanced: API Integration

To connect to a backend API instead of using a JSON file:

1. Open `index.html`
2. Find the `loadNews()` function
3. Change the fetch URL from `'news.json'` to your API endpoint:

```javascript
const response = await fetch('https://api.mach50.com/news');
```

## Support

For issues or questions, contact your development team.

---

**Last Updated**: November 2025
