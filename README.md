# Hyperparameter Optimization: Grid Search vs Randomized Search vs Genetic Algorithm (GA)

## 1. Introduction to Genetic Algorithms (GA)

Genetic Algorithms (GA) are search heuristics used to solve optimization problems by mimicking the process of natural selection. They belong to the class of evolutionary algorithms, which are inspired by the biological evolution process. GA is particularly useful for large and complex search spaces, and it explores the solution space by iterating over generations.

### 1.1 Components of Genetic Algorithm

#### 1.1.1 Initial Population
The initial population consists of a set of possible solutions represented as individuals. These individuals are usually created randomly or based on certain domain-specific rules.

#### 1.1.2 Fitness Score
Each individual in the population is evaluated using a fitness function, which measures how well it solves the optimization problem. The fitness score helps guide the search towards better solutions.

#### 1.1.3 Selection
Selection is the process of choosing individuals to participate in the next generation. The individuals with higher fitness scores have a higher chance of being selected. Popular selection methods include roulette wheel selection, tournament selection, and rank-based selection.

#### 1.1.4 Crossover (Recombination)
Crossover is a genetic operator used to combine the genetic information of two parent individuals to produce offspring. This simulates the process of reproduction in natural selection and allows the algorithm to explore new parts of the solution space.

#### 1.1.5 Mutation
Mutation introduces random changes in an individual’s solution. This process ensures genetic diversity within the population and prevents the algorithm from converging to local optima.

#### 1.1.6 Generating New Generation
After crossover and mutation, the new population is created. The individuals of the new generation are evaluated, and the process repeats for a specified number of generations or until convergence is reached.

### 1.2 GA Parameters

- **Number of Generations**: The number of iterations for evolving the population.
- **Population Size**: The number of individuals in the population.
- **Crossover Rate**: The probability of crossover occurring between two selected parents.
- **Mutation Rate**: The probability of mutation occurring in an individual.
- **Selection Method**: The strategy used to select individuals for reproduction (e.g., tournament selection, roulette wheel).

## 2. Work and Results

Below is the table summarizing the results of the different optimization methods:

| Method              | Hyperparameters               | Best Score (%) | Time Taken (minuts) |
|---------------------|-------------------------------|----------------|-----------------------|
| Grid Search         | batch size = 32, lr = 0.001, epochs = 10 | 97.21         | 15                    |
| Randomized Search   | batch size = 32, lr = 0.001, epochs = 10 | 97.43         | 29                    |
| Genetic Algorithm   | batch size = 49, lr = 0.001, epochs = 49 | 96.71         | 60                    |

## 3. Analysis

### 3.1 Grid Search
- **Best Score**: 97.21%
- **Time Taken**: 15 minuts
- **Advantages**:
  - Performs exhaustive search over a predefined set of hyperparameters.
  - Suitable for small, discrete search spaces.
  - Quick results when the hyperparameter space is limited.
- **Limitations**:
  - Inefficient for large or continuous search spaces.
  - May miss better solutions in complex spaces.

### 3.2 Randomized Search
- **Best Score**: 97.43%
- **Time Taken**: 29 minuts
- **Advantages**:
  - Randomly samples hyperparameter space, providing more flexibility.
  - Can be faster than Grid Search when the search space is large.
  - More efficient than Grid Search in some cases, as it may find good results faster.
- **Limitations**:
  - May not find the absolute best solution if the sampling is not broad enough.
  - Still may not be efficient in very large search spaces.

### 3.3 Genetic Algorithm (GA)
- **Best Score**: 96.71%
- **Time Taken**: 60 minuts
- **Advantages**:
  - Useful for complex, large, or non-linear search spaces.
  - Flexible and adaptable to different optimization problems.
  - Can incorporate domain-specific constraints or preferences.
- **Limitations**:
  - Computationally expensive and slower to converge.
  - May not always provide better performance than traditional methods like Grid Search or Randomized Search.

## 4. Final Interpretation

- **Grid Search**: Performs well with small, discrete search spaces. It is quick and efficient but may miss better results in larger spaces.
- **Randomized Search**: Slightly outperforms Grid Search in terms of accuracy while being more efficient in larger search spaces.
- **Genetic Algorithm (GA)**: Takes more time and results in slightly lower accuracy compared to Grid Search and Randomized Search. However, it is a strong candidate for large and complex search spaces.

## 5. When to Use Genetic Algorithm (GA)
- Large and Complex Search Spaces: GA is suitable for problems with large, non-linear, or continuous hyperparameter spaces where traditional methods may struggle.
- Difficult-to-Model Problems: If the relationship between hyperparameters is not straightforward or well-defined, GA can adapt to find better solutions.
- Flexibility: GA is ideal when domain-specific constraints or preferences need to be incorporated.

## 6. When to Use Grid Search or Randomized Search
- Small and Discrete Search Spaces: If the search space is small and discrete, Grid Search or Randomized Search will be much faster and efficient.
- Quick Results: When you need quick results and the search space is well-understood, Grid Search and Randomized Search are preferable.
- Smooth Objective Functions: If the objective function is smooth and continuous, Grid Search or Randomized Search will often be sufficient.

## 7. Conclusion
- **Grid Search and Randomized Search**: These methods are more efficient for smaller, well-defined search spaces, and they provide fast results.
- **Genetic Algorithm (GA)**: GA is better suited for more complex, large, or poorly understood search spaces, though it is computationally more expensive.
