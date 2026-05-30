# MotionSites Prompts

177 AI prompt templates extracted from [motionsites.ai](https://motionsites.ai) — a platform providing AI-generated prompt templates for building modern web interfaces with React, Tailwind CSS, and Framer Motion.

## Dataset

**`prompts-full.json`** — 1.3MB, 177 entries. Each entry includes:

| Field | Description |
|---|---|
| `id` | Unique slug identifier |
| `title` | Prompt display name |
| `category` | Category (Landing Page, Hero Section, SaaS, etc.) |
| `type` | Component type (hero, cta, features, footer, etc.) |
| `is_free` | Whether the prompt is free or paid |
| `sort_order` | Display ordering |
| `page_type` | Page classification (landing, hero, etc.) |
| `row_span` | Grid row span in the gallery |
| `image_preview_url` | Preview image (Cloudinary) |
| `video_preview_url` | Preview video (Mux HLS) |
| `created_at` | Timestamp of creation |
| `prompt_text` | Full AI prompt — the actual specification used to generate the component |

## Categories

34 categories across 177 prompts:

| Category | Count |
|---|---|
| Landing Page | 38 |
| Hero Section | 35 |
| SaaS | 26 |
| Hero | 20 |
| Agency | 9 |
| Footer Section | 5 |
| Portfolio | 5 |
| Features Section | 4 |
| Social Media | 3 |
| Pricing | 3 |
| Web3, Ecommerce, Dashboard, Signup, Fintech | 2 each |
| 404, CTA, Waitlist, Blog, Travel, Automotive, AI, and more | 1 each |

63 prompts are free, 114 are paid.

## Prompt Structure

Each `prompt_text` is a detailed AI specification covering:

- **Stack**: React 19 + Vite + TypeScript + Tailwind CSS 4
- **Animation**: `motion` (Framer Motion v12+) or native CSS/scroll-driven
- **Component tree**: Exact file structure (`Hero.tsx`, `App.tsx`, `index.css`)
- **Styling**: Color palette, font imports (Google Fonts, Online Web Fonts), inline styles
- **Assets**: Mux HLS video URLs, Cloudinary image URLs
- **Responsive**: Breakpoints at 768px (mobile/desktop)
- **Behavior**: Scroll parallax, video state machines, hover/click interactions

## Example

```json
{
  "id": "layered-depth",
  "title": "Layered Depth",
  "category": "Landing Page",
  "type": "hero",
  "is_free": false,
  "video_preview_url": "https://stream.mux.com/1mqmhNvssKWJ7we02vIVi8zp0100t83TvYxGepZ55ETYf4.m3u8",
  "prompt_text": "Create a React + Vite + TypeScript + Tailwind CSS landing page..."
}
```

## Usage

Clone the repo, the data is in `prompts-full.json`:

```bash
git clone https://github.com/trvanthanhhmaster-spec/motionsites-prompts.git
```

Parse with jq:

```bash
# List all categories with counts
jq -r 'group_by(.category) | .[] | "\(.[0].category): \(length)"' prompts-full.json | sort -t: -k2 -rn

# Get all free prompts
jq 'map(select(.is_free == true))' prompts-full.json

# Extract a specific prompt's full text
jq -r '.[] | select(.id == "layered-depth") | .prompt_text' prompts-full.json
```

## Tools

The companion repo [motionsites-tools](https://github.com/trvanthanhhmaster-spec/motionsites-tools) contains scripts to fetch and sync this data directly from the motionsites.ai API.

## Disclaimer

This dataset is extracted from motionsites.ai for archival/research purposes. All prompt content belongs to their respective creators. If you own any of this content and want it removed, open an issue.
