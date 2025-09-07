# One Piece Card Game Card Data (Unofficial)

This repository contains per-set JSON files scraped from the official One Piece Card Game Card List website. Each file represents a single set and lists all cards in that set as structured JSON objects.

Source: https://en.onepiece-cardgame.com/cardlist/

## What’s included

- One JSON file per set, named by the set code in lowercase with hyphens removed (examples):
  - op01.json, op02.json, …
  - eb01.json, eb02.json, …
  - st01.json, …
- If a set code is not detected, the filename falls back to the numeric series id (e.g., 569901.json).

Each JSON file contains an array of card objects with the following fields:

- series_id: string — Numeric series id used by the site for the set
- set_label: string — Original text of the set option (as shown on the site)
- set_name: string|null — Human-friendly set name
- set_code: string|null — Human set code (e.g., OP11), normalized without hyphens
- dl_id: string — Internal DOM id for the card block
- number: string — Card number printed on the card
- rarity: string — Card rarity
- card_type: string — Card type (e.g., Character, Event, Leader, DON!!)
- name: string — Card name
- image_url: string|null — Absolute URL to the official card image
- image_filename: string|null — Image filename (if downloaded elsewhere)
- attribute: string|null — Attribute text
- attribute_alt: string|null — Attribute alt (from image alt text when present)
- color: string|null — Card color
- block_icon: number|null — Block icon value
- cost: number|null — Cost (for non-Leader cards)
- life: number|null — Life (for Leader cards)
- power: number|null — Power value
- counter: number|null — Counter value
- type_text: string|null — “Feature/Type” text
- effect_text: string|null — Effect text, with line breaks preserved
- sets_text: string|null — Additional set info text (cleaned)

Notes:
- Either `cost` or `life` is set depending on the card (Leader vs others).
- `set_code` is normalized (e.g., [OP-11] → OP11). Filenames use lowercase without hyphens (op11.json).

## Format and structure

- All files are UTF-8 encoded JSON.
- No images are included in this repository; only metadata and image URLs (if available).

## Coverage and freshness

- This is a snapshot of the official site at the time of scraping. See commit history for scrape dates.
- The official site may change content and structure over time.

## Legal / Copyright

- This is an unofficial, non-commercial archival and research dataset.
- All card names, images, trademarks, and related intellectual property are owned by their respective rights holders (including Bandai Co., Ltd., Toei Animation, Shueisha, and others). No affiliation or endorsement is implied.
- The JSON files here contain factual metadata extracted from the publicly accessible Card List website and, where present, public image URLs pointing to the official site. Images themselves are not stored in this repository.
- Use of this dataset should comply with the official site’s Terms of Use and applicable laws (including fair use and database rights where relevant). Do not misrepresent this data as official or complete.
- If you are a rights holder and have concerns, please open an issue or contact the repository owner; we will address removal requests.

## Attribution

When using the data, consider citing the official source:
- One Piece Card Game — Card List: https://en.onepiece-cardgame.com/cardlist/

And this dataset (commit or release tag), if applicable.

## Disclaimer

Provided “as is”, without warranties or guarantees of accuracy or completeness. The maintainers are not responsible for downstream use.
