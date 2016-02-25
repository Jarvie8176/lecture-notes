STAT 231 - Lec #6-1

## Recall


* ```θ``` - unknown constant

* ```^θ``` - point estimate (number) based on onserved data

* ```~θ``` - point estimator (random variable)


-

## Interval Estimation

* ```[ L(y), U(y) ]```

## Relative likelihood function and interval estimatess

* 100p% likelihood interval for θ

	* ```{ θ : R(θ) >= p }```

	* see `Note 1`

## Interpretation of likelihood intervals

* θ inside 10% - `plausible`

* θ inside 50% - `very plausible`

* θ outside 10% - `implausible`

* θ outside 1% - `very implausible`

## Interval Estimation

* coverage probabilities

	* coverage probability for the interval estimator `[L(Y), U(Y)]`

		* `C(θ) = P( θ ∈ [ L(Y), U(Y) ] )`

	* confidence coefficient

		* `p = C(θ)`

## Confidence interval for gaussian population

see `Note 2`


## Pivotal Quantity

* `Q = Q(Y ; θ)`

	* distribuion does not depend on θ

* example - see `Note 2`

	* 90% confidence interval `p = 90, a = 1.645`

	* 95% confidence interval `p = 95, a = 1.960`

	* 99% confidence interval `p = 99, a = 2.576`;.