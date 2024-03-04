# RNN-based-MPC
A CSTR example is used to illustrate the application of LMPC using RNN models to maintain the closed-loop state within the stability region.
## 1. Continuous Stireed Tank Reactor (CSTR) Example

- Let us consider a second-order, exothermic, irreversible reaction from A to B






- The First Principle equation for this system are as follows:
  

     
     <img src="https://github.com/GuoQWu/RNN-based-MPC/assets/85721266/ccfdf6cd-f984-4232-8dd4-1b1c4e5e84e4" width="300" height="300">



- Where,

   - 𝐶_𝐴: Concentration of reactant A (kmol/m3)
   - 𝑇: Temperature of the reactor (K)
   - 𝐶_𝐴0: Concentration of reactant A in the feed
   - 𝑄 :  Heat input rate (kJ/h)
   - F: feed volumetric flow rate (m3/h)
   - 𝑇0: Inlet temperature (K)


- The State and Manipulated variable for this system is:

    - States variables: 𝐱=[𝐶_𝐴−𝐶_𝐴𝑠, 𝑇 −𝑇_𝑠 ]
    - Control / Manipulated variables: 𝐮=[𝐶_𝐴0−𝐶_𝐴0𝑠, 𝑄 −𝑄_𝑠 ]


- The generated dataset with the input and output will look like:

![image](https://github.com/GuoQWu/RNN-based-MPC/assets/85721266/e0e9f633-f1c6-4e22-922f-59ba22f60b0c)


- The above data sample is for a dataset with n samples with 10 internal time-steps for each sample.

- The code for generating the data set for RNN model is available [here]


## 2. Recurrent Neural Network (RNN) Structure

- RNN are a class of neural networks that is powerful for modeling sequence data such as time series data.
- It can handle sequential data and account for past information in the current prediction.

- The RNN model input and output are as follows:
    - Input: System initial state variable 𝐱_𝟎(𝑡_𝑘), and control variables 𝐮(𝑡_𝑘).
    - Output: Future state dynamics 𝐱(𝑡_𝑘+Δ) are predicted for one sampling period ∆.


<p align="center">
<img src="https://github.com/GuoQWu/RNN-based-MPC/assets/85721266/418a7474-f8ff-4eb9-bae9-a3adff794d53" width="600" height="250">
</p>


## 3. Libraries and Tools used

[Tensorflow](https://www.tensorflow.org/): Deep learning framework used for building and training neural networks.

[Matplotlib](https://matplotlib.org/): Python plotting library for creating visualizations.

[SciPy](https://www.scipy.org/): Open-source library used for scientific and technical computing.

[scikit-learn](https://scikit-learn.org/): Machine learning library for Python used for data analysis and modeling.


## 4. Citation

The demonstration of these examples are adapted from the following literature work:

Wu, Z., Tran, A., Rincon, D., & Christofides, P. D. (2019). Machine learning‐based predictive control of nonlinear processes. Part I: theory. AIChE Journal, 65(11), e16729.

Wu, Z., Tran, A., Rincon, D., & Christofides, P. D. (2019). Machine‐learning‐based predictive control of nonlinear processes. Part II: Computational implementation. AIChE Journal, 65(11), e16734.

Additionally, you can find our paper [here]( https://doi-org.libproxy1.nus.edu.sg/10.1002/aic.16734)
