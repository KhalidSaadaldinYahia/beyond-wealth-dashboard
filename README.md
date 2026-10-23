# Beyond Wealth

## Files

- [Open the Power BI dashboard](BeyondWealth.pbix) in Power BI Desktop.
- [Read the PDF analytical preview](Beyond_Wealth_Dashboard.pdf). This PDF summarises independently checked figures; it is not yet a page-for-page export of the PBIX. A matching PDF export is pending verification in Power BI Desktop.

The PBIX is the single-file dashboard. A data refresh may need network access to its saved source URLs.

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

- Power BI Desktop (`.pbix`) report and semantic model
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

The prepared data used for the PBIX is the country-year analytical snapshot. It joins the four listed indicator series by country code and year for the selected 13 countries. The exact original API request URLs, extraction date, and transformation script were not retained; the indicator pages above identify the source series but cannot recreate the identical historical file after publisher revisions.

## Limitations

The dashboard presents descriptive country-level associations. It does not establish that income causes health outcomes, and national averages can conceal differences within countries. GDP per capita is shown in current US dollars and is not adjusted for purchasing-power parity.

The **Health Efficiency Index** is a project-specific arithmetic ratio: mean life expectancy in years divided by the natural logarithm of mean GDP per capita in current US dollars, under the current filters. It is not a standard health-system efficiency measure. Because the denominator is a log of a currency amount, rankings depend on the currency unit and period; interpret it only as an exploratory within-dashboard comparison, never as a causal or cross-study efficiency estimate. All four executive cards now use the maximum visible year. Life expectancy, under-five mortality and GDP per capita are unweighted means across the selected countries in that year; population is summed once per country. Historical charts retain their year-by-year context.


## Author

Khalid SaadAldin Yahia  
Data Analyst | Power BI | SQL | Python | Excel
