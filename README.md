# Linear regression Boston House Dataset

## What is linear regression?
Linear regression is a linear approach for modelling the relationship between a scalar response and one or more explanatory variables. The case of one explanatory variable is called simple linear regression; for more than one, the process is called multiple linear regression. We have two different approach for find wights of Linear regression. first one is closed form of Linear regression which we can find weights of our model in one step. 
second is to use gradiant descent to obtain local optimal answer in specific steps. 

## Closed form 
in Linear regression problems, our goal is to minimize following loss function : 

$$c(x) = \frac{1}{2} (Y-\phi W)^T(Y-\phi W) + \frac{1}{2} \lambda W^TW$$

where **$\phi$ is concatination of original data with column vector of 1 for bias term**

$$minimize \ c(x)=\frac{1}{2} (Y-\phi W)^T(Y-\phi W) + \frac{1}{2} \lambda W^TW
$$

$$
\Rightarrow^{Expanding} \ c(x)=\frac{1}{2} (Y^{T}Y+W^{T}\phi^{T}\phi W-2W^{T}\phi^{T}Y+\lambda W^TW)
$$

$$
\Rightarrow^{derivative} c'(x) =(\phi^{T}\phi W-\phi^{T}Y+\lambda W)
$$

$$
c'(x)=0 → (\phi^{T}\phi W-\phi^{T}Y+\lambda W)=0
$$

$$
\boxed{W^{*}=(\phi^T\phi-\lambda I)^{-1}\phi^{T}Y}
$$

 below is the result of predicting output($Y$) based on weights($W$) and inputs($X$) using closed form method.
 
![1](https://user-images.githubusercontent.com/67091916/219363100-3bde6e71-7602-4735-949e-c56f2bd8a609.png)
![3](https://user-images.githubusercontent.com/67091916/219363776-8a351fef-625f-48d6-8b7f-936977ba383e.png)
![2](https://user-images.githubusercontent.com/67091916/219363784-b18a96fc-4002-45bf-bba7-4965f8c20f0a.png)

* we want our model  to works well not only with training or test data, but also with the data it'll receive in the future. In summary, to achieve this, regularization shrinks the weights toward zero to discourage complex models

* **in the above case, becuase our model didn't see enough data, using regularization, avoid our model from training better. that is why eror becomes greater as lambda goes up**. 
## Add square and power of three of each feature to data set and use closed form linear regression


![5](https://user-images.githubusercontent.com/67091916/219364590-8731cb50-219f-4ebd-aef1-6359dd638f37.png)
![4](https://user-images.githubusercontent.com/67091916/219364600-6e6ffa92-a29a-4916-a6a3-d19c8e1bc0e5.png)

### why using polynomial transformation help model to fit better? 

Polynomial feature transformation, extends the linear model by adding extra predictors, obtained by raising each of the original predictors to a power. For example, a cubic regression uses three variables, $X$, $X^{2}$, and $X^{3}$, as predictors. This approach provides a simple way to provide a non-linear fit to data.

**as we can see above, error of cubic regression is less than linear regression .**

### gradient descent method in Linear regression 

$$
newton \ raphson \ method \ : \ W^{k+1}=W^{k}-H_{k}^{-1}G_{k}
$$

$$
\ where  \ H_{k} \ is \ hessian \ matrix \ and \ G_{k} \ is \ gradient \ vector \ of \ loss \ function.
$$

$$
from \ previous \ part \ we \ know \ that \ G_{k}= \phi^{T}\phi W-2ϕ^{T}Y+2λW
$$

$$
for \ H_{k} \ we \ have \  \boxed{H_{k}=(\phi^{T}\phi-\lambda I)^{-1}}
$$

 below is the result of predicting output($Y$) based on weights($W$) and inputs($X$) using gradient descent method.
 
![6](https://user-images.githubusercontent.com/67091916/219366332-248beb7c-267c-4082-bc4c-722534900d59.png)

![7](https://user-images.githubusercontent.com/67091916/219366338-a1ff8022-1406-4607-beaa-24c545d0435a.png)
![8](https://user-images.githubusercontent.com/67091916/219366321-64fb3fa6-30e5-4405-a270-422bacd7b23a.png)

* we want our model to works well not only with training or test data, but also with the data it'll receive in the future. In summary, to achieve this, regularization shrinks the weights toward zero to discourage complex models

* **you can see the effect of regularization above. as lambda goes up, eror rate decreases approximatly exponentialy**

## Add square and power of three of each feature to data set and use  gradient descent form of linear regression


