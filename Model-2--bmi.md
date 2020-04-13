Model 2: BMI
================

Running the crude model

``` r
crude_bmi = 
  multinom(bmi_cat ~ fuel_used_for_cooking_percent_wood_dung + percent_public_source + percent_private_toilet + percent_employed + percent_without_hs_education + percent_caste, data=total)
```

    ## # weights:  24 (14 variable)
    ## initial  value 147.214047 
    ## iter  10 value 103.295946
    ## iter  20 value 71.570954
    ## iter  30 value 68.734672
    ## iter  40 value 64.698754
    ## iter  50 value 64.252816
    ## iter  60 value 64.222598
    ## iter  70 value 64.212465
    ## iter  80 value 64.198669
    ## final  value 64.174407 
    ## converged

``` r
summary(crude_bmi)
```

    ## Call:
    ## multinom(formula = bmi_cat ~ fuel_used_for_cooking_percent_wood_dung + 
    ##     percent_public_source + percent_private_toilet + percent_employed + 
    ##     percent_without_hs_education + percent_caste, data = total)
    ## 
    ## Coefficients:
    ##            (Intercept) fuel_used_for_cooking_percent_wood_dung
    ## overweight    4.841509                                30.86185
    ## obese        15.710113                               -24.42669
    ##            percent_public_source percent_private_toilet percent_employed
    ## overweight            -0.2066547             0.08686193        -5.065361
    ## obese                 -8.2269022             0.09332604       -20.342390
    ##            percent_without_hs_education percent_caste
    ## overweight                    -4.150815   -0.03260152
    ## obese                        -13.558556    0.08226105
    ## 
    ## Std. Errors:
    ##            (Intercept) fuel_used_for_cooking_percent_wood_dung
    ## overweight    2.587390                                18.81813
    ## obese         3.887663                                33.47660
    ##            percent_public_source percent_private_toilet percent_employed
    ## overweight             0.1391141              0.7738523         4.205084
    ## obese                  3.1036858              0.7739189         6.639545
    ##            percent_without_hs_education percent_caste
    ## overweight                     2.485319     0.1456237
    ## obese                          3.725614     0.0842094
    ## 
    ## Residual Deviance: 128.3488 
    ## AIC: 156.3488

``` r
crude_model=
  crude_bmi %>% 
  broom::tidy() %>% 
  knitr::kable(digits = 3)

crude_or=
  exp(coef(crude_bmi)) %>% 
  knitr::kable(digits = 3)
```

``` r
crude_model
```

| y.level    | term                                          |     estimate | std.error | statistic | p.value |
| :--------- | :-------------------------------------------- | -----------: | --------: | --------: | ------: |
| overweight | (Intercept)                                   | 1.266600e+02 |     2.587 |     1.871 |   0.061 |
| overweight | fuel\_used\_for\_cooking\_percent\_wood\_dung | 2.530055e+13 |    18.818 |     1.640 |   0.101 |
| overweight | percent\_public\_source                       | 8.130000e-01 |     0.139 |   \-1.486 |   0.137 |
| overweight | percent\_private\_toilet                      | 1.091000e+00 |     0.774 |     0.112 |   0.911 |
| overweight | percent\_employed                             | 6.000000e-03 |     4.205 |   \-1.205 |   0.228 |
| overweight | percent\_without\_hs\_education               | 1.600000e-02 |     2.485 |   \-1.670 |   0.095 |
| overweight | percent\_caste                                | 9.680000e-01 |     0.146 |   \-0.224 |   0.823 |
| obese      | (Intercept)                                   | 6.649903e+06 |     3.888 |     4.041 |   0.000 |
| obese      | fuel\_used\_for\_cooking\_percent\_wood\_dung | 0.000000e+00 |    33.477 |   \-0.730 |   0.466 |
| obese      | percent\_public\_source                       | 0.000000e+00 |     3.104 |   \-2.651 |   0.008 |
| obese      | percent\_private\_toilet                      | 1.098000e+00 |     0.774 |     0.121 |   0.904 |
| obese      | percent\_employed                             | 0.000000e+00 |     6.640 |   \-3.064 |   0.002 |
| obese      | percent\_without\_hs\_education               | 0.000000e+00 |     3.726 |   \-3.639 |   0.000 |
| obese      | percent\_caste                                | 1.086000e+00 |     0.084 |     0.977 |   0.329 |

``` r
crude_or
```

|            | (Intercept) | fuel\_used\_for\_cooking\_percent\_wood\_dung | percent\_public\_source | percent\_private\_toilet | percent\_employed | percent\_without\_hs\_education | percent\_caste |
| ---------- | ----------: | --------------------------------------------: | ----------------------: | -----------------------: | ----------------: | ------------------------------: | -------------: |
| overweight |      126.66 |                                  2.530055e+13 |                   0.813 |                    1.091 |             0.006 |                           0.016 |          0.968 |
| obese      |  6649902.54 |                                  0.000000e+00 |                   0.000 |                    1.098 |             0.000 |                           0.000 |          1.086 |

Running the model with age as a confounder

``` r
age_bmi = 
  multinom(bmi_cat ~ fuel_used_for_cooking_percent_wood_dung + percent_public_source + percent_private_toilet + percent_employed + percent_without_hs_education + percent_caste + median_age, data=total)
```

    ## # weights:  27 (16 variable)
    ## initial  value 147.214047 
    ## iter  10 value 85.386969
    ## iter  20 value 67.175228
    ## iter  30 value 63.067548
    ## iter  40 value 62.449084
    ## iter  50 value 59.512392
    ## iter  60 value 59.442741
    ## iter  70 value 59.329178
    ## iter  80 value 59.297019
    ## iter  90 value 59.273833
    ## iter 100 value 59.198945
    ## final  value 59.198945 
    ## stopped after 100 iterations

``` r
summary(age_bmi)
```

    ## Call:
    ## multinom(formula = bmi_cat ~ fuel_used_for_cooking_percent_wood_dung + 
    ##     percent_public_source + percent_private_toilet + percent_employed + 
    ##     percent_without_hs_education + percent_caste + median_age, 
    ##     data = total)
    ## 
    ## Coefficients:
    ##            (Intercept) fuel_used_for_cooking_percent_wood_dung
    ## overweight   0.2328355                                33.51952
    ## obese       -1.8006463                               -38.54670
    ##            percent_public_source percent_private_toilet percent_employed
    ## overweight            -0.2191531             0.05917181        -4.075657
    ## obese                 -8.5898073             0.05998602       -14.509443
    ##            percent_without_hs_education percent_caste median_age
    ## overweight                    -4.367041   -0.04364853   0.104234
    ## obese                        -11.196266    0.09103370   0.342041
    ## 
    ## Std. Errors:
    ##            (Intercept) fuel_used_for_cooking_percent_wood_dung
    ## overweight    5.596398                               15.752876
    ## obese         7.258591                                4.846254
    ##            percent_public_source percent_private_toilet percent_employed
    ## overweight             0.1265065              0.1917711         4.374845
    ## obese                  3.3405435              0.1919833         6.976795
    ##            percent_without_hs_education percent_caste median_age
    ## overweight                     2.422494     0.2085175  0.1169568
    ## obese                          3.754732     0.0816814  0.1379280
    ## 
    ## Residual Deviance: 118.3979 
    ## AIC: 150.3979

``` r
age_model=
  age_bmi %>% 
  broom::tidy() %>% 
  knitr::kable(digits = 3)

age_or=
  exp(coef(age_bmi)) %>% 
  knitr::kable(digits = 3)
```

``` r
age_model
```

| y.level    | term                                          |     estimate | std.error | statistic | p.value |
| :--------- | :-------------------------------------------- | -----------: | --------: | --------: | ------: |
| overweight | (Intercept)                                   | 1.262000e+00 |     5.596 |     0.042 |   0.967 |
| overweight | fuel\_used\_for\_cooking\_percent\_wood\_dung | 3.608622e+14 |    15.753 |     2.128 |   0.033 |
| overweight | percent\_public\_source                       | 8.030000e-01 |     0.127 |   \-1.732 |   0.083 |
| overweight | percent\_private\_toilet                      | 1.061000e+00 |     0.192 |     0.309 |   0.758 |
| overweight | percent\_employed                             | 1.700000e-02 |     4.375 |   \-0.932 |   0.352 |
| overweight | percent\_without\_hs\_education               | 1.300000e-02 |     2.422 |   \-1.803 |   0.071 |
| overweight | percent\_caste                                | 9.570000e-01 |     0.209 |   \-0.209 |   0.834 |
| overweight | median\_age                                   | 1.110000e+00 |     0.117 |     0.891 |   0.373 |
| obese      | (Intercept)                                   | 1.650000e-01 |     7.259 |   \-0.248 |   0.804 |
| obese      | fuel\_used\_for\_cooking\_percent\_wood\_dung | 0.000000e+00 |     4.846 |   \-7.954 |   0.000 |
| obese      | percent\_public\_source                       | 0.000000e+00 |     3.341 |   \-2.571 |   0.010 |
| obese      | percent\_private\_toilet                      | 1.062000e+00 |     0.192 |     0.312 |   0.755 |
| obese      | percent\_employed                             | 0.000000e+00 |     6.977 |   \-2.080 |   0.038 |
| obese      | percent\_without\_hs\_education               | 0.000000e+00 |     3.755 |   \-2.982 |   0.003 |
| obese      | percent\_caste                                | 1.095000e+00 |     0.082 |     1.114 |   0.265 |
| obese      | median\_age                                   | 1.408000e+00 |     0.138 |     2.480 |   0.013 |

``` r
age_or
```

|            | (Intercept) | fuel\_used\_for\_cooking\_percent\_wood\_dung | percent\_public\_source | percent\_private\_toilet | percent\_employed | percent\_without\_hs\_education | percent\_caste | median\_age |
| ---------- | ----------: | --------------------------------------------: | ----------------------: | -----------------------: | ----------------: | ------------------------------: | -------------: | ----------: |
| overweight |       1.262 |                                  3.608622e+14 |                   0.803 |                    1.061 |             0.017 |                           0.013 |          0.957 |       1.110 |
| obese      |       0.165 |                                  0.000000e+00 |                   0.000 |                    1.062 |             0.000 |                           0.000 |          1.095 |       1.408 |

Running the model with sex as a confounder

``` r
sex_bmi = 
  multinom(bmi_cat ~ fuel_used_for_cooking_percent_wood_dung + percent_public_source + percent_private_toilet + percent_employed + percent_without_hs_education + percent_caste + percent_female, data=total)
```

    ## # weights:  27 (16 variable)
    ## initial  value 147.214047 
    ## iter  10 value 91.698791
    ## iter  20 value 69.831614
    ## iter  30 value 66.426622
    ## iter  40 value 65.048422
    ## iter  50 value 63.827600
    ## iter  60 value 63.697417
    ## iter  70 value 63.640356
    ## iter  80 value 63.619764
    ## iter  90 value 63.591148
    ## iter 100 value 63.571797
    ## final  value 63.571797 
    ## stopped after 100 iterations

``` r
summary(sex_bmi)
```

    ## Call:
    ## multinom(formula = bmi_cat ~ fuel_used_for_cooking_percent_wood_dung + 
    ##     percent_public_source + percent_private_toilet + percent_employed + 
    ##     percent_without_hs_education + percent_caste + percent_female, 
    ##     data = total)
    ## 
    ## Coefficients:
    ##            (Intercept) fuel_used_for_cooking_percent_wood_dung
    ## overweight    13.43468                                33.51375
    ## obese         15.39930                               -21.92309
    ##            percent_public_source percent_private_toilet percent_employed
    ## overweight            -0.2237155             0.06137072        -4.695264
    ## obese                 -8.3095525             0.06863637       -19.695791
    ##            percent_without_hs_education percent_caste percent_female
    ## overweight                     -4.75726   -0.03148767    -12.9098479
    ## obese                         -13.78988    0.08118686      0.1021692
    ## 
    ## Std. Errors:
    ##            (Intercept) fuel_used_for_cooking_percent_wood_dung
    ## overweight    9.095626                                19.31279
    ## obese         4.429304                                33.55750
    ##            percent_public_source percent_private_toilet percent_employed
    ## overweight             0.1461252              0.2498667         4.181228
    ## obese                  3.1203122              0.2499311         6.644800
    ##            percent_without_hs_education percent_caste percent_female
    ## overweight                     2.530732    0.13639351      13.040637
    ## obese                          3.738660    0.08580581       3.256491
    ## 
    ## Residual Deviance: 127.1436 
    ## AIC: 159.1436

``` r
sex_model=
  sex_bmi %>% 
  broom::tidy() %>% 
  knitr::kable(digits = 3)

sex_or=
  exp(coef(sex_bmi)) %>% 
  knitr::kable(digits = 3)
```

``` r
sex_model
```

| y.level    | term                                          |     estimate | std.error | statistic | p.value |
| :--------- | :-------------------------------------------- | -----------: | --------: | --------: | ------: |
| overweight | (Intercept)                                   | 6.832907e+05 |     9.096 |     1.477 |   0.140 |
| overweight | fuel\_used\_for\_cooking\_percent\_wood\_dung | 3.587870e+14 |    19.313 |     1.735 |   0.083 |
| overweight | percent\_public\_source                       | 8.000000e-01 |     0.146 |   \-1.531 |   0.126 |
| overweight | percent\_private\_toilet                      | 1.063000e+00 |     0.250 |     0.246 |   0.806 |
| overweight | percent\_employed                             | 9.000000e-03 |     4.181 |   \-1.123 |   0.261 |
| overweight | percent\_without\_hs\_education               | 9.000000e-03 |     2.531 |   \-1.880 |   0.060 |
| overweight | percent\_caste                                | 9.690000e-01 |     0.136 |   \-0.231 |   0.817 |
| overweight | percent\_female                               | 0.000000e+00 |    13.041 |   \-0.990 |   0.322 |
| obese      | (Intercept)                                   | 4.873396e+06 |     4.429 |     3.477 |   0.001 |
| obese      | fuel\_used\_for\_cooking\_percent\_wood\_dung | 0.000000e+00 |    33.558 |   \-0.653 |   0.514 |
| obese      | percent\_public\_source                       | 0.000000e+00 |     3.120 |   \-2.663 |   0.008 |
| obese      | percent\_private\_toilet                      | 1.071000e+00 |     0.250 |     0.275 |   0.784 |
| obese      | percent\_employed                             | 0.000000e+00 |     6.645 |   \-2.964 |   0.003 |
| obese      | percent\_without\_hs\_education               | 0.000000e+00 |     3.739 |   \-3.688 |   0.000 |
| obese      | percent\_caste                                | 1.085000e+00 |     0.086 |     0.946 |   0.344 |
| obese      | percent\_female                               | 1.108000e+00 |     3.256 |     0.031 |   0.975 |

``` r
sex_or
```

|            | (Intercept) | fuel\_used\_for\_cooking\_percent\_wood\_dung | percent\_public\_source | percent\_private\_toilet | percent\_employed | percent\_without\_hs\_education | percent\_caste | percent\_female |
| ---------- | ----------: | --------------------------------------------: | ----------------------: | -----------------------: | ----------------: | ------------------------------: | -------------: | --------------: |
| overweight |    683290.7 |                                   3.58787e+14 |                     0.8 |                    1.063 |             0.009 |                           0.009 |          0.969 |           0.000 |
| obese      |   4873396.2 |                                   0.00000e+00 |                     0.0 |                    1.071 |             0.000 |                           0.000 |          1.085 |           1.108 |

Running the model with marital status as a confounder

``` r
marital_bmi = 
  multinom(bmi_cat ~ fuel_used_for_cooking_percent_wood_dung + percent_public_source + percent_private_toilet + percent_employed + percent_without_hs_education + percent_caste + percent_marital_status, data=total)
```

    ## # weights:  27 (16 variable)
    ## initial  value 147.214047 
    ## iter  10 value 106.922174
    ## iter  20 value 73.993461
    ## iter  30 value 66.997340
    ## iter  40 value 65.717316
    ## iter  50 value 63.595788
    ## iter  60 value 63.435525
    ## iter  70 value 63.405000
    ## iter  80 value 63.388425
    ## iter  90 value 63.370866
    ## iter 100 value 63.347872
    ## final  value 63.347872 
    ## stopped after 100 iterations

``` r
summary(marital_bmi)
```

    ## Call:
    ## multinom(formula = bmi_cat ~ fuel_used_for_cooking_percent_wood_dung + 
    ##     percent_public_source + percent_private_toilet + percent_employed + 
    ##     percent_without_hs_education + percent_caste + percent_marital_status, 
    ##     data = total)
    ## 
    ## Coefficients:
    ##            (Intercept) fuel_used_for_cooking_percent_wood_dung
    ## overweight    3.984556                                31.96985
    ## obese        15.138607                               -23.05708
    ##            percent_public_source percent_private_toilet percent_employed
    ## overweight             -0.213203             0.06273891        -4.818909
    ## obese                  -9.263091             0.06945843       -22.098893
    ##            percent_without_hs_education percent_caste
    ## overweight                    -4.135216   -0.03155531
    ## obese                        -12.846249    0.08741653
    ##            percent_marital_status
    ## overweight              0.8191388
    ## obese                   1.5274265
    ## 
    ## Std. Errors:
    ##            (Intercept) fuel_used_for_cooking_percent_wood_dung
    ## overweight    4.972651                                19.29832
    ## obese         6.876978                                33.78763
    ##            percent_public_source percent_private_toilet percent_employed
    ## overweight             0.1409062              0.2653752         4.188066
    ## obese                  3.3188904              0.2654059         7.026320
    ##            percent_without_hs_education percent_caste
    ## overweight                     2.444694    0.14119997
    ## obese                          3.754602    0.08470863
    ##            percent_marital_status
    ## overweight               4.946923
    ## obese                    6.513098
    ## 
    ## Residual Deviance: 126.6957 
    ## AIC: 158.6957

``` r
marital_model=
  marital_bmi %>% 
  broom::tidy() %>% 
  knitr::kable(digits = 3)

marital_or=
  exp(coef(marital_bmi)) %>% 
  knitr::kable(digits = 3)
```

``` r
marital_model
```

| y.level    | term                                          |     estimate | std.error | statistic | p.value |
| :--------- | :-------------------------------------------- | -----------: | --------: | --------: | ------: |
| overweight | (Intercept)                                   | 5.376100e+01 |     4.973 |     0.801 |   0.423 |
| overweight | fuel\_used\_for\_cooking\_percent\_wood\_dung | 7.661796e+13 |    19.298 |     1.657 |   0.098 |
| overweight | percent\_public\_source                       | 8.080000e-01 |     0.141 |   \-1.513 |   0.130 |
| overweight | percent\_private\_toilet                      | 1.065000e+00 |     0.265 |     0.236 |   0.813 |
| overweight | percent\_employed                             | 8.000000e-03 |     4.188 |   \-1.151 |   0.250 |
| overweight | percent\_without\_hs\_education               | 1.600000e-02 |     2.445 |   \-1.692 |   0.091 |
| overweight | percent\_caste                                | 9.690000e-01 |     0.141 |   \-0.223 |   0.823 |
| overweight | percent\_marital\_status                      | 2.269000e+00 |     4.947 |     0.166 |   0.868 |
| obese      | (Intercept)                                   | 3.755031e+06 |     6.877 |     2.201 |   0.028 |
| obese      | fuel\_used\_for\_cooking\_percent\_wood\_dung | 0.000000e+00 |    33.788 |   \-0.682 |   0.495 |
| obese      | percent\_public\_source                       | 0.000000e+00 |     3.319 |   \-2.791 |   0.005 |
| obese      | percent\_private\_toilet                      | 1.072000e+00 |     0.265 |     0.262 |   0.794 |
| obese      | percent\_employed                             | 0.000000e+00 |     7.026 |   \-3.145 |   0.002 |
| obese      | percent\_without\_hs\_education               | 0.000000e+00 |     3.755 |   \-3.421 |   0.001 |
| obese      | percent\_caste                                | 1.091000e+00 |     0.085 |     1.032 |   0.302 |
| obese      | percent\_marital\_status                      | 4.606000e+00 |     6.513 |     0.235 |   0.815 |

``` r
marital_or
```

|            | (Intercept) | fuel\_used\_for\_cooking\_percent\_wood\_dung | percent\_public\_source | percent\_private\_toilet | percent\_employed | percent\_without\_hs\_education | percent\_caste | percent\_marital\_status |
| ---------- | ----------: | --------------------------------------------: | ----------------------: | -----------------------: | ----------------: | ------------------------------: | -------------: | -----------------------: |
| overweight |      53.761 |                                  7.661796e+13 |                   0.808 |                    1.065 |             0.008 |                           0.016 |          0.969 |                    2.269 |
| obese      | 3755031.361 |                                  0.000000e+00 |                   0.000 |                    1.072 |             0.000 |                           0.000 |          1.091 |                    4.606 |
