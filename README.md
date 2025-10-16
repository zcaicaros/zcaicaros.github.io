# Academic Portfolio Website Template

A clean, responsive academic portfolio website with interactive paper filtering and visitor tracking.

## Features

- 📱 **Responsive Design** - Works on desktop, tablet, and mobile devices
- 🌓 **Dark/Light Mode** - Toggle between themes with a single click
- 🏷️ **Interactive Paper Filtering** - Filter publications by research areas with clickable tags
- ⭐ **GitHub Star Badges** - Automatic display of GitHub repository star counts with fancy animations
- 📊 **Visitor Counter** - Track visitors from different countries
- 🎨 **Modern UI** - Built with Tailwind CSS for a clean, professional look
- 🔗 **Social Integration** - Links to Google Scholar, GitHub, LinkedIn

## Quick Start

### 1. Fork or Clone This Repository

```bash
git clone https://github.com/zcaicaros/zcaicaros.github.io.git
cd zcaicaros.github.io
```

### 2. Customize Your Information

Edit `index.html` and update the following sections:

#### Personal Information
- Line 14: Update meta description
- Line 19: Update page title
- Lines 551-553: Update name (English and Chinese)
- Lines 558-597: Update "About Me" section
- Lines 609-610: Update email address

#### Education & Experience
- Lines 582-587: Update education history
- Lines 643-648: Update news items
- Lines 655-658: Update awards
- Lines 664-668: Update work experience

#### Social Links
- Lines 614-622: Update Google Scholar, GitHub, LinkedIn URLs

#### Profile Picture
- Replace `portrait.jpg` with your own photo (150x150px recommended)

### 3. Add Your Publications

Publications are organized in three sections:

#### Preprints (Lines 686-715)
```html
<div class="flex flex-wrap mb-8 paper-item">
    <div class="w-full md:w-4/4 px-3">
    <h3 class="text-l font-bold mb-1 paper-title">
        <span class="type-tag tag-cop" data-tag="cop">[COP]</span>
        <span class="type-tag tag-llm" data-tag="llm">[LLM]</span> 
        Your Paper Title
    </h3>
    <p class="text-gray-700 mb-1">
        Author 1, 
        <strong>Your Name</strong>, 
        Author 3
    </p>
    <p class="gray-blue-500 mb-1">
        arXiv preprint, 2025
    </p>
    <p>
        <a class="anchor-link text-blue-500" href="URL">paper</a>
        /
        <a class="anchor-link text-blue-500" href="URL">code</a>
        <a class="github-star loading" href="https://github.com/username/repo" target="_blank" rel="noopener" data-repo="username/repo">
            <span class="github-star-label">stars</span>
            <span class="github-star-count">-</span>
        </a>
    </p>
    </div>
</div>
```

#### Conference Papers (Starting Line 725)
Follow the same structure as preprints.

#### Journal Articles (Starting Line 986)
Follow the same structure as preprints.

### 4. Add GitHub Star Badges

For papers with GitHub repositories, you can add fancy star count badges:

```html
<a class="github-star loading" href="https://github.com/username/repo" target="_blank" rel="noopener" data-repo="username/repo">
    <span class="github-star-label">stars</span>
    <span class="github-star-count">-</span>
</a>
```

**Features:**
- ⭐ **Automatic Star Fetching** - Fetches real-time star counts from GitHub API
- 🎨 **Fancy Animations** - Gradient backgrounds, shimmer effects, and hover animations
- 🌙 **Theme Support** - Automatically adapts to light/dark mode
- 📱 **Responsive Design** - Scales appropriately on mobile devices
- 🔄 **Fallback Data** - Shows preset values if API fails
- 🚀 **Dual API Strategy** - Tries direct API first, then CORS proxy

**How it works:**
1. The badge automatically fetches star counts when the page loads
2. Uses GitHub API with CORS proxy for reliability
3. Displays formatted numbers (e.g., 1.2k for 1200 stars)
4. Shows loading animation while fetching
5. Falls back to preset values if API fails

**Customization:**
- Star counts are automatically fetched from GitHub
- Fallback values can be updated in the `fallbackStars` object (around line 1988)
- Badge styling can be customized in the CSS section (lines 446-665)

### 5. Configure Research Area Tags

Available tags (defined in CSS):
- `[COP]` - Combinatorial Optimization Problems (Blue)
- `[JSSP]` - Job Shop Scheduling Problem (Green)
- `[DRL]` - Deep Reinforcement Learning (Orange)
- `[MARL]` - Multi-Agent Reinforcement Learning (Red)
- `[NLP]` - Natural Language Processing (Purple)
- `[VRP]` - Vehicle Routing Problem (Pink)
- `[LLM]` - Large Language Models (Yellow)

To add a new tag type:
1. Add CSS color definition (around line 354-410)
2. Add to `getTagColor()` function (around line 1390)
3. Add to `getTagDisplayName()` function (around line 1374)

### 6. Set Up Visitor Counter

The template uses Flag Counter. To use your own counter:

1. Visit https://flagcounter.com/
2. Customize your counter
3. Get the embed code
4. Replace the code at line 630

### 7. Deploy to GitHub Pages

1. Push changes to GitHub:
```bash
git add .
git commit -m "Customize portfolio"
git push
```

2. Enable GitHub Pages:
   - Go to repository Settings
   - Navigate to Pages section
   - Select "main" branch as source
   - Save

3. Your site will be live at: `https://yourusername.github.io`

## Paper Filtering System

### How It Works

Users can filter papers by clicking on research area tags:

1. **Initial State**: All tags are highlighted, all papers are shown
2. **First Click**: Click any tag to show only papers with that tag
3. **Multi-Select**: Continue clicking tags to add them to the filter
4. **Deselect**: Click a highlighted tag again to remove it from the filter
5. **Reset**: If all tags are deselected, all papers are shown again

### Filter Logic

The filtering uses OR logic: papers are shown if they contain ANY of the selected tags.

## Theme Toggle

The dark/light mode toggle:
- Automatically saves user preference in localStorage
- Smoothly transitions between themes
- Updates all color variables defined in CSS custom properties

## Customization Tips

### Colors
- Theme colors are defined in CSS custom properties (lines 56-74)
- Light theme: `--bg-primary`, `--bg-secondary`, etc.
- Dark theme: `[data-theme="dark"]` section

### Fonts
- Default font: Open Sans (loaded from Google Fonts)
- Change at line 29 and line 87

### Layout Width
- Desktop: 50% width (defined at lines 128-133)
- Mobile/Tablet: 100% width (lines 112-125)
- Adjust these values to change content width

### Container Styling
- Main container: Lines 512-638
- Sections use flexbox for responsive layout
- Tailwind CSS classes for spacing and alignment

## File Structure

```
.
├── index.html          # Main HTML file
├── portrait.jpg        # Profile picture
├── Academic_CV.pdf     # (Optional) CV file
└── README.md          # This file
```

## Technologies Used

- HTML5
- CSS3 (with CSS Custom Properties)
- JavaScript (Vanilla)
- Tailwind CSS (CDN)
- Font Awesome Icons
- Google Fonts
- GitHub API (for star counts)
- CORS Proxy (allorigins.win)

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers

## License

Feel free to use this template for your own academic portfolio. Attribution appreciated but not required.

## Credits

Original template by Cong Zhang ([@zcaicaros](https://github.com/zcaicaros))

## Support

For issues or questions:
1. Check existing GitHub issues
2. Open a new issue with detailed description
3. Contact: cong.zhang92@gmail.com

## Contributing

Contributions are welcome! Please:
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

---

**Note**: Remember to update the visitor counter code and social links with your own information before deploying!
