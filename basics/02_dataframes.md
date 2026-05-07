# Exercise 2 — Introduction to Data Frames and Sample Metadata

In real bioinformatics workflows (especially RNA-seq), data is rarely stored as simple vectors.

Instead, we use **data frames**, which allow us to store:
- gene expression values
- sample IDs
- conditions (Control vs Treatment)
- batch information
- clinical metadata

This exercise introduces the most important structure in R: the **data frame**.

---

# Part 1 — Creating a Data Frame

We will simulate gene expression data from 8 samples.

## Task 1.1

Create the following vectors:

```r
gene <- c("TP53")
sample_id <- c("S1","S2","S3","S4","S5","S6","S7","S8")
expression <- c(12.4, 15.1, 8.7, 20.3, 17.8, 5.2, 13.5, 18.1)
condition <- c("Control","Control","Control","Treatment","Treatment","Treatment","Control","Treatment")
```

## Task 1.2

Combine them into a data frame called `df`.

---

# Part 2 — Inspecting the Data

## Task 2.1

View the dataset.

## Task 2.2

Use the following functions:

- `str(df)`
- `head(df)`
- `dim(df)`
- `summary(df)`

Questions:
1. How many rows and columns are present?
2. What type of data is stored in each column?

---

# Part 3 — Accessing Columns

## Task 3.1

Extract the `expression` column using:
- `$ operator`
- bracket notation

---

## Task 3.2

Extract the `condition` column.

---

## Task 3.3

Print only `sample_id` and `expression`.

---

# Part 4 — Filtering Data

Filtering is extremely important in RNA-seq analysis.

## Task 4.1

Find all samples where expression > 15.

---

## Task 4.2

Find all samples in the Treatment group.

---

## Task 4.3

Find samples where:
- condition = "Control"
AND
- expression < 10

---

## Task 4.4

Count:
- number of Control samples
- number of Treatment samples

---

# Part 5 — Adding New Columns

## Task 5.1

Create a new column called `high_expression`:

- TRUE if expression > 15
- FALSE otherwise

---

## Task 5.2

Add another column called `log_expression`:

```r
log2(expression)
```

---

## Task 5.3

Inspect the updated data frame.

---

# Part 6 — Summarising Data

## Task 6.1

Calculate:
- mean expression in Control group
- mean expression in Treatment group

---

## Task 6.2

Which group has higher expression?

---

## Task 6.3

Find:
- maximum expression per group
- minimum expression per group

---

# Part 7 — Biological Interpretation

Answer in comments:

```r
# 1. Do Treatment samples generally show higher expression?
# 2. What does "high expression" mean biologically here?
# 3. Why do we use log transformation in RNA-seq?
```

---

# Bonus Challenge

## Task B1

Sort the data frame by expression (highest to lowest).

---

## Task B2

Create a subset containing only Treatment samples.

---

## Task B3

Add a new column:
```r
expression_scaled = expression / max(expression)
```
