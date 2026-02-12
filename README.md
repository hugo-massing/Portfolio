# Portfolio - Hugo Massing

A high-performance, dark-themed developer portfolio designed with a focus on **typography, motion, and immersive user experience**. This project serves as a digital garden and professional showcase for a Frontend Engineer specializing in React and Creative Development.

![Portfolio Preview](bettershot_1770291803100.png)

## 🛠️ Technical Stack

* **Framework:** React / Next.js.
* **Styling:** Tailwind CSS.
* **Typography:** Syne (Display) & Space Grotesk (Body).
* **Icons:** Lucide React.
* **Animations:** CSS Keyframes & SVG Filters.

---

## 🚀 Key Features

* **Grain Texture Overlay:** A custom SVG filter overlaying the UI to provide a tactile, "analog" feel.
* **Dynamic Mouse Spotlight:** A radial gradient that follows the user's cursor, creating a deep, interactive lighting effect.
* **Infinite Marquee:** High-speed, bi-directional scrolling skill banners using CSS hardware acceleration.
* **Interactive Project Grid:** Hover-aware list items that dim non-active projects to focus user attention.
* **Adaptive Layout:** Fully responsive grid system built for everything from mobile devices to ultra-wide displays.

---

## 🧠 Challenges & Solutions

### 1. Performance vs. Visual Fidelity
**Issue:** High-resolution grain filters and complex radial gradients often cause "paint flashing" and high CPU usage during scrolling.
**Solution:** I implemented the grain texture using a static, repeating SVG `feTurbulence` filter as a fixed background with `pointer-events: none`. By using CSS-only animations for the marquees, I kept the frame rate smooth even on lower-end devices.

### 2. Modern Navigation Dynamics
**Issue:** Ensuring the navigation bar remains readable while moving across various sections with different background intensities.
**Solution:** I utilized `mix-blend-mode: difference` on the navigation container. This ensures that the menu remains legible regardless of the movement of the spotlight effect or background elements underneath it.

### 3. State Management for Hover Effects
**Issue:** Managing "active" states across a list of project rows can become messy, leading to "stuck" hover states if the mouse moves too quickly.
**Solution:** I implemented a centralized `activeProject` state in the parent component. By combining `onMouseEnter` for specific rows with a `onMouseLeave` on the main container, I ensured a smooth, glitch-free transition between focus states.

---

## 📂 Project Structure

```text
/src
 ├── components/       # Atomic UI components (ProjectRow, Marquee, HobbyCard)
 ├── styles/           # Global CSS and Google Font imports (Syne, Space Grotesk)
 └── Portfolio.js      # Main entry point with logic for mouse tracking and scrolling
