# WordPress Content Converter

A powerful web tool that converts Google Docs content to WordPress block format with automatic detection of FAQ sections, buttons, tables, and more.

## 🚀 Features

- **📑 Automatic Table of Contents** - Generates Yoast SEO TOC from H2-H6 headings
- **❓ FAQ Detection** - Converts Q: A: format to Yoast FAQ blocks with schema markup
- **🔘 Smart Button Detection** - Detects [bracketed text] or action words like "Try Free"
- **📊 Table Support** - Adds "pricing-table" class automatically
- **📋 Nested Lists** - Full support with proper WordPress formatting
- **✨ Clean HTML Output** - Removes Google Docs styling and formatting

## 🎯 Live Demo

Visit: [Your GitHub Pages URL will be here]

## 📖 Usage

### Basic Conversion

1. **Upload File** - Export your Google Doc as .docx (File → Download → Microsoft Word)
2. **Or Paste HTML** - Copy content directly from Google Docs
3. **Click Convert** - Get instant WordPress block code
4. **Copy & Paste** - Use the WordPress Blocks tab to copy formatted code

### FAQ Format

The tool detects FAQ sections automatically:

```html
<h2>FAQ</h2>

<p>Q: What's your product? A: Our product helps businesses grow.</p>
<p>Q: How much does it cost? A: Starting at $10/month.</p>
```

**Output:** Yoast FAQ blocks with proper schema markup

### Button Format

Two ways to create buttons:

1. **Brackets:** `[Try Free Trial]`
2. **Action Links:** Links containing "Try", "Free", "Get Started", etc.

### List Format

Supports both ordered and unordered lists with nesting:

```html
<ol>
  <li>First item</li>
  <li>Second item
    <ul>
      <li>Nested item</li>
    </ul>
  </li>
</ol>
```

## 🛠️ Technical Details

### Built With

- **Vanilla JavaScript** - No frameworks required
- **Mammoth.js** - .docx to HTML conversion
- **DOMParser API** - HTML parsing and manipulation

### WordPress Compatibility

Generates proper WordPress block format:

- `<!-- wp:paragraph -->` for text
- `<!-- wp:list {"ordered":true} -->` for lists
- `<!-- wp:yoast/faq-block -->` for FAQs
- `<!-- wp:yoast-seo/table-of-contents -->` for TOC
- `<!-- wp:buttons -->` for CTAs

## 📦 Installation

### For GitHub Pages

1. Fork this repository
2. Go to Settings → Pages
3. Select "main" branch
4. Your site will be live at `https://[username].github.io/wordpress-converter/`

### For Local Development

```bash
# Clone the repository
git clone https://github.com/[username]/wordpress-converter.git

# Open in browser
cd wordpress-converter
open index.html
```

No build process or dependencies required!

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

MIT License - feel free to use this in your projects!

## 🐛 Issues

Found a bug? Please [open an issue](https://github.com/[username]/wordpress-converter/issues) with:
- Description of the problem
- Steps to reproduce
- Expected vs actual behavior
- Sample content that causes the issue

## 🎨 Customization

### Change Colors

Edit the CSS gradient in the `<style>` section:

```css
background: linear-gradient(135deg, #f75a1b 0%, #ff8c42 100%);
```

### Modify Detection Patterns

Edit the FAQ detection regex around line 830:

```javascript
/Q:\s*(.+?)\s+A:\s*(.+?)(?=\s+Q:|$)/gis
```

## 📚 Resources

- [WordPress Block Editor Handbook](https://developer.wordpress.org/block-editor/)
- [Yoast SEO Blocks](https://yoast.com/wordpress/plugins/seo/)
- [Mammoth.js Documentation](https://github.com/mwilliamson/mammoth.js)

## 💡 Tips

- Use consistent heading hierarchy (H2, H3, H4...)
- Keep FAQ answers concise for better schema
- Test buttons before pasting into WordPress
- Use Chrome DevTools to inspect generated blocks

---

Made with ❤️ for WordPress content creators
