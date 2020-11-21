Financial Statement Analysis
================

In this quick project I will use financial data in order to calculate
some financial metrics such as profits. I will prompt and answer
questions that might provide useful analysis of the data. Below I have
two example vectors representing a possible financial scenario of
monthly revenue and monthly expenses.

``` r
revenue <- c(14574.49, 7606.46, 8611.41, 9175.41, 8058.65, 8105.44, 11496.28, 9766.09, 10305.32, 14379.96, 10713.97, 15433.50)
expenses <- c(12051.82, 5695.07, 12319.20, 12089.72, 8658.57, 840.20, 3285.73, 5821.12, 6976.93, 16618.61, 10054.37, 3803.96)
```

##### What is the profit for each month?

``` r
profit <- revenue - expenses
profit
```

    ##  [1]  2522.67  1911.39 -3707.79 -2914.31  -599.92  7265.24  8210.55  3944.97
    ##  [9]  3328.39 -2238.65   659.60 11629.54

##### What is the profit after tax for each month, assuming that the tax rate is 30%?

``` r
profit_after_tax <- round(profit*0.7,digits=2)
profit_after_tax
```

    ##  [1]  1765.87  1337.97 -2595.45 -2040.02  -419.94  5085.67  5747.39  2761.48
    ##  [9]  2329.87 -1567.06   461.72  8140.68

##### What is the profit margin for each month?

``` r
profit_margin <- round(profit_after_tax/revenue,digits=2)*100
profit_margin
```

    ##  [1]  12  18 -30 -22  -5  63  50  28  23 -11   4  53

##### Assume we define “good months” as months where the profit after tax was greater than the mean of the profit after tax over the year. What were the good months?

``` r
good_months <- profit_after_tax > mean(profit_after_tax)
good_months
```

    ##  [1]  TRUE FALSE FALSE FALSE FALSE  TRUE  TRUE  TRUE  TRUE FALSE FALSE  TRUE

January, June, July, August, September, December

##### If “bad months” were described in a similar way, what were the bad months?

``` r
bad_months <- profit_after_tax < mean(profit_after_tax)
bad_months
```

    ##  [1] FALSE  TRUE  TRUE  TRUE  TRUE FALSE FALSE FALSE FALSE  TRUE  TRUE FALSE

February, March, April, May, October, November

##### What was the best month, where the profit after tax was the highest of the year?

``` r
best_month <- profit_after_tax == max(profit_after_tax)
best_month
```

    ##  [1] FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE  TRUE

December

##### What was the worst month?

``` r
worst_month <- profit_after_tax == min(profit_after_tax)
worst_month
```

    ##  [1] FALSE FALSE  TRUE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE

March
