# Comparing Option Pricing Models

In this repository I evaluated the ability of the Black Scholes, Merton Jump Diffusion and Kou Jump Diffusion models to price European call options on SPY. I also calibrated the model parameters using various methods to identify the performance of the models in out-of-sample testing.


---


## Parameters to be Calibrated

Black Scholes
- annual volatility (σ)

Merton Jump Diffusion
- annual volatility (σ)
- annual jump rate (λ)
- mean jump size (μJ)
- jump volatility (σJ)

Kou Jump Diffusion
- annual volatility (σ)
- annual jump rate (λ)
- probability of upward jump (p)
- inverse magnitude of upward jump (η1)
- inverse magnitude of upward jump (η2)


---


## Model Calibration Methods

Historical data
- I estimated the parameter values using hisotrical data. I chose to calibrate the model on 45 years of data to account for all the possible jump behaviour that may occur.
  
Market Prices
- Here I attempt to minmise the difference between the estimated prices and market prices using basinhopping function from SciPy.
- I use the minimise function with the output values from the basinhopping function as a my starting values to improve the accuracy of the parameter values.

Implied Volatility (IV)
- I compute the IVs inferred by the models and calibrate the parameters on these volatilities.
- The calibration functions used for market prices are also used here.


---



## Results

To evaluate the performance of these models I test the models ability to price options using out-of-sample data and compute the root mean squared errors. I find that when averaging rmse across different calibrations, the Black Scholes model performs best with both 7 day and 30 day maturities, followed by the Merton and finally the Kou model. However, I find that the Kou model produced the lowest rmse score for options with 30 days to maturity and the Merton model produced the lowest rmse score for pricing 7 day maturity options. 


---


## Conclusions

Although the market price calibrated models perform the best, they produce parameter values that are much more different to values estiamted using historical data. Perhaps adjusting the minimum criteria for jump size in historically calibrated data and the bounds for optimisation may make the models more representative of emprical data and possibly more generalisable. 

Furthermore, I think more investigation should be done on the length of data to calibrate the paramteres on. My suggestion would be to trial different periods lengths and jump size criteria to identify what most closely matches market prices. In hindsight, I would collect more option price data to more accurately calibrate my models and conduct more thorough testing. 

Finally, I would like to collect more data to better capture the volaility surface. I would also further investigate why the Kou created unsual IV outputs for options with 95 days to maturity. 


---

## Contact

For any inquiries or contributions, feel free to reach out:

- **Email:** farhankbhamgara@gmail.com 
- **LinkedIn:** [LinkedIn Profile](https://www.linkedin.com/in/farhanbh/)
