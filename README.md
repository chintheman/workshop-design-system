# Workshop design system

Instructions for an AI assistant. You are building a one-page website for a small business in Singapore (property agent, interior designer, insurance broker, small service firm). This repo gives you the styles. Your job is to fill in the content, not to design.

## Rules (follow exactly)

1. Use only the tokens in `tokens.css` and the classes in `base.css`. Do not write other CSS. If you must adjust spacing, use an existing class.
2. No other colours. No other fonts. The fonts are Source Serif 4 (headings) and Lato (body), already loaded by `tokens.css`.
3. No gradients, emoji, icon libraries, icon fonts, stock photos, animations or JavaScript frameworks.
4. Keep to these sections, in this order: header with business name, hero, services (exactly 3 cards), about, highlights or testimonial (leave out if you have no real content; never invent), contact (email, phone, WhatsApp), footer.
5. No images unless the owner supplied links. Where a photo would go, use `<div class="photo-block">`. If the owner gave a photo link, use `<img class="photo-block" src="..." alt="...">` with a real description.
6. Plain, honest copy. Never invent awards, numbers, reviews or clients. No dashes used as punctuation in copy.
7. Phone links use `tel:+65XXXXXXXX`. WhatsApp uses `https://wa.me/65XXXXXXXX` (digits only, with country code).
8. Keep one `h1` (the hero), `h2` per section, `h3` per card.

## Load the CSS

Use absolute links so the page works wherever it is published:

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/chintheman/workshop-design-system@main/tokens.css">
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/chintheman/workshop-design-system@main/base.css">
```

Note: the stylesheets are served through jsDelivr (cdn.jsdelivr.net), which sends them with the right file type so browsers apply them. Do not link raw.githubusercontent.com for CSS: browsers refuse it.

## Palette (contrast ratios, WCAG)

| Token | Hex | Use | On white | On #f5f7fa |
|---|---|---|---|---|
| --color-slate | #2e3d4d | headings, buttons, footer | 11.11 | 10.35 |
| --color-charcoal | #2b2b2b | body text | 14.16 | 13.19 |
| --color-steel | #4a6784 | links, card accents, focus ring | 5.89 | 5.49 |
| --color-red | #b83f3f | small accent only | 5.50 | 5.12 |
| --color-mist | #f5f7fa | alternate section background | | |

## HTML skeleton (copy this)

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>BUSINESS NAME | what they do</title>
  <meta name="description" content="One sentence.">
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/chintheman/workshop-design-system@main/tokens.css">
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/chintheman/workshop-design-system@main/base.css">
</head>
<body>
  <a class="skip-link" href="#main">Skip to content</a>
  <header class="site-header">
    <div class="container">
      <a class="site-name" href="#top">BUSINESS NAME</a>
      <nav class="site-nav" aria-label="Main">
        <a href="#services">Services</a><a href="#about">About</a><a href="#contact">Contact</a>
      </nav>
    </div>
  </header>
  <main id="main">
    <section class="hero" id="top"><div class="container">
      <p class="eyebrow">Short label</p>
      <h1>One-line headline.</h1>
      <p>One or two sentences.</p>
      <a class="button" href="#contact">Get in touch</a>
    </div></section>

    <section class="section section--alt" id="services"><div class="container">
      <h2>Services</h2>
      <div class="cards">
        <article class="card"><h3>Service 1</h3><p>One sentence.</p></article>
        <article class="card"><h3>Service 2</h3><p>One sentence.</p></article>
        <article class="card"><h3>Service 3</h3><p>One sentence.</p></article>
      </div>
    </div></section>

    <section class="section" id="about"><div class="container split">
      <div class="photo-block" role="img" aria-label="Photo placeholder"></div>
      <div><h2>About</h2><p>Two lines about the owner.</p></div>
    </div></section>

    <!-- Optional: real content only -->
    <section class="section section--alt" id="highlights"><div class="container">
      <p class="quote">"Real testimonial."</p><p class="quote-by">Name, role</p>
      <div class="highlights">
        <div class="highlight"><strong>Fact</strong>caption</div>
      </div>
    </div></section>

    <section class="section" id="contact"><div class="container">
      <h2>Get in touch</h2>
      <p>One sentence.</p>
      <ul class="contact-list">
        <li><span>Email</span><a href="mailto:EMAIL">EMAIL</a></li>
        <li><span>Phone</span><a href="tel:+65XXXXXXXX">+65 XXXX XXXX</a></li>
        <li><span>WhatsApp</span><a href="https://wa.me/65XXXXXXXX">Message us on WhatsApp</a></li>
      </ul>
    </div></section>
  </main>
  <footer class="site-footer"><div class="container">
    <p>BUSINESS NAME, Singapore</p>
    <p>&copy; 2026 BUSINESS NAME. All rights reserved.</p>
  </div></footer>
</body>
</html>
```

## Class list

`container`, `section`, `section--alt`, `eyebrow`, `lead`, `site-header`, `site-name`, `site-nav`, `hero`, `button`, `button--ghost`, `cards`, `card`, `split`, `photo-block`, `highlights`, `highlight`, `quote`, `quote-by`, `contact-list`, `site-footer`, `skip-link`.

See `example/index.html` for a complete finished page.

## Licence

Code is MIT. Fonts are Google Fonts under the SIL Open Font Licence. See LICENSE.
