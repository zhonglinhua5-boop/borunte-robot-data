# Data dictionary — borunte-robots.json

Top level:

| Field | Type | Meaning |
| --- | --- | --- |
| `dataset` | string | Human-readable dataset title |
| `publisher` | string | Publisher domain (borunteofficial.com) |
| `license` | string | CC BY 4.0 |
| `count` | integer | Number of model objects |
| `payload_range_kg` | [min, max] | Payload range across all models |
| `reach_range_mm` | [min, max] | Reach range across all models |
| `updated` | date (YYYY-MM-DD) | Last time the file was regenerated from the product pages |
| `models` | array | One object per robot model |

Each object in `models`:

| Field | Type | Meaning | Null allowed |
| --- | --- | --- | --- |
| `model` | string | Model code as printed on the product page, e.g. `BRTIRPZ1508A` | no |
| `series` | string | Product line, e.g. `Six-axis robot`, `Palletizing workstation` | yes |
| `axes` | integer | Number of axes | yes |
| `payload_kg` | number | Rated payload at flange, kg | yes |
| `reach_mm` | number | Maximum reach, mm | yes |
| `repeatability_mm` | number | Positional repeatability, ±mm | yes |
| `applications` | array of string | Applications named on the product page | yes |
| `price_usd` | number | Published list price, USD, single unit EXW. Not a quotation | yes |
| `url` | string | Canonical product page on borunteofficial.com | no |
| `source_note` | string | Where the values come from | no |

`null` means the manufacturer has not published a verified value; it is never an estimate.
