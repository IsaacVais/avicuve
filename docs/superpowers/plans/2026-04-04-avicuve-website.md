# AVICUVE Website Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build and deploy a satirical single-page support group website for AVICUVE (Asociacion de Victimas de Cuaymas Venezolanas) at avicuve.com.

**Architecture:** Single `index.html` file with embedded `<style>` and `<script>` tags. No build step, no frameworks. Hosted on GitHub Pages with custom domain.

**Tech Stack:** HTML5, CSS3, vanilla JavaScript, Google Fonts (Nunito + Inter)

---

## File Structure

```
/
├── index.html          # The entire website (HTML + CSS + JS)
├── images/             # Downloaded stock photos
│   ├── hero-bg.jpg     # Hero section background
│   ├── testimonial-1.jpg
│   ├── testimonial-2.jpg
│   ├── testimonial-3.jpg
│   ├── testimonial-4.jpg
│   └── testimonial-5.jpg
├── CNAME               # GitHub Pages custom domain config
└── docs/               # Design docs (already exists)
```

---

### Task 1: Source and Download Images

**Files:**
- Create: `images/hero-bg.jpg`
- Create: `images/testimonial-1.jpg` through `images/testimonial-5.jpg`

- [ ] **Step 1: Create images directory**

```bash
mkdir -p images
```

- [ ] **Step 2: Find and download hero background image**

Search Unsplash/Pexels for a moody, emotional image suitable for the hero. Good search terms: "man alone thinking", "lonely man", "emotional support". Download a high-quality landscape image (at least 1920px wide). Save as `images/hero-bg.jpg`.

Use curl to download from Unsplash source URLs. Example:
```bash
curl -L "https://images.unsplash.com/photo-XXXX?w=1920&q=80" -o images/hero-bg.jpg
```

- [ ] **Step 3: Find and download 5 testimonial portrait photos**

Search for diverse photos of men showing emotion — sad, contemplative, stressed, relieved, hopeful. These will be circular-cropped in CSS so portrait orientation works best.

Download each as `images/testimonial-1.jpg` through `images/testimonial-5.jpg`:
```bash
curl -L "https://images.unsplash.com/photo-XXXX?w=400&q=80" -o images/testimonial-1.jpg
# ... repeat for each
```

- [ ] **Step 4: Commit images**

```bash
git add images/
git commit -m "chore: add stock images for hero and testimonials"
```

---

### Task 2: Write All Spanish Copy

This task produces the complete copy that will be embedded in the HTML. Write everything in Spanish, completely straight-faced. The humor comes from treating cuaymismo as a serious condition.

**Files:**
- Output is used directly in Task 3 (the HTML file)

- [ ] **Step 1: Write hero section copy**

```
Headline: "No Estas Solo"
Subline: "AVICUVE es la primera asociacion venezolana dedicada a apoyar a las victimas
del cuaymismo. Desde 2003, hemos ayudado a miles de hombres a recuperar su voz,
su control remoto, y su dignidad."
CTA: "Unete a Nosotros"
```

- [ ] **Step 2: Write "Que es una Cuayma?" section**

Deadpan explanation of the "condition" followed by warning signs presented as a clinical checklist:

```
Title: "Que es una Cuayma?"
Intro: "El cuaymismo es una condicion socio-familiar que afecta a millones de hogares
venezolanos. Una cuayma es un miembro femenino de la familia — madre, suegra, tia,
o esposa — que ejerce un dominio absoluto sobre el hogar mediante tacticas de
intimidacion emocional, control del menu semanal, y administracion unilateral
del aire acondicionado."

Warning Signs:
- "Usted no tiene voz ni voto sobre el destino del control remoto"
- "Su suegra tiene llave de su casa y la usa sin previo aviso"
- "Le dicen que hacer, como vestirse, y a que hora llegar a su propia casa"
- "Su opinion sobre la cena es sistematicamente ignorada"
- "Ha escuchado la frase 'Porque yo lo digo' mas de 3 veces en una semana"
- "Su espacio personal en el closet se ha reducido a un 15% o menos"
```

- [ ] **Step 3: Write testimonials (5 total)**

Each testimonial needs a fake name, age, city, and a quote. All completely straight-faced:

```
Testimonial 1:
Name: "Carlos M., 42 anos — Maracaibo"
Quote: "Llevaba 15 anos sin elegir que comer un domingo. Desde que llegue a AVICUVE,
por primera vez pude decir 'hoy quiero pizza' sin que me respondieran con una mirada
que me hizo cuestionar toda mi existencia."

Testimonial 2:
Name: "Roberto J., 38 anos — Caracas"
Quote: "Mi suegra reorganizo mi taller sin decirme. Mis herramientas, mis tornillos,
todo. Cuando me queje, me dijeron que deberia estar agradecido. En AVICUVE entendi
que mi taller es valido."

Testimonial 3:
Name: "Miguel A., 55 anos — Valencia"
Quote: "Me sentia tan solo. Pensaba que era el unico hombre en Venezuela que pedia
permiso para sentarse en su propio sofa. AVICUVE me hizo ver que somos miles."

Testimonial 4:
Name: "Jose L., 47 anos — Barquisimeto"
Quote: "El dia que mi esposa decidio que ibamos a pintar la casa de rosado sin
consultarme, algo se rompio dentro de mi. Gracias a los grupos de apoyo de AVICUVE,
aprendi a decir 'me gusta el azul' sin temblar."

Testimonial 5:
Name: "Andres P., 33 anos — Merida"
Quote: "Mi mama todavia me llama 3 veces al dia para preguntarme si comi. Tengo 33 anos.
AVICUVE me dio las herramientas para decir 'si mama, comi' sin sentir culpa
cuando en realidad comi cereal."
```

- [ ] **Step 4: Write services section**

```
Section Title: "Nuestros Servicios"

Service 1:
Title: "Grupos de Apoyo"
Description: "Reuniones semanales donde hombres como tu comparten sus experiencias
en un ambiente seguro, libre de juicio y de suegras."

Service 2:
Title: "Linea de Emergencia"
Description: "Disponible 24/7 para momentos criticos. Si su cuayma acaba de
reorganizar su gaveta de medias, llamenos. Entendemos."

Service 3:
Title: "Consejeria Individual"
Description: "Sesiones personalizadas con especialistas en dinamicas cuaymicas.
Aprenda tecnicas de supervivencia domestica avaladas por expertos."

Service 4:
Title: "Programa de Recuperacion"
Description: "Nuestro programa de 12 pasos ha ayudado a miles de hombres a
reconocer que el control remoto no es solo un objeto — es un simbolo de libertad."
```

- [ ] **Step 5: Write statistics section**

```
Stat 1: "1 de cada 3" — "hogares venezolanos presenta al menos un caso de cuaymismo activo"
Stat 2: "73%" — "de los hombres venezolanos han perdido el control de su propio closet"
Stat 3: "+15,000" — "hombres han recuperado su voz gracias a AVICUVE desde 2003"
Stat 4: "24/7" — "nuestra linea de emergencia esta disponible para ti en todo momento"
```

- [ ] **Step 6: Write sign-up section and modal**

```
Section Title: "Da el Primer Paso"
Subtext: "Unirse a AVICUVE es gratuito, confidencial, y no requiere permiso de nadie.
Bueno, tal vez si. Pero estamos trabajando en eso."
CTA Button: "Quiero Unirme"

Modal Title: "Gracias por tu Valentia"
Modal Text: "Tu solicitud ha sido recibida. Un representante llorara contigo en breve.
Mientras tanto, recuerda: no es tu culpa que ella haya movido tus cosas del bano."
Modal Close Button: "Entendido, Gracias"
```

- [ ] **Step 7: Write footer content**

```
Tagline: "AVICUVE — Porque tu tambien tienes derecho a opinar."
Address: "Av. Libertador, Torre de la Esperanza, Piso 3, Oficina 3B — Caracas, Venezuela"
Phone: "Linea de Emergencia: 0-800-CUAYMA-0 (0-800-282-9620)"
Email: "apoyo@avicuve.com"
Copyright: "2003-2026 AVICUVE. Todos los derechos reservados. Algunos derechos en el hogar aun en disputa."
```

---

### Task 3: Build the Complete HTML Page

**Files:**
- Create: `index.html`

This is the main task. Build the entire website as a single HTML file with embedded CSS and JS. Use the copy from Task 2 and reference images from Task 1.

- [ ] **Step 1: Create the HTML skeleton with embedded CSS**

Create `index.html` with:
- DOCTYPE, html lang="es"
- Meta viewport, charset, description, Open Graph tags
- Google Fonts link (Nunito + Inter)
- All CSS in a `<style>` block in `<head>`

CSS must include:
- CSS custom properties for the color palette:
  ```css
  :root {
    --primary: #6B5B95;
    --primary-light: #8E7CC3;
    --lavender: #E8E0F0;
    --bg: #F5F5F5;
    --text: #2D2D2D;
    --text-light: #FFFFFF;
    --accent: #D4A574;
  }
  ```
- Reset/normalize basics
- Responsive typography using clamp()
- Sticky nav styles with scroll-aware shadow
- Hero section full-viewport with gradient overlay
- Two-column layout for "Que es una Cuayma?" section
- Carousel styles with slide transitions
- Service cards grid (2x2 on desktop, 1-col mobile)
- Stats section with large numbers
- Modal overlay styles
- Hamburger menu for mobile
- All responsive breakpoints (768px tablet, 480px mobile)

- [ ] **Step 2: Add the navigation header HTML**

```html
<header class="nav" id="nav">
  <div class="nav-container">
    <a href="#inicio" class="nav-logo">AVICUVE</a>
    <button class="hamburger" aria-label="Menu" aria-expanded="false">
      <span></span><span></span><span></span>
    </button>
    <nav class="nav-links">
      <a href="#inicio">Inicio</a>
      <a href="#cuayma">¿Qué es una Cuayma?</a>
      <a href="#testimonios">Testimonios</a>
      <a href="#servicios">Servicios</a>
      <a href="#unete">Únete</a>
    </nav>
  </div>
</header>
```

- [ ] **Step 3: Add hero section HTML**

Full-viewport section with gradient background, headline, subline, and CTA button. Include the down-arrow scroll hint with CSS animation.

- [ ] **Step 4: Add "Que es una Cuayma?" section HTML**

Two-column layout. Left column: text explanation and warning signs checklist. Right column: a large decorative icon or SVG (warning triangle or similar — use an inline SVG to avoid extra files).

- [ ] **Step 5: Add testimonials carousel HTML**

Container with all 5 testimonial slides (only one visible at a time), prev/next buttons, and dot indicators. Each slide contains the circular photo, name, and quote.

- [ ] **Step 6: Add services grid HTML**

Four cards in a grid. Each card has an inline SVG icon, title, and description. Icons:
- Grupos de Apoyo: people/group icon
- Linea de Emergencia: phone icon
- Consejeria Individual: chat/heart icon
- Programa de Recuperacion: trophy/path icon

Use simple inline SVGs for icons (no icon library needed).

- [ ] **Step 7: Add statistics section HTML**

Four stat blocks in a row. Each has the big number and the label text below.

- [ ] **Step 8: Add sign-up section and modal HTML**

CTA section with button. Hidden modal overlay that appears on button click. Modal has title, text, and close button.

- [ ] **Step 9: Add footer HTML**

AVICUVE wordmark, address, phone, email, social icons (inline SVGs for Facebook, Instagram, Twitter — non-functional), copyright.

- [ ] **Step 10: Add all JavaScript**

At the bottom of the file, a single `<script>` block with:

```javascript
// 1. Sticky nav shadow on scroll
window.addEventListener('scroll', () => {
  document.getElementById('nav').classList.toggle('scrolled', window.scrollY > 50);
});

// 2. Smooth scroll for nav links
document.querySelectorAll('a[href^="#"]').forEach(a => {
  a.addEventListener('click', e => {
    e.preventDefault();
    const target = document.querySelector(a.getAttribute('href'));
    if (target) target.scrollIntoView({ behavior: 'smooth' });
    // Close mobile menu if open
    document.querySelector('.nav-links').classList.remove('active');
    document.querySelector('.hamburger').setAttribute('aria-expanded', 'false');
  });
});

// 3. Hamburger menu toggle
const hamburger = document.querySelector('.hamburger');
hamburger.addEventListener('click', () => {
  const nav = document.querySelector('.nav-links');
  const expanded = hamburger.getAttribute('aria-expanded') === 'true';
  nav.classList.toggle('active');
  hamburger.setAttribute('aria-expanded', !expanded);
});

// 4. Testimonial carousel
let currentSlide = 0;
const slides = document.querySelectorAll('.carousel-slide');
const dots = document.querySelectorAll('.carousel-dot');
let autoPlay;

function goToSlide(n) {
  slides[currentSlide].classList.remove('active');
  dots[currentSlide].classList.remove('active');
  currentSlide = (n + slides.length) % slides.length;
  slides[currentSlide].classList.add('active');
  dots[currentSlide].classList.add('active');
}

function startAutoPlay() {
  autoPlay = setInterval(() => goToSlide(currentSlide + 1), 5000);
}

function stopAutoPlay() { clearInterval(autoPlay); }

document.querySelector('.carousel-prev').addEventListener('click', () => {
  stopAutoPlay(); goToSlide(currentSlide - 1); startAutoPlay();
});
document.querySelector('.carousel-next').addEventListener('click', () => {
  stopAutoPlay(); goToSlide(currentSlide + 1); startAutoPlay();
});
dots.forEach((dot, i) => dot.addEventListener('click', () => {
  stopAutoPlay(); goToSlide(i); startAutoPlay();
}));

const carousel = document.querySelector('.carousel');
carousel.addEventListener('mouseenter', stopAutoPlay);
carousel.addEventListener('mouseleave', startAutoPlay);
startAutoPlay();

// 5. Modal
const modal = document.getElementById('modal');
document.getElementById('cta-unete').addEventListener('click', () => {
  modal.classList.add('active');
});
document.getElementById('modal-close').addEventListener('click', () => {
  modal.classList.remove('active');
});
modal.addEventListener('click', (e) => {
  if (e.target === modal) modal.classList.remove('active');
});

// 6. Stats counter animation on scroll (optional enhancement)
const stats = document.querySelectorAll('.stat-number');
const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add('animated');
      observer.unobserve(entry.target);
    }
  });
}, { threshold: 0.5 });
stats.forEach(stat => observer.observe(stat));
```

- [ ] **Step 11: Verify locally**

Open in browser and verify:
```bash
open index.html
```

Check:
- All sections render correctly
- Nav smooth-scrolls to sections
- Carousel auto-rotates and manual controls work
- Modal opens and closes
- Mobile responsive (resize browser window)
- Images load correctly

- [ ] **Step 12: Commit the HTML file**

```bash
git add index.html
git commit -m "feat: build complete AVICUVE single-page website"
```

---

### Task 4: GitHub Pages Deployment Setup

**Files:**
- Create: `CNAME`

- [ ] **Step 1: Create CNAME file for custom domain**

```bash
echo "avicuve.com" > CNAME
```

- [ ] **Step 2: Create GitHub repository**

```bash
gh repo create avicuve --public --source=. --push
```

- [ ] **Step 3: Enable GitHub Pages**

```bash
gh api repos/{owner}/avicuve/pages -X POST -f source.branch=main -f source.path=/
```

Or enable via GitHub Settings > Pages > Source: main branch, root directory.

- [ ] **Step 4: Configure DNS**

User needs to point avicuve.com DNS to GitHub Pages:
- A records: 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153
- Or CNAME record: `<username>.github.io`

- [ ] **Step 5: Commit and push**

```bash
git add CNAME
git commit -m "chore: add CNAME for GitHub Pages custom domain"
git push origin main
```

- [ ] **Step 6: Verify deployment**

Wait a few minutes, then check:
```bash
curl -I https://avicuve.com
```

Site should be live. If custom domain isn't configured yet, it will be available at `https://<username>.github.io/avicuve/`.
