# Hong Kong Mortality Trends, 1986–2016

Exploratory data analysis and visualisation of three decades of Hong Kong mortality statistics from the Census and Statistics Department.

> First-year course project for **ENGG1003 Digital Literacy and Computational Thinking**, CUHK (Nov 2022). Python, pandas, Altair.

## Questions explored
1. **Crude vs age-standardised death rate.** How have overall mortality and age-adjusted mortality moved since 1986?
2. **Age and sex.** How does mortality differ across age groups and between men and women?
3. **Causes of death.** Which causes dominate, and how did the mix change between 1986–2000 and 2006–2016?
4. **Life expectancy.** How does Hong Kong compare with 11 other economies (Japan, Singapore, the UK, the US, and others)?
5. **Seasonality.** In which months do deaths peak?

## Key findings
- **The crude death rate rose (4.7 → 6.4 per 1,000) while the age-standardised rate fell (10.5 → 6.4).** The two met in 2016. This is the signature of population ageing: mortality at any given age keeps improving, but a growing share of the population is elderly, so total deaths per capita rise.
- Mortality is lowest in childhood and grows roughly exponentially after 60. Male rates exceed female rates in almost every age group.
- **Neoplasms, circulatory and respiratory diseases** account for about three-quarters of deaths. Respiratory diseases rose from 15.8% to 22.8% of deaths, while circulatory diseases fell from 28.9% to 21.5%.
- Hong Kong and Japan trade places for the world's highest life expectancy throughout the period. Hong Kong peaked at 81.4 (men) and 87.3 (women) in 2015.
- Deaths peak in winter (Dec–Mar) and bottom out in summer (Jun–Aug).

## Methods
- Data cleaning and reshaping with pandas (melting wide tables, handling ".." and "N.A." placeholders)
- Gaps in the life-expectancy series (Germany, US) filled with a log-linear trend fit
- Linear trend fits for crude and standardised rates, with a note on why naive extrapolation breaks down (it eventually predicts negative rates)
- Altair charts: area + regression overlays, grouped bars, a bubble chart, a heatmap

## Data
Hong Kong Census and Statistics Department, *Demographic Trends in Hong Kong*, Section 4 (Mortality). Raw tables are in `dataset/`; the combined workbook is `Mortality_trends.xlsx`.

## Run
```bash
pip install pandas altair openpyxl numpy
jupyter notebook Project.ipynb
```
Altair charts do not render on GitHub's notebook viewer. See the exported images in `figures/`, or run the notebook locally.
