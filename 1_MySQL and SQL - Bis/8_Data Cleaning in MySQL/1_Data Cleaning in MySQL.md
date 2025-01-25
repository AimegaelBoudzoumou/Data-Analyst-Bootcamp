# Data Cleaning

### 1. Remove Duplicates

### 2. Standardizing Data

### 3. Null Values or Blank Vakues

### 4. Remove Any Columns Unnecessary


### Create stagging tableRemove Duplicates

```sql
SELECT * FROM layoffs;
```

```sql
CREATE TABLE layoffs_stagging
LIKE layoffs;

SELECT * FROM layoffs; -- No data, only strucrture of layoffs table appears

INSERT layoffs_staging
SELECT *
FROM layoffs;
```

### 1. Remove Duplicates

```sql
SELECT *,
ROW_NUMBER() OVER(
PARTITION BY company, location,
 industry, total_laid_off, percentage_laid_off, `date`, stage, country, funds_raised_millions) AS row_num
FROM layoffs_staging
```

```sql
WITH duplicate_cte AS
(
SELECT *,
ROW_NUMBER() OVER(
PARTITION BY company, location,
 industry, total_laid_off, percentage_laid_off, `date`, stage, country, funds_raised_millions) AS row_num
FROM layoffs_staging
)
SELECT *
FROM duplicate_cte
WHERE row_nulm > 1;
```

```sql
SELECT *
FROM layoffs_staging
WHERE company = 'Oda';
```

```sql
SELECT *
FROM layoffs_staging
WHERE company = 'Casper';
```

```sql
WITH duplicate_cte AS
(
SELECT *,
ROW_NUMBER() OVER(
PARTITION BY company, location,
 industry, total_laid_off, percentage_laid_off, `date`, stage, country, funds_raised_millions) AS row_num
FROM layoffs_staging
)
DELETE 
FROM duplicate_cte
WHERE row_nulm > 1;
```

The above SQL Code produce an error.

```sql
CREATE TABLE `layoffs_staging2` (
`company` text,
`location` text,
`industry` text,
`total_laid_of` int default NULL,
`percentage_laid_of` text,
`date` text,
`stage` text,
`country` text,
`funds_raised_millions` int default NULL,
`row_num` INT
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
```

This table is empty
```sql
SELECT *
FROM layoffs_staging2;
```

```sql
INSERT INTO layoffs_staging2
SELECT *,
ROW_NUMBER() OVER(
PARTITION BY company, location,
 industry, total_laid_off, percentage_laid_off, `date`, stage, country, funds_raised_millions) AS row_num
FROM layoffs_staging;
```

```sql
SELECT *
FROM layoffs_staging2;
```

```sql
SELECT *
FROM layoffs_staging2
WHERE row_num > 1;
```

```sql
DELETE
FROM layoffs_staging2
WHERE row_num > 1;
```

```sql
SELECT *
FROM layoffs_staging2
WHERE row_num > 1;
```

```sql
SELECT *
FROM layoffs_staging2;
```

### 2. Standardizing Data

#### company column

```sql
SELECT company, TRIM(company)
FROM layoffs_staging2;
```

```sql
UPDATE layoffs_staging2
SET company = TRIM(company);
```

```sql
SELECT company, TRIM(company)
FROM layoffs_staging2;
```

#### industry column

```sql
SELECT industry
FROM layoffs_staging2;
```

```sql
SELECT DISTINCT industry
FROM layoffs_staging2;
ORDER BY 1
```

```sql
SELECT *
FROM layoffs_staging2;
WHERE industry LIKE 'Crypto%';
```

```sql
UPDATE layoffs_staging2
SET industry = 'Crypto'
WHERE industry LIKE 'Crypto%';
```

```sql
SELECT *
FROM layoffs_staging2;
WHERE industry LIKE 'Crypto%';
```

```sql
SELECT DISTINCT industry
FROM layoffs_staging2;
```

#### location column

```sql
SELECT DISTINCT location
FROM layoffs_staging2
ORDER BY 1;
```

#### country column

```sql
SELECT DISTINCT country
FROM layoffs_staging2
ORDER BY 1;
```

### 3. Null Values or Blank Vakues



### 4. Remove Any Columns Unnecessary


