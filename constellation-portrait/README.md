# 🌌 Constellation Mesh Portrait Effect (Standalone Drop-in Package)

An interactive, high-performance **Constellation Mesh Portrait** component built with zero dependencies. Drop your high-resolution portrait into any website, React/Next.js app, Webflow embed, or portfolio with desktop cursor dispersion, mobile touch dragging, and tap shockwaves!

---

## 📁 Package Contents

```text
constellation-portrait/
│
├── single-file.html     # ⭐ 100% Self-contained single file (Copy & paste anywhere!)
├── index.html           # Modular component showcase with interactive controls
├── constellation.js     # Lightweight reusable JS engine (Zero dependencies)
├── portrait.jpg         # High-resolution portrait of Mohammed Maaz A
└── README.md            # Integration documentation
```

---

## 🛠️ How to Add It to Any Project

### Option A: Complete Single-File Embed (Easiest)

Copy the code from [`single-file.html`](./single-file.html) directly into your HTML page or embed block.

```html
<!-- Container -->
<div style="position: relative; width: 440px; height: 540px; max-width: 92vw; border-radius: 24px; overflow: hidden; background: #030a14; border: 1px solid rgba(88, 166, 255, 0.25); box-shadow: 0 24px 60px rgba(0,0,0,0.85);">
  <canvas id="constellationCanvas" style="width: 100%; height: 100%; display: block; cursor: crosshair; touch-action: none;"></canvas>
</div>
```

---

### Option B: React / Next.js Integration

```jsx
import { useEffect, useRef } from 'react';
import { ConstellationPortrait } from './constellation.js';

export default function Portrait() {
  const canvasRef = useRef(null);

  useEffect(() => {
    if (canvasRef.current) {
      const portrait = new ConstellationPortrait(canvasRef.current, {
        imageSrc: '/portrait.jpg',
        photoOpacity: 0.85,
        targetCount: 2600,
        hoverRadius: 145,
        meshDistance: 36,
        pixelDisplacement: 2.2
      });

      return () => portrait.destroy();
    }
  }, []);

  return (
    <div style={{ width: '440px', height: '540px', maxWidth: '92vw', position: 'relative' }}>
      <canvas ref={canvasRef} style={{ width: '100%', height: '100%' }} />
    </div>
  );
}
```

---

## 📱 Mobile, iPad & Desktop Features

- **Desktop Cursor Hover**: Moves and scatters pixel particles while weaving luminous constellation connection lines.
- **Mobile / Tablet Touch Drag**: Dragging across the face dynamically guides glowing particle streams.
- **Tap / Click Shockwave Burst**: Emits an explosive kinetic blast that snaps back via spring physics.
- **High-DPI Retina Optimization**: Automatically scales canvas coordinate space for crystal clear rendering.
