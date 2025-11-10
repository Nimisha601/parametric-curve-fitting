# parametric-curve-fitting
Finding the values of unknown variables in the given parametric equation of a curve

\left(t*\cos(0.49076)-e^{0.02139\left|t\right|}\cdot\sin(0.3t)\sin(0.49076)+54.9007,\;42+t*\sin(0.49076)+e^{0.02139\left|t\right|}\cdot\sin(0.3t)\cos(0.49076)\right)

Explaination 

problem statement 
Find the values of unknown variables in the given parametric equation of a curve :
    x=\left(t*\cos(\theta)-e^{M\left|t\right|}\cdot\sin(0.3t)\sin(\theta)\ +X \right )
    y = \left (42 + t*\sin(\theta)+e^{M\left|t\right|}\cdot\sin(0.3t)\cos(\theta)\right)
unknowns are 
   \theta , M ,X
Given range for unknown params is :
   0 \deg<\theta<50 \deg \\
   -0.05<M<0.05 \\
   0<X<100\\
 parameter ‘t’ has range: 6-60  

 solution :
      Step I: Import Libraries
             pandas → to read data from CSV file
             numpy → for math functions
             math → to convert angles from degree to radians
             minimize → to find the best value
      Step II: Load Dataset
      Step III:
            In our dataset, we have x_real and y_real (the real data points).
            But t is not given, so we derive t.
            as given that t ranges between 6 to 60.
            So for each x, y  in dataset we will derive  t starting from 6 which has equal spaces between them.
            using np.linspace(6, 60, len(x_real))
      Step IV: The function get_curve_points just predicts the values of
                  x_pred and y_pred using the formula given in the question.
                  x_pred and y_pred are correct if they fit in our dataset.
      Step V:This is the important step. Here we optimize the values of theta (θ), M, and X so that when placed in the equation, the error is minimum.
             The error is calculated as the mean of absolute differencesn between x_real and x_predicted, plus y_real and y_predicted for every (x_real, y_real) in the dataset 
      Step VI :Find the Best Values 
              We start with an initial guess for the unknown variables θ (theta), M, and X.
             Then we use the minimize() function to get the best values of θ, M, and X so that the error is minimized.
             It works like gradient descent,where the code keeps changing θ, M, X slightly to find the combination that gives the smallest error.
      Step VII – Print and Plot the Result
                Then we print the final results (the best values of θ, M, and X) and plot the graph to compare the predicted curve with the real data points from the dataset.       
    
    

