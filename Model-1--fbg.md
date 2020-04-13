Model 1: Fbg
================

Running the crude model

``` r
crude_fbg = 
  multinom(fbg_cat ~ fuel_used_for_cooking_percent_wood_dung + percent_public_source + percent_private_toilet + percent_employed + percent_without_hs_education + percent_caste, data=total)
```

    ## # weights:  24 (14 variable)
    ## initial  value 147.214047 
    ## iter  10 value 126.004019
    ## iter  20 value 120.958058
    ## iter  30 value 120.478616
    ## iter  40 value 117.231716
    ## iter  50 value 116.951601
    ## final  value 116.946268 
    ## converged

``` r
crude_fbg 
```

    ## Call:
    ## multinom(formula = fbg_cat ~ fuel_used_for_cooking_percent_wood_dung + 
    ##     percent_public_source + percent_private_toilet + percent_employed + 
    ##     percent_without_hs_education + percent_caste, data = total)
    ## 
    ## Coefficients:
    ##             (Intercept) fuel_used_for_cooking_percent_wood_dung
    ## prediabetes    1.962341                                5.484380
    ## diabetes       2.153090                                1.018811
    ##             percent_public_source percent_private_toilet percent_employed
    ## prediabetes             -1.522975            0.003819443        -1.764898
    ## diabetes                -9.700376            0.002497776        -4.201023
    ##             percent_without_hs_education percent_caste
    ## prediabetes                   -1.0984781   -1.54915753
    ## diabetes                      -0.4357859   -0.02781386
    ## 
    ## Residual Deviance: 233.8925 
    ## AIC: 261.8925

Running the model with age as a confounder

``` r
age_fbg = 
  multinom(fbg_cat ~ fuel_used_for_cooking_percent_wood_dung + percent_public_source + percent_private_toilet + percent_employed + percent_without_hs_education + percent_caste + median_age, data=total)
```

    ## # weights:  27 (16 variable)
    ## initial  value 147.214047 
    ## iter  10 value 120.083806
    ## iter  20 value 113.192095
    ## iter  30 value 112.331907
    ## iter  40 value 111.207763
    ## iter  50 value 108.979685
    ## iter  60 value 108.947972
    ## final  value 108.946939 
    ## converged

``` r
summary(age_fbg)
```

    ## Call:
    ## multinom(formula = fbg_cat ~ fuel_used_for_cooking_percent_wood_dung + 
    ##     percent_public_source + percent_private_toilet + percent_employed + 
    ##     percent_without_hs_education + percent_caste + median_age, 
    ##     data = total)
    ## 
    ## Coefficients:
    ##             (Intercept) fuel_used_for_cooking_percent_wood_dung
    ## prediabetes   -9.537129                               4.5782739
    ## diabetes     -14.671208                              -0.1011297
    ##             percent_public_source percent_private_toilet percent_employed
    ## prediabetes             -1.549981           -0.001554108         1.977762
    ## diabetes                -9.015487           -0.004153350         2.375135
    ##             percent_without_hs_education percent_caste median_age
    ## prediabetes                     1.086844    -0.9767290  0.2106869
    ## diabetes                        3.659797    -0.0101799  0.2914880
    ## 
    ## Std. Errors:
    ##             (Intercept) fuel_used_for_cooking_percent_wood_dung
    ## prediabetes    3.908210                                7.360951
    ## diabetes       5.562783                               16.975470
    ##             percent_public_source percent_private_toilet percent_employed
    ## prediabetes              1.248331            0.006573568         3.418176
    ## diabetes                 4.642188            0.008067217         4.702471
    ##             percent_without_hs_education percent_caste median_age
    ## prediabetes                     1.904495     0.9919181 0.06677395
    ## diabetes                        3.209016     0.1491680 0.08847521
    ## 
    ## Residual Deviance: 217.8939 
    ## AIC: 249.8939

``` r
age_fbg %>% 
  broom::tidy() %>% 
  mutate(OR = exp(coef(age_fbg))) %>% 
  knitr::kable(digits = 3)
```

    ## Warning in format.data.frame(x = structure(list(estimate = c(0, 97.346, :
    ## corrupt data frame: columns will be truncated or padded with NAs

    ## Warning in `[<-.data.frame`(`*tmp*`, , isn, value = structure(list(estimate
    ## = structure(c("0.000", : provided 12 variables to replace 5 variables

| y.level     | term                                          | estimate | std.error | statistic | p.value |           OR |
| :---------- | :-------------------------------------------- | -------: | --------: | --------: | ------: | -----------: |
| prediabetes | (Intercept)                                   |    0.000 |     3.908 |   \-2.440 |   0.015 | 7.212363e-05 |
| prediabetes | fuel\_used\_for\_cooking\_percent\_wood\_dung |   97.346 |     7.361 |     0.622 |   0.534 | 4.249869e-07 |
| prediabetes | percent\_public\_source                       |    0.212 |     1.248 |   \-1.242 |   0.214 |           NA |
| prediabetes | percent\_private\_toilet                      |    0.998 |     0.007 |   \-0.236 |   0.813 |           NA |
| prediabetes | percent\_employed                             |    7.227 |     3.418 |     0.579 |   0.563 |           NA |
| prediabetes | percent\_without\_hs\_education               |    2.965 |     1.904 |     0.571 |   0.568 |           NA |
| prediabetes | percent\_caste                                |    0.377 |     0.992 |   \-0.985 |   0.325 |           NA |
| prediabetes | median\_age                                   |    1.235 |     0.067 |     3.155 |   0.002 |           NA |
| diabetes    | (Intercept)                                   |    0.000 |     5.563 |   \-2.637 |   0.008 |           NA |
| diabetes    | fuel\_used\_for\_cooking\_percent\_wood\_dung |    0.904 |    16.975 |   \-0.006 |   0.995 |           NA |
| diabetes    | percent\_public\_source                       |    0.000 |     4.642 |   \-1.942 |   0.052 |           NA |
| diabetes    | percent\_private\_toilet                      |    0.996 |     0.008 |   \-0.515 |   0.607 |           NA |
| diabetes    | percent\_employed                             |   10.752 |     4.702 |     0.505 |   0.614 |           NA |
| diabetes    | percent\_without\_hs\_education               |   38.853 |     3.209 |     1.140 |   0.254 |           NA |
| diabetes    | percent\_caste                                |    0.990 |     0.149 |   \-0.068 |   0.946 |           NA |
| diabetes    | median\_age                                   |    1.338 |     0.088 |     3.295 |   0.001 |           NA |

Running the model with sex as a confounder

``` r
sex_fbg = 
  multinom(fbg_cat ~ fuel_used_for_cooking_percent_wood_dung + percent_public_source + percent_private_toilet + percent_employed + percent_without_hs_education + percent_caste + percent_female, data=total)
```

    ## # weights:  27 (16 variable)
    ## initial  value 147.214047 
    ## iter  10 value 125.132550
    ## iter  20 value 120.689634
    ## iter  30 value 119.663226
    ## iter  40 value 118.460834
    ## iter  50 value 115.640491
    ## iter  60 value 115.430617
    ## final  value 115.256130 
    ## converged

``` r
summary(sex_fbg)
```

    ## Call:
    ## multinom(formula = fbg_cat ~ fuel_used_for_cooking_percent_wood_dung + 
    ##     percent_public_source + percent_private_toilet + percent_employed + 
    ##     percent_without_hs_education + percent_caste + percent_female, 
    ##     data = total)
    ## 
    ## Coefficients:
    ##             (Intercept) fuel_used_for_cooking_percent_wood_dung
    ## prediabetes   -8.788918                                4.205755
    ## diabetes      -8.348199                                1.385184
    ##             percent_public_source percent_private_toilet percent_employed
    ## prediabetes             -1.367466            0.004749212       -0.9709633
    ## diabetes               -10.111438            0.003015511       -2.8511089
    ##             percent_without_hs_education percent_caste percent_female
    ## prediabetes                   -0.6428292   -1.69374532       15.38484
    ## diabetes                      -0.1700545   -0.04084794       14.70183
    ## 
    ## Std. Errors:
    ##             (Intercept) fuel_used_for_cooking_percent_wood_dung
    ## prediabetes    7.809583                                6.766617
    ## diabetes       7.978979                               16.918901
    ##             percent_public_source percent_private_toilet percent_employed
    ## prediabetes              1.237316            0.005988480         3.116130
    ## diabetes                 4.761686            0.007291984         4.157151
    ##             percent_without_hs_education percent_caste percent_female
    ## prediabetes                     1.701773     0.9787261       11.23542
    ## diabetes                        2.889023     0.5833245       11.33858
    ## 
    ## Residual Deviance: 230.5123 
    ## AIC: 262.5123

Running the model with marital status as a confounder

``` r
marital_fbg = 
  multinom(fbg_cat ~ fuel_used_for_cooking_percent_wood_dung + percent_public_source + percent_private_toilet + percent_employed + percent_without_hs_education + percent_caste + percent_marital_status, data=total)
```

    ## # weights:  27 (16 variable)
    ## initial  value 147.214047 
    ## iter  10 value 130.781550
    ## iter  20 value 121.136652
    ## iter  30 value 120.780273
    ## iter  40 value 119.029619
    ## iter  50 value 115.954327
    ## iter  60 value 115.903704
    ## final  value 115.902660 
    ## converged

``` r
summary(marital_fbg)
```

    ## Call:
    ## multinom(formula = fbg_cat ~ fuel_used_for_cooking_percent_wood_dung + 
    ##     percent_public_source + percent_private_toilet + percent_employed + 
    ##     percent_without_hs_education + percent_caste + percent_marital_status, 
    ##     data = total)
    ## 
    ## Coefficients:
    ##             (Intercept) fuel_used_for_cooking_percent_wood_dung
    ## prediabetes    1.986113                                5.560182
    ## diabetes       5.313670                                2.599120
    ##             percent_public_source percent_private_toilet percent_employed
    ## prediabetes             -1.521497            0.003771747        -1.801471
    ## diabetes                -9.472381            0.002049244        -3.745794
    ##             percent_without_hs_education percent_caste
    ## prediabetes                   -1.1303649   -1.53230555
    ## diabetes                      -0.9516206   -0.03719445
    ##             percent_marital_status
    ## prediabetes          -0.0009918383
    ## diabetes             -3.7319658599
    ## 
    ## Std. Errors:
    ##             (Intercept) fuel_used_for_cooking_percent_wood_dung
    ## prediabetes    1.514304                                6.789168
    ## diabetes       3.925159                               17.689565
    ##             percent_public_source percent_private_toilet percent_employed
    ## prediabetes              1.232123            0.005923699         3.155483
    ## diabetes                 4.772094            0.007290674         4.201607
    ##             percent_without_hs_education percent_caste
    ## prediabetes                     1.703190     0.9607122
    ## diabetes                        2.942061     0.4092454
    ##             percent_marital_status
    ## prediabetes             0.01365773
    ## diabetes                3.88993918
    ## 
    ## Residual Deviance: 231.8053 
    ## AIC: 263.8053
