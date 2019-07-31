**Linear Regression**

In statistics, linear regression is a linear approach to modelling the
relationship between a dependent variable and one or more independent variables.
Let **X** be the independent variable and **Y** be the dependent variable. We
will define a linear relationship between these two variables as follows:

![image](https://user-images.githubusercontent.com/36807028/62227651-f028ed80-b3d9-11e9-919e-753214e475f6.png)

![image](<https://user-images.githubusercontent.com/36807028/62227740-18b0e780-b3da-11e9-976c-605e88bafa7f.png>)

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

![image](<https://user-images.githubusercontent.com/36807028/62228067-a42a7880-b3da-11e9-9b83-340f3e205559.png>)

Here yᵢ is the actual value and ȳᵢ is the predicted value. Lets substitute the
value of ȳᵢ:

![image](https://user-images.githubusercontent.com/36807028/62228271-f8355d00-b3da-11e9-809d-52a028d8cc25.png)

So we square the error and find the mean. hence the name Mean Squared Error. Now
that we have defined the loss function, lets get into the interesting part —
minimizing it and finding **m** and **c.**

The Gradient Descent Algorithm
==============================

Gradient descent is an iterative optimization algorithm to find the minimum of a
function. 

![image](https://user-images.githubusercontent.com/36807028/62228297-05eae280-b3db-11e9-9849-ff2bb1096c2e.png)

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

![image](https://user-images.githubusercontent.com/36807028/62228385-2ca91900-b3db-11e9-8d94-45b367efeb72.png)

Derivative with respect to **m**

Dₘ is the value of the partial derivative with respect to **m**. Similarly lets
find the partial derivative with respect to **c**, Dc :

![image](https://user-images.githubusercontent.com/36807028/62228524-709c1e00-b3db-11e9-858d-71d6cadf2205.png)

Now we update the current value of **m** and **c** using the following equation:

![image](https://user-images.githubusercontent.com/36807028/62228553-84478480-b3db-11e9-8749-2e26d03f8513.png)

3.We repeat this process until our loss function is a very small value or
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
