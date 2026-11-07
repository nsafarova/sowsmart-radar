# SowSmart data information

## Sources

| Data | Where it came from | How the dashboard uses it |
| --- | --- | --- |
| Demo loan portfolio | 200 simulated loan records and monthly snapshots embedded in the supplied portfolio dashboard. | Maps, rankings, insurance and repayment figures. Loan outcomes are illustrative. |
| Historical daily high temperatures and rainfall | Daily arrays embedded in the original [SowSmart Radar](https://sowsmart-radar.vercel.app) for the Buenos Aires pilot at 34.06°S, 61.20°W. The saved Radar source does not identify the original upstream dataset. | Historical charts for Oct 1–Apr 30 in 2022/23 and 2024/25. Historical temperatures and rainfall were computed from the embedded values and were not independently checked against a weather archive. |
| Historical root-zone soil wetness | Team-supplied NASA POWER CSV exports `sm 22-23.csv` and `soil moisture oct 24 - apr 25.csv`. The closest available grid point is 34.00°S, 61.25°W. [NASA POWER Daily API](https://power.larc.nasa.gov/docs/services/api/temporal/daily/) | MERRA-2 `GWETROOT`, a modeled 0–1 root-zone wetness index. It is a different measure from volumetric soil moisture in the live outlook. |
| Argentine national soybean production | Team-supplied `soja-serie-1941-2024-anual.csv`. [USDA context for 2022/23](https://esmis.nal.usda.gov/sites/default/release-files/tx31qh68h/0p097v25v/sx61g667f/oilseeds.pdf) | National production context, separate from the local pilot. The project series shows a drop from 43.9 million to 25.0 million tonnes around the 2022/23 drought. |
| Current weather and forecasts | [Open-Meteo Forecast API](https://open-meteo.com/en/docs), queried in the browser at the selected demo loan coordinates. | Current modeled temperature and 27–81 cm volumetric soil moisture where available, plus seven local dates of forecast daily highs and rain including today. The panel shows the model valid time and retrieval time. |
| Farm map | The supplied Buenos Aires map image with OpenStreetMap and CARTO attribution, with selectable reference points tied to the `ba-coordinates` sheet in the team’s `farm_data.xlsx`. | Location reference in the Spatial map tab. Its controls are separate from the portfolio filters. |

## How the historical charts were calculated

- **Weekly temperature:** Average of daily maxima in consecutive seven-day blocks starting October 1. The final block covers April 29–30.
- **Hot days:** Count of daily maxima at or above 35 °C. The comparison baseline in the detail table averages matched months across 27 earlier seasons, 1995/96–2021/22, with leap day excluded. The threshold is an illustrative screening rule.
- **Rain:** Daily values are summed by calendar month and accumulated from October 1 for the season chart.
- **Soil wetness:** The chart shows only complete months. The table also shows means for available days in partial months, with day counts. The supplied 2022/23 export covers Oct 15–Mar 15; the 2024/25 export covers Oct 15–Apr 15. Missing periods are left blank in the chart.

At the pilot, January–March included **19 hot days in 2023** and **4 in 2025**. Rainfall across those months was **150.2 mm** and **451.8 mm**, respectively. In 2025, most of that rainfall arrived after January. These local conditions illustrate exposure and do not establish the cause of the national production change. [USDA February 2025 outlook](https://ers.usda.gov/sites/default/files/_laserfiche/outlooks/110935/OCS-25b.pdf)

The irrigation guidance draws on [INTA research on soybean water deficits in northern Buenos Aires](https://repositorio.inta.gob.ar/bitstream/handle/20.500.12123/24602/INTA_CRBsAsNorte_EEAPergamino_Avalos-Br%C3%ADtez_Selva_Ganancia_de_rendimiento_en_grano_en_el_cultivo_de_soja_en_el_norte_de_la_pcia_de_Bs_As.pdf?isAllowed=y&sequence=1). The dashboard cannot verify irrigation access, field conditions or how much water was applied.

## Repository contents

`index.html` is the standalone dashboard source. This release contains the web demo and documentation. The team’s original workbooks, weather exports and planning materials are separate from this release.
