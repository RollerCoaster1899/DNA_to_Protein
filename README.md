# DNA_to_Protein
The code consists of two parts: the first part converts a DNA sequence into a protein sequence, and the second part simulates DNA mutations with a given mutation rate and tracks the fitness scores over generations.

### Part 1: DNA to Protein Conversion
The `dna_to_protein` function takes a DNA sequence as input and converts it into a protein sequence using a codon table. A codon is a sequence of three nucleotides in DNA, and each codon corresponds to a specific amino acid or a stop signal in the protein sequence. The function iterates over the DNA sequence, processing codons and looking up their corresponding amino acids in the codon table.

Here's a breakdown of how the `dna_to_protein` function works:
1. The `codon_table` is a dictionary that maps each codon to its corresponding amino acid or stop signal.
2. The function initializes an empty string `protein_sequence` to store the resulting protein sequence.
3. It iterates over the DNA sequence with a step size of 3 (since each codon is three nucleotides long).
4. Inside the loop, it extracts the current codon from the DNA sequence.
5. It looks up the codon in the `codon_table` using the `get` method, which returns the corresponding amino acid. If the codon is not found in the table, an empty string is returned.
6. The resulting amino acid is concatenated to the `protein_sequence` string.
7. After processing all codons, the function returns the final `protein_sequence`.

### Part 2: DNA Mutation Simulation
The second part of the code simulates DNA mutations with a given mutation rate and tracks the fitness scores over generations. It includes additional functions to simulate mutations, calculate fitness scores, and plot the fitness scores over generations.

Here's a breakdown of the simulation process:
1. The `simulate` function takes the initial DNA sequence, mutation rate, and number of generations as input.
2. It initializes two empty lists: `fitness_scores` to store the fitness scores over generations, and `mutated_dnas` to store the mutated DNA sequences for each generation.
3. The function iterates over the specified number of generations.
4. Inside the loop, it calculates the fitness score for the current DNA sequence by subtracting the count of mutations (represented by '-') from the total length of the DNA sequence.
5. It appends the fitness score to the `fitness_scores` list.
6. It initializes an empty string `mutated_dna` to store the mutated DNA sequence for the current generation.
7. It iterates over each base in the DNA sequence.
8. For each base, it randomly decides whether to mutate the base based on the given mutation rate. If the random number is less than the mutation rate, the base is replaced with a randomly chosen nucleotide ('A', 'T', 'C', or 'G'). Otherwise, the base remains unchanged.
9. The resulting mutated DNA sequence is appended to the `mutated_dnas` list.
10. The current mutated DNA sequence becomes the input for the next generation.
11. After all generations are simulated, the function returns the `fitness_scores` and `mutated_dnas` lists.

The code also includes a `plot_fitness_scores` function that takes the `fitness_scores` list as input and plots the fitness scores over generations using the Matplotlib library. The example usage at the bottom of the code demonstrates how to convert a DNA sequence to a protein sequence and print the result.
