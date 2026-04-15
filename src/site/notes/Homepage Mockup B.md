---
{"dg-publish":true,"permalink":"/homepage-mockup-b/","title":"Homepage Mockup B","tags":["gardenEntry"],"dg-note-properties":{"title":"Homepage Mockup B","tags":null}}
---


<div style="
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 60vh;
  text-align: center;
  gap: 2rem;
">

<p style="font-size: 1.1em; opacity: 0.75; max-width: 38ch; line-height: 1.6;">
  This is a garden grown from a boneyard.<br>What you find depends on how you enter.
</p>

<button onclick="
  fetch('/sitemap.xml')
    .then(r => r.text())
    .then(xml => {
      const urls = [...xml.matchAll(/<loc>(.*?)<\/loc>/g)]
        .map(m => new URL(m[1]).pathname)
        .filter(p => p !== '/' && p !== '/404/');
      window.location.pathname = urls[Math.floor(Math.random() * urls.length)];
    });
" style="
  background: none;
  border: 1px solid currentColor;
  color: inherit;
  font: inherit;
  font-size: 1.05em;
  letter-spacing: 0.08em;
  padding: 0.6em 2em;
  cursor: pointer;
  text-transform: lowercase;
">enter</button>

</div>
