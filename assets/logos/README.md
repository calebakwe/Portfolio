# Organisation logos

Add a logo file to this folder with one of the names below, and it shows up everywhere that organisation appears on the site. Until a logo is added, the client and training cards show plain initials or an icon, and nothing shows in the other places.

## Adding logos on github.com

1. Open this folder (`assets/logos`) in the repository.
2. Choose **Add file → Upload files**, drop the files in, and press **Commit changes**.
3. The site updates on its own a minute or two later.

To remove a logo, delete its file the same way.

## Which file to use

- **Format:** `.svg` is best. A `.png` or `.webp` with a transparent background, at least 120 px tall, also works. A `.jpg` is fine if the logo sits on white.
- **Colour version:** use the full-colour logo made for **white** backgrounds. Each logo is shown on a small white tile, so an all-white logo would be invisible.
- **Name:** the name before the extension must match the list, e.g. `world-bank.png`. If both `world-bank.svg` and `world-bank.png` exist, the `.svg` is used.
- **Shape:** wide logos and square emblems both fit. Very long wordmarks are shrunk to fit their tile.

## File names

| File name | Organisation | Appears in |
|---|---|---|
| `unhcr` | UNHCR | Clients, Projects, Experience |
| `world-bank` | World Bank Group | Clients, Projects, Experience |
| `concern-worldwide` | Concern Worldwide | Clients, Projects, Experience |
| `cws` | Church World Service (CWS) | Clients, Projects, Experience |
| `world-vision` | World Vision Kenya | Clients, Projects, Experience |
| `nia` | National Irrigation Authority | Clients, Projects, Experience |
| `wra` | Water Resources Authority | Clients, Projects, Experience |
| `wstf` | Water Sector Trust Fund | Clients, Projects, Experience |
| `lvswwda` | Lake Victoria South Water Works Development Agency | Clients, Experience |
| `mantrac` | Mantrac Kenya | Clients, Experience |
| `rhines` | Rhines Engineering Services | Clients, Projects, Experience |
| `welle` | Welle Group | Clients, Projects, Experience |
| `ministry-of-water` | Ministry of Water, Sanitation & Irrigation | Projects, Experience |
| `smec` | SMEC International | Projects, Experience |
| `nuist` | Nanjing University of Information Science & Technology | Projects, Experience |
| `jkuates` | JKUAT Enterprises Services Ltd (JKUATES) | Projects, Experience |
| `pwrdf` | PWRDF | Projects |
| `cfgb` | Canadian Foodgrains Bank (CFGB) | Projects |
| `marsabit-county` | Marsabit County Government | Projects |
| `danida` | DANIDA | Projects |
| `jkuat` | Jomo Kenyatta University of Agriculture and Technology | Projects, Education |
| `cisco` | Cisco | Education |
| `kisumu-boys` | Kisumu Boys' High School | Education |
| `caterpillar` | Caterpillar | Training, Education |
| `ewb-uk` | Engineers Without Borders UK | Training |
| `kpmg` | KPMG | Training |
| `ge` | General Electric (GE) | Training |
| `goldman-sachs` | Goldman Sachs | Training |
| `deloitte` | Deloitte | Training |
| `huawei` | Huawei | Training |
| `new-kpcu` | New KPCU | Training |
| `coffee-research-institute` | Coffee Research Institute | Training |
| `ebk` | Engineers Board of Kenya | About (registration card) |

## Permission

Logos belong to their organisations. Many allow you to show their logo to name a client or employer, but some restrict it, including UN agencies, the World Bank, and Kenyan government bodies that use the national coat of arms. Check each organisation's brand guidelines, or ask your contact there, before adding those.

## How it works

When the site is published to GitHub Pages, the deploy workflow (`.github/workflows/static.yml`) writes `manifest.json` here, listing the logo files. The page reads that list. On hosts that skip that step (Netlify, Vercel, or a local preview), the page asks GitHub for the folder's file list instead. You don't need to create or edit `manifest.json` yourself.
