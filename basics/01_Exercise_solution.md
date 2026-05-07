---

# Optional Full Solution

Try completing the exercise before looking at the solution.

```r
# Part 1
expression <- c(12.4, 15.1, 8.7, 20.3, 17.8, 5.2, 13.5, 18.1)

mean(expression)
max(expression)
min(expression)
length(expression)
sum(expression)

# Part 2
expression[1]
expression[3]
expression[length(expression)]

sample2 <- expression[2]

expression_range <- max(expression) - min(expression)

# Part 3
expression_doubled <- expression * 2

expression_plus5 <- expression + 5

log2(expression)

# Part 4
expression[expression > 10]

expression[expression >= 15]

expression[expression < 10]

length(expression[expression > 15])

length(expression[expression < 10])

# Part 5
genes <- c("TP53", "EGFR", "MYC", "BRCA1",
           "ACTB", "GAPDH", "VEGFA", "CDKN1A")

genes[1]

genes[4]

length(genes)

genes <- c(genes, "STAT3")

# Part 6
genes[expression > 15]

genes[expression < 10]

high_expression_genes <- genes[expression > 15]

low_expression_genes <- genes[expression <= 15]

# Part 7
names(expression) <- genes[1:length(expression)]

expression["TP53"]

expression["BRCA1"]

# Part 8
filtered_expression <- expression[expression >= 8]

mean(filtered_expression)

max(filtered_expression)

min(filtered_expression)

length(expression) - length(filtered_expression)

# Bonus
treatment_group <- c("Control", "Control", "Control",
                     "Treatment", "Treatment",
                     "Treatment", "Treatment", "Control")

length(treatment_group[treatment_group == "Treatment"])

is_high <- expression > 15

sort(expression)

sort(expression, decreasing = TRUE)
```
