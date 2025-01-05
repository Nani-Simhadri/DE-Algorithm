The Differential Evolution (DE) Algorithm is a population-based optimization algorithm [1] used to optimize non-linear and real-valued continuous space functions. The DE algorithm involves the use of three processes known as mutation, crossover, and selection to optimize the functions. The DE algorithm has three parameters, which are population size (denoted as $PS$), mutation factor (denoted as $F_m$), and crossover probability (denoted as $CP$).

[1] R. Storn, K. Price, “Differential Evolution – A Simple and Efficient Heuristic for global Optimization over Continuous Spaces,” J Glob. Optim., vol. 11, no. 4. Springer Science and Business Media LLC, pp. 341–359, 1997.

The DE algorithm can also be used to optimize functions with multiple real-valued constraints using the penalty function method [2].

[2] Changshou Deng, Changyong Liang, Bingyan Zhao, and Anyuan Deng, "New penalty function with differential evolution for constrained optimization," 2008 7th World Congress on Intelligent Control and Automation, Chongqing, China, 2008, pp. 5304-5307, doi: 10.1109/WCICA.2008.4593792.
 
The DE algorithm has been used as an optimization technique in the fields of electronics, instrumentation, and measurements, and a list of the research papers that have discussed the use of the DE algorithm is given below.

[3] R. Yang, X. Li, R. Cong and J. Du, "A Novel Cylindricity Measurement Method for Large Workpiece Based on Improved Model and Algorithm, " in IEEE Transactions on Instrumentation and Measurement, vol. 73, pp. 1-11, 2024, Art no. 3000211, doi: 10.1109/TIM.2023.3331408.

[4] Z. Qiu and Y. Zhang, "Three-Dimensional Low-Frequency Earthquake Monitoring Vibration Sensor Based on FBG," in IEEE Transactions on Instrumentation and Measurement, vol. 73, pp. 1-9, 2024, Art no. 9510709, doi: 10.1109/TIM.2024.3406839.

[5] T. Mathew, N. Simhadri, E. K, A. Chandrika Sreekantan and V. B. Sukumaran, "A Digital Thermistor Read-Out Based on Charge-Discharge Topologies Coupled With Optimal Linearization Strategies," in IEEE Sensors Journal, vol. 24, no. 24, pp. 41099-41109, 15 Dec.15, 2024, doi: 10.1109/JSEN.2024.3483906.

[6] N. Simhadri, V. B. S and A. Chandrika Sreekantan, "Resistance Network Synthesis for Analog Thermistor-Linearizer Circuits using Differential Evolution and Graph Laplacian," 2023 16th International Conference on Sensing Technology (ICST), HYDERABAD, India, 2023, pp. 1-6, doi: 10.1109/ICST59744.2023.10460779. 

[7] T. Mathew, S. Nani, A. C. S. and V. B. S., "Studies on Linearizing Direct-Digital Converter Schemes for Thermistors," 2023 IEEE International Instrumentation and Measurement Technology Conference (I2MTC), Kuala Lumpur, Malaysia, 2023, pp. 1-6, doi: 10.1109/I2MTC53148.2023.10176107.

[8] S. Sundararajan, K. N. Madhusoodanan, A. Abudhahir and G. Noble, "Implementation and Analysis of an Evolutionary Optimized Non-Linear Function for Linearization of Thermo-Resistive Sensors," 6th International Conference on Devices, Circuits and Systems (ICDCS), Coimbatore, India, 2022, pp. 74-79, doi: 10.1109/ICDCS54290.2022.9780706.

The basic implementation of the DE algorithm available in the Python SciPy library [9] helps to optimize the functions. In addition, it helps in creating the framework without the need for substantial efforts, followed by the choice of fine-tuning and defining the aforementioned three DE parameters (population size, mutation factor, and crossover probability), search space, and linear and non-linear constraints functions as per the user application to solve the optimization problem. 

[9] DE algorithm implementation of SciPy library - https://docs.scipy.org/doc/scipy/reference/generated/scipy.optimize.differential_evolution.html

DE for Solution of duty-ratio based thermistor linearizer (DTL) Optimization :

The optimization problem is a non-linear function with possibly multiple minima. This problem requires the use of evolutionary methods [10], [6] to locate the global optimum. We propose the use of the DE [1] as the optimization method to minimize \%NL subject to constraints $\vert{m}\vert$ and $V_{L} \leq V_{theta} \leq V_{H}$.

[10] E. K, B. A. Sontakke and A. Chandrika Sreekantan, "Design, Analysis, and Hardware Verification of a Linearized Thermistor-Based Temperature Measurement System," in IEEE Transactions on Instrumentation and Measurement, vol. 71, pp. 1-9, 2022, Art no. 2002709, doi: 10.1109/TIM.2022.3167787.

Optimization Problem : minimization of \%NLsubject to constraints $\vert{m}\vert$ and $V_{L} \leq V_{theta} \leq V_{H}$.
              
DE optimizes an objective function by maintaining a population of decision variable vectors. The value of the objective function for each decision variable vector is used to evolve the population iteratively. As the iteration proceeds, the population contains decision variable vectors with better values for the objective function. The evolution algorithm has three important parameters, namely population size ($PS$), mutation factor ($F_m$), and crossover probability ($CP$). We use the following values: $PS\geq4$, $F_m\in[0,2]$, and $CP\in[0,1]$. The parameters/symbols used in the DE optimization are expanded and are given below for ease of reference.
                                                                                                   
   a. $PS$                    = Population Size
                                                                                                  
   b. $F_m$                   = Mutation Factor
                                                                                                  
   c. $CP$                    = Crossover Probability
                                                                                            
   d. $g$                     = Generation Index
                                                                                                 
   e. $i$                     = Index in the Population Size
                                                                                   
   f. $D$                     = Dimension of the Decision Variable Vector
                                                                        
   g. $j$                     = Index of the Decision Variables, $1, \ldots, D$
                                                                  
   h. $p_1$, $p_2$, and $p_3$ = Random Indexes in the Population different from the running Index $i$

   i. $rand_{j,i}$            = Uniformly Distributed Random Value in the range $[1, D]$

   j. $I_{rand}$              = Randomly Selected Integer in the range $[1, D]$
                                                                  
   k. $x^{g}[i]$              = Decision Variable Vector
                                                                                                 
   l. $V^{g+1}[i]$            = Donor Vector
                                                                                                    
   m. $U^{g+1}[i]$            = Trial Vector                                                                                                     

Consider that $NL(x)$ represents the objective function (\%NL), where $x$ stands for the decision variable vector. In our case, $x\in[G, d, R_1, R_2]$. Note that $G$ is included in the vector, though it does not directly affect the \%NL of $V_{\theta}$. However, inclusion of $G$ enables us to obtain the minimum gain needed to meet the $S_L$ condition, while satisfying other constraints. As a first step for minimizing $NL$, an initial population, with $PS$ number of $x$, is randomly and uniformly selected within the lower and upper bounds of $x$.

Objective Function:

\%NL = $\left( \frac{\max_{k}(\vert{V_{\theta{k}}- (m\theta_{k} + c)}\vert)}{V_{\theta1}-V_{\theta{N}}}\right)\times 100\%$

The decision-variable vectors have the form: $x^{g}[i]$ = $[x^{g}_{1}[i], \ldots, x^{g}_{D}[i]]$,
where, $i$ stands for the index in the population, $i=1,\ldots,PS$, $D$ is the dimension of the decision-variable vector, and $g$ is the generation index.

The process of the DE algorithm is as follows:

1. Mutation: In mutation phase, for each decision variable vector, $x^{g}[i]$, the DE algorithm creates the donor vector, $V^{g+1}[i]$, according to the equation
$V^{g+1}[i]$ = $x^{g}[p_1]$ + $F_{m}(x^{g}[p_2] - x^{g}[p_3])$.
   For this purpose, three other decision variable vectors: $x^{g}[p_1]$, $x^{g}[p_2]$, and $x^{g}[p_3]$, where the indices $p_1$, $p_2$, and $p_3$ are randomly selected and $i$, $p_1$,     $p_2$, and $p_3$ are distinct, are used.

2. Recombination: Here, the trial vector, $U^{g+1}[i]$, is generated using the decision variable vector, $x^{g}[i]$ and the donor vector, $V^{g+1}[i]$.

where $rand_{j,i}$ is an independent sample from a uniformly distributed random value in the range [0, 1], $j=1,\ldots,D$, and $I_{rand}$ is an integer selected uniformly at random from $[1,\ldots,D]$.

3. Selection: In the selection phase, the objective function values of the trial vector and the decision variable vector are compared for population selection to the next generation. The vector with the minimum objective function value is given to the next generation.

The DE algorithm modifies the decision-variable vectors by applying mutation, recombination, and selection phases until the termination criteria are satisfied. The DE algorithm returns the optimal decision variable vector, for which the objective function is minimal, once the termination conditions are satisfied. The termination conditions of the DE algorithm are mentioned in [6]. This algorithm was applied to linearize the characteristics of commercial thermistors.
