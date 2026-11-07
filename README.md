# SowSmart

SowSmart is a climate-risk dashboard for agricultural lenders, built for the **Suyana Climate Insurance challenge** at the **2026 MIT Energy & Climate Hack**. It helps a loan officer identify soybean loans that may warrant a grower check-in, see which climate signals explain the concern, and ask about crop stage, field conditions and irrigation access.

## Team and challenge

- **Contributors** — Ansha Pathak, Katherine Book, Janhavi Beley and Nikki Safarova.
- **Challenge sponsor** — [Suyana Climate Insurance](https://suyana.io/).
- **Suyana challenge representatives** — Fernando Yu and Justin Muñoz.
- **Event** — [MIT Energy & Climate Hack 2026](https://www.mitenergyhack.org/).

Credits follow the team’s challenge plan and pitch deck.

## What we built

- An interactive map, ranked loan list and loan details for a simulated portfolio of **200 Argentine soybean loans**.
- Region filters for Buenos Aires, Córdoba, Entre Ríos, La Pampa and Santa Fe. The map, loan list and live outlook use the selected region.
- A live climate outlook for a selected loan, with current modeled air temperature and soil moisture when available, seven days of forecast highs and rainfall, and an automatic summary.
- A historical **Data Analysis** tab comparing the **2022/23 drought** and **2024/25** at a Buenos Aires pilot. It includes weekly temperature, monthly hot days and rainfall, cumulative rainfall and root-zone soil wetness, plus irrigation follow-up guidance.

The portfolio and repayment figures are simulated. The weather views illustrate how a lender can investigate exposure. Forecast skill, borrower outcomes and lending impact were not validated.

## Try the dashboard

1. Open `index.html` in a browser. Internet access is required for the dashboard’s external libraries and live weather.
2. Choose a **Region**. Country and Crop show the demo’s scope, **Argentina** and **Soybean**.
3. Open **Spatial map** or **Loans** and select a loan. Expand **Explore the Buenos Aires farm map** for an additional interactive map of the project’s farm reference points.
4. Go to **Climate** and click **Get latest forecast**. The dashboard retrieves and summarizes the forecast. The non-commercial demo uses the public Open-Meteo endpoint without an API key.
5. Open **Data Analysis** next to **Loans**. Compare the seasons in the charts, then expand **View exact monthly values and soil wetness** to inspect values and coverage.

