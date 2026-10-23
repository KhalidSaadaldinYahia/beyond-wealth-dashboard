# Beyond Wealth

## Download the complete project

**To open this project:** [download the complete repository ZIP](https://github.com/KhalidSaadaldinYahia/beyond-wealth-dashboard/archive/refs/heads/main.zip), extract it, and open `project/BeyondWealth.pbip` in Power BI Desktop. Keep the `.Report`, `.SemanticModel`, and `data` folders beside the `.pbip` file. **Downloading the `.pbip` file alone will not produce a working report.** The included CSVs are the inspectable data snapshot; the model refreshes from a fixed online copy of those CSVs by default. The PDF is a static preview.

An interactive Power BI analysis of how national prosperity relates to life expectancy and under-five mortality across selected economies.

The dashboard combines World Bank development indicators for 13 countries from 2000 to 2024. It is designed to show where higher income aligns with stronger health outcomes—and where the relationship breaks down.

## Analytical questions

- How have life expectancy and under-five mortality changed since 2000?
- Which countries achieve better health outcomes at comparable income levels?
- Where does economic prosperity fail to translate into longer lives?
- How large is the remaining gap to the best observed health outcome?

## Dashboard pages

### Executive Overview

Headline measures use the latest visible year for all four KPIs; long-term health trends, geographic filters, and country rankings provide historical context.

### Wealth vs Outcomes

An animated country-year analysis compares GDP per capita with life expectancy while population supplies scale context. A supporting burden view highlights under-five mortality.

### Country Explorer

Country and year controls support focused analysis of prosperity, longevity, child mortality, and comparative performance.

### Methodology & Sources

Indicator definitions, data coverage, calculation logic, assumptions, and limitations are documented inside the report.

## Measures

- Average life expectancy at birth (latest visible year on the executive card)
- Average under-five mortality per 1,000 live births (latest visible year on the executive card)
- Average GDP per capita in current US dollars (latest visible year on the executive card)
- Population represented in the latest visible year, counting each selected country once
- Latest reporting year
- Exploratory life-expectancy/income ratio and gap-to-best measures

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

The packaged [`project/data/health_outcomes_long.csv`](project/data/health_outcomes_long.csv) is the country-year analytical snapshot. It joins the four listed indicator series by country code and year for the selected 13 countries. The exact original API request URLs, extraction date, and transformation script were not retained; the indicator pages above identify the source series but cannot recreate the identical historical file after publisher revisions.

## Limitations

The dashboard presents descriptive country-level associations. It does not establish that income causes health outcomes, and national averages can conceal differences within countries. GDP per capita is shown in current US dollars and is not adjusted for purchasing-power parity.

The **Health Efficiency Index** is a project-specific arithmetic ratio: mean life expectancy in years divided by the natural logarithm of mean GDP per capita in current US dollars, under the current filters. It is not a standard health-system efficiency measure. Because the denominator is a log of a currency amount, rankings depend on the currency unit and period; interpret it only as an exploratory within-dashboard comparison, never as a causal or cross-study efficiency estimate. All four executive cards now use the maximum visible year. Life expectancy, under-five mortality and GDP per capita are unweighted means across the selected countries in that year; population is summed once per country. Historical charts retain their year-by-year context.


## Author

Khalid SaadAldin Yahia  
Data Analyst | Power BI | SQL | Python | Excel

## Open and inspect the report

- [Preview the dashboard PDF](Beyond_Wealth_Dashboard.pdf). This PDF is a newly calculated, source-backed data preview; the `.pbip` project contains the interactive report.
- [Browse the Power BI project](project/) or [download this repository as a ZIP](https://github.com/KhalidSaadaldinYahia/beyond-wealth-dashboard/archive/refs/heads/main.zip). Keep the `project` folder intact after extracting.
- Open [`BeyondWealth.pbip`](project/BeyondWealth.pbip) from the extracted `project` folder in a recent Power BI Desktop. The `.pbip` file references its sibling `.Report` and `.SemanticModel` folders; it cannot open by itself after downloading only that file.
- On refresh, choose **Anonymous** access if Power BI requests credentials for `raw.githubusercontent.com`. The project reads the included CSV snapshot from this repository at fixed commit `d06f94b0b7f0`. For offline refresh, replace each table query's `Web.Contents(...)` CSV source with `File.Contents(...)` pointing to its included local `project/data` CSV.

The CSV data snapshots are included under [`project/data`](project/data/). A `.pbix` was not generated because the PBIP source cannot be converted faithfully without opening and saving it in Power BI Desktop.

**Population correction:** The population measure now uses the latest visible year, so selected countries are counted once rather than summed across 2000–2024. The full-selection 2024 population is 2.397 billion; the superseded PDF export showed the old 53.0 billion sum. The current PDF preview uses the corrected latest-year total.

### Reproducible data snapshot

The semantic model reads CSV files from immutable commit `d06f94b0b7f02075d77e7f045207bfc37688dd0e`. The same files are included in `project/data/` for inspection. Refreshing this project will not silently switch to a later `main` branch snapshot. To analyze newer data, update the CSV and source URL together and revalidate the measures and preview.
