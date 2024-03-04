# RNN-based-MPC
A CSTR example is used to illustrate the application of LMPC using RNN models to maintain the closed-loop state within the stability region.
## 1. Continuous Stireed Tank Reactor (CSTR) Example

- Let us consider a second-order, exothermic, irreversible reaction from A to B


<img src="https://github.com/Keerthana-Vellayappan/Demonstration-of-Physics-Informed-Machine-Learning-Model/assets/160836399/c1337cf1-eb78-47d7-b95b-1ce399d0ad10" alt = " Figure: Schematic diagram of a CSTR" width="250" height="250">



- The First Principle equation for this system are as follows:


     <img src="https://github.com/Keerthana-Vellayappan/Demonstration-of-Physics-Informed-Machine-Learning-Model/assets/160836399/da9e944b-1b0c-4694-8b48-2a21f49d55ed" width="300" height="90">



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

![image](https://github.com/Keerthana-Vellayappan/Demonstration-of-Physics-Informed-Machine-Learning-Model/assets/160836399/f41bd653-cb8d-43de-950e-71946ddc79d8)

- The above data sample is for a dataset with n samples with 6 internal time-steps for each sample.

- The code for demonstrating the PIRNN model for the CSTR is available [here](https://github.com/Keerthana-Vellayappan/Demonstration-of-Physics-Informed-Machine-Learning-Model/blob/main/CSTR%20PI-RNN%20Example.ipynb)


## 2. Recurrent Neural Network (RNN) Structure

- RNN are a class of neural networks that is powerful for modeling sequence data such as time series data.
- It can handle sequential data and account for past information in the current prediction.

- The RNN model input and output are as follows:
    - Input: System initial state variable 𝐱_𝟎(𝑡_𝑘), and control variables 𝐮(𝑡_𝑘).
    - Output: Future state dynamics 𝐱(𝑡_𝑘+Δ) are predicted for one sampling period ∆.
<p align="center">
<img src="https://github.com/Keerthana-Vellayappan/Demonstration-of-Physics-Informed-Machine-Learning-Model/assets/160836399/332a1da6-9b89-4e04-a6b3-1b5c90185319" width="600" height="250">
</p>


## 3. Libraries and Tools used

[Tensorflow]((https://www.tensorflow.org/): Deep learning framework used for building and training neural networks.

[Matplotlib](https://matplotlib.org/): Python plotting library for creating visualizations.

[SciPy](https://www.scipy.org/): Open-source library used for scientific and technical computing.

[scikit-learn](https://scikit-learn.org/): Machine learning library for Python used for data analysis and modeling.


## 4. Citation

The demonstration of these examples are adapted from the following literature work:

Wu, Z., Tran, A., Rincon, D., & Christofides, P. D. (2019). Machine learning‐based predictive control of nonlinear processes. Part I: theory. AIChE Journal, 65(11), e16729.

Wu, Z., Tran, A., Rincon, D., & Christofides, P. D. (2019). Machine‐learning‐based predictive control of nonlinear processes. Part II: Computational implementation. AIChE Journal, 65(11), e16734.

Additionally, you can find our paper [here]( https://doi-org.libproxy1.nus.edu.sg/10.1002/aic.16734)
