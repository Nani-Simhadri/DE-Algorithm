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

The basic implementation of the DE algorithm available in the Python SciPy library [] helps to optimize the functions. In addition, it helps in creating the framework without the need for substantial efforts, followed by the choice of fine-tuning and defining the aforementioned three DE parameters (population size, mutation factor, and crossover probability), search space, and linear and non-linear constraints functions as per the user application to solve the optimization problem. 

[9] DE algorithm implementation of SciPy library - https://docs.scipy.org/doc/scipy/reference/generated/scipy.optimize.differential_evolution.html

DE for Solution of DTL Optimization :

The optimization problem in \eqref{eq:optimizationproblem} is a non-linear function with possibly multiple minima. This problem requires the use of evolutionary methods [], [] to locate the global optimum. We propose the use of the DE [1] as the optimization method for solving \eqref{eq:optimizationproblem}. DE optimizes an objective function by maintaining a population of decision variable vectors. The value of the objective function for each decision variable vector is used to evolve the population iteratively. As the iteration proceeds, the population contains decision variable vectors with \enquote{better} values for the objective function. The evolution algorithm has three important parameters, namely population size ($PS$), mutation factor ($F_m$), and crossover probability ($CP$). We use the following values: $PS\geq4$, $F_m\in[0,2]$, and $CP\in[0,1]$. The parameters/symbols used in the DE optimization are tabulated and expanded in Table for ease of reference.

Consider that $NL(x)$ represents the objective function (\%NL), where $x$ stands for the decision variable vector. In our case, $x\in[G, d, R_1, R_2]$. Note that $G$ is included in the vector, though it does not directly affect the \%NL of $V_{\theta}$. However, inclusion of $G$ enables us to obtain the minimum gain needed to meet the $S_L$ condition, while satisfying other constraints. As a first step for minimizing $NL$, an initial population, with $PS$ number of $x$, is randomly and uniformly selected within the lower and upper bounds of $x$.

\%NL = $\left( \frac{\max_{k}(\vert{V_{\theta{k}}- (m\theta_{k} + c)}\vert)}{V_{\theta1}-V_{\theta{N}}}\right)\times 100\%$

The decision-variable vectors have the form: $x^{g}[i]$ = [$x^{g}_{1}[i]$, $x^{g}_{2}[i]$, $\ldots$, $x^{g}_{D}[i]$]
where, $i$ stands for the index in the population, $i=1,\ldots,PS$, $D$ is the dimension of the decision-variable vector, and $g$ is the generation index.

The process of the DE algorithm is as follows:
