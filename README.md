# Playable Rewarded VAST

VAST tags for rewarded video ads with interactive HTML5 playable endcards.

## VAST Tag URLs

### Recommended (Most Compatible)
```
https://djlord7.github.io/playable-rewarded-vast/vast_rewarded_best.xml
```

### All Available Tags

| File | URL | Description |
|------|-----|-------------|
| **vast_rewarded_best.xml** | [Link](https://djlord7.github.io/playable-rewarded-vast/vast_rewarded_best.xml) | **Recommended** - Minified HTML, most SDK compatible |
| vast_rewarded_playable.xml | [Link](https://djlord7.github.io/playable-rewarded-vast/vast_rewarded_playable.xml) | Full HTML with readable code (same as best, just formatted) |
| vast_rewarded_iframe_endcard.xml | [Link](https://djlord7.github.io/playable-rewarded-vast/vast_rewarded_iframe_endcard.xml) | Uses external HTML URL via IFrame (less compatible) |

## What's Included

### Video
- **Source**: `https://djlord7.github.io/simid-demo/cookingVideo.mp4`
- **Duration**: 15 seconds
- **Resolution**: 1920x1080

### Playable Endcard
- Interactive HTML5 mini-game (tap-to-cook)
- Score counter with food emoji changes
- MRAID-compatible `mraid.open()` with `window.open()` fallback
- Portrait (320x480) and Landscape (480x320) variants

## VAST Structure

```
VAST 3.0
├── Ad
│   └── InLine
│       ├── Impression tracking
│       └── Creatives
│           ├── Creative (sequence 1): Linear Video
│           │   ├── Duration: 00:00:15
│           │   ├── TrackingEvents (start, quartiles, complete)
│           │   ├── VideoClicks (ClickThrough)
│           │   └── MediaFiles (MP4)
│           │
│           └── Creative (sequence 2): CompanionAds
│               ├── Companion 320x480 (Portrait HTML)
│               └── Companion 480x320 (Landscape HTML)
```

## SDK Compatibility

| SDK | Video | HTML Endcard | Expected Result |
|-----|-------|--------------|-----------------|
| Google Mobile Ads | ✅ | ✅ | Full support |
| AppLovin MAX | ✅ | ⚠️ | Video works, endcard may vary |
| IronSource | ✅ | ✅ | Full support |
| Unity Ads | ✅ | ⚠️ | Video works, endcard limited |

## Usage in GAM

1. Create a **Video line item** in Google Ad Manager
2. Add a **VAST redirect** creative
3. Paste the VAST tag URL
4. Target your rewarded ad unit

## Testing

Validate your VAST:
- [Google VAST Inspector](https://developers.google.com/interactive-media-ads/docs/sdks/html5/vastinspector)
- [IAB VAST Validator](https://vastvalidator.iabtechlab.com/)

## Playable Endcard Features

- 🍳 Tap the circle to "cook" and earn points
- 🎲 Food emoji changes randomly on each tap
- 📱 INSTALL FREE button triggers app store
- 📐 Responsive design for portrait and landscape

## Flow

```
User opts-in for reward
        ↓
Video plays (15 seconds)
        ↓
Video completes
        ↓
HTML5 Playable Endcard appears
        ↓
User interacts (tap to cook)
        ↓
User taps INSTALL → App Store
        ↓
Reward granted
```

## License

MIT
