# AVICUVE Website Design Specification

**Date:** 2026-04-04
**Domain:** avicuve.com
**Full Name:** Asociacion de Victimas de Cuaymas Venezolanas

## Overview

A satirical single-page website styled as a professional support group for Venezuelan men who are "victims" of cuaymas (domineering women in the family). The design mirrors real support organizations (AA, mental health platforms) with complete sincerity — the humor comes entirely from the copy, not the visual design.

All content is in Spanish.

## Architecture

Single `index.html` file with embedded CSS and vanilla JavaScript. No frameworks, no build step, no dependencies beyond Google Fonts.

**Hosting:** GitHub Pages (free), custom domain avicuve.com.

## Visual Design

### Palette
- Primary purple: #6B5B95
- Light purple: #8E7CC3
- Soft lavender: #E8E0F0
- Background gray: #F5F5F5
- Text dark: #2D2D2D
- Text light: #FFFFFF
- Accent warm: #D4A574 (subtle gold for CTAs)

### Typography
- Headings: Nunito (Google Fonts) — warm, approachable
- Body: Inter (Google Fonts) — clean, professional
- Font sizes responsive via clamp()

### Imagery
- Stock photos of distressed/emotional men from Unsplash or Pexels (free, no attribution required for Unsplash)
- Images downloaded to repo (not hotlinked) for reliability
- Soft overlay/filter to match the muted purple palette

## Page Sections (Top to Bottom)

### 1. Navigation Header
- Sticky/fixed at top of page
- AVICUVE logo/wordmark on the left
- Anchor links: Inicio, Que es una Cuayma?, Testimonios, Servicios, Unete
- Smooth-scroll behavior on click
- Subtle shadow on scroll, semi-transparent background
- Hamburger menu on mobile

### 2. Hero Section
- Full-viewport height
- Soft gradient background (purple to lavender)
- Headline: "No Estas Solo" (large, emotional)
- Subline: Brief mission statement about AVICUVE
- CTA button: "Unete a Nosotros" (links to sign-up section)
- Subtle down-arrow animation hinting to scroll

### 3. Que es una Cuayma?
- Clean two-column layout (text + illustration or icon)
- Deadpan-serious explanation of what a cuayma is
- Bullet-point "warning signs" presented like a medical checklist
- Tone: Completely sincere, as if describing a real condition

### 4. Testimonios (Carousel)
- Auto-rotating carousel (every 5 seconds)
- Manual prev/next navigation buttons
- Dot indicators for current slide
- Each slide: stock photo of a man, his "name" (fake), his testimonial quote
- 4-6 testimonials total
- Pause auto-rotation on hover
- Pure CSS + vanilla JS implementation (no libraries)
- Touch-swipe support on mobile (nice-to-have, not required)

### 5. Nuestros Servicios
- Grid of 4 service cards with icons
- Services: Grupos de Apoyo, Linea de Emergencia, Consejeria Individual, Programa de Recuperacion
- Each card has an icon, title, and brief description
- All presented with complete professionalism

### 6. Estadisticas
- 3-4 fake statistics in large number + label format
- Examples: "1 de cada 3 hogares", "73% de los hombres venezolanos", etc.
- Counter animation on scroll into view (nice-to-have)
- Presented as seriously as any NGO infographic

### 7. Unete (Sign-up)
- Prominent section with CTA
- Button triggers a JavaScript modal
- Modal message: humorous response like "Un representante llorara contigo en breve"
- Alternative: link to a Google Form (can be added later)

### 8. Footer
- AVICUVE wordmark
- Fake address and contact info
- "Linea de Emergencia" with a fake phone number
- Social media icons (non-functional, just visual)
- Copyright notice

## Interactivity

- Smooth-scroll navigation
- Sticky header with scroll-aware styling
- Testimonial carousel (auto + manual)
- Sign-up modal
- Optional: stats counter animation on scroll
- All implemented in vanilla JS (no jQuery, no frameworks)

## Responsive Behavior

- Desktop: full layouts, multi-column grids
- Tablet: adjusted grid, smaller hero text
- Mobile: single column, hamburger nav, carousel touch-friendly

## Tone Guidelines for Copy

- ALL copy in Spanish
- Written completely straight-faced — no winking, no "jk"
- Mirrors real support organization language
- Humor comes from the absurdity of treating cuaymismo as a medical/social condition
- Testimonials should feel genuine — real emotions, real struggles, just about a ridiculous premise
- Sprinkle subtle funny details (e.g., the hotline number, the fake stats, the service descriptions)

## Out of Scope

- Backend functionality
- Real form submission
- Database
- User accounts
- Multi-page navigation
- CMS
- Analytics (can be added later)
