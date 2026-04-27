# UK-Energy-and-Curtailment-Grid-Analysis
Empirical analysis of UK wind curtailment, gas dispatch and carbon cost using National Grid ESO and NESO Wind BOA data, 2021-2026.
# UK Grid Curtailment and Carbon Cost Analysis

Independent empirical analysis of the UK electricity grid's 
curtailment problem which is wind farms paid to switch off while gas 
plants keep running, and its carbon cost implications.

## Research Question
Why has UK wind curtailment grown sevenfold in four years despite 
record renewable capacity additions, and what is the implied 
carbon cost of the transmission gap?

## Key Findings
- Every 1% increase in renewable share reduces gas dispatch by 
  268 MW (OLS, R² = 0.60, p < 0.001, 2021-2026)
- Wind curtailment grew from 3,083 GWh (2021) to 20,452 GWh 
  (2025), a 7x increase in four years
- Total curtailment 2021-2025: 56,498 GWh which is equivalent to the 
  annual electricity consumption of 16 million UK homes
- Implied carbon cost: £444M (conservative lower bound using 
  BEIS 2025 GHG Conversion Factors, Table 8)
- Every top-10 curtailed wind farm is in Scotland — the 
  transmission bottleneck made visible in data

## Data Sources
- National Grid ESO Historic Generation Mix (half-hourly, 
  2021-2026): https://www.neso.energy/data-portal/historic-generation-mix
- NESO Wind BOA Volumes (2021/22 to 2025/26): 
  neso.energy - search Wind BOA Volumes

Note: Raw data file for fuel generation is not included in this repository. 
Download df_fuel_ckan.csv directly from the NESO data portal using the link above and place in the same 
folder as the analysis script before running.

## Methods
- OLS regression: gas dispatch on renewable share (daily data)
- Time series aggregation of curtailment from 897,000 BOA records
- Carbon counterfactual: curtailed MWh × BEIS grid emission 
  factor × UK ETS Authority reference price

## Assumptions
- Emission factors: BEIS 2025 GHG Conversion Factors, Table 8
  (0.207 kgCO2e/kWh in 2021-22, 0.177 in 2023-25)
- Carbon prices: UK ETS Authority official reference prices 
  for 2021, 2022 and 2025; approximate market averages for 
  2023 and 2024
- Carbon cost is a conservative lower bound so true marginal 
  cost using CCGT emission factor would be higher

## Files
- uk_grid_analysis_final.py - full reproducible analysis
- fig1_gas_vs_renewables.png - OLS scatter plot
- fig2_annual_trend.png - annual renewable share vs gas output
- fig3_carbon_intensity.png - monthly grid carbon intensity
- fig4_curtailment_carbon.png - curtailment and carbon cost
- fig5_monthly_curtailment.png - monthly curtailment trend
- fig6_top_farms.png - top 10 curtailed wind farms

## Related
Full analysis published on Substack: (https://kshitanjay.substack.com/p/why-the-uk-cannot-build-its-way-out)

## Author
Kshitanjay Sondhi
MSc Development Economics, London School of Economics
kshitanjaysondhi@gmail.com
linkedin.com/in/kshitanjay-sondhi
