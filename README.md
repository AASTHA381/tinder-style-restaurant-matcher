# 🍛 FoodMatch India — Tinder-Style Restaurant Matcher

> Stop the endless *"where do you want to eat?"* debate. Both swipe. First match wins.

[![Live Demo](https://img.shields.io/badge/Live%20Demo-Open%20App-orange?style=for-the-badge)](https://AASTHA381.github.io/tinder-style-restaurant-matcher/foodmatch.html)

---

## What is FoodMatch?

FoodMatch is a **single-file web app** that lets two people swipe on nearby restaurants simultaneously — Tinder-style. When both swipe right on the same place, it's a match! 🎉

Built specifically for **India** — with 12 city demos, Indian cuisine categories, ₹ budgets, and real restaurant data.

---

## Features

- **Tinder-style swipe** — drag left (nope) or right (like) on restaurant cards
- **Real-time matching** — the moment both people like the same place, confetti fires
- **Live restaurant data** — OpenStreetMap (Overpass API), free, no key needed
- **Cross-device play** — WebRTC peer-to-peer via PeerJS (works on different phones/laptops)
- **Same-device demo** — BroadcastChannel + localStorage for instant same-browser testing
- **12 Indian cities** — Hyderabad, Mumbai, Delhi, Bangalore, Chennai, Kolkata, Pune, Jaipur, Goa, Kochi, Chandigarh, Ahmedabad
- **14 cuisine filters** — North Indian, South Indian, Biryani, Mughlai, Chinese, Cafe, Street Food, and more
- **Reddit reviews** — tap ℹ on any card for Reddit-sourced opinions
- **Budget filter** — ₹50 to ₹3,000 per person
- **Zero setup** — single HTML file, no install, no server required

---

## How to Play

### Same device (demo)
1. Open `foodmatch.html` in Chrome/Firefox
2. Click **Create a Room** → set your city and preferences → **Create Room**
3. Wait for restaurants to load, then click **🧪 Open Demo Tab**
4. Both tabs swipe independently — first mutual like wins!

### Different devices (same Wi-Fi or mobile data)
1. Deploy to any static host (see below)
2. **Device 1**: Open the URL → Create a Room → note the 6-letter code
3. **Device 2**: Open same URL → Join a Room → enter the code
4. Both swipe — WebRTC connects automatically 🌐

---

## Deploy in 30 Seconds (Netlify Drop)

1. Go to [netlify.com/drop](https://app.netlify.com/drop)
2. Drag and drop `foodmatch.html`
3. Get a shareable live URL instantly — no account needed

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| UI | Vanilla HTML/CSS/JS — single file, no frameworks |
| Restaurant data | [Overpass API](https://overpass-api.de/) (OpenStreetMap) |
| Geocoding | [Nominatim](https://nominatim.org/) |
| Cross-device sync | [PeerJS](https://peerjs.com/) (WebRTC) |
| Same-device sync | BroadcastChannel API + localStorage |
| Swipe gestures | Custom touch + mouse drag |
| Match animation | CSS confetti |

---

## Project Structure

```
foodmatch.html    ← entire app (HTML + CSS + JS in one file)
README.md
```

---

## Contributors

| | |
|--|--|
| **AASTHA381** | Creator & developer |
| **karan68** | Contributor |

---

## Roadmap

- [ ] Firebase backend for reliable cross-device sync on all networks
- [ ] Real restaurant photos (Google Places API)
- [ ] Group mode (3+ people)
- [ ] Share match result card

---

## License

MIT — free to use, modify, and share.
