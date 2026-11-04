# Math Study Notes (Statistics)

## Mean, Median, and Mode
1. Mean is the arithmetic average calculated by summing all values and dividing by the count (n).
2. Median is the middle value in a sorted data set; if n is even, it is the average of the two middle values.
3. Mode is the value that occurs most frequently in a data set; a set can be bimodal or multimodal.
4. Mean is sensitive to outliers, while Median is robust (less affected by extreme values).
5. In a perfectly symmetrical distribution, Mean = Median = Mode.
6. Right-skewed distribution: Mean > Median > Mode.
7. Left-skewed distribution: Mean < Median < Mode.
8. The sum of deviations from the Mean is always zero.
9. Weighted Mean accounts for the relative importance (weights) of different values.
10. Harmonic and Geometric means are used for specific rates and growth ratios.
**Sample Problem:** Find Mean, Median, and Mode of {5, 8, 8, 12, 17}.
*Mean: (5+8+8+12+17)/5 = 10. Median: 8. Mode: 8.*

## Permutations and Combinatorics
1. Permutations are used when the order of selection matters (e.g., arrangements).
2. Combinations are used when the order does not matter (e.g., groups/sets).
3. Formula for Permutation: P(n, r) = n! / (n - r)!.
4. Formula for Combination: C(n, r) = n! / [r!(n - r)!].
5. Factorial (n!) is the product of all positive integers up to n.
6. Circular Permutation: (n - 1)! for arranging n items in a circle.
7. Distinguishable Permutations: n! / (n1! * n2! ...) for items with repetitions.
8. Fundamental Counting Principle: Multiply possibilities for independent events.
9. Combinations always result in smaller or equal values compared to permutations for the same n and r.
10. C(n, r) = C(n, n - r) due to symmetry in the binomial coefficient.
**Sample Problem:** How many ways to choose a committee of 3 from 10 people?
*Use C(10, 3) = (10*9*8)/(3*2*1) = 120.*

## Probability Foundations
1. Probability is the measure of likelihood, ranging from 0 (impossible) to 1 (certain).
2. Theoretical Probability = (Number of Favorable Outcomes) / (Total Outcomes).
3. Complement Rule: P(not A) = 1 - P(A).
4. Independent Events: P(A and B) = P(A) * P(B).
5. Dependent Events: P(A and B) = P(A) * P(B|A).
6. Addition Rule for Mutually Exclusive Events: P(A or B) = P(A) + P(B).
7. General Addition Rule: P(A or B) = P(A) + P(B) - P(A and B).
8. Conditional Probability: P(A|B) = P(A and B) / P(B).
9. Law of Large Numbers: Experimental probability approaches theoretical probability as trials increase.
10. Sample Space is the set of all possible outcomes of an experiment.
**Sample Problem:** Probability of drawing an Ace or a King from a 52-card deck?
*P(Ace) + P(King) = 4/52 + 4/52 = 8/52 = 2/13.*

## Z-scores and Standardization
1. Z-score represents the number of standard deviations a value is from the Mean.
2. Formula: z = (x - μ) / σ (where μ is Mean and σ is Standard Deviation).
3. A positive Z-score means the value is above the Mean; negative means below.
4. Z-scores allow comparison of data from different distributions.
5. Standard Normal Distribution has a Mean of 0 and Standard Deviation of 1.
6. Empirical Rule: ~68% of data falls within |z| < 1.
7. Empirical Rule: ~95% of data falls within |z| < 2.
8. Empirical Rule: ~99.7% of data falls within |z| < 3.
9. A Z-score of 0 indicates the value is exactly at the Mean.
10. Percentiles can be found by looking up Z-scores in a standard normal table.
**Sample Problem:** x = 85, μ = 70, σ = 10. Find Z-score.
*z = (85 - 70) / 10 = 1.5.*

## P-value and Significance
1. P-value is the probability of obtaining results at least as extreme as observed, assuming H0 is true.
2. Small P-value (typically < 0.05) suggests evidence against the Null Hypothesis.
3. Significance Level (α) is the threshold for rejecting H0 (commonly 0.05 or 0.01).
4. If P-value ≤ α, the result is "statistically significant" and H0 is rejected.
5. If P-value > α, we "fail to reject" H0 (insufficient evidence).
6. P-value does not measure the magnitude of the effect or the probability that H0 is true.
7. Smaller α reduces Type I error but increases the risk of Type II error.
8. Two-tailed tests split α into both tails (α/2 each).
9. One-tailed tests look for an effect in a specific direction.
10. Reporting P-values provides more detail than just stating "significant" or "not significant."
**Sample Problem:** If α = 0.05 and p = 0.03, what is the conclusion?
*Reject H0; result is statistically significant.*

## Null and Alternative Hypotheses
1. Null Hypothesis (H0) assumes no effect, no difference, or status quo.
2. Alternative Hypothesis (Ha or H1) represents the claim or research hypothesis.
3. H0 always contains the equality sign (=, ≤, or ≥).
4. Ha never contains the equality sign (≠, <, or >).
5. Hypothesis testing is a process of using sample data to evaluate the credibility of H0.
6. A "rejection region" is the set of values for which we reject H0.
7. Non-directional (Two-tailed): Ha: μ ≠ value.
8. Directional (One-tailed): Ha: μ > value or Ha: μ < value.
9. We never "accept" H0; we only "fail to reject" it.
10. Test Statistic (z, t, F, or χ²) is calculated from sample data to find the P-value.
**Sample Problem:** Claim: Average height is greater than 160cm. State H0 and Ha.
*H0: μ ≤ 160. Ha: μ > 160.*

## Frequency Distributions
1. Organizes raw data into classes or intervals showing the number of occurrences.
2. Frequency (f) is the number of times a value or class appears.
3. Relative Frequency is the proportion of total observations in a class (f / n).
4. Cumulative Frequency is the running total of frequencies.
5. Midpoint of a class: (Lower Limit + Upper Limit) / 2.
6. Class Width: The difference between consecutive lower class limits.
7. Grouped Frequency Distribution is used for large ranges of continuous data.
8. Ungrouped Frequency Distribution is used for discrete data with few values.
9. Frequency Histograms visually represent grouped frequency distributions.
10. Sum of relative frequencies must always equal 1 (or 100%).
**Sample Problem:** Data: {1, 2, 2, 3, 3, 3}. Find frequency of 3.
*Frequency = 3. Relative Frequency = 3/6 = 0.5.*

## Boxplot and Stem-and-Leaf Plots
1. Boxplot (Box-and-Whisker) summarizes data using a 5-number summary.
2. 5-number summary: Min, Q1 (25th), Median (50th), Q3 (75th), Max.
3. Interquartile Range (IQR) = Q3 - Q1.
4. Whiskers usually extend to 1.5 * IQR from the quartiles; points beyond are outliers.
5. Stem-and-Leaf plot displays actual data values while showing distribution shape.
6. Stem: Leading digit(s); Leaf: Final digit.
7. Boxplots are excellent for comparing distributions between multiple groups.
8. Stem-and-Leaf plots are best for small to medium datasets.
9. The "Box" in a boxplot contains the middle 50% of the data.
10. A vertical line inside the box marks the Median.
**Sample Problem:** Q1=10, Q3=20. Find IQR and outlier boundary.
*IQR = 10. Upper boundary = 20 + 1.5(10) = 35.*

## Alpha and Beta Errors (Type I & II)
1. Type I Error (Alpha, α): Rejecting a true Null Hypothesis ("False Positive").
2. Type II Error (Beta, β): Failing to reject a false Null Hypothesis ("False Negative").
3. Power of a Test (1 - β): Probability of correctly rejecting a false H0.
4. Increasing Sample Size (n) decreases both α and β (increases Power).
5. As α decreases, β increases (trade-off).
6. Level of Significance (α) is chosen before the experiment.
7. Consequences of Type I error often involve wasted resources or unnecessary action.
8. Consequences of Type II error involve missing a real effect or discovery.
9. Effect Size: Larger differences between populations are easier to detect (higher Power).
10. Non-significant results (high P-value) may be due to high β (low Power).
**Sample Problem:** Innocent person found guilty. Which error?
*Type I Error (True H0 rejected).*

## Correlation and Regression
1. Correlation (r) measures the strength and direction of a linear relationship.
2. r ranges from -1 (perfect negative) to +1 (perfect positive).
3. r = 0 indicates no linear correlation.
4. Correlation does not imply causation.
5. Coefficient of Determination (r²) represents the proportion of variance explained by the model.
6. Simple Linear Regression predicts Y based on X using the equation Y = a + bX.
7. Residual: The difference between observed and predicted values (y - ŷ).
8. Least Squares Method minimizes the sum of squared residuals.
9. Influential points (outliers) can significantly alter the regression line.
10. Homoscedasticity: Constant variance of residuals across all levels of X.
**Sample Problem:** If r = 0.8, what is r²?
*r² = 0.64 (64% of variance explained).*

## One-way ANOVA Interpretation
1. ANOVA (Analysis of Variance) compares means of 3 or more independent groups.
2. H0: All group means are equal (μ1 = μ2 = μ3...).
3. Ha: At least one group mean is different.
4. F-statistic = (Variance between groups) / (Variance within groups).
5. Large F-ratio indicates group differences are likely not due to chance.
6. Degrees of Freedom (between): k - 1 (where k is number of groups).
7. Degrees of Freedom (within): N - k (where N is total sample size).
8. Assumptions: Normality, Independence, and Homogeneity of Variance.
9. Post-hoc tests (e.g., Tukey) are performed only if ANOVA is significant to find which groups differ.
10. Total Variation = Between-Group Variation + Within-Group Variation.
**Sample Problem:** ANOVA p = 0.01. Can we say group 1 is higher than group 2?
*No, only that at least one difference exists. Post-hoc needed.*

## Graph Interpretations
1. X-axis usually represents the independent variable; Y-axis the dependent variable.
2. Trend: General direction in which data is moving (Increasing, Decreasing, Stable).
3. Intercept: Where the graph crosses an axis (e.g., y-intercept at x=0).
4. Slope: Rate of change (Rise / Run).
5. Inflection Point: Where the curve changes concavity.
6. Asymptote: A line that a graph approaches but never touches.
7. Extrapolation: Estimating values outside the known data range (risky).
8. Interpolation: Estimating values between known data points.
9. Correlation on Scatterplot: Closeness of points to a straight line.
10. Scale Manipulation: Changing axis increments can make trends look more/less dramatic.
**Sample Problem:** A distance-time graph is a horizontal line. Describe motion.
*Velocity is zero; object is stationary.*

## Types of Statistical Graphs
1. Bar Graph: Used for categorical data; bars do not touch.
2. Histogram: Used for continuous numerical data; bars touch.
3. Pie Chart: Shows proportions of a whole (best for few categories).
4. Line Graph: Best for showing trends over time (Time Series).
5. Scatterplot: Shows relationship between two numerical variables.
6. Pareto Chart: Bar graph sorted from highest to lowest frequency.
7. Frequency Polygon: Line graph connecting midpoints of histogram bars.
8. Ogive: Graph of cumulative frequency.
9. Dot Plot: Shows frequency of small datasets along a number line.
10. Boxplot: Displays distribution and outliers via quartiles.
**Sample Problem:** Which graph best shows a student's grade improvement over 5 months?
*Line Graph.*

## Percentiles and Quartiles
1. Percentile (Pk) is a value below which k percent of the data falls.
2. Median is the 50th percentile (P50).
3. Q1 is the 25th percentile; Q3 is the 75th percentile.
4. Percentile Rank: The percentage of scores equal to or lower than a given score.
5. Deciles divide data into 10 equal parts (D1, D2... D9).
6. Quartiles divide data into 4 equal parts.
7. Standardized tests often use percentiles to compare student performance.
8. High percentile rank means a score is high relative to the group.
9. Formula for position: L = (k/100) * n.
10. Unlike raw scores, percentiles provide relative standing.
**Sample Problem:** If you are in the 90th percentile of a class of 100, how many students scored lower or equal to you?
*90 students.*

## Margin of Error, Standard Error, and Limits
1. Standard Error (SE) measures the precision of the sample mean (σ / √n).
2. Margin of Error (ME) defines the range around a sample statistic in a confidence interval.
3. ME = Critical Value (z* or t*) * Standard Error.
4. Confidence Interval (CI) = Point Estimate ± Margin of Error.
5. Lower Limit = Estimate - ME; Upper Limit = Estimate + ME.
6. Higher Confidence Level (e.g., 99% vs 95%) increases the ME and widens the CI.
7. Larger Sample Size (n) decreases the SE and ME, narrowing the CI.
8. Standard Error decreases as population variability (σ) decreases.
9. Interpretation: "We are 95% confident that the true population mean falls within the CI."
10. Confidence interval does not mean 95% of individual data points fall in the range.
**Sample Problem:** Mean = 50, ME = 5. Find the 95% Confidence Interval.
*45 to 55.*

## Normal and Standard Normal Curves
1. Normal Curve is bell-shaped, symmetrical, and unimodal.
2. The total area under the curve is exactly 1.
3. Mean, Median, and Mode are located at the center.
4. The tails are asymptotic (never touch the x-axis).
5. Standard Normal Curve (Z-distribution) has μ = 0 and σ = 1.
6. Skewness measures asymmetry (0 for normal).
7. Kurtosis measures "peakedness" or tail thickness.
8. Empirical Rule (68-95-99.7) applies only to normal distributions.
9. Probability of a specific point (e.g., P(x=5)) in a continuous normal curve is 0.
10. Areas under the curve represent probabilities or proportions of the population.
**Sample Problem:** What percentage of a normal distribution is above the mean?
*50%.*

## Compound Probability (Coin and Dice)
1. Independent Events: Outcome of coin flip does not affect dice roll.
2. Sample Space for Coin: {H, T}. Total = 2.
3. Sample Space for 6-sided Die: {1, 2, 3, 4, 5, 6}. Total = 6.
4. Total Outcomes for Coin + Die = 2 * 6 = 12.
5. P(Heads and 6) = P(H) * P(6) = 1/2 * 1/6 = 1/12.
6. P(Heads or 6) = P(H) + P(6) - P(H and 6) = 6/12 + 2/12 - 1/12 = 7/12.
7. For a 4-sided die, total outcomes = 2 * 4 = 8.
8. Tree Diagrams help visualize all possible paths for compound events.
9. Sampling with replacement: Events remain independent.
10. Sampling without replacement: Events become dependent.
**Sample Problem:** Probability of flipping Tails and rolling an even number on a 6-sided die?
*1/2 * 3/6 = 3/12 = 1/4.*

## Parameters vs. Statistics
1. Parameter is a numerical summary of a Population (e.g., Population Mean μ).
2. Statistic is a numerical summary of a Sample (e.g., Sample Mean x̄).
3. We use statistics to estimate unknown parameters.
4. Sampling Error is the natural difference between a statistic and its parameter.
5. Notation: Population Std Dev is σ; Sample Std Dev is s.
6. Notation: Population Proportion is P or π; Sample Proportion is p̂.
7. Parameters are usually fixed but unknown values.
8. Statistics vary from sample to sample (sampling distribution).
9. Census measures every member of a population to find parameters.
10. Inferential Statistics involves making claims about parameters based on statistics.
**Sample Problem:** A researcher finds 25% of 100 polled students smoke. Is 25% a parameter or statistic?
*Statistic (based on a sample).*
