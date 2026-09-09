# Cloud Cost Optimization & Commitment-Risk Advisory

**Status: in progress — scaffolding stage.**

A simulated FinOps consulting engagement. A fictional mid-size e-commerce
retailer is evaluating whether shifting compute spend from on-demand to
1-year/3-year reserved pricing is worth the commitment risk, given a
workload with sharp, unpredictable demand spikes (monthly product drops
plus a Nov/Dec seasonal peak) layered on top of a steady baseline.

This repo pulls live pricing from the Azure Retail Prices API and the AWS
Price List API, normalizes both into one schema, simulates a year of
hourly usage against that workload, and compares three commitment
strategies (all on-demand, all 1-year-reserved, and a hybrid) in dollar
terms — including where reservations *lose* money against mismatched
demand.

## Repo layout

```
src/config/     workload and region definitions
src/clients/    Azure / AWS pricing API clients
data/raw/       cached raw API pulls (committed, for reproducibility)
data/reference/ manual SKU crosswalk between clouds
data/curated/   normalized pricing + simulation output
notebooks/      sensitivity analysis
powerbi/        dashboard (.pbix)
docs/           engagement brief, recommendation memo
```

## Setup

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

Full write-up (API integration notes, normalization logic, simulation
methodology) will land here as the project is built out.
