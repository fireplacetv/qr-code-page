# QR Code Generator

A simple, fast QR code generator that creates QR codes for any URL. Perfect for event tickets, registration links, or any scenario where you need to encode a URL as a QR code.

**Live:** https://fireplacetv.github.io/qr-code-page/

## Features

- 🎯 Generate QR codes for any URL
- 📝 Support for URLs with existing query parameters
- 🔗 Generate shareable links to QR codes
- 📋 Copy-to-clipboard functionality
- 🎨 Clean, modern UI with examples
- ⚡ Fast, client-side generation (no server required)

## Usage

### Web Interface

Visit the live site and use the form to generate QR codes:
https://fireplacetv.github.io/qr-code-page/

1. Enter any URL in the form
2. Click "Generate QR Code Link"
3. Click "Get QR Code" to view the PNG or "Copy Link" to share it

### Direct URL Encoding

You can also directly encode a URL as a query parameter:

```
https://fireplacetv.github.io/qr-code-page/?url=<encoded-url>
```

The `url` parameter must be URL-encoded. Use these character replacements:

| Character | Encoding |
|-----------|----------|
| `:` | `%3A` |
| `/` | `%2F` |
| `?` | `%3F` |
| `=` | `%3D` |
| `&` | `%26` |
| `#` | `%23` |

### Examples

**Simple URL:**
```
?url=https%3A%2F%2Fexample.com
```

**URL with parameters:**
```
?url=https%3A%2F%2Fdomain.com%3Ffirst_option%3Dabc%26second_option%3Ddef
```

**Event registration:**
```
?url=https%3A%2F%2Fevents.example.com%2Fregister%3Fticket_id%3DTICKET_001
```

## How It Works

- When you visit the page without a `url` parameter, it displays documentation and a form
- When you visit with a `url` parameter, it generates and displays a QR code PNG
- The QR code is generated client-side using the [QRCode.js](https://davidshimjs.github.io/qrcodejs/) library
- ZIP file downloads use [JSZip](https://stuk.github.io/jszip/)

## Technical Details

- **No backend required** — runs entirely in the browser
- **No tracking** — all processing happens client-side
- **No dependencies** — external libraries are loaded from CDN
- **Responsive design** — works on mobile, tablet, and desktop

## Privacy

**You can trust this page to generate QR codes privately:**

- ✅ All QR code generation happens client-side in your browser
- ✅ No data is sent to any server (no API calls or form submissions)
- ✅ No telemetry, analytics, or tracking code
- ✅ Tokens and URLs never leave your device
- ✅ Downloads are local (blob URLs, no server involvement)

**Minor caveats:**
- External libraries are loaded from CDN (Cloudflare) — this creates visible network requests in browser history
- Network observers could see you're using this tool but not what QR codes you generate

**Bottom line:** Safe for private token generation and event management workflows. All sensitive data stays on your device.

## Deployment

This project is deployed to GitHub Pages automatically via GitHub Actions on every push to `main`.

See `.github/workflows/static.yml` for the deployment configuration.

## Libraries

- [QRCode.js](https://davidshimjs.github.io/qrcodejs/) - QR code generation
- [JSZip](https://stuk.github.io/jszip/) - ZIP file creation (for bulk downloads)

## License

Open source. Feel free to use, modify, and distribute.

## Contributing

Contributions are welcome! Feel free to fork, make improvements, and submit pull requests.
