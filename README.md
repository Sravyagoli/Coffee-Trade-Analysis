# ☕ Coffee Trade Analysis: A Comparative Study of Africa and Global Coffee Production

An independent Excel analytics project examining 60+ years (1961–2022) of global coffee production data to evaluate Africa's competitiveness in the global coffee trade relative to the Americas, Asia, and Oceania.

This project began as a team assignment for **BIA 500-B Business Analytics: Data, Models, and Decisions** at Stevens Institute of Technology (MS Computer Science, Spring 2025). I rebuilt the full analysis independently from the raw dataset feature engineering, all 6 pivot tables, slicers, and charts to deepen my own understanding of the methodology and findings.

## Project Overview

Africa has significant agricultural potential for coffee production, but how does it actually stack up against the world's top producers? This project uses 61 years of FAOSTAT data to quantify Africa's contribution to global coffee output and diagnose *why* the continent lags — testing the hypothesis that the gap is driven by yield inefficiency rather than insufficient land.

**Key question:** Is Africa's underperformance in global coffee production a land-use problem or a productivity problem?

**Key finding:** Africa holds roughly 18% of global coffee production share, trailing the Americas (~59%) and Asia (~21%). Despite farming a comparable amount of land to Asia, Africa converts far less of it into output pointing to yield efficiency, not land scarcity, as the binding constraint.

## Dataset

- **Source:** [FAOSTAT Coffee Production Data 1961–2022](https://www.kaggle.com/datasets/junkochida/faostat-coffee-production-data-1961-2022) (via Kaggle)
- **File used:** `Coffee_Production_1961-2022.csv`
- **Size:** 4,818 rows × 7 columns
- **Fields:** Area (Country), Year, Production (tons), Area Harvested (hectares), Production Yield, Continent, Region

## Visualizations 🫘

![Production by Country](images/production_by_country.png)
![Production Trends Over Time](images/production_trends_over_time.png)
![Yearly Trends by Continent](images/yearly_trends_by_continent.png)
![Yield by Continent](images/yield_by_continent.png)
![Production Share by Continent](images/production_share_by_continent.png)
![Area vs Production by Continent](images/area_vs_production_by_continent.png)

## Methodology

All analysis was performed in Microsoft Excel:

1. **Data preparation** — loaded the raw CSV into a structured Excel Table (no missing values found in this dataset).
2. **Feature engineering**
   - `Decade`: grouped years into 10-year bins for trend aggregation
     `=FLOOR([@Year],10)&"s"`
   - `Efficiency Level`: classified records as High/Medium/Low
     `=IF([@[Production.t]]>4000,"High",IF([@[Production.t]]>2000,"Medium","Low"))`
3. **Pivot table analysis** — built 6 pivot tables with slicers and value-field customization:
   1. Total coffee production by country
   2. Global production trends over time
   3. Yearly trends by continent (production, area harvested, yield)
   4. Average yield by continent
   5. Production share by continent
   6. Area harvested vs. production by continent (land-use efficiency)
4. **Visualization** — column, line, and doughnut charts paired with interactive year/continent slicers.

## Key Findings

- **Production by country:** Brazil leads with ~117M tons cumulative, nearly 3x Colombia (~40.6M) and ~4x Viet Nam (~31.8M). Uganda (~11.7M) and Ethiopia (~9.4M) lead within Africa but trail the global top producers by a wide margin.
- **Production trends over time:** Global output has climbed steadily since 1961, roughly doubling from ~4.5M tons to over 11M tons by the 2020s.
- **Yield by continent:** Asia posts the highest average yield (8,293 kg/ha), followed by the Americas (6,578). Africa (5,626) and Oceania (5,568) trail behind Africa is not the single lowest performer, but it's well behind the two largest global producers.
- **Production share by continent:** The Americas account for ~59% of global production, Asia ~21%, Africa ~18%, and Oceania ~1%.
- **Land-use efficiency:** Africa harvests a similar amount of land as Asia (~102K vs. ~105K hectares on average) but produces far less from it (~42K vs. ~94K tons) confirming the gap is about productivity, not land access.

## Repository Contents

| File | Description |
|---|---|
| `Coffee_Trade_Analysis.xlsx` | Full Excel workbook — raw data, calculated fields, 6 pivot tables, slicers, and charts |
| `README.md` | This file |

## Conclusion

Despite vast agricultural potential, Africa contributes a modest share of global coffee output, driven primarily by lower yield efficiency rather than limited land. Closing the gap with leaders like Brazil and Asia likely depends on mechanization, farmer training, infrastructure investment, and supportive agricultural policy rather than expanding cultivated area.

## References

- [FAOSTAT Coffee Production Data 1961–2022 (Kaggle)](https://www.kaggle.com/datasets/junkochida/faostat-coffee-production-data-1961-2022)
