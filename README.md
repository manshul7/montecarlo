# Simple Monte Carlo Option Pricing Model

A lightweight Python computational model to price European-style call options using Monte Carlo simulations. This script generates thousands of stochastic asset price paths to estimate the fair value of an option under a risk-neutral pricing framework.

## Mathematical Framework

This model simulates the terminal price of an underlying asset using the **Geometric Brownian Motion (GBM)** model. The terminal asset price $S_T$ is calculated as:

$$S_T = S_0 \exp\left(\left(r - \frac{1}{2}\sigma^2\right)T + \sigma \sqrt{T} Z\right)$$

Where:
* $S_0$ = Spot price
* $r$ = Risk-free interest rate
* $\sigma$ = Volatility
* $T$ = Time to expiry (in years)
* $Z$ = Standard normal random variable $Z \sim N(0,1)$

The European call option price is then determined by taking the average of the discounted terminal payoffs:

$$\text{Call Price} = e^{-rT} \frac{1}{N} \sum_{i=1}^{N} \max(S_{T,i} - K, 0)$$

## Prerequisites

This script requires Python 3.x and the following standard libraries:

```bash
pip install numpy matplotlib
