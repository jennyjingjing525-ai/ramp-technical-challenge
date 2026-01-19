# ramp-technical-challenge
FinTech Technical Challenge: Rolling Transaction Analysis
Overview

This repository contains a specialized SQL solution for calculating a 3-day rolling average of transaction volumes. The challenge required aggregating daily transaction totals and providing a rolling average for a specific date (January 31, 2021) while ensuring compatibility with MySQL 5.7.

The Challenge

Modern SQL features like Common Table Expressions (CTEs) and Window Functions (OVER, ROWS BETWEEN) are not supported in MySQL 5.7. This solution demonstrates "Institutional Rigor" by pivoting to a self-joining subquery architecture to achieve the same result with high precision.

Technical Implementation

Environment: MySQL 5.7

Core Logic:

Aggregated raw timestamps into daily totals to ensure a clean 1:1 date-to-volume ratio.

Implemented a correlated subquery with DATE_SUB to calculate the mean of the current day plus the two preceding days.

Used DECIMAL(10,2) for financial precision over floating-point types.

Final Results

For the date 2021-01-31, the analysis yielded:

Daily Total: $59.43

3-Day Rolling Average: $682.15

Live Solution

You can view the schema setup and run the execution live on DB Fiddle: View Live SQL Solution
