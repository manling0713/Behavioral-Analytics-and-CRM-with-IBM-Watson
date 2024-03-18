Customer final
================
2023-12-02

## First Steps

NOTE: Your data needs to be in the folder where your code is located!

The first Chunk of Code will always do 3 Things for us

1)  Clear ALL Variables (to make sure nothing is “left over”) and clear
    the screen.
2)  Read in the data we want to use. In our case the file is called
    “data.price.csv)”
3)  Explore the data (what variables are in it and what are some basic
    statistics for these variables)

``` r
# Clear All Variables & Clear the Screen
rm(list=ls())
cat("\014")
```



``` r
# Read in the Data
df = read.csv("Final_new.csv")



# Explore the data
str(df)
```

    ## 'data.frame':    9134 obs. of  39 variables:
    ##  $ Customer                     : chr  "BU79786" "QZ44356" "AI49188" "WW63253" ...
    ##  $ State                        : chr  "Washington" "Arizona" "Nevada" "California" ...
    ##  $ Customer.Lifetime.Value      : num  2764 6980 12887 7646 2814 ...
    ##  $ Response                     : chr  "No" "No" "No" "No" ...
    ##  $ Coverage_Ext                 : int  0 1 0 0 0 0 0 0 0 1 ...
    ##  $ Coverage_Pre                 : int  0 0 1 0 0 0 0 1 0 0 ...
    ##  $ Edu_College                  : int  0 0 0 0 0 0 1 0 0 1 ...
    ##  $ Edu_Bach                     : int  1 1 1 1 1 1 0 0 1 0 ...
    ##  $ Edu_Master                   : int  0 0 0 0 0 0 0 1 0 0 ...
    ##  $ Edu_Doctor                   : int  0 0 0 0 0 0 0 0 0 0 ...
    ##  $ Effective.To.Date            : chr  "2/24/11" "1/31/11" "2/19/11" "1/20/11" ...
    ##  $ Employ_Unemp                 : int  0 1 0 1 0 0 0 1 0 0 ...
    ##  $ Employ_Dis                   : int  0 0 0 0 0 0 0 0 0 0 ...
    ##  $ Employ_Med                   : int  0 0 0 0 0 0 0 0 1 0 ...
    ##  $ Employ_Ret                   : int  0 0 0 0 0 0 0 0 0 0 ...
    ##  $ Gender                       : chr  "F" "F" "F" "M" ...
    ##  $ Income                       : int  56274 0 48767 0 43836 62902 55350 0 14072 28812 ...
    ##  $ Locat_Sub                    : int  1 1 1 1 0 0 1 0 1 0 ...
    ##  $ Locat_Rural                  : int  0 0 0 0 1 1 0 0 0 0 ...
    ##  $ Marital.Status               : chr  "Married" "Single" "Married" "Married" ...
    ##  $ Monthly.Premium.Auto         : int  69 94 108 106 73 69 67 101 71 93 ...
    ##  $ Months.Since.Last.Claim      : int  32 13 18 18 12 14 0 0 13 17 ...
    ##  $ Months.Since.Policy.Inception: int  5 42 38 65 44 94 13 68 3 7 ...
    ##  $ Number.of.Open.Complaints    : int  0 0 0 0 0 0 0 0 0 0 ...
    ##  $ Number.of.Policies           : int  1 8 2 7 1 2 9 4 2 8 ...
    ##  $ Policy_Cor                   : int  1 0 0 1 0 0 1 1 1 0 ...
    ##  $ Policy_Spe                   : int  0 0 0 0 0 0 0 0 0 1 ...
    ##  $ Level_2                      : int  0 0 0 1 0 0 0 0 0 1 ...
    ##  $ Level_3                      : int  1 1 1 0 0 1 1 1 1 0 ...
    ##  $ Renew_O2                     : int  0 0 0 0 0 1 0 0 0 1 ...
    ##  $ Renew_O3                     : int  0 1 0 0 0 0 0 0 0 0 ...
    ##  $ Renew_O4                     : int  0 0 0 0 0 0 0 0 0 0 ...
    ##  $ Sales_Bch                    : int  0 0 0 0 0 0 0 0 0 1 ...
    ##  $ Sales_Call                   : int  0 0 0 1 0 0 0 0 0 0 ...
    ##  $ Sales_Web                    : int  0 0 0 0 0 1 0 0 0 0 ...
    ##  $ Total.Claim.Amount           : num  385 1131 566 530 138 ...
    ##  $ Vehicle.Class                : chr  "Two-Door Car" "Four-Door Car" "Two-Door Car" "SUV" ...
    ##  $ Vehicle_Med                  : int  1 1 1 1 1 1 1 1 1 1 ...
    ##  $ Vehicle_Large                : int  0 0 0 0 0 0 0 0 0 0 ...

``` r
summary(df)
```

    ##    Customer            State           Customer.Lifetime.Value
    ##  Length:9134        Length:9134        Min.   : 1898          
    ##  Class :character   Class :character   1st Qu.: 3994          
    ##  Mode  :character   Mode  :character   Median : 5780          
    ##                                        Mean   : 8005          
    ##                                        3rd Qu.: 8962          
    ##                                        Max.   :83325          
    ##    Response          Coverage_Ext     Coverage_Pre      Edu_College    
    ##  Length:9134        Min.   :0.0000   Min.   :0.00000   Min.   :0.0000  
    ##  Class :character   1st Qu.:0.0000   1st Qu.:0.00000   1st Qu.:0.0000  
    ##  Mode  :character   Median :0.0000   Median :0.00000   Median :0.0000  
    ##                     Mean   :0.3002   Mean   :0.09021   Mean   :0.2935  
    ##                     3rd Qu.:1.0000   3rd Qu.:0.00000   3rd Qu.:1.0000  
    ##                     Max.   :1.0000   Max.   :1.00000   Max.   :1.0000  
    ##     Edu_Bach        Edu_Master        Edu_Doctor      Effective.To.Date 
    ##  Min.   :0.0000   Min.   :0.00000   Min.   :0.00000   Length:9134       
    ##  1st Qu.:0.0000   1st Qu.:0.00000   1st Qu.:0.00000   Class :character  
    ##  Median :0.0000   Median :0.00000   Median :0.00000   Mode  :character  
    ##  Mean   :0.3009   Mean   :0.08113   Mean   :0.03744                     
    ##  3rd Qu.:1.0000   3rd Qu.:0.00000   3rd Qu.:0.00000                     
    ##  Max.   :1.0000   Max.   :1.00000   Max.   :1.00000                     
    ##   Employ_Unemp      Employ_Dis        Employ_Med       Employ_Ret     
    ##  Min.   :0.0000   Min.   :0.00000   Min.   :0.0000   Min.   :0.00000  
    ##  1st Qu.:0.0000   1st Qu.:0.00000   1st Qu.:0.0000   1st Qu.:0.00000  
    ##  Median :0.0000   Median :0.00000   Median :0.0000   Median :0.00000  
    ##  Mean   :0.2537   Mean   :0.04434   Mean   :0.0473   Mean   :0.03087  
    ##  3rd Qu.:1.0000   3rd Qu.:0.00000   3rd Qu.:0.0000   3rd Qu.:0.00000  
    ##  Max.   :1.0000   Max.   :1.00000   Max.   :1.0000   Max.   :1.00000  
    ##     Gender              Income        Locat_Sub       Locat_Rural    
    ##  Length:9134        Min.   :    0   Min.   :0.0000   Min.   :0.0000  
    ##  Class :character   1st Qu.:    0   1st Qu.:0.0000   1st Qu.:0.0000  
    ##  Mode  :character   Median :33890   Median :1.0000   Median :0.0000  
    ##                     Mean   :37657   Mean   :0.6327   Mean   :0.1941  
    ##                     3rd Qu.:62320   3rd Qu.:1.0000   3rd Qu.:0.0000  
    ##                     Max.   :99981   Max.   :1.0000   Max.   :1.0000  
    ##  Marital.Status     Monthly.Premium.Auto Months.Since.Last.Claim
    ##  Length:9134        Min.   : 61.00       Min.   : 0.0           
    ##  Class :character   1st Qu.: 68.00       1st Qu.: 6.0           
    ##  Mode  :character   Median : 83.00       Median :14.0           
    ##                     Mean   : 93.22       Mean   :15.1           
    ##                     3rd Qu.:109.00       3rd Qu.:23.0           
    ##                     Max.   :298.00       Max.   :35.0           
    ##  Months.Since.Policy.Inception Number.of.Open.Complaints Number.of.Policies
    ##  Min.   : 0.00                 Min.   :0.0000            Min.   :1.000     
    ##  1st Qu.:24.00                 1st Qu.:0.0000            1st Qu.:1.000     
    ##  Median :48.00                 Median :0.0000            Median :2.000     
    ##  Mean   :48.06                 Mean   :0.3844            Mean   :2.966     
    ##  3rd Qu.:71.00                 3rd Qu.:0.0000            3rd Qu.:4.000     
    ##  Max.   :99.00                 Max.   :5.0000            Max.   :9.000     
    ##    Policy_Cor       Policy_Spe         Level_2          Level_3      
    ##  Min.   :0.0000   Min.   :0.00000   Min.   :0.0000   Min.   :0.0000  
    ##  1st Qu.:0.0000   1st Qu.:0.00000   1st Qu.:0.0000   1st Qu.:0.0000  
    ##  Median :0.0000   Median :0.00000   Median :0.0000   Median :1.0000  
    ##  Mean   :0.2155   Mean   :0.04138   Mean   :0.3154   Mean   :0.5023  
    ##  3rd Qu.:0.0000   3rd Qu.:0.00000   3rd Qu.:1.0000   3rd Qu.:1.0000  
    ##  Max.   :1.0000   Max.   :1.00000   Max.   :1.0000   Max.   :1.0000  
    ##     Renew_O2         Renew_O3         Renew_O4        Sales_Bch    
    ##  Min.   :0.0000   Min.   :0.0000   Min.   :0.0000   Min.   :0.000  
    ##  1st Qu.:0.0000   1st Qu.:0.0000   1st Qu.:0.0000   1st Qu.:0.000  
    ##  Median :0.0000   Median :0.0000   Median :0.0000   Median :0.000  
    ##  Mean   :0.3203   Mean   :0.1568   Mean   :0.1121   Mean   :0.281  
    ##  3rd Qu.:1.0000   3rd Qu.:0.0000   3rd Qu.:0.0000   3rd Qu.:1.000  
    ##  Max.   :1.0000   Max.   :1.0000   Max.   :1.0000   Max.   :1.000  
    ##    Sales_Call       Sales_Web      Total.Claim.Amount Vehicle.Class     
    ##  Min.   :0.0000   Min.   :0.0000   Min.   :   0.099   Length:9134       
    ##  1st Qu.:0.0000   1st Qu.:0.0000   1st Qu.: 272.258   Class :character  
    ##  Median :0.0000   Median :0.0000   Median : 383.945   Mode  :character  
    ##  Mean   :0.1932   Mean   :0.1451   Mean   : 434.089                     
    ##  3rd Qu.:0.0000   3rd Qu.:0.0000   3rd Qu.: 547.515                     
    ##  Max.   :1.0000   Max.   :1.0000   Max.   :2893.240                     
    ##   Vehicle_Med     Vehicle_Large   
    ##  Min.   :0.0000   Min.   :0.0000  
    ##  1st Qu.:0.0000   1st Qu.:0.0000  
    ##  Median :1.0000   Median :0.0000  
    ##  Mean   :0.7033   Mean   :0.1036  
    ##  3rd Qu.:1.0000   3rd Qu.:0.0000  
    ##  Max.   :1.0000   Max.   :1.0000

## PREPARE DATA

In our case we have to create new variables: log(Units) and log(Prices)

``` r
# Create log CLV
df$logCLV <- log(df$Customer.Lifetime.Value)

## Make a dummy variable 

df$Gender <- ifelse(df$Gender == 'M', 1, 0)
df$Marital.Status <- ifelse(df$Marital.Status == 'Married', 1, 0)

# Display the modified data frame
head(df)
```

    ##   Customer      State Customer.Lifetime.Value Response Coverage_Ext
    ## 1  BU79786 Washington                2763.519       No            0
    ## 2  QZ44356    Arizona                6979.536       No            1
    ## 3  AI49188     Nevada               12887.432       No            0
    ## 4  WW63253 California                7645.862       No            0
    ## 5  HB64268 Washington                2813.693       No            0
    ## 6  OC83172     Oregon                8256.298      Yes            0
    ##   Coverage_Pre Edu_College Edu_Bach Edu_Master Edu_Doctor Effective.To.Date
    ## 1            0           0        1          0          0           2/24/11
    ## 2            0           0        1          0          0           1/31/11
    ## 3            1           0        1          0          0           2/19/11
    ## 4            0           0        1          0          0           1/20/11
    ## 5            0           0        1          0          0         2002/3/11
    ## 6            0           0        1          0          0           1/25/11
    ##   Employ_Unemp Employ_Dis Employ_Med Employ_Ret Gender Income Locat_Sub
    ## 1            0          0          0          0      0  56274         1
    ## 2            1          0          0          0      0      0         1
    ## 3            0          0          0          0      0  48767         1
    ## 4            1          0          0          0      1      0         1
    ## 5            0          0          0          0      1  43836         0
    ## 6            0          0          0          0      0  62902         0
    ##   Locat_Rural Marital.Status Monthly.Premium.Auto Months.Since.Last.Claim
    ## 1           0              1                   69                      32
    ## 2           0              0                   94                      13
    ## 3           0              1                  108                      18
    ## 4           0              1                  106                      18
    ## 5           1              0                   73                      12
    ## 6           1              1                   69                      14
    ##   Months.Since.Policy.Inception Number.of.Open.Complaints Number.of.Policies
    ## 1                             5                         0                  1
    ## 2                            42                         0                  8
    ## 3                            38                         0                  2
    ## 4                            65                         0                  7
    ## 5                            44                         0                  1
    ## 6                            94                         0                  2
    ##   Policy_Cor Policy_Spe Level_2 Level_3 Renew_O2 Renew_O3 Renew_O4 Sales_Bch
    ## 1          1          0       0       1        0        0        0         0
    ## 2          0          0       0       1        0        1        0         0
    ## 3          0          0       0       1        0        0        0         0
    ## 4          1          0       1       0        0        0        0         0
    ## 5          0          0       0       0        0        0        0         0
    ## 6          0          0       0       1        1        0        0         0
    ##   Sales_Call Sales_Web Total.Claim.Amount Vehicle.Class Vehicle_Med
    ## 1          0         0           384.8111  Two-Door Car           1
    ## 2          0         0          1131.4649 Four-Door Car           1
    ## 3          0         0           566.4722  Two-Door Car           1
    ## 4          1         0           529.8813           SUV           1
    ## 5          0         0           138.1309 Four-Door Car           1
    ## 6          0         1           159.3830  Two-Door Car           1
    ##   Vehicle_Large   logCLV
    ## 1             0 7.924260
    ## 2             0 8.850738
    ## 3             0 9.464008
    ## 4             0 8.941920
    ## 5             0 7.942253
    ## 6             0 9.018732

## REGRESSION MODELS

1)  Define y (Dependent Variable). For this example, Sales for Brand 1
    (UNITS1) is used.

2)  Define X (Independent Variables). For this example, OWN Marketing
    Activity (PRICE1, FEAT1 and DISP1) is used

3)  Run the Models. For example, a linear model where Sales for Brand 1
    (UNITS1) are a function of Units1’s Price (PRICE1), Feature (FEAT1),
    and Display (DISP1)

``` r
# Run the Regression (includes an INTERCEPT)

# Define TRAINING Data (i.e, using the FIRST 3000)
data.training <- df[1:7321,]
data.test <- df[7322:9134,]
head(data.training)
```

    ##   Customer      State Customer.Lifetime.Value Response Coverage_Ext
    ## 1  BU79786 Washington                2763.519       No            0
    ## 2  QZ44356    Arizona                6979.536       No            1
    ## 3  AI49188     Nevada               12887.432       No            0
    ## 4  WW63253 California                7645.862       No            0
    ## 5  HB64268 Washington                2813.693       No            0
    ## 6  OC83172     Oregon                8256.298      Yes            0
    ##   Coverage_Pre Edu_College Edu_Bach Edu_Master Edu_Doctor Effective.To.Date
    ## 1            0           0        1          0          0           2/24/11
    ## 2            0           0        1          0          0           1/31/11
    ## 3            1           0        1          0          0           2/19/11
    ## 4            0           0        1          0          0           1/20/11
    ## 5            0           0        1          0          0         2002/3/11
    ## 6            0           0        1          0          0           1/25/11
    ##   Employ_Unemp Employ_Dis Employ_Med Employ_Ret Gender Income Locat_Sub
    ## 1            0          0          0          0      0  56274         1
    ## 2            1          0          0          0      0      0         1
    ## 3            0          0          0          0      0  48767         1
    ## 4            1          0          0          0      1      0         1
    ## 5            0          0          0          0      1  43836         0
    ## 6            0          0          0          0      0  62902         0
    ##   Locat_Rural Marital.Status Monthly.Premium.Auto Months.Since.Last.Claim
    ## 1           0              1                   69                      32
    ## 2           0              0                   94                      13
    ## 3           0              1                  108                      18
    ## 4           0              1                  106                      18
    ## 5           1              0                   73                      12
    ## 6           1              1                   69                      14
    ##   Months.Since.Policy.Inception Number.of.Open.Complaints Number.of.Policies
    ## 1                             5                         0                  1
    ## 2                            42                         0                  8
    ## 3                            38                         0                  2
    ## 4                            65                         0                  7
    ## 5                            44                         0                  1
    ## 6                            94                         0                  2
    ##   Policy_Cor Policy_Spe Level_2 Level_3 Renew_O2 Renew_O3 Renew_O4 Sales_Bch
    ## 1          1          0       0       1        0        0        0         0
    ## 2          0          0       0       1        0        1        0         0
    ## 3          0          0       0       1        0        0        0         0
    ## 4          1          0       1       0        0        0        0         0
    ## 5          0          0       0       0        0        0        0         0
    ## 6          0          0       0       1        1        0        0         0
    ##   Sales_Call Sales_Web Total.Claim.Amount Vehicle.Class Vehicle_Med
    ## 1          0         0           384.8111  Two-Door Car           1
    ## 2          0         0          1131.4649 Four-Door Car           1
    ## 3          0         0           566.4722  Two-Door Car           1
    ## 4          1         0           529.8813           SUV           1
    ## 5          0         0           138.1309 Four-Door Car           1
    ## 6          0         1           159.3830  Two-Door Car           1
    ##   Vehicle_Large   logCLV
    ## 1             0 7.924260
    ## 2             0 8.850738
    ## 3             0 9.464008
    ## 4             0 8.941920
    ## 5             0 7.942253
    ## 6             0 9.018732

``` r
lm.linear   <- lm(Customer.Lifetime.Value  ~ ., data = data.training[, -c(1, 2, 4, 11, 37, 40)])
lm.semi_log <- lm(logCLV  ~ ., data = data.training[, -c(1, 2, 3, 4, 11, 37)])
lm.semi_log2 <- lm(logCLV  ~ ., data = data.training[, c(5,6,12,13,14,15,21,24,25,26,27,30,31,32,40)])


# Display Results
summary(lm.linear)
```

    ## 
    ## Call:
    ## lm(formula = Customer.Lifetime.Value ~ ., data = data.training[, 
    ##     -c(1, 2, 4, 11, 37, 40)])
    ## 
    ## Residuals:
    ##    Min     1Q Median     3Q    Max 
    ## -13443  -3267  -1338    582  62721 
    ## 
    ## Coefficients:
    ##                                 Estimate Std. Error t value Pr(>|t|)    
    ## (Intercept)                    1.834e+03  5.518e+02   3.323 0.000894 ***
    ## Coverage_Ext                  -1.667e+02  1.727e+02  -0.965 0.334626    
    ## Coverage_Pre                  -6.531e+02  2.903e+02  -2.250 0.024496 *  
    ## Edu_College                   -3.641e+02  1.950e+02  -1.867 0.061981 .  
    ## Edu_Bach                      -3.532e+02  1.940e+02  -1.820 0.068734 .  
    ## Edu_Master                    -2.515e+02  2.971e+02  -0.846 0.397366    
    ## Edu_Doctor                    -5.472e+02  4.041e+02  -1.354 0.175745    
    ## Employ_Unemp                  -8.197e+02  3.035e+02  -2.700 0.006940 ** 
    ## Employ_Dis                    -6.289e+02  3.991e+02  -1.576 0.115120    
    ## Employ_Med                    -3.644e+02  3.866e+02  -0.943 0.345935    
    ## Employ_Ret                    -8.721e+02  4.646e+02  -1.877 0.060520 .  
    ## Gender                        -2.177e+02  1.487e+02  -1.464 0.143219    
    ## Income                        -3.355e-03  4.320e-03  -0.777 0.437411    
    ## Locat_Sub                      7.454e+00  2.365e+02   0.032 0.974863    
    ## Locat_Rural                   -1.111e+02  2.701e+02  -0.411 0.680727    
    ## Marital.Status                 2.551e+01  1.606e+02   0.159 0.873802    
    ## Monthly.Premium.Auto           8.831e+01  3.594e+00  24.572  < 2e-16 ***
    ## Months.Since.Last.Claim        8.014e+00  7.319e+00   1.095 0.273602    
    ## Months.Since.Policy.Inception -1.415e+00  2.670e+00  -0.530 0.596283    
    ## Number.of.Open.Complaints     -2.275e+02  8.123e+01  -2.801 0.005116 ** 
    ## Number.of.Policies             5.003e+01  3.081e+01   1.624 0.104384    
    ## Policy_Cor                    -2.912e+02  1.832e+02  -1.589 0.112033    
    ## Policy_Spe                     8.698e+02  3.561e+02   2.442 0.014619 *  
    ## Level_2                       -1.749e+02  2.186e+02  -0.800 0.423795    
    ## Level_3                       -1.147e+02  2.012e+02  -0.570 0.568710    
    ## Renew_O2                      -1.086e+03  1.833e+02  -5.925 3.26e-09 ***
    ## Renew_O3                      -5.977e+02  2.235e+02  -2.674 0.007518 ** 
    ## Renew_O4                      -1.227e+03  2.566e+02  -4.783 1.76e-06 ***
    ## Sales_Bch                      1.608e+02  1.840e+02   0.874 0.382271    
    ## Sales_Call                     1.921e+02  2.081e+02   0.923 0.355988    
    ## Sales_Web                     -4.639e+01  2.284e+02  -0.203 0.839065    
    ## Total.Claim.Amount            -1.264e+00  5.299e-01  -2.385 0.017121 *  
    ## Vehicle_Med                   -1.190e+02  1.933e+02  -0.616 0.538059    
    ## Vehicle_Large                 -2.139e+02  2.866e+02  -0.746 0.455540    
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 6297 on 7287 degrees of freedom
    ## Multiple R-squared:  0.175,  Adjusted R-squared:  0.1712 
    ## F-statistic: 46.83 on 33 and 7287 DF,  p-value: < 2.2e-16

``` r
summary(lm.semi_log)
```

    ## 
    ## Call:
    ## lm(formula = logCLV ~ ., data = data.training[, -c(1, 2, 3, 4, 
    ##     11, 37)])
    ## 
    ## Residuals:
    ##     Min      1Q  Median      3Q     Max 
    ## -1.0801 -0.4513 -0.1088  0.2638  1.8731 
    ## 
    ## Coefficients:
    ##                                 Estimate Std. Error t value Pr(>|t|)    
    ## (Intercept)                    7.960e+00  4.946e-02 160.932  < 2e-16 ***
    ## Coverage_Ext                   4.125e-02  1.548e-02   2.664  0.00773 ** 
    ## Coverage_Pre                   2.220e-02  2.602e-02   0.853  0.39352    
    ## Edu_College                   -3.366e-02  1.748e-02  -1.926  0.05419 .  
    ## Edu_Bach                      -3.891e-02  1.739e-02  -2.237  0.02530 *  
    ## Edu_Master                    -2.646e-02  2.663e-02  -0.993  0.32051    
    ## Edu_Doctor                    -7.241e-02  3.622e-02  -1.999  0.04563 *  
    ## Employ_Unemp                  -7.993e-02  2.721e-02  -2.938  0.00331 ** 
    ## Employ_Dis                    -5.041e-02  3.577e-02  -1.409  0.15878    
    ## Employ_Med                    -5.401e-02  3.465e-02  -1.559  0.11912    
    ## Employ_Ret                    -8.926e-02  4.164e-02  -2.144  0.03209 *  
    ## Gender                        -2.091e-02  1.333e-02  -1.569  0.11668    
    ## Income                         2.022e-07  3.872e-07   0.522  0.60154    
    ## Locat_Sub                     -3.896e-03  2.120e-02  -0.184  0.85422    
    ## Locat_Rural                   -1.077e-02  2.421e-02  -0.445  0.65630    
    ## Marital.Status                 1.890e-02  1.440e-02   1.313  0.18926    
    ## Monthly.Premium.Auto           8.744e-03  3.221e-04  27.144  < 2e-16 ***
    ## Months.Since.Last.Claim        5.342e-04  6.560e-04   0.814  0.41552    
    ## Months.Since.Policy.Inception -3.358e-04  2.394e-04  -1.403  0.16063    
    ## Number.of.Open.Complaints     -2.869e-02  7.281e-03  -3.940 8.22e-05 ***
    ## Number.of.Policies             5.195e-02  2.761e-03  18.815  < 2e-16 ***
    ## Policy_Cor                    -2.476e-02  1.642e-02  -1.508  0.13168    
    ## Policy_Spe                     9.174e-02  3.192e-02   2.874  0.00407 ** 
    ## Level_2                       -6.428e-03  1.959e-02  -0.328  0.74288    
    ## Level_3                       -5.479e-03  1.804e-02  -0.304  0.76131    
    ## Renew_O2                      -1.325e-01  1.643e-02  -8.064 8.56e-16 ***
    ## Renew_O3                      -7.000e-02  2.004e-02  -3.493  0.00048 ***
    ## Renew_O4                      -1.524e-01  2.300e-02  -6.627 3.67e-11 ***
    ## Sales_Bch                      7.493e-03  1.649e-02   0.454  0.64961    
    ## Sales_Call                     1.455e-02  1.865e-02   0.780  0.43540    
    ## Sales_Web                     -2.155e-02  2.047e-02  -1.052  0.29263    
    ## Total.Claim.Amount            -1.055e-04  4.749e-05  -2.221  0.02638 *  
    ## Vehicle_Med                   -5.827e-03  1.733e-02  -0.336  0.73667    
    ## Vehicle_Large                 -2.142e-02  2.569e-02  -0.834  0.40434    
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 0.5644 on 7287 degrees of freedom
    ## Multiple R-squared:  0.2602, Adjusted R-squared:  0.2568 
    ## F-statistic: 77.65 on 33 and 7287 DF,  p-value: < 2.2e-16

``` r
summary(lm.semi_log2)
```

    ## 
    ## Call:
    ## lm(formula = logCLV ~ ., data = data.training[, c(5, 6, 12, 13, 
    ##     14, 15, 21, 24, 25, 26, 27, 30, 31, 32, 40)])
    ## 
    ## Residuals:
    ##     Min      1Q  Median      3Q     Max 
    ## -1.0757 -0.4592 -0.1114  0.2659  1.8509 
    ## 
    ## Coefficients:
    ##                             Estimate Std. Error t value Pr(>|t|)    
    ## (Intercept)                7.9352335  0.0254911 311.295  < 2e-16 ***
    ## Coverage_Ext               0.0431497  0.0154534   2.792  0.00525 ** 
    ## Coverage_Pre               0.0239962  0.0259835   0.924  0.35577    
    ## Employ_Unemp              -0.1195313  0.0158453  -7.544 5.12e-14 ***
    ## Employ_Dis                -0.0668636  0.0329290  -2.031  0.04234 *  
    ## Employ_Med                -0.0753617  0.0317513  -2.373  0.01765 *  
    ## Employ_Ret                -0.1183461  0.0388741  -3.044  0.00234 ** 
    ## Monthly.Premium.Auto       0.0081876  0.0002166  37.801  < 2e-16 ***
    ## Number.of.Open.Complaints -0.0286805  0.0072762  -3.942 8.17e-05 ***
    ## Number.of.Policies         0.0522081  0.0027538  18.959  < 2e-16 ***
    ## Policy_Cor                -0.0241376  0.0164113  -1.471  0.14139    
    ## Policy_Spe                 0.0912785  0.0318373   2.867  0.00416 ** 
    ## Renew_O2                  -0.1299291  0.0160120  -8.114 5.68e-16 ***
    ## Renew_O3                  -0.0679791  0.0198515  -3.424  0.00062 ***
    ## Renew_O4                  -0.1471387  0.0224736  -6.547 6.26e-11 ***
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 0.5647 on 7306 degrees of freedom
    ## Multiple R-squared:  0.2574, Adjusted R-squared:  0.256 
    ## F-statistic: 180.9 on 14 and 7306 DF,  p-value: < 2.2e-16

``` r
# Assuming you have logCLV values in data.test$logCLV
real_logCLV <- data.test$logCLV

# Predicted values from the linear regression model lm.semi_log2
predicted_logCLV <- predict(lm.semi_log2, newdata = data.test)

# Create a data frame for plotting
plot_data <- data.frame(Real_LogCLV = real_logCLV, Predicted_LogCLV = predicted_logCLV)

# Calculate the breaks for the histograms
breaks <- seq(min(c(plot_data$Real_LogCLV, plot_data$Predicted_LogCLV)),
              max(c(plot_data$Real_LogCLV, plot_data$Predicted_LogCLV)),
              length.out = 30)  # Adjust the number of bins as needed

# Create a histogram for real log CLV in blue
hist(plot_data$Real_LogCLV, col = rgb(0, 0, 1, alpha = 0.4), main = "Histogram of Real LogCLV",
     xlab = "Real LogCLV", ylab = "Frequency", border = "white", xlim = range(breaks), breaks = breaks)

# Add histogram for predicted log CLV in green
hist(plot_data$Predicted_LogCLV, col = rgb(0, 1, 0, alpha = 0.4), add = TRUE, border = "white", breaks = breaks)

# Adding legend
legend("topright", legend = c("Real LogCLV", "Predicted LogCLV"), 
       fill = c(rgb(0, 0, 1, alpha = 0.4), rgb(0, 1, 0, alpha = 0.4)))
```

![](IBM-wastson_files/figure-gfm/unnamed-chunk-3-1.png)<!-- -->

``` r
#produce residual vs. fitted plot
#get list of residuals 
res <- resid(lm.semi_log2)
plot(fitted(lm.semi_log2), res)

#add a horizontal line at 0 
abline(0,0)
```

![](IBM-wastson_files/figure-gfm/unnamed-chunk-3-2.png)<!-- -->

``` r
#create Q-Q plot for residuals
qqnorm(res)

#add a straight diagonal line to the plot
qqline(res) 
```

![](IBM-wastson_files/figure-gfm/unnamed-chunk-3-3.png)<!-- -->
