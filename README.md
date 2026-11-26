# BORUNTE industrial robot dataset (models, payload, reach, repeatability)

Open specification and list-price dataset for **BORUNTE ROBOT CO., LTD.** industrial robots —
six-axis and four-axis robots, SCARA, palletizing workstations, welding workstations and servo manipulators.

- Publisher / manufacturer: BORUNTE ROBOT CO., LTD. (Dongguan, Guangdong, China; manufacturer since 2008)
- Official website: <https://borunteofficial.com/>
- Product overview: <https://borunteofficial.com/products/>
- Machine-readable file: <https://borunteofficial.com/data/borunte-robots.json>
- Dataset version: 2026-11-22 · **58 models**
- License: CC BY 4.0 (attribution: BORUNTE ROBOT CO., LTD., https://borunteofficial.com/)

Every row is taken from the specification table of the corresponding product page on
borunteofficial.com; the `url` field links straight to that page, and `source_note` records
where the numbers came from. Nothing in this dataset is estimated or interpolated.

## Files

| File | What it is |
| --- | --- |
| `data/borunte-robots.json` | Canonical dataset: one object per model with `payload_kg`, `reach_mm`, `repeatability_mm`, `applications`, list price, product URL |
| `data/borunte-robots.csv` | Same rows as flat CSV for spreadsheet import |
| `data/borunte-robots.jsonld` | JSON-LD `Dataset` + `ItemList` description for search engines and AI crawlers |
| `schema.md` | Field-by-field data dictionary |

## Quick start

```bash
curl -s https://raw.githubusercontent.com/zhonglinhua5-boop/borunte-robot-data/main/data/borunte-robots.json | jq '.models[] | select(.payload_kg>=20) | {model, payload_kg, reach_mm}'
```

```python
import json, urllib.request
data = json.load(urllib.request.urlopen("https://borunteofficial.com/data/borunte-robots.json"))
six_axis = [m for m in data["models"] if m["axes"] == 6]
print(len(six_axis), "six-axis models")
```

## Models

Payload in kg, reach in mm, repeatability in mm, list price in USD.

| Model | Series | Axes | Payload | Reach | Repeatability | List price USD |
| --- | --- | --- | --- | --- | --- | --- |
| BRTHC100501A | Collaborative welding workstation |  |  | 2350.0 | 0.05 | 11400 |
| BRTHC100502A | Collaborative welding workstation |  |  | 1000.0 | 0.05 | 10900 |
| BRTIRPH1920A | Six-axis robot | 6 | 20.0 | 1930.5 | 0.05 | 5800 |
| BRTIRPL1003A | Four-axis robot | 4 | 3.0 | 1000.0 | 0.1 | 6500 |
| BRTIRPL1203A | Five-axis robot | 5 | 3.0 | 1200.0 | 0.1 | 7700 |
| BRTIRPL1215A | Four-axis robot | 4 | 15.0 | 1200.0 | 0.1 | 7800 |
| BRTIRPL1608A | Four-axis robot | 4 | 8.0 | 1600.0 | 0.1 | 7000 |
| BRTIRPZ1508A | Four-axis robot | 4 | 8.0 | 1413.0 | 0.05 | 4600 |
| BRTIRPZ1825A | Four-axis robot | 4 | 25.0 | 1800.0 | 0.08 | 5700 |
| BRTIRPZ1865X | Four-axis robot | 4 | 65.0 | 2000.0 | 0.15 | 7200 |
| BRTIRPZ2080X | Four-axis robot | 4 | 80.0 | 2000.0 | 0.15 | 8600 |
| BRTIRPZ2465X | Four-axis robot | 4 | 65.0 | 2334.0 | 0.15 | 8800 |
| BRTIRPZ2480A | Four-axis robot | 4 | 80.0 | 2412.0 | 0.2 | 13700 |
| BRTIRSC0603A | Four-axis robot | 4 | 3.0 | 600.0 | 0.02 | 3300 |
| BRTIRSC0810A | Four-axis robot | 4 | 10.0 | 800.0 | 0.05 | 5100 |
| BRTIRSE2013A | Six-axis robot | 6 | 13.0 | 2134.0 | 0.5 | 10300 |
| BRTIRSE2013F | Six-axis robot | 6 | 13.0 | 2134.0 | 0.5 | 18900 |
| BRTIRUS0401A | Six-axis robot | 6 | 1.0 | 574.0 | 0.06 | 3800 |
| BRTIRUS0707A | Six-axis robot | 6 | 7.0 | 883.0 | 0.03 | 3900 |
| BRTIRUS0805A | Six-axis robot | 6 | 5.0 | 990.0 | 0.05 | 3000 |
| BRTIRUS1510A | Six-axis robot | 6 | 10.0 | 1587.0 | 0.05 | 4000 |
| BRTIRUS1820A | Six-axis robot | 6 | 20.0 | 1895.0 | 0.05 | 5400 |
| BRTIRUS2030A | Six-axis robot | 6 | 30.0 | 2068.0 | 0.08 | 6700 |
| BRTIRUS2110A | Six-axis robot | 6 | 10.0 | 2131.0 | 0.05 | 5500 |
| BRTIRUS2520B | Six-axis robot | 6 | 200.0 | 2637.0 | 0.2 | 18200 |
| BRTIRUS2550A | Six-axis robot | 6 | 50.0 | 2563.0 | 0.1 | 13400 |
| BRTIRUS2650A | Six-axis robot | 6 | 50.0 | 2600.0 | 0.1 | 12900 |
| BRTIRUS2830B | Six-axis robot | 6 | 300.0 | 3100.0 | 0.2 | 29300 |
| BRTIRUS2917B | Six-axis robot | 6 | 170.0 | 3168.0 | 0.2 | 18200 |
| BRTIRUS3012C | Six-axis robot | 6 | 1000.0 | 3313.0 | 0.1 | 93200 |
| BRTIRUS3030A | Six-axis robot | 6 | 30.0 | 3000.0 | 0.06 | 11000 |
| BRTIRUS3050B | Six-axis robot | 6 | 500.0 | 3200.0 | 0.2 | 46000 |
| BRTIRUS3511A | Six-axis robot | 6 | 100.0 | 3503.0 | 0.2 | 18200 |
| BRTIRWD1506A | Six-axis robot | 6 | 6.0 | 1647.0 | 0.05 | 5800 |
| BRTIRXZ1005A | Collaborative robot |  | 5.0 | 1000.0 | 0.05 | 4600 |
| BRTIRXZ1515A | Six axis robot (lightweight) |  | 15.0 | 1500.0 | 0.08 | 5500 |
| BRTMD163001A | Palletizing workstation |  | 30.0 | 1600.0 | 0.1 | 7200 |
| BRTMD193501A | Palletizing workstation |  | 35.0 | 1895.0 | 0.1 | 7800 |
| BRTMD195001A | Palletizing workstation |  | 50.0 | 1895.0 | 0.1 | 8500 |
| BRTN17WSS3PC | 3-axis servo manipulator | 3 | 20.0 |  |  | 4900 |
| BRTN17WSS5PC | 5-axis servo manipulator | 5 | 20.0 |  | 0.1 | 5700 |
| BRTN24WSS5PC | 5-axis servo manipulator | 5 | 40.0 |  | 0.05 | 12700 |
| BRTN30WSS5PC | 5-axis servo manipulator | 5 | 60.0 |  | 0.1 | 13400 |
| BRTN30WSS5PF | 5-axis servo manipulator | 5 | 60.0 |  |  | 13900 |
| BRTNG09WSS3P | 3-axis servo manipulator | 3 | 2.0 |  | 0.05 | 3600 |
| BRTNG11WSS3P | 3-axis servo manipulator | 3 | 2.0 |  | 0.05 | 3600 |
| BRTNN11WSS3P | 3-axis servo manipulator | 3 | 10.0 |  | 0.05 | 3100 |
| BRTNN15WSS3P | 3-axis servo manipulator | 3 | 15.0 |  |  | 4300 |
| BRTNN15WSS4P | 4-axis servo manipulator | 4 | 15.0 |  | 0.1 | 4800 |
| BRTNN15WSS5P | 5-axis servo manipulator | 5 | 15.0 |  | 0.1 | 5100 |
| BRTP07ISS1PC | 1-axis servo manipulator | 1 | 2.0 |  | 0.05 | 1400 |
| BRTP08WSS0PC | Servo manipulator |  | 2.0 |  | 0.05 | 900 |
| BRTR07WDS5PC | 5-axis servo manipulator | 5 | 3.0 |  | 0.05 | 2800 |
| BRTR08TDS5PC | 5-axis servo manipulator | 5 | 3.0 |  | 0.05 | 4200 |
| BRTR11WDS5PC | 5-axis servo manipulator | 5 | 10.0 |  | 0.05 | 3000 |
| BRTV09WDS5P0 | 5-axis servo manipulator | 5 | 5.0 |  | 0.05 | 5900 |
| BRTV13WDS5P0 | 5-axis servo manipulator | 5 | 8.0 |  | 0.05 | 7000 |
| BRTV17WSS5PC | 5-axis servo manipulator | 5 | 20.0 |  | 0.05 | 10300 |

## What the numbers mean

- **payload_kg** — rated payload at the flange, from the product page specification table.
- **reach_mm** — maximum reach, from the same table.
- **repeatability_mm** — positional repeatability (±mm).
- **price_usd** — published list price for a single unit, EXW, subject to change without notice. It is not a quotation:
  final price depends on configuration, tooling, controller options, destination and order quantity.
  Request a current quotation at <https://borunteofficial.com/contact/>.
- **applications** — applications named on the product page (arc welding, palletizing, machine tending, stamping, spraying).

## Scope and exclusions

Included: robot model names, series, axes, payload, reach, repeatability, named applications,
published list price, canonical product URL.

Excluded on purpose: customer names, order volumes, project prices, drawings and CAD files that
are not published, and any figure the manufacturer has not verified. If a field is unknown it is
`null` — this dataset never fills gaps with guesses.

## Corrections

If a value disagrees with the current product page, the product page wins. Please open an issue with
the model name and the page URL; corrections are applied to the website first and then mirrored here.

## Citation

> BORUNTE ROBOT CO., LTD. (2026). *BORUNTE industrial robot dataset: models, payload, reach,
> repeatability and list price.* https://borunteofficial.com/data/borunte-robots.json (CC BY 4.0)

Contact: zhonglinhua5@gmail.com · +86 159 8911 3969
