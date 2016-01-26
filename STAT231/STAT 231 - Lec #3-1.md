STAT 231 - Lec # 3-1

# Recalls

## Terminology

* statistical model

	* study variability and uncertainty and to draw conclusions

* Numerical / graphical summaries

	* determine which statistical models are suitable

* Random variables in staistical models

	* represent variates of random units

* arrtibutes

	* parameters in a statistical model

## Family of models

### Example

```Y ~ Bionomial(n, θ)```

-

# Estimation problems

* randomly selected data

## Terminology


* ```θ``` - ```Estimate of unknown parameter```

	* the value of observed data and other known quantities, e.g. sample size n

### Example

* Y = # of heads in 25 tosses of a coin

	* Y ~ Binomial(25, θ)

	* P(Y = 10; θ)

		* see ```Note 1```


# Method of Maximum Likelihood

* random variable ```Y```

	* potential data for estimating θ

* random variable ```y```

	* observed data

## Terminiology

* ```L(θ)``` - likelihood function for θ

	* see ```Note 2```

* ```^θ``` - maximum likelihood estimate

	* the value of θ that maximizes L(θ) for given data y

	* Example

	* **L(θ) for binomial data**

		* see ```Note 3```

		* ```^θ = y/n```

* ```R(θ)``` - Relative likelihood function

* ```l(θ)``` - Log Likelihood function

	* ```l(θ) = log( L(θ) )```

		* note: log = ln in here

## Note

* The likelihood function of θ

	* the probability of observing the data y as a function of unknown parameter θ

* it is easier to maximize the l(θ) rather than L(θ)

	* see ```Note 4```