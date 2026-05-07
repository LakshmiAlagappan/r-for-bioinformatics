# Exercise 3 — Solutions: Mini Gene Expression Analysis

---

# Part 1 — Creating Dataset

```r
gene <- c("TP53","EGFR","MYC","BRCA1","ACTB","GAPDH","VEGFA","CDKN1A")

sample_id <- c("S1","S2","S3","S4","S5","S6","S7","S8")

expression <- c(12.4, 15.1, 8.7, 20.3, 17.8, 5.2, 13.5, 18.1)

condition <- c("Control","Control","Control","Treatment",
               "Treatment","Treatment","Control","Treatment")

df <- data.frame(gene, sample_id, expression, condition)
```

---

# Part 2 — Inspection

```r
str(df)
head(df)
summary(df)
```

### Answers:
- 8 rows, 4 columns
- gene → character
- sample_id → character
- expression → numeric
- condition → character/factor

---

# Part 3 — Gene Filtering

```r
df[df$expression > 15, ]
```

```r
df$gene[df$expression > 15]
```

```r
df$gene[df$expression < 10]
```

---

### Counts

```r
sum(df$expression > 15)
sum(df$expression < 10)
```

---

# Part 4 — Condition Analysis

```r
control <- df[df$condition == "Control", ]
treatment <- df[df$condition == "Treatment", ]
```

```r
mean(control$expression)
mean(treatment$expression)
```

### Answer:
- Treatment has higher mean expression

---

# Part 5 — Combined Logic

```r
df[df$condition == "Treatment" & df$expression > 15, ]
```

```r
df[df$condition == "Control" & df$expression < 10, ]
```

### Interpretation:
- These represent condition-specific high/low expression genes

---

# Part 6 — Expression Categories

```r
df$expression_category <- ifelse(df$expression > 15, "High",
                          ifelse(df$expression >= 10, "Medium", "Low"))
```

---

### Counts

```r
table(df$expression_category)
```

---

# Part 7 — Sorting

```r
df[order(df$expression, decreasing = TRUE), ]
```

---

### Top 3 genes

```r
head(df[order(df$expression, decreasing = TRUE), ], 3)
```

---

# Part 8 — Interpretation (comments)

```r
# 1. BRCA1 has the highest expression (20.3)

# 2. Yes, Treatment samples show slightly higher expression overall

# 3. Categorization helps simplify interpretation of continuous data

# 4. Real RNA-seq would have thousands of genes, requiring matrix-based analysis
```

---

# Bonus

## B1 — Scaled expression

```r
df$expression_scaled <- df$expression / max(df$expression)
```

---

## B2 — High expression in Treatment

```r
df[df$condition == "Treatment" & df$expression > 15, ]
```

---

## B3 — Summary table

```r
aggregate(expression ~ condition, data = df, mean)
```

---
