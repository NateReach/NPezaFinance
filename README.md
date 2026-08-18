# Derivative Pricing & Volatility Modelling
A from scratch exploration of option pricing methodology, progressing from classical constant volatility frameworks (Black-Scholes / GBM) through path-dependent exotics, Monte Carlo variance reduction, and finally non Markovian rough volatility models (rough Bergomi). The goal was to build up each model from first principles, implementing the simulation schemes, and validating each model against theory, while tracking why each successive model is needed to fix a specific empirical shortcoming of the last.

## Project Overview

This project is an exploration into the evolution of option pricing methodologies, beginning from classical constant volatility frameworks to more advanced non Markovian rough volatility regimes. The purpose of this project was for me to explore these concepts, while learning and implementing them simultaneously.

The project roughly flows as follows:

1. Foundational option pricing - 
Beginning with Geometric Brownian Motion (GBM), and the Black-Scholes model. We develop crude Monte Carlo simulation paths for standard European options and validate their accuracy directly against analytical closed form solutions.

2. Extension to Path Dependent Derivatives - 
This portion explores some more exotic options to see how the framework in section 1 can be applied directly.

3. Simulation Efficiency, Variance Reduction - 
Crude Monte Carlo simulations have a slow convergence rate, we implement and try out a Control Variate (CV) scheme to try to achieve a large variance reduction factor that accelerates convergence precision.

4. Relaxing Volatility Constraints with the Heston Model - 
GBM provides a solid baseline, but its assumption of constant volatility fails to replicate real world market dynamics, such as the volatility smile or skew implied volatility surfaces. We transition to the Heston Stochastic Volatility Model, treating variance as a coupled, mean reverting stochastic process that incorporates asset volatility correlation to capture the leverage effect. 

5. Capturing Market Microstructure with Rough Volatility - 
By relaxing the Markovian assumption entirely, we implement a Rough Volatility model driven by Fractional Brownian Motion (fBM) with a low Hurst parameter ($H \approx 0.1$). We try to replicate the short-term implied volatility smiles observed in live options markets.

Notebook:

The full write-up, derivations, and code are in Derivative_Pricing_and_Volatility_Modelling.ipynb.

Possible future exploration:

- Calibrate the Heston and rough Bergomi models to a real options chain and compare the fitted implied volatility surface to the market
- Add Greeks (Delta, Vega, Gamma) via pathwise or bump and revalue estimators


