This repository collects together the (anonymised) data and code from the paper "Could Graded Repetitive Arm Strengthening Programme (GRASP) benefit stroke survivors when delivered at home? Results of a randomised controlled feasibility trial", by Wilson Dodzo, Gita Ramdharry, Robert Grant and Leigh Forsyth, published in 2020 in the International Journal of Therapy and Rehabilitation.

A copy of the post-print will appear here 6 months after publication.

We used the WinBUGS software, with a burn-in of 1000 iterations to achieve convergence, then evaluated over 200,000 iterations thinned to every tenth to reduce autocorrelation. The file model.txt defines the model, and data.txt contains the data.

Because of the pseudo-random nature of Markov chain Monte Carlo, if you run the same code, you will obtain slightly different results. The "MC error" shows the extent of this variability.

Diffuse conjugate priors were used throughout; we contend that this is justified by the equipoise in a random trial. Times taken in each task were logarithmically transformed to an approximate normal distribution (after adding one second to avoid very large negative values), and those that were not completed were incorporated by regarding the times as a mixture of two normal distributions: one containing the log-times to completion and the other containing the incomplete tasks with a shared large mean and very small standard deviation. To achieve this we replaced the 120s with values of 900, sufficiently far removed from the completed times to clearly be from a different distribution. As the completion of the task was known, this allowed participants who could not complete a task before treatment, but could afterwards, to ‘switch’ from one distribution to the other without artificially large changes in WMFT time unduly dominating the data.

For comparison with the task-by-task non-parametric tests, we provided approximate equivalent p-values from the Bayesian model. This is unusual but we felt it was justified because the comparison would be clearer that way. See the image below. The posterior distributions were all convincingly close to Gaussian (normal) with modes close to zero, and priors were symmetric about zero and diffuse, so we assert that if there had been an equivalent Neyman-Pearson type test (two-tailed), it would have had tail probabilities well-approximated by twice the tail of the posterior on the other side of zero from the mode.

!(Diagram of sampling distribution under H0 and posterior distribution)[aepv.jpg]

The patients’ impairments and tasks’ difficulties are represented as crossed random effects (also known as an item-response theory model). So, although this model included all results on all tasks at both time points, it does not regard these as independent observations but as arising from a specific patient and a specific task. See the paper for details of the model's conceptualisation as a structural equation model.

**Suggested reading:**

* Bayesian Data Analysis* by Gelman et al
* The BUGS Book* by Spiegelhalter et al
* Basic and Advanced Bayesian Structural Equation Models* by Song & Lee


(c) the authors, CC-BY 4.0
