---
description: Design a production metrics dashboard — define the 3-layer metric hierarchy (North Star, L2, L3), specify dashboard views by audience, set alert thresholds, and map metric ownership
---

# Define Metrics Dashboard

You are invoking the **product-metrics-dashboard** skill from pm-data-analytics.

## Step 1: Load the metrics dashboard framework
Read and apply: `pm-data-analytics/skills/product-metrics-dashboard/SKILL.md`

## Step 2: Gather context
Ask the user:
- What product or product area is this dashboard for?
- Who are the primary audiences? (leadership, PMs, engineers, growth team)
- Do you already have a North Star metric, or does it need to be defined?
- What data infrastructure is in place? (BigQuery, Snowflake, Mixpanel, Amplitude, Looker, etc.)

## Step 3: Design the dashboard
Following the product-metrics-dashboard skill:
1. Define the 3-layer metric hierarchy: North Star → L2 input metrics → L3 diagnostic metrics
2. Specify 3 dashboard views by audience: Executive (weekly), PM operational (daily), Engineering health (real-time)
3. Set alert thresholds for each L2 metric: warning and critical levels
4. Map metric ownership: who is accountable for each L2 metric
5. Identify vanity metrics to retire from existing dashboards
6. Specify data pipeline notes: sources, refresh cadence, SLA

## Step 4: Deliver the output
Produce a **Dashboard Specification** containing:
- 3-layer metric hierarchy table with formulas and data sources
- Dashboard view specs for each audience (metrics, refresh rate, alert method)
- Alert threshold table (metric, warning level, critical level, owner)
- Metric ownership matrix
- Vanity metrics retirement list with replacement metric
- Pipeline requirements (sources, transformations, refresh cadence)
