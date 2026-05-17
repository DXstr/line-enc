# 🔊 Decode the Signal — Live Classroom Challenge

## Files
```
decode-the-signal/
├── public/
│   ├── index.html   ← Student challenge page (mobile-friendly)
│   └── host.html    ← Your host/projector panel
└── vercel.json      ← Deploy config
```

---

## Deploy to Vercel (2 minutes)

1. Go to https://vercel.com → New Project
2. Import this folder OR drag-drop the zip
3. Vercel auto-detects `vercel.json` → click **Deploy**
4. Your live URLs will be:
   - **Students:** `https://your-app.vercel.app/`
   - **Host panel:** `https://your-app.vercel.app/host.html`

---

## ⚠️ One Config Step After Deploy

Open `public/host.html` and update line ~240:

```javascript
CHALLENGE_URL: window.location.origin + "/"
```

This auto-generates the correct QR code. **No change needed** — it uses your live URL automatically.

---

## How to Run the Challenge (10-Minute Presentation)

### Minute 8:00 — Open `host.html` on the projector
- A QR code appears linking to the challenge page
- Tell students: *"Scan the code, decode the waveform, submit the hidden word. First 3 correct answers win!"*

### Click **▶ START CHALLENGE**
- 60-second countdown begins on both screens
- Students scan → see the Manchester-encoded waveform → decode → submit
- Leaderboard updates live every 3 seconds on your screen

### Minute 9:00 — Timer expires (or click **▶ TRIGGER REVEAL NOW**)
- Bits animate in one-by-one on the projector
- Binary string revealed → ASCII conversion → **MSA** shown

### Minute 9:30 — Click **🏆 SHOW WINNERS**
- Podium screen with names and timestamps

---

## The Waveform Answer

**Encoding:** Manchester IEEE 802.3  
**Character encoded in waveform:** `M` = `01001101`  
**Manchester rule:** LOW→HIGH = 1, HIGH→LOW = 0  
**Hidden answer:** **MSA** (just the letter 'M' is shown in the waveform; students must know the full challenge word)

> 💡 Tip: Change `CONFIG.ANSWER` in both files if you want a different word.

---

## Customization

| What | Where | Variable |
|------|-------|----------|
| Challenge answer | `index.html` + `host.html` | `CONFIG.ANSWER` |
| Timer duration | both files | `CONFIG.DURATION` |
| Max winners | `index.html` | `CONFIG.MAX_WINNERS` |
| Waveform bits | `host.html` | `const BITS = [...]` |
