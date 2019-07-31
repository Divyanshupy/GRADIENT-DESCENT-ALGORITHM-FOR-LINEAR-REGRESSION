**Linear Regression**

In statistics, linear regression is a linear approach to modelling the
relationship between a dependent variable and one or more independent variables.
Let **X** be the independent variable and **Y** be the dependent variable. We
will define a linear relationship between these two variables as follows:

![https://miro.medium.com/max/375/1\*p3LTR6GB6g2MpRZzE5JIxw.png](media/40930ab3cd6e2f94481f9d464ae55b32.png)

![https://miro.medium.com/max/445/1\*ETn5o9GRaF8ZK6wIHvGrJQ.gif](media/1a4cd247031b4955490a5e9d626b0939.gif)

This is the equation for a line that you studied in high school. **m** is the
slope of the line and **c** is the y intercept.

Loss Function
=============

The loss is the error in our predicted value of **m** and **c**. Our goal is to
minimize this error to obtain the most accurate value of **m** and **c**.  
We will use the Mean Squared Error function to calculate the loss. There are
three steps in this function:

1.  Find the difference between the actual y and predicted y value(y = mx + c),
    for a given x.

2.  Square this difference.

3.  Find the mean of the squares for every value in X.

![https://miro.medium.com/max/375/1\*_y5QA1yF4w6LDDRxfTt6GA.jpeg](media/5726152058501f0a0fd903f0dcc3613a.jpg)

Here yᵢ is the actual value and ȳᵢ is the predicted value. Lets substitute the
value of ȳᵢ:

![https://miro.medium.com/max/500/1\*3cpC7oHy4IbH3o3Jc-ygVw.jpeg](media/a84d338351c9ec1f883d96ad2f7ba981.jpg)

So we square the error and find the mean. hence the name Mean Squared Error. Now
that we have defined the loss function, lets get into the interesting part —
minimizing it and finding **m** and **c.**

The Gradient Descent Algorithm
==============================

Gradient descent is an iterative optimization algorithm to find the minimum of a
function. 

![https://miro.medium.com/max/875/1\*N5WjbzwsCFse-KPjBWZZ6g.jpeg](media/93fb08c55d8a9f2d18efe24d0006d402.jpg)

Imagine a valley and a person with no sense of direction who wants to get to the
bottom of the valley. He goes down the slope and takes large steps when the
slope is steep and small steps when the slope is less steep. He decides his next
position based on his current position and stops when he gets to the bottom of
the valley which was his goal.  
Let’s try applying gradient descent to **m** and **c** and approach it step by
step:

1.  Initially let m = 0 and c = 0. Let L be our learning rate. This controls how
    much the value of **m** changes with each step. L could be a small value
    like 0.0001 for good accuracy.

2.  Calculate the partial derivative of the loss function with respect to m, and
    plug in the current values of x, y, m and c in it to obtain the derivative
    value **D**.

![https://miro.medium.com/max/500/1\*FvYfCBrl2gX9K-KxSO1eIw.jpeg](media/2e3fb32112464e1a92c64036569a5575.jpg)

Derivative with respect to **m**

Dₘ is the value of the partial derivative with respect to **m**. Similarly lets
find the partial derivative with respect to **c**, Dc :

![https://miro.medium.com/max/375/1\*rj09w2TcBxnHPtQ0oq4ehA.jpeg](media/251791392b0d271cb0e43ee4f086491e.jpg)

1.  Now we update the current value of **m** and **c** using the following
    equation:

![](media/ab59265db420cb5e26bbffe113af3091.jpg)

>   https://miro.medium.com/max/375/1\*JDcHqFK8jLcgQu1cj2XuVQ.jpeg

4. We repeat this process until our loss function is a very small value or
ideally 0 (which means 0 error or 100% accuracy). The value
of **m** and **c**that we are left with now will be the optimum values.

Now going back to our analogy, **m** can be considered the current position of
the person. **D** is equivalent to the steepness of the slope and **L** can be
the speed with which he moves. Now the new value of **m** that we calculate
using the above equation will be his next position, and **L×D** will be the size
of the steps he will take. When the slope is more steep (**D** is more) he takes
longer steps and when it is less steep (**D** is less), he takes smaller steps.
Finally he arrives at the bottom of the valley which corresponds to our loss =
0.  
Now with the optimum value of **m** and **c** our model is ready to make
predictions !
