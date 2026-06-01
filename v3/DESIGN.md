# DESIGN.md — Moon Phase PWA

## Colors
Background: #050810 | Accent: #E09DFF | Text: #ffffff | Card: rgba(255,255,255,0.05)

## Typography
Font: Jost (Google Fonts) | Headings: bold | Body: regular

## Atmosphere
Dark space aesthetic. Minimal UI. No clutter.
Glassmorphism cards with subtle borders.
CSS starfield + nebula in background.

## Decisions
- SunCalc.js via cdnjs CDN — not local
- moon.jpg bundled locally (hotlinking Wikipedia was blocked)
- SVG phase masking with terminator tilt angle from SunCalc
- Geolocation: browser API → ipapi.co fallback → Tel Aviv default
- Nav pills: Today | Month (Week removed — no lunar use case)
- PWA installable: icon-192.png + icon-512.png required (at root of v3/)
- Flying moon transition: Today → Month (shared element, spring easing)
- Moonrise transition: Month → Today (view rises translateY 28px → 0)
- Stagger entry: phaseSection → countdown → cards (55ms delay each)
- CSS grid overlay on #viewContainer — both views always in DOM for correct rects
- Full moon reminder: Notification API native, no backend, fires on app open
- Location sheet: GPS + city search via open-meteo geocoding API
