# 🍛 FoodMatch India — Tinder-Style Restaurant Matcher

> Stop the endless *"where do you want to eat?"* debate. Everyone swipes — first match wins.

[![Live Demo](https://img.shields.io/badge/Live%20Demo-Open%20App-orange?style=for-the-badge)](https://AASTHA381.github.io/tinder-style-restaurant-matcher/)

---

## What is FoodMatch?

FoodMatch is a **single-file web app** that lets a group of friends swipe on nearby restaurants simultaneously — Tinder-style. When enough people like the same place, it's a match! 🎉

Built specifically for **India** — with 12 city demos, Indian cuisine categories, ₹ budgets, and real restaurant data.

---

## Features

- **Tinder-style swipe** — drag left (nope) or right (like) on restaurant cards
- **Group matching (2 to N people)** — pick a rule: *Majority agree* or *Everyone agrees*; host taps **Start** when everyone's in
- **Real-time matching** — the moment the group threshold is hit, confetti fires; if the deck runs out, the host reveals the most-liked "top pick"
- **Live restaurant data** — OpenStreetMap (Overpass API), free, no key needed
- **Works across ANY network** — MQTT-over-WebSocket global bus (no NAT/TURN needed), plus WebRTC (PeerJS) for low-latency same-network play
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
3. Wait for restaurants to load, then click **🧪 Open Demo Tab** (once per extra player)
4. Each tab appears in the roster → host clicks **▶️ Start Swiping** → first match wins!

### Different devices / different networks (group of friends)
1. Open the live URL (see **Deploy** below) on every phone
2. **Host**: Create a Room → choose the match rule → share the 6-letter code
3. **Everyone else**: Join a Room → enter the code
4. When all are in the roster, the host taps **▶️ Start Swiping** — sync runs over MQTT, so it works on any Wi-Fi or mobile data 🌍

---

## Deploy

### Permanent hosting — GitHub Pages (recommended)

The repo already contains `index.html` at the root, so GitHub Pages just works. **A repo admin (owner)** enables it once:

1. Repo → **Settings** → **Pages**
2. **Source**: *Deploy from a branch*
3. **Branch**: `main`, folder: `/ (root)` → **Save**

Or, with the GitHub CLI as an admin:

```bash
gh api -X POST repos/AASTHA381/tinder-style-restaurant-matcher/pages \
  -f "source[branch]=main" -f "source[path]=/"
```

Within ~1 minute the app is live (and stays live — no server needed) at:

**https://AASTHA381.github.io/tinder-style-restaurant-matcher/**

Every future `git push origin main` redeploys automatically.

### Quick share — Netlify Drop

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
| Cross-network sync | [MQTT.js](https://github.com/mqttjs/MQTT.js) over WebSocket (public broker) |
| Same-network sync | [PeerJS](https://peerjs.com/) (WebRTC) |
| Same-device sync | BroadcastChannel API + localStorage |
| Swipe gestures | Custom touch + mouse drag |
| Match animation | CSS confetti |

---

## Project Structure

```
foodmatch.html    ← entire app (HTML + CSS + JS in one file)
index.html        ← identical copy, served by GitHub Pages
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

- [x] Group mode (3+ people)
- [x] Reliable cross-network sync (MQTT over WebSocket)
- [ ] Real restaurant photos (Google Places API)
- [ ] Private broker + locked room codes
- [ ] Share match result card

---

## License

MIT — free to use, modify, and share.
