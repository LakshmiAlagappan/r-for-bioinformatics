---
title: "Exercise 1 - Vectors"
---

# Exercise 1 — Introduction to R for Gene Expression Analysis

Welcome to your first R exercise.

In bioinformatics and transcriptomics, we often work with:
- gene expression values
- sample measurements
- vectors of genes
- patient metadata
- filtering and summarising data

This exercise introduces the core R concepts that will later become important for:
- bulk RNA-sequencing analysis
- differential expression analysis
- quality control
- data wrangling
- plotting

This exercise is intentionally detailed and designed to take approximately **45–60 minutes**.

---

# Part 1 — Creating Numerical Vectors

In RNA-seq analysis, each sample may contain an expression value for a gene.

Suppose the expression values for a gene across 8 samples are:

```r
12.4, 15.1, 8.7, 20.3, 17.8, 5.2, 13.5, 18.1
```

## Task 1.1

Create a vector called `expression`.

---

## Task 1.2

Print the vector to the console.

---

## Task 1.3

Use functions on the vector to answer the following:

Questions:
1. What is the mean expression value?
2. What is the highest expression value?
3. What is the lowest expression value?
4. How many samples are present?
5. What is the total expression?

---

# Part 2 — Working with Individual Elements

Each value in a vector has a position called an **index**.

In R:
- the first element is position `1`
- not position `0`

---

## Task 2.1

Print:
- the first value
- the third value
- the last value

---

## Task 2.2

Store the second expression value in a new variable called `sample2`.

Print `sample2`.

---

## Task 2.3

Calculate the difference between:
- highest expression
- lowest expression

Store this in a variable called `expression_range`.

---

# Part 3 — Basic Arithmetic

R can perform calculations directly.

---

## Task 3.1

Multiply all expression values by 2.

Store the result in:

```r
expression_doubled
```

Print the result.

---

## Task 3.2

Add 5 to every value.

Store the result in:

```r
expression_plus5
```

---

## Task 3.3

Calculate log2-transformed expression values using:

```r
log2(expression)
```

Questions:
1. Why might log transformation be useful in RNA-seq?
2. Which values changed the most after transformation?

---

# Part 4 — Logical Filtering

Filtering is extremely important in bioinformatics.

We often:
- remove lowly expressed genes
- keep highly variable genes
- select significant genes

---

## Task 4.1

Find all expression values greater than 10.

---

## Task 4.2

Find all values:
- greater than or equal to 15

---

## Task 4.3

Find all values:
- below 10

---

## Task 4.4

Count:
- how many values are above 15
- how many values are below 10

---

# Part 5 — Creating Character Vectors

Gene names are often stored as text.

Create the following vector:

```r
TP53, EGFR, MYC, BRCA1, ACTB, GAPDH, VEGFA, CDKN1A
```

---

## Task 5.1

Create a vector called `genes`.

---

## Task 5.2

Print:
- the first gene
- the fourth gene
- the last gene

---

## Task 5.3

Count how many genes are present.

---

## Task 5.4

Add a new gene:

```r
STAT3
```

to the vector.

---

# Part 6 — Combining Biological Information

Suppose each expression value corresponds to a gene:

| Gene | Expression |
|---|---|
| TP53 | 12.4 |
| EGFR | 15.1 |
| MYC | 8.7 |
| BRCA1 | 20.3 |
| ACTB | 17.8 |
| GAPDH | 5.2 |
| VEGFA | 13.5 |
| CDKN1A | 18.1 |

---

## Task 6.1

Print:
- genes with expression greater than 15

---

## Task 6.2

Print:
- genes with expression below 10

---

## Task 6.3

Create:
- `high_expression_genes`
- `low_expression_genes`

Definitions:
- High expression: >15
- Low expression: <=15

---

# Part 7 — Naming Vector Elements

R allows vectors to have names.

---

## Task 7.1

Assign gene names to the expression vector using:

```r
names(expression) <- genes
```

Print the vector.

---

## Task 7.2

Retrieve the expression value for:
- TP53
- BRCA1

---

# Part 8 — Simple Quality Control

In RNA-seq analysis, we often remove low-quality values.

Suppose expression values below 8 are considered low quality.

---

## Task 8.1

Create a filtered vector containing only values >=8.

Store this in:

```r
filtered_expression
```

---

## Task 8.2

Recalculate:
- mean
- max
- min

for the filtered data.

---

## Task 8.3

How many samples were removed?

---

# Part 9 — Small Biological Interpretation

Answer the following questions in your own words.

1. Which gene appears most highly expressed?
2. Which gene appears least expressed?
3. Why might we remove low-expression genes in RNA-seq analysis?
4. Why might log transformation help visualisation or downstream analysis?

Write your answers as comments in R using:

```r
# example comment
```

---

# Bonus Challenge 1

Create a new vector called:

```r
treatment_group
```

containing:

```r
Control, Control, Control, Treatment, Treatment, Treatment, Treatment, Control
```

Questions:
1. How many samples belong to Treatment?
2. How many belong to Control?

---

# Bonus Challenge 2

Create a logical vector indicating whether expression is above 15.

Example output:

```r
FALSE TRUE FALSE TRUE ...
```

Store this in:

```r
is_high
```

---

# Bonus Challenge 3

Sort the expression vector from:
- lowest to highest
- highest to lowest
