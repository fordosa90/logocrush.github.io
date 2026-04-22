# Contributing to LogoCrush

## Adding SVG Icons

### Naming Convention
- Use kebab-case matching the product name: `azure-functions.svg`, `power-bi.svg`
- All lowercase, hyphens between words

### SVG Requirements
- `viewBox="0 0 100 100"` — exactly this viewBox
- File size under 10 KB
- No embedded fonts (use `font-family="system-ui, sans-serif"` if needed)
- No raster images embedded
- No proprietary assets

### manifest.json Entry
Add to the `icons` array:
```json
{
  "id": "your-product",
  "name": "Your Product",
  "file": "icons/your-product.svg",
  "tags": ["azure"]
}
```

### Tags
Every icon must have at least one tag:
- `azure` — Azure infrastructure and platform services
- `m365` — Microsoft 365 productivity apps
- `power-platform` — Power BI, Power Apps, Power Automate, Power Pages, Copilot Studio
- `dynamics` — Dynamics 365 business applications
- `security` — Defender, Purview, Sentinel, Entra ID
- `modern-workplace` — Teams, Viva, SharePoint, OneDrive
- `developer` — GitHub, Azure DevOps, Visual Studio Code, Azure Functions
- `data` — Microsoft Fabric, Synapse, Power BI, Purview
- `copilot` — all Copilot-branded products
- `legacy` — retired or rebranded products such as Skype for Business, Cortana

### Minimum Icon Pool
If a tag has fewer than 6 icons, the game silently pads the pool with random icons from other tags to reach the minimum of 6. This means tags with very few icons will mix with icons from other categories. To keep the "Your Cloud" experience pure, aim for at least 6 icons per tag.

### PR Checklist
- [ ] SVG file in `/icons/` directory
- [ ] Entry added to `manifest.json`
- [ ] Icon has at least one valid tag
- [ ] File size under 10 KB
- [ ] viewBox is exactly `0 0 100 100`
- [ ] No embedded fonts or raster images
- [ ] Tested locally (open index.html, verify icon appears in the correct tag filter)
