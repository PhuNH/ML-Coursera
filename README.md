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

- ![equation](https://latex.codecogs.com/gif.latex?y%3Dh_%5Ctheta%20%28X%29%3D%5Cfrac%7B1%7D%7B1&plus;e%5E%7B-%5Ctheta%20X%7D%7D)
and ![equation](https://latex.codecogs.com/gif.latex?%5Ctheta%20X%3D%5Cln%20%5Cfrac%7By%7D%7B1-y%7D)
- The odds is the ratio between the amounts staked by parties to a bet. Here the odds is $${y \over {1-y}}$$.

**Maximum Likelihood Estimation**

- Likelihood function is the joint probability distribution of observed data

