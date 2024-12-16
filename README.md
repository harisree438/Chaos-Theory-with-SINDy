 Discovering Governing Equations From Data By Sparse Identification Of Nonlinear Dynamical Systems
  
|  Time-series-data-analysis                       |
|  Chaos Theory – Time-Series Modeling using SINDy |
  
  Method: SINDy framework

  Python libraries: NumPy, matplotlib, and PySINDy

  Results: Visualizations of predictions and governing dynamics.

   Tools: Python

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Problem Statement: 

1. Governing Equation Challenge: Extracting governing equations from data is a central challenge in diverse fields like climate science, neuroscience, ecology, finance, and epidemiology.

2. Elusiveness of Models: Models remain elusive in various scientific domains, hindering a comprehensive understanding of system dynamics.

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Objective :

1. Sparse Identification: Identify concise governing equations using sparse models for accurate representation of system dynamics.
2. Nonlinear Dynamics: Capture and understand nonlinear relationships within data, addressing the inherent nonlinear behavior of real-world systems.
3. Data-Driven Approach: Rely on data, not pre-existing knowledge, to uncover governing equations, ensuring applicability to a wide range of systems.
4. Model Simplicity: Emphasize simplicity in discovered models, favoring sparse representations for interpretability and ease of use.
5. Generalizability: Design the approach to generalize across diverse datasets and systems, providing a versatile modeling tool.

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

   Data Set Description: Chaotic Lorenz System

1. Time Series Data: The dataset records state variable values over discrete time intervals, capturing the system's dynamic evolution.
2. Chaotic Dynamics: The Lorenz system exhibits chaotic behavior, leading to complex and unpredictable trajectories with sensitivity to initial conditions.
3. Three-Dimensional Data: Each data point represents a three-dimensional state vector (x, y, z) at a specific time step, reflecting the Lorenz system's inherent three-dimensionality.

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
    Experimental setup

1. Data preprocessing : 
  Define parameters:  regularization parameter (λ), time step (dt), and maximum time (t_max).
  Extract individual components (x, y, z) from the loaded data.
  Compute derivatives (dx/dt, dy/dt, dz/dt) using numerical gradients.

2. Construct Theta matrix :
  Build the design matrix (Theta(X)) incorporating constants, individual variables, products, squared terms, and trigonometric functions.

                              Θ(X) = [1.. X,X^2,X^3...   sin(X)   cos(X)   ...]

3. SINDy iterative Algorithm :

Iterative Coefficient Refinement: Iterate to set small coefficients to zero and update non-zero coefficients using least squares regression (χ_i).
Significant Term Identification: Identify and keep significant terms, pruning less influential ones during each iteration.
Regularization Threshold (𝜆): Use 𝜆 as a threshold to discard small coefficients, achieving a sparse system dynamics representation.

4. Model Evaluation: 
Simulate the Lorenz system using the obtained coefficients and the odeint function and comparing it with original coefficients.
Visualize and compare the generated data with the original data in a 3D plot.
Calculate the Root Mean Squared Error (RMSE) to quantify the accuracy of the model.
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
 
  
  Performance Measures

1. Simulation and Visualization of SINDy-Generated Lorenz System Trajectories
    Utilizing the obtained coefficients and the odeint function to simulate the Lorenz system dynamics.
    Plotting the dynamics of the SINDy-generated Lorenz system alongside the original data to facilitate a detailed comparison of the results.
2. Data Regeneration: 
   Use the discovered governing equations to regenerate data points and compare them with the original data. This validates if the equations capture the essential dynamics.
3. Root Mean Squared Error (RMSE):
   Calculate the Root Mean Squared Error (RMSE) to quantify the accuracy of the model.
   It is used  as a metric for comparing SINDy-generated data with the original data.
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Results are showcased in the .ipynb file
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

  Conclusion 
  
SINDy : The Sparse Identification of Nonlinear Dynamics (SINDy) algorithm successfully unraveled the governing equations underlying the chaotic Lorenz system.
Iterative Coefficient Refinement: Through an iterative process, SINDy refined initial coefficients to yield final unknown coefficients, demonstrating the algorithm's effectiveness in capturing significant terms.

Visualization and Validation: The SINDy-generated data was visually compared in a three-dimensional plot, showcasing a reliable fit with the original Lorenz system dynamics. Data regeneration further validated the discovered governing equations.

Quantitative Accuracy: The Root Mean Squared Error (RMSE) of 11.576 quantifies the accuracy of the SINDy-generated model, providing a numerical measure of the alignment between predicted and actual values.

Broad Applicability: The study highlights the broader applicability of SINDy as a data-driven approach, offering valuable insights into complex dynamics across diverse scientific domains.

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Possible future directions

1. Polynomial and specialized nonlinear terms, could refine the algorithm's ability to capture intricate system dynamics.
2. L1 Regularization Implementation: Consideration of L1 regularization techniques in the sparse regression process could contribute to obtaining more refined and accurate results. 
3. Adaptive Parameter Tuning: Exploring adaptive parameter tuning strategies, such as dynamic adjustment of the regularization parameter (𝜆), could further optimize the algorithm's 
   performance. 
4. Benchmarking and Comparison: Extensive benchmarking against alternative data-driven methods and traditional modeling approaches could provide a comprehensive evaluation of SINDy's 
    strengths and limitations.
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
   References
   
1. Brunton, S., Proctor, J., & Kutz, J. (2016). Discovering governing equations from data by sparse identification of nonlinear dynamical systems. Proceedings of the National Academy 
    of  Sciences, 113(15), 3932-3937.
2. Brunton, S., & Kutz, J. (2019). Data-driven science and engineering: Machine learning, dynamical systems, and control. Cambridge University Press.
3. Proctor, J., & Brunton, S. (2019). Sparse identification of nonlinear dynamics for model predictive control in the low-data limit. IEEE Transactions on Control of Network Systems,  6(3), 1028-1038.
4. Brunton, S., & Kutz, J. (2020). Machine learning for dynamical systems. Annual Review of Fluid Mechanics, 52, 477-508. 


