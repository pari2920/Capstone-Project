# Capstone Project
🚗 Dynamic Pricing for Urban Parking Lots

Capstone Project – Summer Analytics 2025Hosted by Consulting & Analytics Club × Pathway

📌 Project Overview

Urban parking spaces are limited and often inefficiently priced. Static pricing leads to overcrowded lots or unused capacity. This project implements a real-time dynamic pricing engine for 14 urban parking lots, adapting prices based on demand, congestion, special events, and vehicle types.

We simulate real-time conditions using Pathway’s streaming data framework and implement three levels of pricing models using only NumPy and Pandas. Visualizations are built with Bokeh.

🧰 Tech Stack

Python – Core language
NumPy & Pandas – Data preprocessing and modeling
Pathway – Real-time data simulation and processing
Bokeh – Visualization of live data streams
Google Colab – Development and execution
Panel – Interactive dashboarding (optional)

🧠 Objective

Design a dynamic pricing system that:
Starts from a base price of $10
Adjusts prices smoothly based on real-time inputs:
Occupancy rate
Queue length
Traffic congestion
Special events
Vehicle type (bike, car, truck)
Competitor pricing (optional, advanced)
Supports rerouting logic if a lot is full

🏗️ Architecture Diagram

flowchart TD
    DataStream[CSV Real-Time Stream] -->|Ingest| Pathway
    Pathway --> FeatureEngineering
    FeatureEngineering --> PricingModel
    PricingModel -->|Output| PriceUpdates
    PriceUpdates --> BokehPlots
    PricingModel --> CompetitorLogic

⚙️ Workflow Breakdown

1. Data Ingestion

Real-time stream simulated via Pathway
73-day data from 14 parking lots
18 time points/day (30-minute intervals from 8 AM–4:30 PM)

2. Feature Engineering
Normalize occupancy
Weight vehicle types: bike (0.5), car (1), truck (1.5)
Process traffic and event indicators

3. Pricing Models

Model 1: Baseline Linear
Price[t+1] = Price[t] + α × (occupancy / capacity)

Model 2: Demand-Based Function
Demand = α(occupancy/capacity) + β(queue) - γ(traffic) + δ(special_day) + ε(vehicle_type)
Price = Base × (1 + λ × normalized_demand)

Model 3: Competitive Pricing (Optional)

Use lat-long to calculate nearby lots
Adjust price based on proximity and competitor rates
Suggest rerouting when full

📊 Visualization (Bokeh)

Real-time pricing trends per lot
Competitor comparison (if implemented)
Occupancy vs. Price curves

Example:![Bokeh Graph](https://github.com/user-attachments/assets/21a2f3af-9a36-469f-82fe-033a81001ef4)


