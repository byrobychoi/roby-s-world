---
draft: true
template: default
seo: {}
blocks: []
---

<pre><code>
&lt;!DOCTYPE html&gt;
&lt;html lang="en"&gt;
&lt;head&gt;
&lt;meta charset="UTF-8"&gt;
&lt;meta name="viewport" content="width=device-width, initial-scale=1.0"&gt;
&lt;title&gt;All Courses&lt;/title&gt;
&lt;link rel="preconnect" href="https://fonts.googleapis.com"&gt;
&lt;link href="https://fonts.googleapis.com/css2?family=SF+Pro+Display:wght@300;400;500;600&amp;display=swap" rel="stylesheet"&gt;
&lt;style&gt;
  :root {
    --white: #ffffff;
    --gray-50: #fafafa;
    --gray-100: #f5f5f7;
    --gray-200: #e8e8ed;
    --gray-300: #d2d2d7;
    --gray-400: #aeaeb2;
    --gray-500: #86868b;
    --gray-600: #6e6e73;
    --gray-700: #48484a;
    --gray-800: #333336;
    --gray-900: #1d1d1f;
    --black: #000000;
    --font: -apple-system, BlinkMacSystemFont, "SF Pro Display", "SF Pro Text", "Helvetica Neue", Helvetica, Arial, sans-serif;
    --transition: 0.3s cubic-bezier(0.25, 0.1, 0.25, 1);
  }

  *, *::before, *::after {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  html {
    font-size: 16px;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
  }

  body {
    font-family: var(--font);
    background: var(--white);
    color: var(--gray-900);
    line-height: 1.5;
  }

  /* ── NAV ── */
  .nav {
    position: sticky;
    top: 0;
    z-index: 100;
    background: rgba(255,255,255,0.72);
    backdrop-filter: saturate(180%) blur(20px);
    -webkit-backdrop-filter: saturate(180%) blur(20px);
    border-bottom: 0.5px solid var(--gray-200);
  }

  .nav-inner {
    max-width: 1024px;
    margin: 0 auto;
    padding: 0 22px;
    height: 48px;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .nav-logo {
    font-size: 21px;
    font-weight: 600;
    letter-spacing: -0.02em;
    color: var(--gray-900);
  }

  .nav-links {
    display: flex;
    gap: 28px;
    list-style: none;
  }

  .nav-links a {
    font-size: 12px;
    font-weight: 400;
    color: var(--gray-600);
    text-decoration: none;
    transition: color var(--transition);
    letter-spacing: 0.01em;
  }

  .nav-links a:hover {
    color: var(--gray-900);
  }

  .nav-hamburger {
    display: none;
    background: none;
    border: none;
    cursor: pointer;
    width: 18px;
    height: 18px;
    position: relative;
  }

  .nav-hamburger span {
    display: block;
    width: 18px;
    height: 1.5px;
    background: var(--gray-900);
    border-radius: 1px;
    position: absolute;
    left: 0;
    transition: all var(--transition);
  }

  .nav-hamburger span:nth-child(1) { top: 4px; }
  .nav-hamburger span:nth-child(2) { top: 9px; }
  .nav-hamburger span:nth-child(3) { top: 14px; }

  /* ── HERO ── */
  .hero {
    max-width: 1024px;
    margin: 0 auto;
    padding: 80px 22px 40px;
    text-align: center;
  }

  .hero h1 {
    font-size: 56px;
    font-weight: 600;
    letter-spacing: -0.03em;
    line-height: 1.07;
    color: var(--gray-900);
  }

  .hero p {
    margin-top: 16px;
    font-size: 21px;
    font-weight: 400;
    color: var(--gray-500);
    letter-spacing: 0.01em;
    line-height: 1.38;
  }

  /* ── GRID ── */
  .courses-section {
    max-width: 1024px;
    margin: 0 auto;
    padding: 20px 22px 100px;
  }

  .grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 16px;
  }

  /* ── CARD ── */
  .card {
    background: var(--gray-50);
    border-radius: 18px;
    padding: 30px 28px 28px;
    transition: background var(--transition), transform var(--transition);
    cursor: default;
  }

  .card:hover {
    background: var(--gray-100);
    transform: scale(1.01);
  }

  .card-title {
    font-size: 22px;
    font-weight: 600;
    letter-spacing: -0.02em;
    color: var(--gray-900);
    margin-bottom: 16px;
    line-height: 1.18;
  }

  .card-list {
    list-style: none;
  }

  .card-list li {
    font-size: 14px;
    font-weight: 400;
    color: var(--gray-600);
    padding: 7px 0;
    border-bottom: 0.5px solid var(--gray-200);
    transition: color var(--transition);
    cursor: pointer;
    letter-spacing: 0.01em;
  }

  .card-list li:last-child {
    border-bottom: none;
  }

  .card-list li:hover {
    color: var(--gray-900);
  }

  /* ── FOOTER ── */
  .footer {
    border-top: 0.5px solid var(--gray-200);
    padding: 20px 22px;
    text-align: center;
  }

  .footer p {
    font-size: 12px;
    color: var(--gray-400);
    letter-spacing: 0.01em;
  }

  /* ── FADE-IN ── */
  .card {
    opacity: 0;
    transform: translateY(20px);
    animation: fadeUp 0.6s ease forwards;
  }

  @keyframes fadeUp {
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }

  .card:nth-child(1)  { animation-delay: 0.04s; }
  .card:nth-child(2)  { animation-delay: 0.08s; }
  .card:nth-child(3)  { animation-delay: 0.12s; }
  .card:nth-child(4)  { animation-delay: 0.16s; }
  .card:nth-child(5)  { animation-delay: 0.20s; }
  .card:nth-child(6)  { animation-delay: 0.24s; }
  .card:nth-child(7)  { animation-delay: 0.28s; }
  .card:nth-child(8)  { animation-delay: 0.32s; }
  .card:nth-child(9)  { animation-delay: 0.36s; }
  .card:nth-child(10) { animation-delay: 0.40s; }
  .card:nth-child(11) { animation-delay: 0.44s; }
  .card:nth-child(12) { animation-delay: 0.48s; }
  .card:nth-child(13) { animation-delay: 0.52s; }
  .card:nth-child(14) { animation-delay: 0.56s; }

  /* ── RESPONSIVE ── */
  @media (max-width: 834px) {
    .grid {
      grid-template-columns: repeat(2, 1fr);
    }
    .hero h1 {
      font-size: 40px;
    }
    .hero p {
      font-size: 19px;
    }
    .hero {
      padding: 60px 22px 30px;
    }
  }

  @media (max-width: 600px) {
    .nav-links { display: none; }
    .nav-hamburger { display: block; }
    .nav-inner { height: 44px; }

    .hero {
      padding: 48px 22px 24px;
    }
    .hero h1 {
      font-size: 32px;
      letter-spacing: -0.025em;
    }
    .hero p {
      font-size: 17px;
      margin-top: 10px;
    }

    .grid {
      grid-template-columns: 1fr;
      gap: 12px;
    }

    .card {
      padding: 24px 22px 22px;
      border-radius: 14px;
    }

    .card-title {
      font-size: 19px;
      margin-bottom: 12px;
    }

    .card-list li {
      font-size: 14px;
      padding: 8px 0;
    }

    .courses-section {
      padding: 12px 16px 72px;
    }
  }
&lt;/style&gt;
&lt;/head&gt;
&lt;body&gt;

&lt;!-- Nav --&gt;
&lt;nav class="nav"&gt;
  &lt;div class="nav-inner"&gt;
    &lt;div class="nav-logo"&gt;Courses&lt;/div&gt;
    &lt;ul class="nav-links"&gt;
      &lt;li&gt;&lt;a href="#"&gt;Browse&lt;/a&gt;&lt;/li&gt;
      &lt;li&gt;&lt;a href="#"&gt;Popular&lt;/a&gt;&lt;/li&gt;
      &lt;li&gt;&lt;a href="#"&gt;New&lt;/a&gt;&lt;/li&gt;
      &lt;li&gt;&lt;a href="#"&gt;My Learning&lt;/a&gt;&lt;/li&gt;
    &lt;/ul&gt;
    &lt;button class="nav-hamburger" aria-label="Menu"&gt;
      &lt;span&gt;&lt;/span&gt;&lt;span&gt;&lt;/span&gt;&lt;span&gt;&lt;/span&gt;
    &lt;/button&gt;
  &lt;/div&gt;
&lt;/nav&gt;

&lt;!-- Hero --&gt;
&lt;section class="hero"&gt;
  &lt;h1&gt;All Courses&lt;/h1&gt;
  &lt;p&gt;Browse every category. Find what moves you.&lt;/p&gt;
&lt;/section&gt;

&lt;!-- Grid --&gt;
&lt;section class="courses-section"&gt;
  &lt;div class="grid"&gt;

    &lt;div class="card"&gt;
      &lt;div class="card-title"&gt;Development&lt;/div&gt;
      &lt;ul class="card-list"&gt;
        &lt;li&gt;Web Development&lt;/li&gt;
        &lt;li&gt;Programming Languages&lt;/li&gt;
        &lt;li&gt;Data Science&lt;/li&gt;
        &lt;li&gt;Game Development&lt;/li&gt;
        &lt;li&gt;Mobile Development&lt;/li&gt;
        &lt;li&gt;Software Testing&lt;/li&gt;
        &lt;li&gt;Databases&lt;/li&gt;
        &lt;li&gt;Interview Prep&lt;/li&gt;
        &lt;li&gt;Software Engineering&lt;/li&gt;
      &lt;/ul&gt;
    &lt;/div&gt;

    &lt;div class="card"&gt;
      &lt;div class="card-title"&gt;Design&lt;/div&gt;
      &lt;ul class="card-list"&gt;
        &lt;li&gt;Graphic Design&lt;/li&gt;
        &lt;li&gt;Web Design&lt;/li&gt;
        &lt;li&gt;Game Design&lt;/li&gt;
        &lt;li&gt;UI / UX&lt;/li&gt;
        &lt;li&gt;Design Packs&lt;/li&gt;
        &lt;li&gt;3D &amp;amp; Animation&lt;/li&gt;
        &lt;li&gt;Video Editing / Filming&lt;/li&gt;
      &lt;/ul&gt;
    &lt;/div&gt;

    &lt;div class="card"&gt;
      &lt;div class="card-title"&gt;IT &amp;amp; Software&lt;/div&gt;
      &lt;ul class="card-list"&gt;
        &lt;li&gt;IT Certification&lt;/li&gt;
        &lt;li&gt;Network &amp;amp; Security&lt;/li&gt;
        &lt;li&gt;Operating Systems&lt;/li&gt;
        &lt;li&gt;Hardware&lt;/li&gt;
        &lt;li&gt;Other Software&lt;/li&gt;
      &lt;/ul&gt;
    &lt;/div&gt;

    &lt;div class="card"&gt;
      &lt;div class="card-title"&gt;Business&lt;/div&gt;
      &lt;ul class="card-list"&gt;
        &lt;li&gt;Management&lt;/li&gt;
        &lt;li&gt;Entrepreneurship&lt;/li&gt;
        &lt;li&gt;Finance&lt;/li&gt;
        &lt;li&gt;Sales&lt;/li&gt;
        &lt;li&gt;Communications&lt;/li&gt;
        &lt;li&gt;e-Commerce&lt;/li&gt;
        &lt;li&gt;Dropship&lt;/li&gt;
        &lt;li&gt;Data &amp;amp; Analytics&lt;/li&gt;
      &lt;/ul&gt;
    &lt;/div&gt;

    &lt;div class="card"&gt;
      &lt;div class="card-title"&gt;Marketing&lt;/div&gt;
      &lt;ul class="card-list"&gt;
        &lt;li&gt;Digital Marketing&lt;/li&gt;
        &lt;li&gt;Social Media Marketing&lt;/li&gt;
        &lt;li&gt;Search Engine Optimization (SEO)&lt;/li&gt;
        &lt;li&gt;Advertising&lt;/li&gt;
        &lt;li&gt;Affiliate Marketing&lt;/li&gt;
        &lt;li&gt;Clickfunnels&lt;/li&gt;
        &lt;li&gt;CPA Marketing&lt;/li&gt;
        &lt;li&gt;Copywriting&lt;/li&gt;
        &lt;li&gt;Email Marketing&lt;/li&gt;
        &lt;li&gt;Traffic Generation&lt;/li&gt;
      &lt;/ul&gt;
    &lt;/div&gt;

    &lt;div class="card"&gt;
      &lt;div class="card-title"&gt;Office Productivity&lt;/div&gt;
      &lt;ul class="card-list"&gt;
        &lt;li&gt;Microsoft&lt;/li&gt;
        &lt;li&gt;Apple&lt;/li&gt;
        &lt;li&gt;Google&lt;/li&gt;
        &lt;li&gt;SAP&lt;/li&gt;
        &lt;li&gt;Oracle&lt;/li&gt;
        &lt;li&gt;Productivity Tools&lt;/li&gt;
      &lt;/ul&gt;
    &lt;/div&gt;

    &lt;div class="card"&gt;
      &lt;div class="card-title"&gt;Lifestyle&lt;/div&gt;
      &lt;ul class="card-list"&gt;
        &lt;li&gt;Arts &amp;amp; Crafts&lt;/li&gt;
        &lt;li&gt;Photography &amp;amp; Videography&lt;/li&gt;
        &lt;li&gt;Food &amp;amp; Beverage&lt;/li&gt;
        &lt;li&gt;Beauty &amp;amp; Makeup&lt;/li&gt;
        &lt;li&gt;Film &amp;amp; TV&lt;/li&gt;
        &lt;li&gt;Home Improvement&lt;/li&gt;
        &lt;li&gt;Gaming&lt;/li&gt;
        &lt;li&gt;Travel&lt;/li&gt;
        &lt;li&gt;Other Lifestyle&lt;/li&gt;
      &lt;/ul&gt;
    &lt;/div&gt;

    &lt;div class="card"&gt;
      &lt;div class="card-title"&gt;Personal Development&lt;/div&gt;
      &lt;ul class="card-list"&gt;
        &lt;li&gt;Personal Transformation&lt;/li&gt;
        &lt;li&gt;Career Development&lt;/li&gt;
        &lt;li&gt;Personal Finance&lt;/li&gt;
        &lt;li&gt;Productivity&lt;/li&gt;
        &lt;li&gt;Leadership&lt;/li&gt;
        &lt;li&gt;Parenting &amp;amp; Relationships&lt;/li&gt;
      &lt;/ul&gt;
    &lt;/div&gt;

    &lt;div class="card"&gt;
      &lt;div class="card-title"&gt;Health &amp;amp; Fitness&lt;/div&gt;
      &lt;ul class="card-list"&gt;
        &lt;li&gt;Fitness&lt;/li&gt;
        &lt;li&gt;Sports&lt;/li&gt;
        &lt;li&gt;Nutrition&lt;/li&gt;
        &lt;li&gt;Meditation&lt;/li&gt;
        &lt;li&gt;Yoga&lt;/li&gt;
        &lt;li&gt;Mental Health&lt;/li&gt;
      &lt;/ul&gt;
    &lt;/div&gt;

    &lt;div class="card"&gt;
      &lt;div class="card-title"&gt;Teaching &amp;amp; Academics&lt;/div&gt;
      &lt;ul class="card-list"&gt;
        &lt;li&gt;Engineering&lt;/li&gt;
        &lt;li&gt;Humanities&lt;/li&gt;
        &lt;li&gt;Math&lt;/li&gt;
        &lt;li&gt;Science&lt;/li&gt;
        &lt;li&gt;Social Science&lt;/li&gt;
        &lt;li&gt;Languages&lt;/li&gt;
        &lt;li&gt;Test Prep&lt;/li&gt;
        &lt;li&gt;Online Education&lt;/li&gt;
        &lt;li&gt;Course Creation&lt;/li&gt;
      &lt;/ul&gt;
    &lt;/div&gt;

    &lt;div class="card"&gt;
      &lt;div class="card-title"&gt;Music&lt;/div&gt;
      &lt;ul class="card-list"&gt;
        &lt;li&gt;Instruments&lt;/li&gt;
        &lt;li&gt;Production&lt;/li&gt;
        &lt;li&gt;Music Fundamentals&lt;/li&gt;
        &lt;li&gt;Vocal&lt;/li&gt;
        &lt;li&gt;Music Software&lt;/li&gt;
      &lt;/ul&gt;
    &lt;/div&gt;

    &lt;div class="card"&gt;
      &lt;div class="card-title"&gt;MMA &amp;amp; Combat Sports&lt;/div&gt;
      &lt;ul class="card-list"&gt;
        &lt;li&gt;Brazilian Jiu-Jitsu&lt;/li&gt;
        &lt;li&gt;Wrestling&lt;/li&gt;
        &lt;li&gt;Muay Thai &amp;amp; Kickboxing&lt;/li&gt;
        &lt;li&gt;Boxing&lt;/li&gt;
        &lt;li&gt;Judo&lt;/li&gt;
        &lt;li&gt;Striking Fundamentals&lt;/li&gt;
        &lt;li&gt;Grappling &amp;amp; Submissions&lt;/li&gt;
        &lt;li&gt;Self-Defense&lt;/li&gt;
        &lt;li&gt;Strength &amp;amp; Conditioning for Fighters&lt;/li&gt;
      &lt;/ul&gt;
    &lt;/div&gt;

    &lt;div class="card"&gt;
      &lt;div class="card-title"&gt;Food &amp;amp; Cooking&lt;/div&gt;
      &lt;ul class="card-list"&gt;
        &lt;li&gt;Culinary Fundamentals&lt;/li&gt;
        &lt;li&gt;Baking &amp;amp; Pastry&lt;/li&gt;
        &lt;li&gt;World Cuisines&lt;/li&gt;
        &lt;li&gt;Meal Prep &amp;amp; Planning&lt;/li&gt;
        &lt;li&gt;Plant-Based Cooking&lt;/li&gt;
        &lt;li&gt;Grilling &amp;amp; BBQ&lt;/li&gt;
        &lt;li&gt;Food Photography &amp;amp; Plating&lt;/li&gt;
        &lt;li&gt;Wine &amp;amp; Beverages&lt;/li&gt;
        &lt;li&gt;Food Business &amp;amp; Entrepreneurship&lt;/li&gt;
      &lt;/ul&gt;
    &lt;/div&gt;

  &lt;/div&gt;
&lt;/section&gt;

&lt;!-- Footer --&gt;
&lt;footer class="footer"&gt;
  &lt;p&gt;&amp;copy; 2026 Courses. All rights reserved.&lt;/p&gt;
&lt;/footer&gt;

&lt;/body&gt;
&lt;/html&gt;
</code></pre><p></p>
