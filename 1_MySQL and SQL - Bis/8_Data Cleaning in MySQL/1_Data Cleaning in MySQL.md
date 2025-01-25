# Data Cleaning

### 1. Remove Duplicates

### 2. Standardizing Data

### 3. Null Values or Blank Values

### 4. Remove Any Columns Unnecessary


### First Creating stagging table

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

## 1. Remove Duplicates

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
`total_laid_off` int default NULL,
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

## 2. Standardizing Data

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

```sql
SELECT DISTINCT country, TRIM(country)
FROM layoffs_staging2
ORDER BY 1;
```

```sql
SELECT DISTINCT country, TRIM(TRAILING '.' FROM country)
FROM layoffs_staging2
ORDER BY 1;
```

```sql
UPDATE layoffs_staging2
SET country = TRIM(TRAILING '.' FROM country)****
WHERE country LIKE 'United States%';
```

```sql
SELECT DISTINCT country, TRIM(TRAILING '.' FROM country)
FROM layoffs_staging2
ORDER BY 1;
```

```sql
SELECT *
FROM layoffs_staging2;
```

#### date column

```sql
SELECT `date`
FROM layoffs_staging2;
```

```sql
SELECT `date`,
STR_TO_DATE(`date`, '%m/%d/%Y')
FROM layoffs_staging2;
```

__Change all dates to the same date format__

```sql
UPDATE layoffs_staging2
SET `date` = STR_TO_DATE(`date`, '%m/%d/%Y');
```

```sql
SELECT `date`
FROM layoffs_staging2;
```

__Change the `date` column to date type__

```sql
ALTER TABLE layoffs_staging2
MODIFY COLUMN `date` DATE;
```

```sql
SELECT * 
FROM layoffs_staging2;
```

## 3. Null Values or Blank Values


#### total_laid_off column

```sql
SELECT *
FROM layoffs_staging2
WHERE total_laid_off IS NULL
AND percentage_laid_off IS NULL;
```

```sql
UPDATE layoffs_staging2
SET industry = NULL
WHERE industry = '';
```

```sql
SELECT DISTINCT industry
FROM layoffs_staging2
WHERE industry IS NULL
OR industry = '';
```

```sql
SELECT *
FROM layoffs_staging2
WHERE industry IS NULL
OR industry = '';
```

```sql
SELECT *
FROM layoffs_staging2
WHERE company = 'Airbnb';
```

------------------------------------------------------------------------------------------------------------------
#### Based on company and location : we want to update the column industry where it is blank

Eg : we wish the column industry of the first line (in the next table) have not blank, but contains Travel 

|   company |   location |   industry | 
|:-:    |:-:    |:-:   |
|   Airbnb   |   SF Bay Area |
|   Airbnb  |   SF Bay Area | Travel


```sql
SELECT *
FROM layoffs_staging2 t1
JOIN layoffs_staging2 t2
  ON t1.company = t2.company
  AND t1.location = t2.location
WHERE (t1.industry IN NULL OR t1.industry = '')
AND t2.industry IS NOT NULL;
```

```sql
SELECT t1.industry, t2.industry
FROM layoffs_staging2 t1
JOIN layoffs_staging2 t2
  ON t1.company = t2.company
  AND t1.location = t2.location
WHERE (t1.industry IN NULL OR t1.industry = '')
AND t2.industry IS NOT NULL;
```

```sql
UPDATE layoffs_staging2 t1
JOIN layoffs_staging2 t2
  ON t1.company = t2.company
SET t1.company = t2.company
WHERE t1.industry IN NULL
AND t2.industry IS NOT NULL;
```

------------------------------------------------------------------------------------------------------------------

SELECT *
FROM layoffs_staging2
WHERE company LIKE 'Bally%';

```sql
SELECT *
FROM layoffs_staging2
WHERE total_laid_off IS NULL
AND percentage_laid_off IS NULL;
```

```sql
DELETE
FROM layoffs_staging2
WHERE total_laid_off IS NULL
AND percentage_laid_off IS NULL;
```

```sql
SELECT *
FROM layoffs_staging2;
```


## 4. Remove Any Columns Unnecessary

```sql
ALTER TABLE layoffs_staging2
DROP COLUMN row_num;
```

```sql
SELECT *
FROM layoffs_staging2;
```

