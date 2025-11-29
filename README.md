# Python vCard Generator

A simple, modern Python tool for generating business card QR codes with vCard (3.0/4.0) support, social media, and logo overlay.

---

## Features
- Generates vCard QR codes (v3.0 or v4.0)
- Supports X-SOCIALPROFILE for social media links
- Customizable QR code color, size, and border
- Logo overlay (local file or URL)
- Exports both QR image (PNG) and vCard file (VCF)

---

## Example Usage

```python
from vcard_generator import generate_modern_vcard

personal_data = {
	"first_name": "Alex",
	"last_name": "Smith",
	"position": "Software Engineer",
	"organization": "Tech Innovations",
	"mobile": "+1 555 123 4567",
	"email": "alex.smith@example.com",
	"website": "https://alexsmith.dev",
	"address": "123 Main St;New York;;10001;USA"
}
socials = {
	"linkedin": "https://www.linkedin.com/in/alexsmith",
	"twitter": "https://twitter.com/alexsmith_dev",
	"github": "https://github.com/alexsmith",
	"instagram": "https://instagram.com/alexsmith"
}
img, vcard_txt = generate_modern_vcard(
	personal_data,
	socials,
	qr_color="#1A1A1D",
	logo_path="https://upload.wikimedia.org/wikipedia/commons/thumb/c/c3/Python-logo-notext.svg/1200px-Python-logo-notext.svg.png",
	vcard_version="3.0",
	qr_box_size=12,
	qr_border=2
)
img.save("business_card.png")
with open("business_card.vcf", "w", encoding="utf-8") as f:
	f.write(vcard_txt)
```

---

## Requirements
- Python 3.7+
- `qrcode[pil]`, `requests`, `Pillow`

Install dependencies:
```bash
pip install qrcode[pil] requests
```

---

## Notebook Example
See `vCard-Generator.ipynb` for a ready-to-use Jupyter Notebook example.

---

## License
MIT License