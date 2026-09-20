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

## Open the project

1. [Download the Power BI project archive](Beyond_Wealth_Power_BI_Project.rar) and extract it.
2. Open the `.pbip` file using a recent version of Power BI Desktop.
3. If Power Query requests the source location, set the `DataFolder` parameter to the extracted project's `data` folder.

Preview the completed dashboard: [open the PDF](Beyond_Wealth_Dashboard.pdf).

## Author

Khalid SaadAldin Yahia  
Data Analyst | Power BI | SQL | Python | Excel
