# SkyMoon Cloud visual identity

SkyMoon Cloud is built on a fork of Apache CloudStack. This initial change applies
SkyMoon branding to the existing Vue UI without changing CloudStack's API,
virtualization, networking, or resource management internals.

## Brand source

Existing, user-supplied brand files and design tokens were reused from the
private `SkyMoonTechnologies/SkyMoonTech` repository.

| Asset | Original SkyMoonTech source | Destination |
| --- | --- | --- |
| Full SkyMoon logo | `public/skymoonlogo.png` | `ui/public/assets/skymoon/skymoonlogo.png` |
| Square product mark | `public/icon-192.png` | `ui/public/assets/skymoon/icon-192.png` |
| Small favicon | `public/favicon.png` | `ui/public/assets/skymoon/favicon.png` |
| 48px favicon | `public/favicon-48.png` | `ui/public/assets/skymoon/favicon-48.png` |

Theme colors originate from the CSS HSL design tokens in
`SkyMoonTech/app/globals.css`. In particular:

- Primary blue: `#0B4B6F` (202 82% 24%)
- Canvas background: `#F5F7FA` (210 29% 97%)
- Dark background: `#101419` (214 24% 8%)
- Body ink: `#0C0F13` (214 24% 6%)
- Muted text: `#44516A` (219 22% 34%)
- Border: `#E1E5EA` (213 18% 90%)

No AI-generated images, artwork, or icons were used.

## Changed UI files

- `ui/public/config.json`: resource references, UI titles, light-theme tokens
- `ui/public/index.html` and `ui/index.html`: page title and favicon
- `ui/src/components/header/Logo.vue`: responsive existing-logo wordmark
- `ui/src/layouts/UserLayout.vue`: branded login identity
- `ui/src/style/vars.less`: matching fallback theme values

## Run and test

```bash
cd ui
npm ci
npm run lint
npm run build
```

See `ui/README.md` for details on running the frontend against a
CloudStack management server. Branding edits do not automatically configure
customer sign-up or multi-tenant product provisioning.

## Attribution and licensing

Apache CloudStack remains governed by its Apache License 2.0, with upstream
copyright notices, license files, and attribution retained. SkyMoon brand
artwork is derived from SkyMoonTech; do not mistake it for ASF artwork.
