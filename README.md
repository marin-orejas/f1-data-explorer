![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![Chart.js](https://img.shields.io/badge/Chart.js-FF6384?style=flat&logo=chartdotjs&logoColor=white)
![License: MIT](https://img.shields.io/badge/License-MIT-blue?style=flat)

# f1-data-explorer

Interactive dashboard for exploring 75 years of Formula 1 history (1950–2024). No backend, no build step — one HTML file that runs entirely in the browser.

---

## Preview

<img width="1919" height="914" alt="image" src="https://github.com/user-attachments/assets/bb94c2b8-9c91-476c-9495-8d1cda595499" />

## Dataset

UCI / Ergast Motor Racing dataset via [Kaggle](https://www.kaggle.com/datasets/rohanrao/formula-1-world-championship-1950-2020). Four CSV tables embedded directly in the HTML so the file works offline:

| Table | Content |
|---|---|
| `constructors` | ~215 teams with nationality and Wikipedia link |
| `drivers` | All drivers from 1950 to 2024 |
| `races` | Race details — circuit, year, round |
| `results` | Per-race result: grid position, finish, points, lap times |

## Features

- KPI cards — total races, drivers, constructors, top nationality by wins
- Filter by decade (1950s through 2020s)
- Highlight a driver by name across all charts
- Five charts:
  - Top 15 drivers by career points (bar)
  - Points per decade, top 5 constructors (line)
  - Top 10 driver nationalities (doughnut)
  - Grid position vs. final position, sample of 500 entries (scatter)
  - Top 10 circuits by races held (bar)
- Sortable top-100 results table
- Key insights auto-generated from the data
- Dark / light theme toggle

## Tech stack

| | Technology |
|---|---|
| Charts | Chart.js 4.4.1 |
| CSV parsing | PapaParse 5.4.1 |
| Fonts | Inter via Google Fonts |
| Everything else | Vanilla JS, HTML5, CSS3 |

No npm, no bundler, no framework.

## Running the project

Just open the file:

```bash
open f1-data-explorer.html
```

Or serve it locally:

```bash
python -m http.server 8080
# then open http://localhost:8080/f1-data-explorer.html
```

No install, no build.

## Notes

- All data is embedded in the HTML at build time — no network requests after the initial CDN loads for fonts and Chart.js.
- The scatter chart samples 500 random entries per render to stay readable.
- Data covers up to the end of the 2024 season.

## License

MIT, see [LICENSE](LICENSE) for details.
