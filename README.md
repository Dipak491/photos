# 📷 Dipak · Photos

A beautiful, private photo gallery hosted directly on GitHub Pages. This is a minimal, elegant portfolio gallery with password protection and zero backend dependencies.

![License](https://img.shields.io/badge/license-MIT-blue)
![Built with](https://img.shields.io/badge/built%20with-HTML%20%7C%20CSS%20%7C%20JS-blueviolet)

## ✨ Features

- 🔒 **Password Protected** – SHA-256 hashed authentication, no plain text passwords
- 🎨 **Modern Design** – Responsive masonry layout with smooth animations
- ⚡ **Zero Backend** – Fully static, runs on GitHub Pages
- 🖼️ **Auto-Loading** – Photos sync automatically from GitHub repo
- 🌓 **Dark Theme** – Elegant, easy on the eyes with warm accents
- 📱 **Responsive** – Works beautifully on desktop, tablet, and mobile
- 🎬 **Smooth Interactions** – Hover effects, lightbox gallery, keyboard navigation
- 💾 **Auto-Login** – Session persistence for 7 days
- 🔐 **Client-Side Security** – No backend, all hashing happens in your browser

## 🚀 Getting Started

### Prerequisites
- A GitHub account
- Git installed on your computer

### Setup Instructions

1. **Clone or fork this repository:**
   ```bash
   git clone https://github.com/Dipak491/photos.git
   cd photos
   ```

2. **Create a `photos/` folder** in your repository:
   ```bash
   mkdir photos
   ```

3. **Add your photos** to the `photos/` folder (supports: `jpg`, `jpeg`, `png`, `gif`, `webp`, `avif`)

4. **Push to GitHub:**
   ```bash
   git add .
   git commit -m "Add initial photos"
   git push origin main
   ```

5. **Enable GitHub Pages:**
   - Go to your repository settings
   - Scroll to "GitHub Pages"
   - Set source to `main` branch
   - Your gallery is now live! 🎉

## 🔐 Setting Your Password

The default password is `Dipak@1234`. To change it:

1. **Open your gallery in a browser** (e.g., `https://yourusername.github.io/photos`)
2. **Open the browser's developer console** (`F12` or `Ctrl+Shift+I`)
3. **Type this command:**
   ```javascript
   generateHash('YourNewPassword')
   ```
4. **Copy the hash** that appears in the console
5. **Edit `index.html`** and find this line:
   ```javascript
   const PASSWORD_HASH = 'b8bc670dcee5ebc0350e8a5145e7b6963f475e2ef12a7672b7de64e86528494f';
   ```
6. **Replace the hash value** with your new one
7. **Push the changes:**
   ```bash
   git add index.html
   git commit -m "Update gallery password"
   git push origin main
   ```

## 📸 Adding Photos

1. **Add image files** to the `photos/` folder
2. **Supported formats:** JPG, JPEG, PNG, GIF, WebP, AVIF
3. **Commit and push:**
   ```bash
   git add photos/
   git commit -m "Add new photos"
   git push origin main
   ```
4. **Your gallery updates automatically** within seconds!

### Tips for Best Results
- Use **descriptive filenames** – they appear as image captions (underscores and hyphens become spaces)
- **Optimize images** – keep file sizes reasonable for faster loading
- **Consistent dimensions** – the masonry layout works best with similar aspect ratios

## 🎮 How to Use

### Desktop
- **Click any photo** to open the lightbox
- **Use arrow buttons** or **← →** keys to navigate
- **Press `Escape`** or click the **✕** to close
- **Click the Lock button** to logout

### Mobile
- **Tap any photo** to view fullscreen
- **Swipe or use arrows** to navigate (on supported devices)
- **Tap ✕** to close or outside the image

### Login
- Enter your password and press **Enter** or click **Unlock Gallery →**
- You'll stay logged in for 7 days automatically
- Click **🔒 Lock** anytime to logout

## 🛠️ Customization

### Edit Gallery Text

In `index.html`, find the hero section and update:

```html
<h1>My <em>Moments</em><br>& Memories</h1>
<p>A collection of photos from life's beautiful chapters.</p>
```

### Change Colors

The color scheme uses CSS variables. Edit the `:root` section in `index.html`:

```css
:root {
  --bg: #0f0f0f;           /* Background */
  --surface: #1a1a1a;      /* Card background */
  --text: #f0ece4;         /* Main text */
  --accent: #c9a96e;       /* Accent color */
  /* ... */
}
```

### Adjust Layout

Change the number of columns:

```css
.masonry { columns: 4; }        /* Desktop: 4 columns */
@media (max-width: 1100px) { .masonry { columns: 3; } }  /* Tablet: 3 columns */
@media (max-width: 700px)  { .masonry { columns: 2; } }  /* Mobile: 2 columns */
@media (max-width: 400px)  { .masonry { columns: 1; } }  /* Small: 1 column */
```

## 📋 Configuration

All configuration is at the top of the `<script>` section in `index.html`:

```javascript
const GITHUB_USER   = 'Dipak491';      // Your GitHub username
const GITHUB_REPO   = 'photos';        // Your repo name
const PHOTOS_FOLDER = 'photos';        // Folder with photos
const BRANCH        = 'main';          // Git branch to use
const PASSWORD_HASH = '...';           // Your password hash
const SESSION_DAYS  = 7;               // Login session duration
```

## 🔒 Security & Privacy

- **Passwords are hashed** using SHA-256 in your browser – never sent anywhere
- **All processing is client-side** – no backend or external services
- **Your photos are public** (via GitHub raw content URL), so don't use private photos
- **Session tokens** are stored in browser localStorage for 7 days

## 📱 Browser Support

- ✅ Chrome / Edge 90+
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ Mobile browsers (iOS Safari, Chrome Mobile)

## 🎨 Design Features

- **Masonry Layout** – Photos adapt to different screen sizes
- **Smooth Animations** – Fade-in effects, hover scales, zoom transitions
- **Gradient Overlays** – Photo names appear on hover
- **Modern Fonts** – Playfair Display & DM Sans for elegance
- **Backdrop Blur** – Frosted glass effects on sticky header

## 🐛 Troubleshooting

### Photos not showing?
- Ensure the `photos/` folder exists in your repo
- Check that your repo is **public**
- Verify filenames have valid image extensions
- Open the browser console (`F12`) to see error messages

### Password not working?
- Make sure you copied the full hash from `generateHash()`
- Clear your browser cache and reload
- Check that `PASSWORD_HASH` value is exactly right in `index.html`

### Gallery not loading?
- GitHub Pages can take up to 5 minutes to deploy
- Try a hard refresh (`Ctrl+Shift+R` or `Cmd+Shift+R`)
- Check repository settings → Pages → is it enabled?

### Session issues?
- Clear browser localStorage: Open console, type `localStorage.clear()`
- Session automatically expires after 7 days
- Click the **Lock** button to logout manually

## 📝 License

MIT License – feel free to use this as a template for your own gallery!

## 🙌 Credits

Built with ♥ by [Dipak Narkhede](https://github.com/Dipak491)

---

**Happy sharing! 📸**

Need help? Check the [GitHub Issues](https://github.com/Dipak491/photos/issues) or create a new one.
