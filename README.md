# Linear regression Boston House Dataset

## What is linear regression?
Linear regression is a linear approach for modelling the relationship between a scalar response and one or more explanatory variables. The case of one explanatory variable is called simple linear regression; for more than one, the process is called multiple linear regression. We have two different approach for find wights of Linear regression. first one is closed form of Linear regression which we can find weights of our model in one step. 
second is to use gradiant descent to obtain local optimal answer in specific steps. 

### Closed form 
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

 below is the result of predicting output($Y$) based on weights($W$) and inputs($X$).
 
![1](https://user-images.githubusercontent.com/67091916/219363100-3bde6e71-7602-4735-949e-c56f2bd8a609.png)
![3](https://user-images.githubusercontent.com/67091916/219363776-8a351fef-625f-48d6-8b7f-936977ba383e.png)
![2](https://user-images.githubusercontent.com/67091916/219363784-b18a96fc-4002-45bf-bba7-4965f8c20f0a.png)

* we want our model  to works well not only with training or test data, but also with the data it'll receive in the future. In summary, to achieve this, regularization shrinks the weights toward zero to discourage complex models

* **in the above case, becuase our model didn't see enough data, using regularization, avoid our model from training better. that is why eror becomes greater as lambda goes up**. 
## Add square and power of three of each feature to data set and use closed form linear regression



