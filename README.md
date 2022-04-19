## Artificial Intelligence Assignment 2

For more information, see readme_report.pdf.

The main idea behind the algorithm: initial picture is repeatedly di- vided into areas (squares) of sizes in the range [256, 4] pixels (next size in the range is smaller than the previous in 4 times). So, first iteration contains sam- ples with 4 square areas each of 256 px size. This is done to gradually increase level of detalization of output images.

Stages of algorithm execution:
1. Calculate color matrix using original image.
Color matrix is used as a perfect example in comparison with samples.
2. Compose the fittest sample using variation variables and selection.
3. Initialize new samples for the next iteration by mutating the best sample a little.
4. Divide samples (decrease the size of squares, increase number of squares).

The best picture of an iteration (for a particular square size) is built using a function pic execution() which just executes row execution() for all rows to get the best picture.
And row execution() actually process the samples and develops new gen- erations of samples. That's why a sample is considered to be a single row of squares. It is executed until fitness pass condition is satisfied. Each iteration includes:
1. Comparison among row samples from the current population which is of the current population size. As a result an array of individual fitness scores for each sample and an array with sorted fitness scores are calculated.
2. Then, top 90 percent of the population is chosen as parents to produce the next generation. The size of the next generation (next population size) is reduced by 10 percent with every new generation. And the next generation is composed of children only (no samples from the previous generation).
3. And, finally, function choose best fitness() finds a sample that passes the fitness threshold parameter and returns its index in the array of samples (or -1, otherwise).

