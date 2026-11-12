# data-engineering-project


# REST Countries — Milestone 1

Data profiling, cleaning, validation, and exploratory visualization using the REST Countries API.

## Overview

This milestone works with **254 country and territory records** collected from the REST Countries API. The data was flattened into a tabular structure, profiled, cleaned, and explored through five visualizations.

## Dataset

| Column | Description |
|---|---|
| `CountryName` | Country or territory name |
| `Region` | API region |
| `Area(km2)` | Area in square kilometers |
| `Languages` | Comma-separated language names |
| `CurrencyCodes` | Comma-separated currency codes |
| `borders` | Comma-separated neighboring country codes |
| `Population` | Population count |

## Workflow

1. **Data Acquisition:** Retrieve country and territory data from the REST Countries API.
2. **Data Flattening:** Convert nested language, currency, and border information into tabular columns.
3. **Data Profiling:** Examine data types, completeness, descriptive statistics, duplicates, and potential outliers.
4. **Data Cleaning:** Apply documented corrections while keeping the original raw data separate.
5. **Exploratory Analysis:** Create visualizations to investigate population, area, and regional patterns.

## Profiling Highlights

- Total records: **254**
- Empty language values: **1**
- Empty currency values: **3**
- Empty border values: **86**
- No null values were found in `CountryName`, `Region`, `Area(km2)`, or `Population`.
- No duplicate rows, nonpositive areas, or negative populations were found.
- Two records have a population of zero: Bouvet Island and Heard Island and McDonald Islands.

Empty border values do not necessarily indicate missing data; they may represent records with no land neighbors.

## Cleaning Decisions

- Kept Antarctica's language and currency fields blank.
- Set Bouvet Island's currency to `NOK`.
- Set Heard Island and McDonald Islands' currency to `AUD`.
- Added the documented border entries for Greenland (`CAN`), Cyprus (`GBR`), and Åland Islands (`SWE`).
- Added Greenland (`GRL`) as a reciprocal border entry for Canada.
- Kept the border fields blank for Cuba, Antarctica, and French Southern and Antarctic Lands.
- Retained zero-population records and all IQR-flagged values because they were not identified as errors.

The cleaned dataset retains **254 records**. The number of blank border fields decreases from **86 to 83**.

## Visualizations

The report includes five visualizations:

1. Total recorded population by region.
2. Number of country and territory records by region.
3. Population distribution across countries and territories.
4. Area distribution by region using a boxplot.
5. Population versus area using logarithmic axes.

Each visualization is accompanied by an analytical question and a short interpretation in the report.

## References

1. **REST Countries API**  
   https://restcountries.com/

2. **Australian Border Force — Invoice Currency Code List**  
   https://www.abf.gov.au/help-and-support/ics/integrated-cargo-system-%28ics%29/software-developers/reference-materials/code-list/invoice-currency-code

3. **Government of Canada — Boundary Dispute**  
   https://www.canada.ca/en/global-affairs/news/2022/06/boundary-dispute.html

4. **Government of Canada — Canada/Denmark/Greenland Historic Agreement**  
   https://www.canada.ca/en/global-affairs/news/2022/06/canada-and-the-kingdom-of-denmark-together-with-greenland-reach-historic-agreement-on-long-standing-boundary-disputes.html

5. **CIA World Factbook Archive — Cyprus Land Boundaries**  
   https://www.thefactbook.org/cyprus/land-boundaries

6. **UK House of Commons Library — Sovereign Base Areas**  
   https://commonslibrary.parliament.uk/research-briefings/cbp-10540/

7. **Nordic Cooperation — About Åland**  
   https://www.norden.org/en/information/about-aland

8. **Swedish Mapping Authority — Finland/Sweden Boundary**  
   https://www.lantmateriet.se/sv/om-lantmateriet/Samverkan-med-andra/sveriges-riksgranser/riksgransen-sverige-finland/

9. **Australian Government — Heard Marine Habitats Report**  
   https://www.agriculture.gov.au/sites/default/files/documents/heard-marine-habitats.pdf

10. **Australian Antarctic Program — Heard Island**  
    https://www.antarctica.gov.au/antarctic-operations/stations-and-field-locations/heard-island/

11. **Antarctic Treaty Secretariat**  
    https://www.ats.aq/e/antarctictreaty.html

---

For detailed profiling results, cleaning rationale, charts, and the full explanations, see the Milestone 1 report.
