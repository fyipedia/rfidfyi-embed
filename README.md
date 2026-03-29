# rfidfyi-embed

[![npm](https://img.shields.io/npm/v/rfidfyi-embed)](https://www.npmjs.com/package/rfidfyi-embed)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Zero Dependencies](https://img.shields.io/badge/dependencies-0-brightgreen)](https://www.npmjs.com/package/rfidfyi-embed)
[![Size](https://img.shields.io/badge/size-~11--16KB_gzipped-green)](https://bundlephobia.com/package/rfidfyi-embed)

Embed **RFIDFYI** specification widgets — rfid tags, technical standards, glossary terms, and interactive tools — on any website. **9 widget types**, zero dependencies, Shadow DOM style isolation, 3 built-in themes (light, dark, sepia), and live data from the [RFIDFYI](https://rfidfyi.com) database.

Every widget includes a "Powered by RFIDFYI" backlink directing readers to the full technical reference.

> **Try the interactive widget builder at [widget.rfidfyi.com](https://widget.rfidfyi.com)**

## Quick Start

```html
<!-- Place widget div where you want it to appear -->
<div data-rfidfyi="spec" data-slug="tags" data-theme="light"></div>

<!-- Load the embed script once, anywhere on the page -->
<script src="https://cdn.jsdelivr.net/npm/rfidfyi-embed@1/dist/embed.min.js"></script>
```

That's it. The widget fetches data from the RFIDFYI API and renders with full style isolation.

## Widget Types

| Type | Usage | Description |
|------|-------|-------------|
| `spec` | `<div data-rfidfyi="spec" data-slug="..."></div>` | Technical specification card — protocol, range, data rate, standards |
| `compare` | `<div data-rfidfyi="compare" data-slug="..."></div>` | Side-by-side comparison of two technologies or standards |
| `features` | `<div data-rfidfyi="features" data-slug="..."></div>` | Feature list card — capabilities, supported modes, variants |
| `glossary` | `<div data-rfidfyi="glossary" data-slug="..."></div>` | Glossary term definition with cross-references |
| `faq` | `<div data-rfidfyi="faq" data-slug="..."></div>` | FAQ accordion for common technical questions |
| `guide` | `<div data-rfidfyi="guide" data-slug="..."></div>` | Implementation guide — setup, code examples, best practices |
| `search` | `<div data-rfidfyi="search" data-slug="..."></div>` | Search box linking to the full technology database |
| `epc-decoder` | `<div data-rfidfyi="epc-decoder" data-slug="..."></div>` | EPC barcode decoder — parse GS1 EPC/Gen 2 tags |
| `frequency` | `<div data-rfidfyi="frequency" data-slug="..."></div>` | RFID frequency bands — LF/HF/UHF spectrum visualization |

## Widget Options

| Attribute | Values | Default | Description |
|-----------|--------|---------|-------------|
| `data-rfidfyi` | spec, compare, features, glossary, faq, guide, search, [tools] | required | Widget type |
| `data-slug` | e.g. "tags" | — | Entity slug from the RFIDFYI database |
| `data-theme` | light, dark, sepia, auto | light | Visual theme (`auto` follows OS preference) |
| `data-styleVariant` | technical, modern | technical | Widget design style |
| `data-size` | default, compact, large | default | Widget size |
| `data-placeholder` | any string | "Search RFID Tags…" | Search box placeholder |

## Themes

```html
<!-- Light (default) -->
<div data-rfidfyi="spec" data-slug="tags" data-theme="light"></div>

<!-- Dark -->
<div data-rfidfyi="spec" data-slug="tags" data-theme="dark"></div>

<!-- Sepia -->
<div data-rfidfyi="spec" data-slug="tags" data-theme="sepia"></div>

<!-- Auto — follows OS dark/light preference -->
<div data-rfidfyi="spec" data-slug="tags" data-theme="auto"></div>
```

## Web Components (Custom Elements)

As an alternative to `data-*` attributes, you can use native HTML custom elements:

```html
<!-- Custom element form -->
<rfidfyi-spec slug="tags" theme="light"></rfidfyi-spec>
<rfidfyi-compare slug-a="tags" slug-b="other-slug"></rfidfyi-compare>
<rfidfyi-search placeholder="Search RFID Tags…"></rfidfyi-search>

<script src="https://cdn.jsdelivr.net/npm/rfidfyi-embed@1/dist/embed.min.js"></script>
```

Use `style-variant` (not `style`) to avoid conflicts with the HTML reserved `style` attribute.

## Examples

### Specification Card

```html
<div data-rfidfyi="spec" data-slug="tags" data-theme="light"></div>
<script src="https://cdn.jsdelivr.net/npm/rfidfyi-embed@1/dist/embed.min.js"></script>
```

### Side-by-Side Comparison

```html
<div data-rfidfyi="compare" data-slug-a="tags" data-slug-b="other-slug"></div>
<script src="https://cdn.jsdelivr.net/npm/rfidfyi-embed@1/dist/embed.min.js"></script>
```

### Search Box

```html
<div data-rfidfyi="search" data-placeholder="Search RFID Tags…"></div>
<script src="https://cdn.jsdelivr.net/npm/rfidfyi-embed@1/dist/embed.min.js"></script>
```

### Glossary Term

```html
<div data-rfidfyi="glossary" data-slug="example-term" data-theme="light"></div>
<script src="https://cdn.jsdelivr.net/npm/rfidfyi-embed@1/dist/embed.min.js"></script>
```

## CDN Options

### jsDelivr (recommended — global CDN, auto-updates with npm)

```html
<script src="https://cdn.jsdelivr.net/npm/rfidfyi-embed@1/dist/embed.min.js"></script>
```

### Specific version (production stability)

```html
<script src="https://cdn.jsdelivr.net/npm/rfidfyi-embed@1.0.0/dist/embed.min.js"></script>
```

### npm (for bundlers)

```bash
npm install rfidfyi-embed
```

```javascript
import 'rfidfyi-embed';
```

## Technical Details

- **Shadow DOM**: Complete style isolation — no CSS conflicts with your site
- **Zero dependencies**: No jQuery, React, or any external library
- **JetBrains Mono**: Code blocks use JetBrains Mono loaded from jsDelivr
- **System fonts**: Body text uses system-ui — no extra font requests
- **CORS**: RFIDFYI API has CORS enabled for all origins
- **MutationObserver**: Works with dynamically added elements (SPAs)
- **IntersectionObserver**: Lazy loading — widgets only fetch when entering viewport (200px margin)
- **Bundle size**: ~11–16KB gzipped (per-site build — only includes tools available on RFIDFYI)

## Learn More About RFID Tags

Visit [rfidfyi.com](https://rfidfyi.com) — RFIDFYI is a comprehensive rfid tags technical reference with specifications, standards, interactive tools, and implementation guides.

- **API docs**: [rfidfyi.com/developers/](https://rfidfyi.com/developers/)
- **Widget builder**: [widget.rfidfyi.com](https://widget.rfidfyi.com)
- **npm package**: [npmjs.com/package/rfidfyi-embed](https://www.npmjs.com/package/rfidfyi-embed)
- **GitHub**: [github.com/fyipedia/rfidfyi-embed](https://github.com/fyipedia/rfidfyi-embed)

## Tag FYI Family

Part of [FYIPedia](https://fyipedia.com) — open-source developer tools ecosystem. Tag FYI covers identification, tagging, and wireless communication technologies.

| Site | Domain | Focus | Package |
|------|--------|-------|---------|
| BarcodeFYI | [barcodefyi.com](https://barcodefyi.com) | Barcode formats, EAN, UPC, ISBN, QR, Code 128 standards | [npm](https://www.npmjs.com/package/barcodefyi-embed) |
| QRCodeFYI | [qrcodefyi.com](https://qrcodefyi.com) | QR code generation, scanning, error correction, encoding modes | [npm](https://www.npmjs.com/package/qrcodefyi-embed) |
| NFCFYI | [nfcfyi.com](https://nfcfyi.com) | NFC tags, NDEF records, contactless payments, ISO 14443 | [npm](https://www.npmjs.com/package/nfcfyi-embed) |
| BLEFYI | [blefyi.com](https://blefyi.com) | Bluetooth Low Energy, GATT profiles, beacons, iBeacon, Eddystone | [npm](https://www.npmjs.com/package/blefyi-embed) |
| **RFIDFYI** | [rfidfyi.com](https://rfidfyi.com) | RFID tags, frequency bands, EPC Gen 2, ISO 18000 standards | **[npm](https://www.npmjs.com/package/rfidfyi-embed)** |
| SmartCardFYI | [smartcardfyi.com](https://smartcardfyi.com) | Smart cards, EMV, APDU commands, Java Card, ISO 7816 | [npm](https://www.npmjs.com/package/smartcardfyi-embed) |

## Embed Widget

Embed [RFIDFYI](https://rfidfyi.com) widgets on any website with [rfidfyi-embed](https://widget.rfidfyi.com):

```html
<script src="https://cdn.jsdelivr.net/npm/rfidfyi-embed@1/dist/embed.min.js"></script>
<div data-rfidfyi="entity" data-slug="example"></div>
```

Zero dependencies · Shadow DOM · 4 themes (light/dark/sepia/auto) · [Widget docs](https://widget.rfidfyi.com)

## License

MIT — see [LICENSE](./LICENSE).

Built with care by [FYIPedia](https://fyipedia.com).
