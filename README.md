# ML-Coursera
**Gradient Descent**

_Feature scaling:_

- Features being on similar scales is better for GD, making it converge faster.
- Rule of thumbs: change scales to between [-1/3; 1/3] and [-3; 3]

_Mean normalization:_ Replace x<sub>i</sub> with x<sub>i</sub> - &mu;<sub>i</sub> to make feature have approximately zero mean.

**Linear Regression**

_Normal equation (analytic method):_

- &theta; = (X<sup>T</sup>X)<sup>-1</sup>X<sup>T</sup>y
- Slow if n (# of features) is very large (10k can still be fine, GD can be more suitable for more than that).
- X<sup>T</sup>X might be **noninvertible** when: some features are linearly dependent, or there are too many features (n &ge; m)

**Logistic Regression**

- y = h<sub>&theta;</theta>(X) = 1 / (1 + e<sup>-&theta;X</sup>) and &theta;X = ln(y/(1-y))
- The odds is the ratio between the amounts staked by parties to a bet. Here the odds is y/(1-y).

**Maximum Likelihood Estimation**

- Likelihood function is the joint probability distribution of observed data

