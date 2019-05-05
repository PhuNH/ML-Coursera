# ML-Coursera
**Gradient Descent**

&theta;<sub>j</sub> = &theta;<sub>j</sub> - &alpha; * derivative{&theta;<sub>j</sub>}(J(&theta;))  

_Feature scaling:_

- Features being on similar scales is better for GD, making it converge faster.
- Rule of thumbs: change scales to between [-1/3; 1/3] and [-3; 3]

_Mean normalization:_ Replace x<sub>i</sub> with x<sub>i</sub> - &mu;<sub>i</sub> to make feature have approximately zero mean.

**Linear Regression**

derivative{&theta;<sub>j</sub>}(J(&theta;)) = (1/m) sum{i}{1}{m}((h<sup>(i)</sup> - y<sup>(i)</sup>) * x<sub>j</sub><sup>(i)</sup>)  
&theta; = &theta; - (&alpha;/m) * (X<sup>T</sup> * diff) with diff = X * &theta; - y.

_Normal equation (analytic method):_

- &theta; = (X<sup>T</sup>X)<sup>-1</sup>X<sup>T</sup>y
- Slow if n (# of features) is very large (10k can still be fine, GD can be more suitable for more than that).
- X<sup>T</sup>X might be **noninvertible** when: some features are linearly dependent, or there are too many features (n &ge; m)

**Logistic Regression**

- h<sub>&theta;</sub>(X) = 1/(1 + e<sup>-&theta;X</sup>) and &theta;X = ln(h/(1-h)).
- The odds is the ratio between the amounts staked by parties to a bet. Here the odds is h/(1-h).
- The likelihood of h is a function of &theta;, which shows the probability that the classification is correct in all examples, based on &theta;. In the discrete case, each example is a binomial count, so the probability of each example is the PMF that there are y<sub>i</sub> correct classification out of n<sub>i</sub> samples in that example, which is C{n<sub>i</sub>}{y<sub>i</sub>} * h<sub>i</sub><sup>y<sub>i</sub></sup> * (1-h<sub>i</sub>)<sup>(n<sub>i</sub> - y<sub>i</sub>)</sup>. The likelihood is the product of all examples' probability.
- Or we can use GD by defining the cost function of each example, and then minimizing the total cost function J:  
cost(h,y) = [-ln(h) if y=1 and -ln(1-h) if y=0] = -y * ln(h) - (1-y) * ln(1-h) and J(&theta;) = (1/m) sum{i}{1}{m}(cost)  
derivative{&theta;<sub>j</sub>}(J(&theta;)) = the same as this of Linear Regression (but h<sup>(i)</sup> is different).  
&theta; = &theta; - (&alpha;/m) * (X<sup>T</sup> * diff) with diff = h - y.

**Maximum Likelihood Estimation**

- The likelihood function is the joint probability distribution of observed data expressed as a function of parameters.
- The likelihood function has the same form as the PMF (in case of discrete inputs) and the PDF (in case of continuous inputs), but is a function of parameters, not y.

**Regularization**

- Used to fight overfitting: keep all features but reduce magnitude/values of parameters &theta;<sub>j</sub>.  
- Underfitting: high bias; overfitting: high variance.  
- We need to have a regularization parameter &lambda; so that when we minimize the cost function, we would need to decrease values of &theta;<sub>j</sub>'s more than usual. Like a penalization.  
- Setting &lambda; too large might result in the algorithm being underfit (all &theta;<sub>j</sub> might get to 0).

Use L2 Reg. (lambda squared):  
- Gradient Descent: This is usually true: 1 - &alpha; * &lambda; / m < 1, it is usually a bit < 1.
- Linear Regression - Normal Equation:
    - &theta; = (X<sup>T</sup>X + &lambda;L)<sup>-1</sup>X<sup>T</sup>y with L a diagonal matrix of size (n+1)x(n+1) with all diagonal elements being 1, except the first one.
    - X<sup>T</sup>X + &lambda;L is invertible.


