# Evolutionary-Algorithm
A evolutionary (genetic) algorithm implement largest amount of money problem. 

## The problem 
Find the largest amount of money that can be packed into a security van. There are 100 bags with different weights and values (see *BankProblem.txt*) and the van can only carry a limited weight. The algorithm is ued to try and decide which bags to carry without overload.

## The Evolutionary Algorithm
1. Generate an initial population of p randomly generated solutions, and evaluate the fitness of everything in the population.
2. Use the binary tournament selection twice (with replacement) to select two parents a and b.
3. Run crossover on these parents to give 2 children, c and d.
4. Run mutation on c and d to give two new solutions e and f. Evaluate the fitness of e and f.
5. Run weakest replacement, first using e, then f.
6. If a termination criterion has been reached, then stop. Otherwise return to step 2.


**Termination Criterion**: Will simply be having reached a maximum number of fitness evaluations which is 10,000

**Binary Tournament Selection**: Randomly choose a chromosome from the population; call it a. Randomly choose another chromosome from the population; call this b. The fittest of these two (breaking ties randomly) becomes the selected parent.

**Single-Point Crossover**: Randomly select a ‘crossover point’ which should be smaller than the total length of the chromosome. Take the two parents, and swap the gene values between them ONLY for those genes which appear AFTER the crossover point to create two new children.

**Mutation**: The mutation function must take a single integer parameter which will determine how many times it is repeated on a solution (e.g. M(1) – one mutation per chromosome, M(3) – 3 mutations).

**Weakest Replacement**: If the new solution is fitter than the worst in the population, then overwrite the worst (breaking ties randomly) with the new solution.
