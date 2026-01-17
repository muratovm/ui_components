# UI Components Style Guide

This project follows a "Cyber/Hacker" aesthetic characterized by deep dark backgrounds, neon accents, and glassmorphism.

## 1. Color Palette

### Backgrounds
- **Page Background**: `#0f172a` (Slate 900) to `#020617` (Slate 950).
- **Glass Panel**: `rgba(15, 23, 42, 0.6)` with `backdrop-filter: blur(12px)`.

### Text
- **Main**: `#e2e8f0` (Slate 200).
- **Muted**: `#94a3b8` (Slate 400).
- **Headings/Accents**: White `#ffffff` or Accent Color.

### Accents (Neon/Glow)
- **Primary (Sky)**: `#38bdf8` (Sky 400).
- **Success (Traffic/Matrix)**: `#34d399` (Emerald 400).
- **Danger (Critical)**: `#ef4444` (Red 500) or `#f87171` (Red 400).
- **Warning**: `#f97316` (Orange 500).

## 2. Typography

We use Monospace fonts to maintain the technical/terminal feel.
- **Font Family**: `'JetBrains Mono', 'Courier New', Courier, monospace`.
- **Weights**: Light (100) for large displays, Regular (400) for body, Bold (700) for headers.

## 3. Core Components

### Glass Panel
The fundamental container for all UI elements.
```css
.glass-panel {
    background: rgba(15, 23, 42, 0.6);
    backdrop-filter: blur(12px);
    -webkit-backdrop-filter: blur(12px);
    border: 1px solid rgba(255, 255, 255, 0.1);
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
}
```

### Glowing Text
Used for counters, headers, or critical status.
```css
.glow-text {
    text-shadow: 0 0 10px rgba(56, 189, 248, 0.5); /* Adjust color as needed */
}
```

### Action Buttons (`btn-icon`)
Simple textual or icon-based buttons that scale and glow on hover.
```css
.btn-icon {
    transition: all 0.2s cubic-bezier(0.4, 0, 0.2, 1);
}
.btn-icon:hover {
    transform: scale(1.1);
    color: #38bdf8; /* Accent */
    text-shadow: 0 0 8px rgba(56, 189, 248, 0.6);
}
.btn-icon:active {
    transform: scale(0.95);
}
```

### Custom Sliders
Minimalist sliders with glowing thumbs.
```css
input[type=range]::-webkit-slider-thumb {
    -webkit-appearance: none;
    height: 16px;
    width: 16px;
    border-radius: 50%;
    background: #38bdf8;
    box-shadow: 0 0 10px rgba(56, 189, 248, 0.5);
    margin-top: -6px;
}
input[type=range]::-webkit-slider-runnable-track {
    background: #334155;
    height: 4px;
    border-radius: 2px;
}
```

## 4. Atmospherics

### Ambient Background Glow
A large, blurred circle behind the main content to add depth.
```html
<div class="absolute inset-0 overflow-hidden pointer-events-none z-0">
    <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[600px] h-[600px] rounded-full bg-sky-500/10 blur-[100px]"></div>
</div>
```

### Scanlines (Optional)
For an extra retro/terminal effect.
```css
.scanlines {
    background: repeating-linear-gradient(
        to bottom,
        transparent 0%,
        rgba(0, 0, 0, 0.2) 50%,
        transparent 100%
    );
    background-size: 100% 4px;
}
```
