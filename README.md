# Beyond Wealth

An interactive Power BI analysis of how national prosperity relates to life expectancy and under-five mortality across selected economies.

The dashboard combines World Bank development indicators for 13 countries from 2000 to 2024. It is designed to show where higher income aligns with stronger health outcomes—and where the relationship breaks down.

## Analytical questions

- How have life expectancy and under-five mortality changed since 2000?
- Which countries achieve better health outcomes at comparable income levels?
- Where does economic prosperity fail to translate into longer lives?
- How large is the remaining gap to the best observed health outcome?

## Dashboard pages

### Executive Overview

Headline measures, long-term health trends, geographic filters, and country rankings provide a fast summary of global health performance.

### Wealth vs Outcomes

An animated country-year analysis compares GDP per capita with life expectancy while population supplies scale context. A supporting burden view highlights under-five mortality.

### Country Explorer

Country and year controls support focused analysis of prosperity, longevity, child mortality, and comparative performance.

### Methodology & Sources

Indicator definitions, data coverage, calculation logic, assumptions, and limitations are documented inside the report.

## Measures

- Average life expectancy at birth
- Average under-five mortality per 1,000 live births
- Average GDP per capita in current US dollars
- Population represented
- Latest reporting year
- Health-efficiency and gap-to-best measures

## Design and development

- Power BI Project (`.pbip`) format
- Power Query data preparation
- DAX measures and filter-aware calculations
- Interactive region and year controls
- Animated scatter analysis
- Four-page analytical narrative

## Data source

World Bank World Development Indicators:

- Life expectancy at birth: https://data.worldbank.org/indicator/SP.DYN.LE00.IN
- Under-five mortality: https://data.worldbank.org/indicator/SH.DYN.MORT
- GDP per capita: https://data.worldbank.org/indicator/NY.GDP.PCAP.CD
- Population: https://data.worldbank.org/indicator/SP.POP.TOTL

Coverage: 13 selected countries, 2000–2024.

## Limitations

The dashboard presents descriptive country-level associations. It does not establish that income causes health outcomes, and national averages can conceal differences within countries. GDP per capita is shown in current US dollars and is not adjusted for purchasing-power parity.


## Author

Khalid SaadAldin Yahia  
Data Analyst | Power BI | SQL | Python | Excel

## Open and inspect the report

- [Preview the dashboard PDF](Beyond_Wealth_Dashboard.pdf). A PDF is a static export; the `.pbip` project contains the interactive report.
- [Browse the Power BI project](project/) or [download this repository as a ZIP](https://github.com/KhalidSaadaldinYahia/beyond-wealth-dashboard/archive/refs/heads/main.zip). Keep the `project` folder intact after extracting.
- Open [`BeyondWealth.pbip`](project/BeyondWealth.pbip) from the extracted `project` folder in a recent Power BI Desktop. The `.pbip` file references its sibling `.Report` and `.SemanticModel` folders; it cannot open by itself after downloading only that file.
- On refresh, choose **Anonymous** access if Power BI requests credentials for `raw.githubusercontent.com`. The project reads the included CSV snapshot from this repository's public `main` branch. For offline refresh, replace each table query's `Web.Contents(...)` CSV source with `File.Contents(...)` pointing to its included local `project/data` CSV.

The CSV data snapshots are included under [`project/data`](project/data/). A `.pbix` was not generated because the PBIP source cannot be converted faithfully without opening and saving it in Power BI Desktop.

**Population correction:** The population measure now uses the latest visible year, so selected countries are counted once rather than summed across 2000–2024. The full-selection 2024 population is 2.397 billion; the prior PDF export shows the old 53.0 billion sum and should be treated as an archival visual until re-exported from Power BI Desktop.
