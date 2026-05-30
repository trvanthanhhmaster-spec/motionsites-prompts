# MotionSites Prompts

> [Tiếng Việt bên dưới](#tiếng-việt)

177 AI prompt templates extracted from [motionsites.ai](https://motionsites.ai) — a platform providing AI-generated prompt templates for building modern web interfaces with React, Tailwind CSS, and Framer Motion.

---

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

## Disclaimer

This dataset is extracted from motionsites.ai for archival/research purposes. All prompt content belongs to their respective creators. If you own any of this content and want it removed, open an issue.

---

## Tiếng Việt

177 mẫu prompt AI được trích xuất từ [motionsites.ai](https://motionsites.ai) — nền tảng cung cấp prompt AI để tạo giao diện web hiện đại với React, Tailwind CSS và Framer Motion.

## Dữ Liệu

**`prompts-full.json`** — 1.3MB, 177 mục. Mỗi mục bao gồm:

| Trường | Mô Tả |
|---|---|
| `id` | Mã định danh duy nhất (slug) |
| `title` | Tên hiển thị của prompt |
| `category` | Danh mục (Landing Page, Hero Section, SaaS, v.v.) |
| `type` | Loại component (hero, cta, features, footer, v.v.) |
| `is_free` | Prompt miễn phí hay trả phí |
| `sort_order` | Thứ tự sắp xếp hiển thị |
| `page_type` | Phân loại trang (landing, hero, v.v.) |
| `row_span` | Chiều cao ô lưới trong gallery |
| `image_preview_url` | Ảnh xem trước (Cloudinary) |
| `video_preview_url` | Video xem trước (Mux HLS) |
| `created_at` | Thời gian tạo |
| `prompt_text` | Toàn bộ prompt AI — đặc tả chi tiết dùng để tạo component |

## Danh Mục

34 danh mục trong tổng số 177 prompt:

| Danh Mục | Số Lượng |
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
| Web3, Ecommerce, Dashboard, Signup, Fintech | mỗi loại 2 |
| 404, CTA, Waitlist, Blog, Travel, Automotive, AI, v.v. | mỗi loại 1 |

63 prompt miễn phí, 114 prompt trả phí.

## Cấu Trúc Prompt

Mỗi `prompt_text` là một đặc tả AI chi tiết bao gồm:

- **Stack**: React 19 + Vite + TypeScript + Tailwind CSS 4
- **Hoạt ảnh**: `motion` (Framer Motion v12+) hoặc CSS/scroll-driven thuần
- **Cây component**: Cấu trúc file chính xác (`Hero.tsx`, `App.tsx`, `index.css`)
- **Style**: Bảng màu, import font (Google Fonts, Online Web Fonts), inline styles
- **Tài nguyên**: URL video Mux HLS, URL ảnh Cloudinary
- **Responsive**: Breakpoint tại 768px (mobile/desktop)
- **Hành vi**: Scroll parallax, video state machine, tương tác hover/click

## Ví Dụ

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

## Cách Dùng

Clone repo, dữ liệu nằm trong `prompts-full.json`:

```bash
git clone https://github.com/trvanthanhhmaster-spec/motionsites-prompts.git
```

Truy vấn với jq:

```bash
# Liệt kê danh mục kèm số lượng
jq -r 'group_by(.category) | .[] | "\(.[0].category): \(length)"' prompts-full.json | sort -t: -k2 -rn

# Lấy tất cả prompt miễn phí
jq 'map(select(.is_free == true))' prompts-full.json

# Trích xuất nội dung một prompt cụ thể
jq -r '.[] | select(.id == "layered-depth") | .prompt_text' prompts-full.json
```

## Tuyên Bố

Dữ liệu được trích xuất từ motionsites.ai cho mục đích nghiên cứu/lưu trữ. Toàn bộ nội dung prompt thuộc về các tác giả tương ứng. Nếu bạn sở hữu nội dung trong dataset này và muốn gỡ bỏ, hãy mở issue.
