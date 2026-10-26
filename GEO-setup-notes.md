# Navora GEO / SEO setup — what to upload and where

## 1. Upload the files
| File | Upload to | Live URL |
|---|---|---|
| `learn/index.html` | `/learn/index.html` | https://navoranow.com/learn/ |
| `llms.txt` | site root | https://navoranow.com/llms.txt |

## 2. Add "Learn" to the site menu
In the nav/footer of the Home, Manjeri and About pages, add:

```html
<a href="https://navoranow.com/learn/">Learn</a>
```

## 3. Add this to the <head> of the home page (navoranow.com/)
It tells Google and AI engines that the Instagram and Facebook accounts belong to Navora.

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "@id": "https://navoranow.com/#organization",
  "name": "Navora",
  "url": "https://navoranow.com/",
  "logo": "https://navoranow.com/navora-desktop.webp",
  "description": "Navora is a Kerala-based hyperlocal quick-commerce brand connecting customers with local shops, launching first in Manjeri, Malappuram.",
  "areaServed": { "@type": "Place", "name": "Manjeri, Malappuram, Kerala, India" },
  "sameAs": [
    "https://www.instagram.com/navoranow/",
    "https://www.facebook.com/profile.php?id=61595473692720"
  ]
}
</script>
```

Also add a Facebook link next to the Instagram link in the site footer.

## 4. Sitemap
Add to `sitemap.xml`:

```xml
<url>
  <loc>https://navoranow.com/learn/</loc>
  <lastmod>2026-10-26</lastmod>
</url>
```

## 5. robots.txt — let AI crawlers in
Make sure robots.txt does NOT block these (if you have no rules for them, they're already allowed):
`GPTBot`, `OAI-SearchBot`, `ChatGPT-User`, `PerplexityBot`, `ClaudeBot`, `Google-Extended`, `Bingbot`.
If you use Cloudflare, check **Security → Bots → "Block AI bots"** is OFF, or those crawlers can't read the site.

## 6. After uploading
1. Google Search Console → URL Inspection → paste `https://navoranow.com/learn/` → **Request indexing**.
2. Test the structured data: https://search.google.com/test/rich-results
3. Bing Webmaster Tools → submit the sitemap (Bing powers ChatGPT search).

## 7. Keep it growing
- Every new reel = one new section on /learn/ (question as the heading, 1–2 sentence answer first, facts with sources, link to the reel).
- Update the "Last updated" date and `dateModified` when you add sections.
- When the reels are on YouTube Shorts, link the YouTube version too; Google shows YouTube videos in search far more often.
