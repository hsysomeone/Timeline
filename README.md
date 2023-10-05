# Table of Contents 
[*generated with markdown-toc*](http://ecotrust-canada.github.io/markdown-toc/)

- [10/22/2020](#10/22/2020)
- [11/16/2020](#11/16/2020)
- [1/11/2021](#1/11/2021)
- [1/20/2021](#1/20/2021)
- [2/17/2021](#2/17/2021)
- [3/10/2021](#3/10/2021)
- [3/12/2021](#3/12/2021)
- [4/16/2021](#4/16/2021)
- [5/13/2021](#5/13/2021)
- [6/8/2021](#6/8/2021)
- [9/15/2021](#9/15/2021)
- [6/9/23](#6/9/23)
- [10/4/23](#10/4/23)

---
### 10/22/2020

#### Communication
Objectives: be proactive/outspoken, considerate, your own advocate, improve organization and English skills, and deliver.

Action: Listen to radio 30 minutes/day, 88.5, get Grammarly, and find opportunities to

practice organization

#### Understand self:
Strength: Analytical skills, programming skills; Areas to improve: critical thinking skill

#### Possible areas of inquiry: PEM: Partial EM algorithm:
Finite Mixture distribution 


### 11/16/2020

WWW of Tibetans Study 

What: A study of the fertility in Tibetans
Why:  Understanding natural selection as G X E X S 
How: Get best data, probe the important features that impact on the outcomes, via a collaborative interdisciplinary team 

ToDo: 

#### Regression $Y\sim x$ use logistic, Poisson, Tree/RF

#### Network analysis: nFCA

### 1/11/2021

How to treat missing information:

#### 1.Tree/Random Forest  – just run it with the default and the alternative options and show me the results
Priors:
P1 -The default (natural) prior probability mimics the natural frequencies of the response variable from a dataset.
P2 - The equal prior probability places no bias toward either stage for each record and is based on the symptoms
and other predictors, rather than a-priori assumptions.

Missing variable surrogate criterion:
M1- ‘Regular (or raw) accuracy’ selects surrogate variables by maximizing the total number of correct classifications for a potential surrogate variable. Thus, both missing and non-missing variables contribute to the
surrogate variable.
M2- ‘Percent accuracy’ selects surrogate variables by maximizing the percent correct classification, calculated
over the non-missing values of the surrogate at the current node. Thus, all non-missing values contribute to
the surrogate variable.

#### 2.Logistic/Poisson regression 
     If y is missing, remove the row
     For X
-	Participation: F vs P, do simple summary() the two groups separately 
-	Age: fill in

General guideline:
1.	Fill in missing info as much as possible
2.	Run summary() to get a sense of % missing
3.	Check the patterns for those are missing:  missing(), ggobi
4.	Remove variables with a large % of missing 
5.	Run analysis with complete data, and with incomplete data
        Y ~ complete x
        Y ~ partial columns

### 1/20/2021

#### 1.	Cleaned data summary
#### 2.	Tree modeling
#### 3.	Basic regression analysis after treating missing values.

### 2/17/2021 

#### Remove more variables
#### Find derive variables
#### Compare difference between everpregnants no vs. yes
#### U-agemeno clustering, check the difference

1.    Remove variables

1)     Remove handtemp, pulse, sat, hb,
perfusion for 2019, diff, diffavg.

Reason: we should include only the actual variables for handtemp, pulse, sat, hb, and perfusion.

2)     Add avg value for id=317 & 676

They missed avg value, but
they have 2019 value. 

3)     Remove breathless, MenstrualStatus2012,
altitude2

4)     Question: MenstrualStatus2019 vs.
MenstrualStatus2019-2

U_marstatus2019
vs. U_ marstatus2019two

2.    Find derive variables. (Color it)

Height, weight, BMI

FEV1,FEV6
 
FEV1FEV6ratio

LVEwave, LVAwave
 
LVEA

? TRVEL, TRGRAD, TRmeanGRAD,
PASP 

TRGRAD = PASP-3

TRGRAD- 98NA’s. 

1.   Clean data, Check missing patterns: if MAR, imputation or remove; if not MAR, do #2, #3, If # missing for X is large – remove X, if MAR; do #3 if not MAR.

2.   Run tree models (NA’s)

3.   Run parametric model, note that High TRGRAD is dangerous to fetus

Run Y~X [with TRGRAD]
[-mssing row], on the sup-pop w TRGRAD

Y~X [without TRGRAD] [- column of TRGRAD], on the whole population 

Y~X [without TRGRAD] [- column of TRGRAD, - rows w. TRGRAD], on subpop w/o TRGRAD [subpop size is 70]

4.   Compare difference between everpregnants no vs. yes

Slightly difference for some variables No vs. yes 

### 3/10/2021

To do: 
1.	Plots VIM of RF (Y~X) to figure out which variables are important by RF [=> X1]
a.	Tree(Y~Xi) for all I’s,  MSE, sort, remove ones that have very large MSE which may be presented as small numbers (ie revised in the VIM plot)  [=> X2]
2.	X= cbind(X1, and ones Dr. Beall were interested), or X=cbind(X2, Dr. B’s babys)
3.	Poisson (Y~ X). [on complete cases]
4.	Use step() to select variables in Poisson regression
5.	Repeat when the age of last pregnancy is removed
6.	Arrange the output by Poisson regression and RF side-by-side, to compare the chosen variables

### 3/12/2021

Check the analyses already done
Complete the analyses/comparisons with X1 and X2 as noted in 3/10/21’s notes
Dr. B let us know comments before we meet again, if needed 

### 4/16/2021

lm: Y ~  X b,              E(y_i) = x_i1 * b1+ x_i2* b2+ … 
glm: Y~Xb,                g( E(y_i)) = x_i1 * b1+ x_i2* b2+ … , if Possion


### 5/11/2021

Linear model: (p+1)
Y = f(x)+ e= a + b_1 x_1+ ..+ b_p x_p + e = X\beta+e,    regression function  f(x) is linear in x’s and e ~ normal or Y|x ~ N(mu(x), sigma^2), e~N(0, sigma^2)
            
    Denote: mu(x)=E(Y|x), eta(x) =  a + b_1 x_1+ ..+ b_p x_p. In this case, mu(x)=eta(x). 

General Linear model: (p+1):
      Generalized linear model:   g(mu(x))=eta(x),  Y|x  ~ exponential family of distributions 
                                                       
               Exponential family of distributions includes: Normal, Poisson, Binomial, Gamma, …

      General Linear model:  Y = X\beta + Z \alpha + e, \alpha ~ normal, e ~normal 

      General Generalized Linear model: g(mu(x))= X\beta + Z \alpha

### 5/13/2021

How to compare competing models:
1.	Look at fitted/predicted plots in one picture:  
         y ~ f_1(x),  y ~e^(f_2(x))
or even residual plots at the equalized scale (pattern and magnitude) and the transformed scales (pattern)
2.	Examine a numerical measure of GOF 
    || y - f_1(x)||^2,  ||y -e^(f_2(x))||
(or use GCV for GOP)

### 6/8/2021

To do:
•	Correction: Remove polyandrous
•	Sub models: 
1. Remove age, lengthmarray, b1momage
2. Include A, B, C group only, respectively.

•	Explain the variable importance measures

### 9/15/2021

1.	ICSA – hard and soft skills
2.	Tibetan Study: semiparametric model (p+n independently, stepwisely, iteratively)
3.	PEM: Formulation, review some references from ICSA
4.	Whole person training: 
o	Key elements of research (literature search, learning,  collaboration, solving problems, communication, …) 
o	Data Science Training
o	Personal & Professional Development 

•	Semiparametric model vs GAM
Original:
Semi: Y = h(x1)+ g(x2)+ e, where h is parametric while g is nonparametric, x1 and x2 mutually exclusive subsets of the predictors x
GAM: Y = \sum_{i=1}^p g_i (x_i) +e  


### 6/9/23

-	Draft an outline of dissertation
-	Create a gitHub space for communication
-	Continue with SGD, making a possible connection with sEM pipeline
-	Finish preparing the 3 chapters of  DL
-	Bring in at least one Q with substance 


### 8/29/2023

- SGD reference
- start to write
- identifiability
- optimization


### 10/4/23

- PEM: complete simulation, do an application (keep in mind of suitable data)

- ExpM:

1. Property A (Coverage and Length of Conformal Prediction Interval)

Property B (Convergence of MM algorithm, characterizing the objective functions, do we need penalty terms, ….)

2. Performance

C. Convergence of Joint Estimates?
     simulation+proof

D. Correct identification of features?

E. Modeling evaluated by prediction power/stability – repeated CV; CPI ; comparison with simple linear model and DL model?





