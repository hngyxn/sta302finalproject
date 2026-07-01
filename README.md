# STA302 Final Project: Cross-Platform Music Promotion Analysis

## Final Grade: 40/40

## Overview
This repository contains the code and formal report for our STA302 Final Project. We investigate the relationship between a song's accumulated Spotify streams and its engagement metrics on TikTok and YouTube, and analyze how this relationship significantly differs across various release decades.

## Dataset
The analysis is based on the **"Most Streamed Spotify Songs 2024"** dataset, compiled by Nidula Elgiriyewithana and sourced from Kaggle. The dataset includes programmatically scraped metrics from official developer APIs for Spotify, YouTube, and TikTok.

## Methodology
We employed multiple linear regression to isolate the effects of individual social media engagement metrics. Key steps in our analytical pipeline included:
* **Data Engineering:** Converting raw release dates into a three-level categorical factor (Pre-2010s, 2010s, 2020s) to account for baseline shifts across music eras.
* **Transformations:** Applying a Box-Cox transformation (cube root) to the response variable (Spotify Streams) and log transformations to all continuous predictors to address severe right skewness and heteroscedasticity.
* **Diagnostics & Outlier Removal:** Systematically identifying and removing 44 problematic influential points using a combination of Cook's Distance, DFFITS, and DFBETAS thresholds.
* **Variable Selection:** Utilizing Best Subset Selection (BIC) and Variance Inflation Factor (VIF) analysis to eliminate multicollinearity (e.g., dropping TikTok Views in favor of TikTok Likes).

## Key Findings
1. **YouTube Engagement is the Primary Driver:** YouTube Likes demonstrated the most robust positive association with streaming volume, indicating that active long-form video appreciation strongly propels sustained audio streaming success.
2. **TikTok as a Discovery Pipeline:** Short-form virality via TikTok Likes also exhibits a highly significant positive relationship with stream volume, though its influence scales lower than YouTube engagement.
3. **The "Accumulation Effect" of Legacy Tracks:** Catalog tracks (Pre-2010s) hold a profound structural advantage with a naturally high baseline of cumulative streams. Conversely, modern frontline releases (2020s) face a steep baseline deficit and rely aggressively on multi-platform digital engagement to compete for market share.

## Repository Contents
* `Final Project.Rmd`: The complete R Markdown file containing all data cleaning, diagnostic testing, Box-Cox transformations, model selection procedures, and final outputs.
* `sta302 final project.pdf`: The comprehensive academic report detailing the literature review, statistical methodology, residual visualizations, and theoretical implications of the results.

## Contributors
* Rita Huang
* Jennifer Du
* Sophia Ning
* Crystal Lam
