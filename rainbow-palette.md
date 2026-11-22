# Rainbow accent 🌈

A thin rainbow strip to be shown at the top of every screen in the app, as a playful accent on top of the Covered AI design system.

| Stripe | Color | Hex |
|---|---|---|
| 1 | Red | `#E5484D` |
| 2 | Orange | `#F76B15` |
| 3 | Yellow | `#F5D90A` |
| 4 | Green | `#2F5D50` (brand sage) |
| 5 | Blue | `#3E63DD` |
| 6 | Purple | `#8E4EC6` |

CSS for the strip:

```css
.rainbow-strip {
  height: 4px;
  background: linear-gradient(90deg, #E5484D, #F76B15, #F5D90A, #2F5D50, #3E63DD, #8E4EC6);
}
```

Status: palette only. The strip is not applied to any screen yet.
