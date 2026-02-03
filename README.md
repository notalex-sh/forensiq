# FORENSIQ

A browser-based image forensics and enhancement tool.

by notalex.sh

## Features

### Image Enhancement

#### Adjustments
| Control | Description |
|---------|-------------|
| **Brightness** | Shifts all pixel values lighter or darker (-100 to +100) |
| **Contrast** | Increases or decreases the difference between light and dark areas |
| **Saturation** | Controls color intensity. Negative values desaturate toward grayscale |
| **Sharpen** | Enhances edges using an unsharp mask kernel |
| **Gamma** | Non-linear brightness adjustment (0.5 to 2.0) |

#### Color Balance
| Control | Description |
|---------|-------------|
| **Red** | Adjust red channel intensity (-50 to +50) |
| **Green** | Adjust green channel intensity (-50 to +50) |
| **Blue** | Adjust blue channel intensity (-50 to +50) |

#### Curves
Interactive curves editor for precise tonal adjustments. Click to add control points, drag to adjust.

#### Auto-Enhancement Presets
| Preset | Description |
|--------|-------------|
| **Auto** | Balanced enhancement for general use |
| **Low Light** | Brightens dark images |
| **Forensic** | High contrast, desaturated for detail analysis |
| **Clarity** | Sharpens and enhances mid-tones |
| **Vivid** | Boosts colors and contrast |
| **Muted** | Reduces saturation and contrast |

### Transform

| Control | Description |
|---------|-------------|
| **Zoom** | Scale the image from 10% to 500% |
| **Rotate** | Rotate the image -180° to +180° |
| **90° CW/CCW** | Quick 90-degree rotation buttons |
| **Flip H/V** | Mirror the image horizontally or vertically |
| **Crop Mode** | Click to enter, drag to select area, click again to apply |

**Panning**: Hold `SPACE` and drag to pan around when zoomed in. Mouse wheel also zooms.

### Filters

| Filter | Description |
|--------|-------------|
| **Gray** | Converts to grayscale using luminance weights |
| **Invert** | Inverts all color values (negative effect) |
| **Edges** | Sobel edge detection - highlights boundaries |
| **Emboss** | Creates a 3D raised effect |
| **Equalize** | Histogram equalization - improves contrast distribution |
| **Denoise** | Median filter - reduces noise while preserving edges |

### Magnifier

Hover over the image to see a magnified view (hidden in Annotate tab).

| Option | Description |
|--------|-------------|
| **Zoom** | Magnification level (2-10x) |
| **Size** | Magnifier window size in pixels |
| **Enhancement** | Apply processing to magnified area only |
| **Pixel Info** | Show RGB/HEX values at cursor |
| **Crosshair** | Show center crosshair |
| **Grid** | Show pixel grid overlay |

### Annotate

Draw annotations over the image for marking areas of interest.

| Tool | Description |
|------|-------------|
| **Rect** | Draw rectangles (outline or filled) |
| **Circle** | Draw circles (outline or filled) |
| **Arrow** | Draw arrows pointing to areas |
| **Line** | Draw straight lines |
| **Text** | Place text labels |
| **Blur** | Blur selected rectangular regions (with gradient edges) |
| **Color Picker** | Sample colors from the image |

**Settings**:
- **Color**: Annotation color
- **Width**: Line thickness
- **Fill**: Outline only or filled shapes

Click an active tool again to deselect it.

#### Watermark
Add text watermarks to images with customizable:
- Text content
- Size and opacity
- Color and position (corners, center, or tiled)
- Rotation angle

#### Caption
Add caption bars to images with customizable:
- Text content
- Bar height and font size
- Background and text colors
- Position (top or bottom)

### Metadata

Displays image metadata including:
- File information (name, size, type, dimensions)
- SHA-256 file hash (click to copy)
- EXIF data (camera, settings, date)
- GPS coordinates with map link (if available)

### Histogram

Real-time RGB histogram display showing the distribution of pixel values in the current image.

## Keyboard Shortcuts

| Key | Action |
|-----|--------|
| `A` | Toggle annotation visibility |
| `M` | Toggle magnifier |
| `P` | Activate color picker |
| `Ctrl+Z` | Undo last annotation/blur |
| `Ctrl+V` | Paste image from clipboard |
| `Space` + drag | Pan when zoomed |
| Mouse wheel | Zoom in/out |

## Import/Export

- **Open**: Load image from file
- **Paste**: Paste image from clipboard (Ctrl+V or button)
- **Copy**: Copy current view to clipboard
- **Export**: Download as PNG (includes annotations and overlays)
- **Reset**: Clear image and all settings

## Header Controls

| Control | Description |
|---------|-------------|
| **Annotations** | Toggle annotation layer visibility |
| **Magnifier** | Toggle magnifier on hover |
| **Color Picker** | Toggle color picker mode |
| **Sidebar** | Collapse/expand the control panel |

## File Structure

```
forensiq/
├── api/
│   └── index.js        # API endpoint (Vercel)
├── public/
│   ├── js/
│   │   ├── app.js          # Main application
│   │   ├── annotations.js  # Drawing tools
│   │   ├── curves.js       # Curves editor
│   │   ├── enhancements.js # Image adjustments
│   │   ├── filters.js      # Image filters
│   │   ├── histogram.js    # Histogram display
│   │   ├── magnifier.js    # Magnifier tool
│   │   ├── transform.js    # Zoom/rotate/crop
│   │   └── utils.js        # Utilities
│   ├── index.html
│   └── styles.css
└── README.md
```

## Browser Support

Works in modern browsers with ES6 module support (Chrome, Firefox, Safari, Edge).

## License

MIT
