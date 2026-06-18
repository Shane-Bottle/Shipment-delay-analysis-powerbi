# Shipment Delay Analysis | Power BI

## Overview
Interactive Power BI dashboard analysing cargo shipment delays 
across handlers, commodities, routes, and monthly trends.

Built as part of a self-directed data analytics portfolio combining 
aviation operations experience with self-taught BI skills.

---

## Dashboard Features
- **KPI Cards** — Total Shipments, Total Delayed, On Time Rate %, Avg Delay Minutes
- **Bar Chart** — Delays by Reason Code
- **Bar Chart** — Delays by Ground Handler
- **Bar Chart** — Delays by Commodity Type
- **Line Chart** — Monthly Delay Trend (Jan–Dec 2024)
- **Slicers** — Filter by Commodity, Delay Reason, Origin

---

## DAX Measures Used
```DAX
Total Shipments = COUNTROWS(shipment_delays)

Total Delayed = 
COUNTROWS(FILTER(shipment_delays, shipment_delays[DelayMinutes] > 0))

On Time Rate % = 
DIVIDE(
    COUNTROWS(FILTER(shipment_delays, shipment_delays[DelayMinutes] = 0)),
    COUNTROWS(shipment_delays)
) * 100

Avg Delay Minutes = 
AVERAGEX(
    FILTER(shipment_delays, shipment_delays[DelayMinutes] > 0),
    shipment_delays[DelayMinutes]
)
```

---

## Dataset
- 800 rows of simulated cargo shipment data
- Handlers: JAS, dnata, Menzies, WFS, Swissport
- Commodities: General Cargo, Pharmaceuticals, Perishables, 
  Dangerous Goods, Courier, Valuables, Live Animals
- Delay Reasons: Documentation, Customs, Late Arrival, 
  Equipment Fault, Weight & Balance, Security Hold, Weather
- Period: January 2024 – December 2024

---

## Key Insights
- Documentation Issues are the #1 delay cause
- JAS recorded highest total delays among handlers
- General Cargo most affected commodity
- Delay spike visible in April–May period

---

## Tools Used
- Power BI Desktop
- DAX
- Power Query

---

## Author
**Shane Dodwell Holdenbottle**  
Senior Airport Service Agent | Emirates Airlines  
Self-directed Data Analytics Portfolio  
Dubai, U.A.E
