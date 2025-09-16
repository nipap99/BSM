# Black-Scholes-Merton Option Pricing Model

This Python script calculates and visualizes European call and put option prices using the Black-Scholes-Merton model. It generates 3D surface plots to show how option prices vary with different stock prices and time to expiration.

## Features

- **Black-Scholes-Merton Formula Implementation**: Accurate calculation of European call and put option prices
- **3D Visualization**: Interactive surface plots for both call and put options
- **Parameter Customization**: Easily modify strike price, risk-free rate, and volatility
- **Professional Visualization**: Uses matplotlib with viridis and plasma color maps for clear representation

## Formula

The Black-Scholes-Merton formula calculates option prices as follows:

### Call Option:
$C = S \cdot N(d_1) - K \cdot e^{-rT} \cdot N(d_2)$

### Put Option:
$P = K \cdot e^{-rT} \cdot N(-d_2) - S \cdot N(-d_1)$

### Where:
$d_1 = \frac{\ln(S/K) + (r + \sigma^2/2)T}{\sigma\sqrt{T}}$

$d_2 = d_1 - \sigma\sqrt{T}$

- $S$ = Current stock price
- $K$ = Strike price
- $T$ = Time to expiration (years)
- $r$ = Risk-free interest rate
- $\sigma$ = Volatility
- $N()$ = Cumulative distribution function of the standard normal distribution

## Parameters

The script uses the following default parameters:
- **Strike Price (K)**: 100
- **Risk-Free Rate (r)**: 0.05 (5%)
- **Volatility (σ)**: 0.2 (20%)
- **Stock Price Range**: 50 to 150 (50 points)
- **Time to Expiration Range**: 0.1 to 2 years (50 points)

## Output

The script generates two 3D surface plots side by side:

1. **Call Option Prices**: Visualized with a viridis color scheme
2. **Put Option Prices**: Visualized with a plasma color scheme

Each plot shows:
- X-axis: Stock Price ($50-$150)
- Y-axis: Time to Expiration (0.1-2 years)
- Z-axis: Option Price

## Usage

``` bash
# Calculate a single option price
call_price = black_scholes_merton(100, 100, 1, 0.05, 0.2, 'call')
put_price = black_scholes_merton(100, 100, 1, 0.05, 0.2, 'put')

print(f"Call Option Price: {call_price:.2f}")
print(f"Put Option Price: {put_price:.2f}")
``` 
## Dependencies

- `numpy` - Numerical computations
- `matplotlib` - Data visualization  
- `scipy` - Statistical functions (normal distribution)

Install required packages:
```bash
pip install numpy matplotlib scipy
```

## Example Output


The visualization shows how:
1. **Call option prices** increase with higher stock prices
2. **Put option prices** decrease with higher stock prices
3. **Both options** lose value as time to expiration decreases (time decay)
4. **The relationship between stock price, time, and option premium**

## Applications

- **Option pricing education and research** - Ideal for academic study and understanding Black-Scholes-Merton model fundamentals
- **Risk management and hedging strategies** - Analyze option price behavior under different market scenarios
- **Quantitative finance analysis** - Foundation for more complex derivatives pricing models
- **Visualizing the "Greeks" indirectly** - Observe how Delta, Gamma, Theta, Vega, and Rho affect option prices through 3D surface patterns

## Limitations

- **Assumes constant volatility and risk-free rate** - Real-world volatility fluctuates (volatility smile/skew)
- **Suitable for European options only** - Cannot price American options with early exercise features
- **Assumes log-normal distribution of stock prices** - Actual market returns often exhibit fat tails and skewness
- **No dividend payments considered** - Does not account for dividend-paying underlying assets
