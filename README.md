# Genetic Algorithm for Exam Scheduling Optimization

## Objective
The primary goal of this code is to optimize the scheduling of exams by assigning courses to classrooms while adhering to constraints such as room capacity and type compatibility. By using a Genetic Algorithm (GA), the implementation ensures an efficient allocation of resources, minimizing conflicts and maximizing satisfaction for all stakeholders.

## Overview
This project is centered around solving a combinatorial optimization problem related to exam scheduling. Given the constraints of classroom capacity and type compatibility, the Genetic Algorithm:

1. Randomly generates an initial population of potential schedules.
2. Iteratively improves these schedules through fitness-based selection, crossover, and mutation.
3. Outputs the best solution—a schedule that adheres to constraints and maximizes overall fitness.

This approach demonstrates the practical application of artificial intelligence in solving real-world problems and optimizing resources.

---

## 1. Classrooms Dataset Analysis
The dataset classrooms.csv serves as the foundation for room assignments in the algorithm.

### Dataset Attributes
- **classroom_id**: Unique identifier for each classroom.
- **building_name**: Name of the building where the classroom is located.
- **room_number**: Specific room number within the building.
- **capacity**: Maximum seating capacity.
- **room_type**: Classification (for example: Lecture Hall, Classroom).

### Dataset Highlights
- **Total Rows**: 30
- **Columns**: 5
- **No missing values** in the dataset.

### Sample Data
| classroom_id | building_name | room_number | capacity | room_type   |
|--------------|---------------|-------------|----------|-------------|
| 1            | A             | 305         | 35       | Lecture Hall|
| 2            | K             | 144         | 24       | Classroom   |
| 3            | B             | 710         | 46       | Classroom   |
| 4            | A             | 541         | 30       | Classroom   |
| 5            | I             | 747         | 35       | Lecture Hall|

### 1.1. Data Augmentation
To create a more robust testing environment, the original dataset of 30 rows was expanded to 100 rows using synthetic data generation. Random values were added for attributes like building_name, room_number, capacity, and room_type, while maintaining the realistic distribution of classroom properties.

---

## 2. Genetic Algorithm Implementation
The Genetic Algorithm systematically searches for the optimal solution through:

1. **Population Initialization**: Generates random schedules.
2. **Fitness Evaluation**: Scores schedules based on adherence to constraints.
3. **Selection**: Chooses the best schedules for reproduction.
4. **Crossover and Mutation**: Introduces variation to improve solutions.

### 2.1. Key Parameters
| Parameter       | Value | Description                                          |
|-----------------|-------|------------------------------------------------------|
| Population Size | 50    | Number of chromosomes (schedules) in each generation.|
| Generations     | 20    | Number of iterations to refine solutions.            |
| Crossover Rate  | 70%   | Probability of combining two chromosomes to create new offspring.|
| Mutation Rate   | 10%   | Probability of altering a chromosome to introduce diversity.|

### 2.2. Fitness Function
The fitness function evaluates the quality of a chromosome (solution) by:
1. **Room Type Compatibility**: Ensuring assigned classrooms match course requirements.
2. **Capacity Sufficiency**: Confirming classrooms can accommodate the number of students.

### 2.3. Selection Process
A weighted random selection ensures that chromosomes with higher fitness scores are more likely to be chosen for crossover. This approach mimics the concept of "survival of the fittest."

### 2.4. Crossover and Mutation
- **Crossover**: Combines traits from two parent chromosomes to produce offspring.
- **Mutation**: Introduces small changes to offspring, maintaining genetic diversity.

### 2.5. Execution Process
1. Initialize a random population of 50 schedules.
2. Compute fitness scores for all schedules.
3. Apply selection, crossover, and mutation iteratively for 20 generations.
4. Output the best schedule with the highest fitness score.

---

## 3. Results and Key Outcomes

### Final Outputs
1. **Best Fitness Score**: A numerical representation of the best schedule's quality.
2. **Optimal Schedule**: A detailed mapping of courses to classrooms.

### Performance Highlights
- **Conflict-Free Scheduling**: Ensures no overlapping or overcapacity issues.
- **Efficient Resource Allocation**: Maximizes utilization of classroom resources.
- **Scalability**: Handles large datasets effectively (tested with up to 100 classrooms).

---

## 4. Applications
This project demonstrates the practical application of Genetic Algorithms in educational logistics. Key use cases include:

1. **Exam Scheduling**: Allocating classrooms and time slots for exams efficiently.
2. **Timetable Optimization**: Generalizing the solution to full academic schedules.
3. **Resource Management**: Adapting the framework to other resource allocation problems.

---

## Conclusion
The Genetic Algorithm successfully optimizes exam scheduling by balancing room type compatibility and capacity requirements. Its iterative approach, leveraging fitness-based selection and genetic operators, ensures effective and conflict-free scheduling. This solution is a scalable and adaptable tool for educational institutions aiming to streamline their logistics.
