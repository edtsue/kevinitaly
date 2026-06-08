# Athens → Milan · Kevin & Jace (June 2026)

A phone-first, single-file trip hub for a mythology-loving family trip:
**Athens → Naples → Rome → Bologna → Milan**, 8–23 June 2026.

- **Mythology-first**: open-air ancient sites over museums (Acropolis, Mycenae & the Lion Gate, Epidaurus, Delphi, Pompeii, Paestum's Greek temples, Ostia Antica, the Appian Way).
- **Iconic food + shopping** woven into every city.
- Day-by-day itinerary, month calendar, city guides, packing/booking checklists, Greek + Italian phrases, weather.

## Tech
- **One file**: `index.html` (HTML + CSS + JS), Tailwind via CDN, Google Fonts.
- **No accounts, no cloud, no API keys.** All data (checklists, bookings) is saved in your browser's `localStorage` only.
- **No Supabase, no Vercel.** Export/Import in Settings moves your data between devices.
- Installable as a PWA (offline) via `manifest.webmanifest` + `sw.js`.

## Run it
Just open `index.html` in any browser. On your phone: open the page, then
**Share → Add to Home Screen** (iOS) or **menu → Install app** (Android).

For the service worker / PWA to work, serve over http rather than `file://`:
```
cd kevinitaly
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploy (free, no Vercel)
Use **GitHub Pages**: repo **Settings → Pages → Source: `main` / root**.
Your app will be live at `https://<username>.github.io/kevinitaly/`.

## Customise
All trip content lives in clearly-labelled data blocks near the top of the
`<script>` in `index.html`: `TRIP`, `SEED_TIPS`, `SHOPS_BY_CITY`,
`FOODS_BY_CITY`, `MICHELIN_BY_CITY`, `BOOKINGS_CATALOG`, `GREEK_PHRASES`,
`ITALIAN_PHRASES`, `CITY_COORDS`, `JUNE_CLIMATE`, `SHOP_ROUTES`.
To change dates, edit each day's `date`/`weekday` in `TRIP` and the
`JUNE 2026` block in `renderCalendar()`.
