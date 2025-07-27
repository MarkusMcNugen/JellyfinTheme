# Jellyfin Ultimate Collection Theme

[![Jellyfin Badge](https://img.shields.io/badge/Jellyfin-10.10.x-00A4DA)](https://jellyfin.org/)

> A feature-rich custom theme for Jellyfin media server combining Ultrachromic's flexibility with enhanced visual elements, focused on creating an elegant and responsive media viewing experience.

## ✨ Features

- **Modern UI**: Clean, glassy interface with hover effects and animations
- **Responsive Design**: Optimized for desktop, tablet, and mobile devices
- **Custom Pause Screen**: Enhanced viewing experience with logos and plot details
- **Gradient Button Styling**: Elegant My Media section with gradient borders
- **Enhanced Media Details**: Better metadata display and provider icons
- **Backdrop Effects**: Improved background styling and animations
- **Accessibility Improvements**: Better focus states and touch-friendly elements

## 📋 Table of Contents

- [Overview](#overview)
- [Installation](#installation)
- [Required Plugins & Dependencies](#required-plugins--dependencies)
- [Customization](#customization)
- [Components](#components)
- [Troubleshooting](#troubleshooting)
- [Credits](#credits)
- [License](#license)

## 🔍 Overview

This theme combines several popular Jellyfin CSS frameworks and plugins into a cohesive experience. It's built on the Ultrachromic theme system by CTalvio with custom modifications for improved aesthetics and functionality.

The theme adds a modern touch with glassmorphism effects, custom animations, elegant styling for the My Media section, and an enhanced pause screen experience. It's designed to be responsive across different devices while maintaining performance.

## 📥 Installation

### Prerequisites

1. Jellyfin server (version 10.9.x - 10.10.x)
2. Administrative access to your Jellyfin instance

### Steps

1. Log in to your Jellyfin admin dashboard
2. Navigate to **Dashboard > General**
3. Scroll down to the **Branding** section
4. Paste the entire CSS content from the [theme file](paste.txt) into the **Custom CSS** field
5. Click **Save**
6. Refresh your browser to see the changes

The theme will be applied server-wide to all users. Individual users can override this by setting their own custom CSS in their profile settings.

## 🔌 Required Plugins & Dependencies

### Core Themes

- [Ultrachromic](https://github.com/CTalvio/Ultrachromic) - Main theme framework
- [Monochromic](https://github.com/CTalvio/Monochromic) - For backdrop hack support

### Plugin Enhancements

- [Jellyfin Icon Metadata](https://github.com/Druidblack/jellyfin-icon-metadata) - Displays provider icons instead of text links
- [Jellyfin Pause Screen](https://github.com/BobHasNoSoul/Jellyfin-PauseScreen) - Enhances the pause screen with media info

### Optional Compatible Plugins

- [Media Bar Plugin](https://github.com/IAmParadox27/jellyfin-plugin-media-bar) - For featured content bar
- [JellySkin](https://github.com/prayag17/JellySkin) - For additional styling options
- [Intro Skipper](https://github.com/ConfusedPolarBear/intro-skipper) - For detecting and skipping intros
- [Fanart](https://github.com/jellyfin/jellyfin-plugin-fanart) - For enhanced artwork

## ⚙️ Customization

### Accent Color

You can customize the accent color by modifying the following CSS variable in the theme:

```css
:root {
    --accent: 0, 164, 218;  /* Change to your preferred RGB color values */
}
```

### Rounding

Adjust the corner roundness throughout the interface:

```css
:root {
    --rounding: 12px;  /* Change to your preferred pixel value */
}
```

### Backdrop Styling

Customize how backdrop images appear:

```css
.backdropImage {
    filter: blur(18px) saturate(120%) contrast(120%) brightness(40%);
}
```

### Login Background

To set a custom login background, modify:

```css
#loginPage {
    background: url(https://your-image-url.jpg) !important;
}
```

### My Media Section Customization

The My Media section features gradient-bordered buttons that can be customized:

![My Media Section](https://raw.githubusercontent.com/MarkusMcNugen/JellyfinTheme/main/MyMediaSmall.png)

```css
/* Text Gradient Colors */
.section0 a.homeLibraryButton .homeLibraryText,
.section0 a.homeLibraryButton .homeLibraryIcon {
    background: linear-gradient(135deg, #00a4da 0%, #aa5cc3 100%);
    -webkit-background-clip: text;
    background-clip: text;
    -webkit-text-fill-color: transparent;
}
```

You can modify the gradient colors to match your preferred color scheme.

### Pause Screen Adjustments

The pause screen elements can be customized for position and appearance:

```css
/* Plot description styling */
#overlay-plot {
    top: 61% !important;
    max-width: 54% !important;
    /* Additional styling properties */
}

/* Logo styling */
#overlay-logo {
    max-width: 50vw !important;
    max-height: 23vh !important;
    /* Additional positioning properties */
}
```

Adjust the percentage and pixel values to fine-tune the positioning for your specific setup.

## 🧩 Components

### Theme Structure

The theme is composed of multiple modular components that work together to create a cohesive experience. Below is a breakdown of each section and its purpose:

1. **Core Imports**: Base styles and accent lists
2. **UI Layout**: Rounding, headers, login screen, fields
3. **Type/Color Scheme**: Dark theme with accent
4. **Title Page**: Banner and logo styling
5. **Progress Indicators**: Floating progress bars
6. **Effects**: Hover glow and glassmorphism
7. **External Additions**: Monochromic backdrop hack, plugin enhancements
8. **Custom Variables**: Accent colors and rounding
9. **Responsive Designs**: Mobile and tablet optimizations
10. **Pause Screen**: Custom media display when paused

## 🎨 CSS Structure Breakdown

### Core Ultrachromic Theme Imports

```css
/* ============================================================================
   CORE ULTRACHROMIC THEME IMPORTS (Required Order)
   Documentation: https://github.com/CTalvio/Ultrachromic
   ============================================================================ */
```

This section establishes the foundation by importing Ultrachromic components in their required order. It includes fixes, fonts, and the base styling that everything else builds upon. The order is crucial for proper functionality.

### UI Layout Components

```css
/* UI Layout Components */
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/rounding.css');
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/smallercast.css');
/* Additional layout imports... */
```

These imports define the appearance of different interface elements, including rounded corners, compact episode lists, transparent headers, minimalistic login screen, field styling, and corner indicators.

### Type/Color Scheme

```css
/* Type/Color Scheme (REQUIRED - choose one) */
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/type/dark_withaccent.css');
```

The dark theme with accent colors provides a sleek, modern look that's easier on the eyes for media consumption. It serves as the core color palette for the entire interface.

### Title Page and Progress Indicators

The title page styling creates banner-style layouts for media content pages with logo integration, while the progress indicators section provides floating progress bars that offer a clean, unobtrusive way to show media playback progress.

### Effects and External Additions

```css
/* Effects (should be last among Ultrachromic imports) */
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/effects/hoverglow.css');
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/effects/glassy.css');
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/effects/pan-animation.css');
```

These effects add hover glow animations, glassmorphism (frosted glass appearance), and smooth pan animations to create a more dynamic interface.

### Plugin Enhancements

```css
/* Metadata Provider Icons Plugin */
@import url("https://cdn.jsdelivr.net/gh/Druidblack/jellyfin-icon-metadata@main/public-icon.css");

/* Icon Replacements - Using Active Alternative to prayag17 */
@import url("https://cdn.jsdelivr.net/gh/ealap/jellyfin-icons/Sharp.css");
```

These sections enhance the visual presentation of metadata by replacing text-based provider links with recognizable icons and implementing the Sharp icon set for a consistent look.

### My Media Small Section Styling

```css
/* ============================================================================
   MY MEDIA SMALL SECTION STYLING
   ============================================================================ */
```

This custom section creates elegant gradient-bordered buttons for the My Media section with special hover effects:

- Uses a transparent background with gradient borders
- Implements text gradient effects that change on hover
- Centers the section content for balanced presentation
- Creates a cohesive look that draws attention to library categories

### Backdrop Styling

```css
/* ============================================================================
   BACKDROP STYLING
   ============================================================================ */
```

The backdrop section enhances background images with blur, saturation, and contrast adjustments, while implementing mobile-specific animations that create a subtle scrolling effect for a more dynamic experience.

### Pause Screen Styling

```css
/* ============================================================================
   PAUSE SCREEN STYLING (BobHasNoSoul)
   From: https://github.com/BobHasNoSoul/Jellyfin-PauseScreen
   ============================================================================ */
```

This integration creates an enhanced pause screen experience:

- Plot description appears in a stylized, blurred container with accent-colored border
- Media logo displays prominently with drop shadow effects
- Optional spinning disc animation (hidden in this implementation)
- Automatically appears when video is paused and disappears when resumed
- Responsive design that adapts to different screen sizes

## 🔧 Troubleshooting

### Theme Not Loading

If the theme doesn't load properly:

1. **Clear Browser Cache**: Clear your browser cache and reload
2. **Check CSS Syntax**: Ensure the CSS was pasted correctly without truncation
3. **Reverse Proxy Issues**: If using Nginx, add the following to your configuration:

```nginx
add_header Content-Security-Policy "default-src https: data: blob: http://image.tmdb.org; style-src 'self' 'unsafe-inline' https://cdn.jsdelivr.net/; script-src 'self' 'unsafe-inline' https://www.gstatic.com/cv/js/sender/v1/cast_sender.js https://www.youtube.com blob:; worker-src 'self' blob:; connect-src 'self'; object-src 'none'; frame-ancestors 'self'";
```

### Mobile Issues

For optimal mobile experience:

1. Enable **Backdrops** in Settings > Display
2. Check that the theme renders correctly on different screen sizes
3. For any display issues, report them for future updates

### Plugin Integration Issues

If metadata icons aren't displaying correctly:
1. Ensure the Metadata Provider Icons import is at the top of your custom CSS
2. Check that you have metadata providers enabled in your library settings
3. For local metadata providers like Stash and Shoko, update the CSS with your server address

### Pause Screen Not Working

If the pause screen doesn't appear:
1. Make sure the custom CSS is applied server-wide
2. Try clearing the browser cache and reloading
3. Verify there are no JavaScript errors in the browser console
4. Check that media has proper metadata (logos, descriptions) in your library

## 🙏 Credits

This theme builds upon the work of several talented developers:

- [CTalvio](https://github.com/CTalvio/Ultrachromic) - Ultrachromic theme framework
- [Druidblack](https://github.com/Druidblack/jellyfin-icon-metadata) - Metadata provider icons
- [ealap](https://github.com/ealap/jellyfin-icons) - Sharp icon replacement
- [BobHasNoSoul](https://github.com/BobHasNoSoul/Jellyfin-PauseScreen) - Pause screen implementation
- [prayag17](https://github.com/prayag17/JellySkin) - Inspiration for various elements

## 📜 License

This theme is provided as-is for personal use. Component licenses apply to their respective parts.

---

Last Updated: July 26, 2025  
Compatible with: Jellyfin 10.9.x - 10.10.x

For issues or updates, please refer to the original component repositories linked in the Credits section.
