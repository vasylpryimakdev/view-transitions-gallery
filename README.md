# View Transitions Gallery

A modern web animation demo showcasing the CSS View Transitions API with a beautiful image gallery that smoothly transitions between grid and detail views.

## 🚀 Live Demo

👉 [https://vasylpryimakdev.github.io/view-transitions-gallery/](https://vasylpryimakdev.github.io/view-transitions-gallery/)

## Features

- **Smooth View Transitions**: Utilizes the native CSS View Transitions API for seamless animations
- **Image Gallery**: Grid layout with thumbnail images that expand to detailed views
- **Responsive Design**: Works seamlessly across different screen sizes
- **Modern UI**: Dark theme with clean typography using Source Code Pro font
- **Accessibility**: Proper ARIA labels and keyboard navigation support
- **Fallback Support**: Gracefully degrades for browsers that don't support View Transitions

## Demo

The gallery displays a collection of artistic photographs with poetic titles. Click any image in the grid to see it expand with a smooth transition effect. The transition uses a clipping mask animation that reveals the full image from its thumbnail position.

## Technologies Used

- **HTML5**: Semantic markup structure
- **CSS3**: Modern styling with CSS custom properties and View Transitions
- **JavaScript (Vanilla)**: DOM manipulation and View Transitions API integration
- **Google Fonts**: Source Code Pro for typography
- **Normalize.css**: CSS reset for cross-browser consistency

## Browser Support

This demo uses the experimental CSS View Transitions API. Currently supported in:

- Chrome 111+
- Edge 111+
- Other Chromium-based browsers

For browsers without View Transitions support, the gallery still functions with basic state changes.

## File Structure

```
view-transitions/
  index.html          # Main HTML structure
  styles.css          # CSS styling and view transition animations
  script.js           # JavaScript for interactions and view transitions
  assets/             # Images and SVG icons
    img-*-th.jpg      # Thumbnail images
    img-*-lg.jpg      # Large images for detail view
    *.svg             # Icon assets
```

## How It Works

### View Transitions API

The core of the demo uses `document.startViewTransition()` to create smooth animations between DOM states:

```javascript
const transition = document.startViewTransition(() => {
  expandImage(item);
});
```

### Animation Logic

The transition uses a custom clip-path animation that:

1. Starts with a clip matching the thumbnail's position
2. Expands to reveal the full image
3. Includes a contrast filter effect for visual polish

### CSS View Transition Names

Elements are marked with `view-transition-name` properties to participate in the transition:

- Header: `view-transition-name: header`
- Root element participates via pseudo-elements

## Getting Started

1. Clone the repository

```bash
git clone https://github.com/vasylpryimakdev/view-transitions-gallery.git
cd view-transitions-gallery
```

2. Open `index.html` in a supported browser
3. Click on any image in the grid to see the transition effect

## Customization

### Adding New Images

To add new images to the gallery:

1. Add thumbnail and large image files to the `assets/` folder
2. Update the HTML in `index.html` with new grid items:

```html
<div class="grid-item" tabindex="0" data-large-image="./assets/img-new-lg.jpg">
  <img src="./assets/img-new-th.jpg" alt="" />
  <h3>New Image Title</h3>
</div>
```

### Modifying Transitions

The transition parameters can be adjusted in `script.js`:

- Duration (currently 300ms)
- Easing function (currently "ease-in")
- Clip-path animation values

### Styling Changes

Modify `styles.css` to customize:

- Colors and theme
- Typography
- Layout dimensions
- Animation effects
