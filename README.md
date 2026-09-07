# brand-cdn

Public host for a small number of **Open Summit AI** brand images that have to
be fetchable without a login — chiefly the email-signature mark.

Everything else brand-related lives in the private working repo. This one
exists only because an image in an email signature must resolve for the
recipient: Gmail proxies images through `googleusercontent.com`, and that
proxy arrives unauthenticated, so a private URL renders as a broken box.

## Files

| File | Ground | Display at |
|---|---|---|
| `signature-mark-240.png` | Void `#050506` | 120px (2x master) |
| `signature-mark-120.png` | Void `#050506` | 120px (1x fallback) |
| `signature-mark-clear-240.png` | Transparent | 120px (2x master) |
| `signature-mark-clear-120.png` | Transparent | 120px (1x fallback) |
| `signature-mark-clear-trim-280.png` | Transparent, trimmed | 140x97 (2x master) |
| `signature-mark-clear-trim-140.png` | Transparent, trimmed | 140x97 (1x fallback) |

The `-trim-` files are cropped to the artwork with a small margin, so the mark
fills its box on a light ground. The square transparent files leave the art in
a centred band and read as undersized next to a block of text.

## URLs

Use jsDelivr, not `raw.githubusercontent.com` — raw is not a CDN and is
rate-limited for hotlinking.

```
https://cdn.jsdelivr.net/gh/hennerzdagoth/brand-cdn@main/signature-mark-240.png
https://cdn.jsdelivr.net/gh/hennerzdagoth/brand-cdn@main/signature-mark-clear-240.png
```

`@main` tracks the branch, so replacing a file here updates the signature
everywhere without anyone re-pasting. jsDelivr caches a branch URL for about
12 hours; pin `@<tag>` instead if you ever need a frozen version.

## Usage

```html
<img src="https://cdn.jsdelivr.net/gh/hennerzdagoth/brand-cdn@main/signature-mark-240.png"
     alt="Open Summit AI"
     width="120" height="120"
     style="display:block; width:120px; height:120px; border:0;
            outline:none; text-decoration:none;">
```

The file is 240px while the attributes say 120 — that is what keeps it sharp
on Retina. Set size with the HTML attributes, not CSS alone; Outlook ignores
much of the CSS but honours the attributes.

---

© Open Summit AI. The marks here are company trademarks, published for use in
first-party email and web templates — not placed in the public domain.
