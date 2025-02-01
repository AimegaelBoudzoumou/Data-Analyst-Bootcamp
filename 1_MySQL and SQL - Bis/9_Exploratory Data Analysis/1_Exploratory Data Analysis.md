# Exploratory Data Analysis

```sql
select *
from layoffs_staging2;
```

```sql
select MAX(total_laid_off), MAX(percentaage_laid_off)
from layoffs_staging2;
```

```sql
select *
from layoffs_staging2
where percentage_laid_off = 1;
```

```sql
select *
from layoffs_staging2
where percentage_laid_off = 1;
order by total_laid_off desc;
```

```sql
select *
from layoffs_staging2
where percentage_laid_off = 1;
order by funds_raised_millions desc;
```

```sql
select company, SUM(total_laid_off)
from layoffs_staging2
group by company
order by 2 desc;
```

```sql
select min(`date`), max(`date`)
from layoffs_staging2;
```

```sql
select industry, SUM(total_laid_off)
from layoffs_staging2
group by company
order by 2 desc;
```

```sql
select country, SUM(total_laid_off)
from layoffs_staging2
group by country
order by 2 desc;
```

```sql
select *
from layoffs_staging2;
```

```sql
select `date`, SUM(total_laid_off)
from layoffs_staging2
group by `date`
order by 2 desc;
```

```sql
select YEAR(`date`), SUM(total_laid_off)
from layoffs_staging2
group by YEAR(`date`)
order by 1 desc;
```

```sql
select YEAR(`date`), SUM(total_laid_off)
from layoffs_staging2
group by YEAR(`date`)
order by 2 desc;
```

```sql
select stage, SUM(total_laid_off)
from layoffs_staging2
group by stage
order by 1 desc;
```

```sql
select stage, SUM(total_laid_off)
from layoffs_staging2
group by stage
order by 2 desc;
```

```sql
select company, SUM(percentage_laid_off)
from layoffs_staging2
group by company
order by 2 desc;
```

```sql
select company, AVG(percentage_laid_off)
from layoffs_staging2
group by company
order by 2 desc;
```

```sql
select substring(`date`,6,2) as `month`, sum(total_laid_off)
forom layoffs_staging2
group by`month`;
```

```sql
select substring(`date`,1,7) as `month`, sum(total_laid_off)
from layoffs_staging2
where substring(`date`,1,7) is not null
group by`month`
order by 1 asc
;
```

```sql
with Rolling_total as
(
select substring(`date`,1,7) as `month`, sum(total_laid_off) as total_off
from layoffs_staging2
where substring(`date`,1,7) is not null
group by`month`
order by 1 asc
)
select `month`, total_off,
sum(total_off) over ( order by  `month`) as rolling_total
from Rolling_total;
```

```sql
select company, SUM(total_laid_off)
from layoffs_staging2
group by company
order by 2 desc;
```

```sql
select company, YEAR(`date`), SUM(total_laid_off)
from layoffs_staging2
group by company, YEAR(`date`)
order by company asc;
```

```sql
select company, YEAR(`date`), SUM(total_laid_off)
from layoffs_staging2
group by company, YEAR(`date`)
order by 3 desc;
```

```sql
with Company_Year as
(
select company, YEAR(`date`), SUM(total_laid_off)
from layoffs_staging2
group by company, YEAR(`date`)
)
select *
from Company_Year;
```

```sql
with Company_Year (company, years, total_laid_off) as
(
select company, YEAR(`date`), SUM(total_laid_off)
from layoffs_staging2
group by company, YEAR(`date`)
)
select *, dense_rank() over (partition by years order by total_laid_off desc) as Ranking
from Company_Year
where years is not null
order by Ranking asc
;
```

```sql
with Company_Year (company, years, total_laid_off) as
(
select company, YEAR(`date`), SUM(total_laid_off)
from layoffs_staging2
group by company, YEAR(`date`)
), Company_Year_Rank AS
(
select *, dense_rank() over (partition by years order by total_laid_off desc) as Ranking
from Company_Year
where years is not null
)
select *
from Company_Year_Rank
where Ranking <= 5
;
```
