# Playable Rewarded VAST

VAST tags for rewarded video ads with interactive HTML5 playable endcards.

## VAST Tag URL

```
https://djlord7.github.io/playable-rewarded-vast/vast_rewarded_playable.xml
```

## What's Included

### Video
- **Source**: `https://djlord7.github.io/simid-demo/cookingVideo.mp4`
- **Duration**: 15 seconds
- **Resolution**: 1920x1080

### Playable Endcard
- Interactive HTML5 mini-game
- Tap-to-cook mechanic with score counter
- MRAID-compatible `install()` function
- Portrait (320x480) and Landscape (480x320) variants
- Static fallback for non-MRAID environments

## Structure

```
VAST 3.0
├── Video Creative (sequence 1)
│   └── MediaFile: cookingVideo.mp4
└── CompanionAds (sequence 2)
    ├── HTML Playable (320x480) - Portrait
    ├── HTML Playable (480x320) - Landscape
    └── Static Fallback (320x480)
```

## Usage in GAM

1. Create a Video line item
2. Use VAST redirect or paste the VAST tag URL
3. Target your rewarded ad unit

## Testing

Use a VAST validator or test in your app:
- [Google VAST Inspector](https://developers.google.com/interactive-media-ads/docs/sdks/html5/vastinspector)
- [IAB VAST Validator](https://vastvalidator.iabtechlab.com/)

## Playable Features

- Tap the circle to "cook" and earn points
- Food emoji changes randomly on each tap
- INSTALL FREE button triggers `mraid.open()` or `window.open()` fallback
- Responsive design for portrait and landscape

## License

MIT
