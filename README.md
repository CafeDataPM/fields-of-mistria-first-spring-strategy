# Fields of Mistria: First Spring Crop Strategy Analysis

## Project Overview

This project analyzes crop purchasing and reinvestment decisions for a new player during the first Spring season in *Fields of Mistria*.

The analysis simulates a 28-day Spring season in which the player starts with limited working capital: 50 Tesserae, three free turnip seeds, three free tulip seeds, and access to 68 farm plots.

Although the player has space to plant up to 68 crops, they cannot afford to fill all plots on Day 1. The project therefore focuses on cash flow, harvest timing, seed affordability, and reinvestment decisions rather than only comparing each crop's selling price or profit per plot.

## Business Problem

New players need to decide how to use a limited starting budget efficiently. They must choose whether to buy cheaper seeds, prioritize crops with fast harvest cycles, invest in high-ROI crops, or save Tesserae for future purchases.

A crop may appear highly profitable over a full season but still be impractical for a player with only 50 Tesserae if it requires too much initial capital or takes too long to generate cash.

## Main Question

> Given a starting balance of 50 Tesserae, three free turnip seeds, three free tulip seeds, and 68 available farm plots, which crop-purchasing and reinvestment strategy maximizes a new player's ending Tesserae balance by Day 28 of the first Spring season?

## Stakeholders

- New *Fields of Mistria* players
- Guide writers and content creators
- Intermediate players interested in early-game optimization
- Game economy and farming strategy enthusiasts

## Starting Scenario

| Resource | Starting Amount |
|---|---:|
| Starting cash | 50 Tesserae |
| Free turnip seeds | 3 |
| Free tulip seeds | 3 |
| Available farm plots | 68 |
| Season length | 28 days |
| Season analyzed | Spring |
| Selling method | Direct crop sales at base price |

## Scope

### Included

- Spring crops available to a new player
- Base seed prices
- Base crop selling prices
- Days to first harvest
- Regrowth days for recurring crops
- Free starter seeds
- Daily cash-flow simulation
- Seed purchasing and reinvestment decisions
- 68-plot capacity constraint
- Crop revenue, seed costs, net gain, ROI, and ending cash balance
- Comparison of multiple crop-purchasing strategies

### Excluded

- Crop quality, random bonuses, perks, essence, and skill effects
- Cooking, crafting, processing, and recipe profitability
- Animal products, fishing, mining, and foraging income
- Energy, watering time, planting time, and player movement time
- Future game updates and economy changes
- The resale value of crops still growing on Day 28

## Methodology

The project uses a daily simulation from Day 1 through Day 28.

1. The player plants the three free turnip seeds and three free tulip seeds on Day 1.
2. The player may buy additional seeds only when sufficient Tesserae are available.
3. Each planting decision must respect the available cash balance and the 68-plot limit.
4. Mature crops are sold at their listed base selling price.
5. Sale proceeds are reinvested according to the rules of each tested strategy.
6. Single-harvest crops may be replanted when enough days remain in the season.
7. Recurring crops remain planted and produce additional harvests after their regrowth period.
8. The primary success metric is the ending Tesserae balance on Day 28.

## Strategies Compared

| Strategy | Decision Rule |
|---|---|
| Starter Seeds Only | Plant the six free starter seeds and make no seed purchases |
| Cheapest Seed | Buy the lowest-cost available seed whenever cash is available |
| Fastest Harvest | Buy the crop with the shortest time to first harvest |
| Highest ROI | Buy the crop with the highest estimated return on investment |
| Highest Net Profit | Buy the crop with the highest estimated seasonal net profit per plot |
| Optimized Strategy | Select purchases that maximize ending Tesserae by Day 28 |

## Key Metrics

| Metric | Definition |
|---|---|
| Ending Cash Balance | Tesserae available at the end of Day 28 |
| Net Seasonal Gain | Ending cash balance minus the initial 50 Tesserae |
| Daily Cash Balance | Tesserae available after daily sales and seed purchases |
| Active Plots | Number of planted plots on a given day |
| Seasonal Revenue | Total revenue from direct crop sales |
| Total Seed Cost | Total Tesserae spent on purchased seeds |
| ROI | Net seasonal gain divided by total seed cost |
| First Harvest Day | The day on which a crop first produces revenue |

## Core Formulas

```text
Ending Cash Balance =
Starting Cash + Total Crop Sales - Total Seed Purchases
```

```text
Net Seasonal Gain =
Ending Cash Balance - Starting Cash
```

```text
ROI (%) =
(Net Seasonal Gain / Total Seed Cost) × 100
```

## Data Sources

- Primary source: Official in-game crop and seed information
- Secondary source: *Fields of Mistria* Wiki — Crops page
- Collection method: Manual data collection into CSV files
- Date verified: 08/19/2026
- Game version: v1.0.4

## Repository Structure

```text
fields-of-mistria-crop-profitability/
│
├── data/
│   ├── raw/
│   └── cleaned/
│
├── notebooks/
│   └── fields_of_mistria_crop_analysis.ipynb
│
├── sql/
│   └── crop_strategy_queries.sql
│
├── dashboard/
│   └── fields_of_mistria_crop_dashboard.pbix
│
├── images/
│   └── dashboard_preview.png
│
├── docs/
│   └── data_dictionary.md
│
└── README.md
```

## Expected Outputs

- Raw and cleaned crop datasets
- Data dictionary
- Daily cash-flow simulation table
- SQL business queries
- A Python script or Jupyter Notebook used for the daily cash-flow simulation
- Power BI dashboard
- Strategy comparison and final recommendation

## Limitations

This analysis is based on fixed assumptions and base crop values. Results may change if game updates modify crop prices, seed costs, crop availability, harvest timing, or farming mechanics. The simulation also excludes quality modifiers, player skills, processing, and the energy or time required to farm.

## Final Recommendation

The final recommendation will identify the strategy that produces the highest ending Tesserae balance by Day 28, while explaining the trade-off between fast cash generation, ROI, crop profitability, and farm-plot usage.
