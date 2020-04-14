Linear Regression
================

Loading in the data:

Model 1: Fasting Blood Glucose

Crude:

    ## 
    ## Call:
    ## lm(formula = fbg ~ fuel_used_for_cooking_percent_wood_dung + 
    ##     percent_public_source + percent_private_toilet + percent_employed + 
    ##     percent_without_hs_education + percent_caste, data = total)
    ## 
    ## Residuals:
    ##     Min      1Q  Median      3Q     Max 
    ## -18.986  -7.429  -0.899   4.378  45.356 
    ## 
    ## Coefficients:
    ##                                          Estimate Std. Error t value
    ## (Intercept)                             122.80107    6.36472  19.294
    ## fuel_used_for_cooking_percent_wood_dung   9.48930   21.22527   0.447
    ## percent_public_source                    -0.09995    0.09406  -1.063
    ## percent_private_toilet                    0.02323    0.02400   0.968
    ## percent_employed                        -10.24753   12.94866  -0.791
    ## percent_without_hs_education            -19.77875    6.15917  -3.211
    ## percent_caste                            -0.06538    0.10860  -0.602
    ##                                         Pr(>|t|)    
    ## (Intercept)                              < 2e-16 ***
    ## fuel_used_for_cooking_percent_wood_dung  0.65558    
    ## percent_public_source                    0.29001    
    ## percent_private_toilet                   0.33487    
    ## percent_employed                         0.43019    
    ## percent_without_hs_education             0.00167 ** 
    ## percent_caste                            0.54823    
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 10.69 on 127 degrees of freedom
    ## Multiple R-squared:  0.1805, Adjusted R-squared:  0.1418 
    ## F-statistic: 4.662 on 6 and 127 DF,  p-value: 0.0002564

    ##                                             Estimate  Std. Error
    ## (Intercept)                             122.80107156  6.36471501
    ## fuel_used_for_cooking_percent_wood_dung   9.48929523 21.22527243
    ## percent_public_source                    -0.09994546  0.09406388
    ## percent_private_toilet                    0.02323417  0.02400153
    ## percent_employed                        -10.24753383 12.94866078
    ## percent_without_hs_education            -19.77874872  6.15917045
    ## percent_caste                            -0.06537879  0.10859781
    ##                                            t value     Pr(>|t|)
    ## (Intercept)                             19.2940409 1.444002e-39
    ## fuel_used_for_cooking_percent_wood_dung  0.4470753 6.555822e-01
    ## percent_public_source                   -1.0625276 2.900125e-01
    ## percent_private_toilet                   0.9680286 3.348700e-01
    ## percent_employed                        -0.7913972 4.301878e-01
    ## percent_without_hs_education            -3.2112683 1.674270e-03
    ## percent_caste                           -0.6020267 5.482296e-01

    ##                             (Intercept) 
    ##                            122.80107156 
    ## fuel_used_for_cooking_percent_wood_dung 
    ##                              9.48929523 
    ##                   percent_public_source 
    ##                             -0.09994546 
    ##                  percent_private_toilet 
    ##                              0.02323417 
    ##                        percent_employed 
    ##                            -10.24753383 
    ##            percent_without_hs_education 
    ##                            -19.77874872 
    ##                           percent_caste 
    ##                             -0.06537879

    ##         1         2         3         4         5         6         7 
    ## 119.01091 116.34154 112.42308 116.46722 114.10933 111.92198 109.14371 
    ##         8         9        10        11        12        13        14 
    ## 105.60747 109.17193 111.52316 109.22524 113.92924 112.29963 114.13588 
    ##        15        16        17        18        19        20        21 
    ## 119.25394 105.99402 114.30314 112.12651 108.03613 114.05193 103.26591 
    ##        22        23        24        25        26        27        28 
    ## 114.17625 109.63894 111.90210 112.46848 110.84780 116.02348 115.02830 
    ##        29        30        31        32        33        34        35 
    ## 105.74324 112.96933 114.20019 115.56389 118.49233 113.18215 114.45635 
    ##        36        37        38        39        40        41        42 
    ## 119.75424 118.02028 117.20549 116.57538 107.50254 122.01719 120.36618 
    ##        43        44        45        46        47        48        49 
    ## 120.57003 118.41260 118.99399 116.35077 118.40242 120.24471 120.53835 
    ##        50        51        52        53        54        55        56 
    ## 118.07903 119.38056 119.50487 120.90492 115.76585 117.30686 113.76497 
    ##        57        58        59        60        61        62        63 
    ## 115.91719 113.69292 109.49499 112.96153 104.42091 113.48919 118.55063 
    ##        64        65        66        67        68        69        70 
    ## 115.46191 112.72777 109.90307 109.70929 111.20991 111.08368 107.68395 
    ##        71        72        73        74        75        76        77 
    ## 119.53492 117.39695 118.79683 103.46317 116.51320 114.00253 107.70584 
    ##        78        79        80        81        82        83        84 
    ## 107.71165 116.65631 118.57285 121.39310 121.28166 106.65912  94.92825 
    ##        85        86        87        88        89        90        91 
    ## 113.53811 113.12021 108.78073 112.01467 111.41077 110.69613 118.33890 
    ##        92        93        94        95        96        97        98 
    ## 119.86197 112.55030 108.83245 114.33685 116.09813 119.53880 116.43208 
    ##        99       100       101       102       103       104       105 
    ## 106.78305 120.44842 104.20343 120.47416 118.09681 115.82543 118.99113 
    ##       106       107       108       109       110       111       112 
    ## 120.68959 114.84628 118.78228 114.65659 117.95440 112.49602 114.17283 
    ##       113       114       115       116       117       118       119 
    ## 111.21986 106.94510 115.90883 116.09081 117.18735 119.04566 119.13617 
    ##       120       121       122       123       124       125       126 
    ## 117.40003 114.85037 118.73793 112.85274 111.34877 120.12747 112.72799 
    ##       127       128       129       130       131       132       133 
    ## 109.14673 112.47638 116.83451 115.55059 115.55603 114.83908 117.38579 
    ##       134 
    ##  98.54199

    ## # A tibble: 1 x 11
    ##   r.squared adj.r.squared sigma statistic p.value    df logLik   AIC   BIC
    ##       <dbl>         <dbl> <dbl>     <dbl>   <dbl> <int>  <dbl> <dbl> <dbl>
    ## 1     0.181         0.142  10.7      4.66 2.56e-4     7  -504. 1024. 1047.
    ## # … with 2 more variables: deviance <dbl>, df.residual <int>

| term                                          | estimate | p.value |
| :-------------------------------------------- | -------: | ------: |
| (Intercept)                                   |  122.801 |   0.000 |
| fuel\_used\_for\_cooking\_percent\_wood\_dung |    9.489 |   0.656 |
| percent\_public\_source                       |  \-0.100 |   0.290 |
| percent\_private\_toilet                      |    0.023 |   0.335 |
| percent\_employed                             | \-10.248 |   0.430 |
| percent\_without\_hs\_education               | \-19.779 |   0.002 |
| percent\_caste                                |  \-0.065 |   0.548 |

Age as a confounder:

    ## 
    ## Call:
    ## lm(formula = fbg ~ fuel_used_for_cooking_percent_wood_dung + 
    ##     percent_public_source + percent_private_toilet + percent_employed + 
    ##     percent_without_hs_education + percent_caste + median_age, 
    ##     data = total)
    ## 
    ## Residuals:
    ##     Min      1Q  Median      3Q     Max 
    ## -19.564  -6.450  -1.840   4.054  39.237 
    ## 
    ## Coefficients:
    ##                                          Estimate Std. Error t value
    ## (Intercept)                             64.394217  14.272593   4.512
    ## fuel_used_for_cooking_percent_wood_dung  1.570375  19.857818   0.079
    ## percent_public_source                   -0.105662   0.087667  -1.205
    ## percent_private_toilet                  -0.005991   0.023291  -0.257
    ## percent_employed                        13.331542  13.155706   1.013
    ## percent_without_hs_education            -4.754544   6.640426  -0.716
    ## percent_caste                           -0.045451   0.101298  -0.449
    ## median_age                               0.998880   0.222016   4.499
    ##                                         Pr(>|t|)    
    ## (Intercept)                             1.45e-05 ***
    ## fuel_used_for_cooking_percent_wood_dung    0.937    
    ## percent_public_source                      0.230    
    ## percent_private_toilet                     0.797    
    ## percent_employed                           0.313    
    ## percent_without_hs_education               0.475    
    ## percent_caste                              0.654    
    ## median_age                              1.53e-05 ***
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 9.965 on 126 degrees of freedom
    ## Multiple R-squared:  0.2939, Adjusted R-squared:  0.2547 
    ## F-statistic: 7.493 on 7 and 126 DF,  p-value: 1.568e-07

    ##                                             Estimate  Std. Error
    ## (Intercept)                             64.394216821 14.27259340
    ## fuel_used_for_cooking_percent_wood_dung  1.570374806 19.85781765
    ## percent_public_source                   -0.105661602  0.08766658
    ## percent_private_toilet                  -0.005991133  0.02329099
    ## percent_employed                        13.331542399 13.15570592
    ## percent_without_hs_education            -4.754543960  6.64042590
    ## percent_caste                           -0.045450956  0.10129831
    ## median_age                               0.998879615  0.22201621
    ##                                             t value     Pr(>|t|)
    ## (Intercept)                              4.51173904 1.454875e-05
    ## fuel_used_for_cooking_percent_wood_dung  0.07908094 9.370937e-01
    ## percent_public_source                   -1.20526667 2.303591e-01
    ## percent_private_toilet                  -0.25722961 7.974211e-01
    ## percent_employed                         1.01336580 3.128275e-01
    ## percent_without_hs_education            -0.71599985 4.753163e-01
    ## percent_caste                           -0.44868425 6.544301e-01
    ## median_age                               4.49912921 1.531179e-05

    ##                             (Intercept) 
    ##                            64.394216821 
    ## fuel_used_for_cooking_percent_wood_dung 
    ##                             1.570374806 
    ##                   percent_public_source 
    ##                            -0.105661602 
    ##                  percent_private_toilet 
    ##                            -0.005991133 
    ##                        percent_employed 
    ##                            13.331542399 
    ##            percent_without_hs_education 
    ##                            -4.754543960 
    ##                           percent_caste 
    ##                            -0.045450956 
    ##                              median_age 
    ##                             0.998879615

    ##         1         2         3         4         5         6         7 
    ## 113.87700 114.81052 114.14995 119.58058 120.83166 108.14677 115.26261 
    ##         8         9        10        11        12        13        14 
    ## 105.88606 115.34107 106.80357 111.57622 107.85608 109.93019 106.39933 
    ##        15        16        17        18        19        20        21 
    ## 120.68158 109.88700 114.07737 108.73789 112.60835 110.50043 106.80856 
    ##        22        23        24        25        26        27        28 
    ## 112.95074 109.32761 114.31402 109.89182 110.86752 113.71121 114.92129 
    ##        29        30        31        32        33        34        35 
    ## 108.06548 112.33163 107.42668 113.19762 113.86629 114.29454 113.98939 
    ##        36        37        38        39        40        41        42 
    ## 115.72678 120.00160 119.73055 115.81883 109.64083 126.58587 120.37824 
    ##        43        44        45        46        47        48        49 
    ## 117.92542 117.93213 121.10101 117.56192 122.06989 119.94474 121.59461 
    ##        50        51        52        53        54        55        56 
    ## 121.15795 128.35646 122.59658 127.16082 119.05614 118.40964 106.02329 
    ##        57        58        59        60        61        62        63 
    ## 107.20896 109.54799  99.85869 107.64622 108.32347 112.56761 125.96453 
    ##        64        65        66        67        68        69        70 
    ## 114.83554 107.93204 110.11757 108.47370 108.64505 110.03122 109.53172 
    ##        71        72        73        74        75        76        77 
    ## 119.71683 120.46889 118.32143 105.04402 115.25285 117.34323 110.04601 
    ##        78        79        80        81        82        83        84 
    ## 111.25117 126.05495 124.71844 123.60701 117.15685 105.41964  95.76251 
    ##        85        86        87        88        89        90        91 
    ## 109.11096 110.90266 111.29701 113.13401 108.93029 111.02691 117.40929 
    ##        92        93        94        95        96        97        98 
    ## 114.26167 109.22027 112.08134 116.81062 111.57769 116.36547 118.75566 
    ##        99       100       101       102       103       104       105 
    ## 111.00033 123.16541 103.99449 119.99624 120.71490 118.15229 124.41385 
    ##       106       107       108       109       110       111       112 
    ## 117.71983 107.89428 118.77064 111.77709 123.56204 110.38666 113.50826 
    ##       113       114       115       116       117       118       119 
    ## 103.95827 107.76548 114.13725 118.88442 119.56606 126.86423 122.33485 
    ##       120       121       122       123       124       125       126 
    ## 125.47188 110.54625 111.34723 107.84065 106.20772 119.01505 115.48664 
    ##       127       128       129       130       131       132       133 
    ## 109.40759 114.81364 120.56042 113.98206 117.73075 113.07159 110.31829 
    ##       134 
    ##  97.71944

    ## # A tibble: 1 x 11
    ##   r.squared adj.r.squared sigma statistic p.value    df logLik   AIC   BIC
    ##       <dbl>         <dbl> <dbl>     <dbl>   <dbl> <int>  <dbl> <dbl> <dbl>
    ## 1     0.294         0.255  9.96      7.49 1.57e-7     8  -494. 1006. 1032.
    ## # … with 2 more variables: deviance <dbl>, df.residual <int>

| term                                          | estimate | p.value |
| :-------------------------------------------- | -------: | ------: |
| (Intercept)                                   |   64.394 |   0.000 |
| fuel\_used\_for\_cooking\_percent\_wood\_dung |    1.570 |   0.937 |
| percent\_public\_source                       |  \-0.106 |   0.230 |
| percent\_private\_toilet                      |  \-0.006 |   0.797 |
| percent\_employed                             |   13.332 |   0.313 |
| percent\_without\_hs\_education               |  \-4.755 |   0.475 |
| percent\_caste                                |  \-0.045 |   0.654 |
| median\_age                                   |    0.999 |   0.000 |

Gender as a confounder:

    ## 
    ## Call:
    ## lm(formula = fbg ~ fuel_used_for_cooking_percent_wood_dung + 
    ##     percent_public_source + percent_private_toilet + percent_employed + 
    ##     percent_without_hs_education + percent_caste + percent_female, 
    ##     data = total)
    ## 
    ## Residuals:
    ##     Min      1Q  Median      3Q     Max 
    ## -18.986  -7.429  -0.899   4.378  45.356 
    ## 
    ## Coefficients:
    ##                                           Estimate Std. Error t value
    ## (Intercept)                             122.798935   6.526982  18.814
    ## fuel_used_for_cooking_percent_wood_dung   9.488922  21.310597   0.445
    ## percent_public_source                    -0.099947   0.094439  -1.058
    ## percent_private_toilet                    0.023238   0.024222   0.959
    ## percent_employed                        -10.248186  13.006282  -0.788
    ## percent_without_hs_education            -19.777409   6.239550  -3.170
    ## percent_caste                            -0.065376   0.109041  -0.600
    ## percent_female                            0.002914   1.814096   0.002
    ##                                         Pr(>|t|)    
    ## (Intercept)                              < 2e-16 ***
    ## fuel_used_for_cooking_percent_wood_dung  0.65689    
    ## percent_public_source                    0.29194    
    ## percent_private_toilet                   0.33919    
    ## percent_employed                         0.43221    
    ## percent_without_hs_education             0.00192 ** 
    ## percent_caste                            0.54988    
    ## percent_female                           0.99872    
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 10.74 on 126 degrees of freedom
    ## Multiple R-squared:  0.1805, Adjusted R-squared:  0.135 
    ## F-statistic: 3.965 on 7 and 126 DF,  p-value: 0.0006013

    ##                                              Estimate  Std. Error
    ## (Intercept)                             122.798934539  6.52698234
    ## fuel_used_for_cooking_percent_wood_dung   9.488922439 21.31059712
    ## percent_public_source                    -0.099946682  0.09443947
    ## percent_private_toilet                    0.023238117  0.02422151
    ## percent_employed                        -10.248185935 13.00628159
    ## percent_without_hs_education            -19.777409261  6.23954968
    ## percent_caste                            -0.065376089  0.10904086
    ## percent_female                            0.002913621  1.81409630
    ##                                              t value     Pr(>|t|)
    ## (Intercept)                             18.814044247 2.102680e-38
    ## fuel_used_for_cooking_percent_wood_dung  0.445267788 6.568903e-01
    ## percent_public_source                   -1.058314694 2.919367e-01
    ## percent_private_toilet                   0.959399995 3.391947e-01
    ## percent_employed                        -0.787941262 4.322109e-01
    ## percent_without_hs_education            -3.169685360 1.915907e-03
    ## percent_caste                           -0.599555870 5.498789e-01
    ## percent_female                           0.001606101 9.987211e-01

    ##                             (Intercept) 
    ##                           122.798934539 
    ## fuel_used_for_cooking_percent_wood_dung 
    ##                             9.488922439 
    ##                   percent_public_source 
    ##                            -0.099946682 
    ##                  percent_private_toilet 
    ##                             0.023238117 
    ##                        percent_employed 
    ##                           -10.248185935 
    ##            percent_without_hs_education 
    ##                           -19.777409261 
    ##                           percent_caste 
    ##                            -0.065376089 
    ##                          percent_female 
    ##                             0.002913621

    ##         1         2         3         4         5         6         7 
    ## 119.01090 116.34101 112.42314 116.46672 114.10928 111.92180 109.14367 
    ##         8         9        10        11        12        13        14 
    ## 105.60751 109.17195 111.52316 109.22507 113.92903 112.29946 114.13564 
    ##        15        16        17        18        19        20        21 
    ## 119.25380 105.99404 114.30294 112.12624 108.03637 114.05180 103.26615 
    ##        22        23        24        25        26        27        28 
    ## 114.17590 109.63902 111.90205 112.46849 110.84775 116.02316 115.02804 
    ##        29        30        31        32        33        34        35 
    ## 105.74359 112.96908 114.19991 115.56367 118.49228 113.18208 114.45597 
    ##        36        37        38        39        40        41        42 
    ## 119.75432 118.01999 117.22249 116.57504 107.50245 122.01724 120.36625 
    ##        43        44        45        46        47        48        49 
    ## 120.56999 118.41244 118.99415 116.35025 118.40241 120.24466 120.53818 
    ##        50        51        52        53        54        55        56 
    ## 118.07859 119.38056 119.50467 120.90477 115.76555 117.30679 113.76476 
    ##        57        58        59        60        61        62        63 
    ## 115.91689 113.69275 109.49518 112.96134 104.42115 113.48891 118.55016 
    ##        64        65        66        67        68        69        70 
    ## 115.46163 112.72772 109.90307 109.70933 111.20982 111.08348 107.68388 
    ##        71        72        73        74        75        76        77 
    ## 119.53471 117.39639 118.79638 103.46359 116.51270 114.00236 107.70585 
    ##        78        79        80        81        82        83        84 
    ## 107.71173 116.65586 118.57277 121.39310 121.28162 106.65914  94.92830 
    ##        85        86        87        88        89        90        91 
    ## 113.53778 113.11987 108.78059 112.01442 111.41059 110.69600 118.33848 
    ##        92        93        94        95        96        97        98 
    ## 119.86191 112.55013 108.83254 114.33654 116.09758 119.53884 116.43174 
    ##        99       100       101       102       103       104       105 
    ## 106.78323 120.44835 104.20374 120.47418 118.09686 115.82567 118.99103 
    ##       106       107       108       109       110       111       112 
    ## 120.68954 114.84609 118.78240 114.65641 117.95397 112.49605 114.17291 
    ##       113       114       115       116       117       118       119 
    ## 111.22041 106.94527 115.90855 116.09063 117.18694 119.04523 119.13622 
    ##       120       121       122       123       124       125       126 
    ## 117.39975 114.85006 118.73793 112.85242 111.34859 120.12743 112.72788 
    ##       127       128       129       130       131       132       133 
    ## 109.14681 112.47616 116.83401 115.55001 115.55557 114.83874 117.38595 
    ##       134 
    ##  98.54194

    ## # A tibble: 1 x 11
    ##   r.squared adj.r.squared sigma statistic p.value    df logLik   AIC   BIC
    ##       <dbl>         <dbl> <dbl>     <dbl>   <dbl> <int>  <dbl> <dbl> <dbl>
    ## 1     0.181         0.135  10.7      3.96 6.01e-4     8  -504. 1026. 1052.
    ## # … with 2 more variables: deviance <dbl>, df.residual <int>

| term                                          | estimate | p.value |
| :-------------------------------------------- | -------: | ------: |
| (Intercept)                                   |  122.799 |   0.000 |
| fuel\_used\_for\_cooking\_percent\_wood\_dung |    9.489 |   0.657 |
| percent\_public\_source                       |  \-0.100 |   0.292 |
| percent\_private\_toilet                      |    0.023 |   0.339 |
| percent\_employed                             | \-10.248 |   0.432 |
| percent\_without\_hs\_education               | \-19.777 |   0.002 |
| percent\_caste                                |  \-0.065 |   0.550 |
| percent\_female                               |    0.003 |   0.999 |

Marital status as a confounder:

    ## 
    ## Call:
    ## lm(formula = fbg ~ fuel_used_for_cooking_percent_wood_dung + 
    ##     percent_public_source + percent_private_toilet + percent_employed + 
    ##     percent_without_hs_education + percent_caste + percent_marital_status, 
    ##     data = total)
    ## 
    ## Residuals:
    ##     Min      1Q  Median      3Q     Max 
    ## -19.036  -7.296  -0.830   4.757  45.216 
    ## 
    ## Coefficients:
    ##                                          Estimate Std. Error t value
    ## (Intercept)                             122.62145    6.39343  19.179
    ## fuel_used_for_cooking_percent_wood_dung   9.54670   21.28819   0.448
    ## percent_public_source                    -0.09870    0.09437  -1.046
    ## percent_private_toilet                    0.02260    0.02410   0.938
    ## percent_employed                         -9.36197   13.10517  -0.714
    ## percent_without_hs_education            -20.42571    6.30929  -3.237
    ## percent_caste                            -0.06682    0.10896  -0.613
    ## percent_marital_status                   -0.03270    0.06488  -0.504
    ##                                         Pr(>|t|)    
    ## (Intercept)                              < 2e-16 ***
    ## fuel_used_for_cooking_percent_wood_dung  0.65460    
    ## percent_public_source                    0.29765    
    ## percent_private_toilet                   0.35019    
    ## percent_employed                         0.47632    
    ## percent_without_hs_education             0.00154 ** 
    ## percent_caste                            0.54083    
    ## percent_marital_status                   0.61513    
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 10.72 on 126 degrees of freedom
    ## Multiple R-squared:  0.1822, Adjusted R-squared:  0.1367 
    ## F-statistic: 4.009 on 7 and 126 DF,  p-value: 0.0005407

    ##                                             Estimate  Std. Error
    ## (Intercept)                             122.62145038  6.39343027
    ## fuel_used_for_cooking_percent_wood_dung   9.54670133 21.28818891
    ## percent_public_source                    -0.09869746  0.09437384
    ## percent_private_toilet                    0.02260344  0.02410484
    ## percent_employed                         -9.36196705 13.10517282
    ## percent_without_hs_education            -20.42571136  6.30929207
    ## percent_caste                            -0.06681502  0.10895543
    ## percent_marital_status                   -0.03270142  0.06488129
    ##                                            t value     Pr(>|t|)
    ## (Intercept)                             19.1792895 3.473968e-39
    ## fuel_used_for_cooking_percent_wood_dung  0.4484506 6.545983e-01
    ## percent_public_source                   -1.0458138 2.976492e-01
    ## percent_private_toilet                   0.9377138 3.501855e-01
    ## percent_employed                        -0.7143719 4.763186e-01
    ## percent_without_hs_education            -3.2374015 1.541765e-03
    ## percent_caste                           -0.6132325 5.408280e-01
    ## percent_marital_status                  -0.5040193 6.151280e-01

    ##                             (Intercept) 
    ##                            122.62145038 
    ## fuel_used_for_cooking_percent_wood_dung 
    ##                              9.54670133 
    ##                   percent_public_source 
    ##                             -0.09869746 
    ##                  percent_private_toilet 
    ##                              0.02260344 
    ##                        percent_employed 
    ##                             -9.36196705 
    ##            percent_without_hs_education 
    ##                            -20.42571136 
    ##                           percent_caste 
    ##                             -0.06681502 
    ##                  percent_marital_status 
    ##                             -0.03270142

    ##         1         2         3         4         5         6         7 
    ## 119.20212 116.63193 112.41039 113.56146 114.08313 111.98892 109.28407 
    ##         8         9        10        11        12        13        14 
    ## 105.60291 109.02956 111.46685 109.38528 113.99757 112.34788 114.24293 
    ##        15        16        17        18        19        20        21 
    ## 119.34750 106.13169 114.37871 112.25997 107.86009 114.10208 103.06454 
    ##        22        23        24        25        26        27        28 
    ## 114.35541 109.59891 111.90224 112.39793 110.88507 116.09213 115.12646 
    ##        29        30        31        32        33        34        35 
    ## 105.52709 113.06721 114.32008 115.55428 118.73307 113.20213 114.62441 
    ##        36        37        38        39        40        41        42 
    ## 119.76464 118.04030 117.42325 116.67691 107.52811 122.01705 120.42672 
    ##        43        44        45        46        47        48        49 
    ## 120.68943 118.59505 119.00343 116.62340 118.51068 120.39413 120.66253 
    ##        50        51        52        53        54        55        56 
    ## 118.24689 119.48407 116.47767 120.99609 115.85505 117.46950 113.84090 
    ##        57        58        59        60        61        62        63 
    ## 116.12563 113.81343 109.34499 113.05865 104.28401 113.59949 115.46932 
    ##        64        65        66        67        68        69        70 
    ## 115.51014 112.75801 109.85914 109.66774 111.23427 111.18239 107.79313 
    ##        71        72        73        74        75        76        77 
    ## 119.74554 117.65603 118.93766 103.28698 116.80822 114.02202 107.67708 
    ##        78        79        80        81        82        83        84 
    ## 107.68274 116.85730 118.77117 121.44864 121.34244 106.59570  94.91804 
    ##        85        86        87        88        89        90        91 
    ## 113.67700 113.29641 108.93285 112.12582 111.51897 110.74485 118.44946 
    ##        92        93        94        95        96        97        98 
    ## 119.97067 112.60311 108.78705 114.43786 116.34208 119.57067 116.57030 
    ##        99       100       101       102       103       104       105 
    ## 106.73175 120.57871 104.06404 120.52128 118.19137 115.75281 119.16846 
    ##       106       107       108       109       110       111       112 
    ## 120.80413 114.88532 118.82025 114.71046 118.16788 112.41553 114.18785 
    ##       113       114       115       116       117       118       119 
    ## 111.05989 106.79873 115.99735 116.13606 117.33719 119.16074 119.20206 
    ##       120       121       122       123       124       125       126 
    ## 117.50904 115.00517 118.82682 112.99228 111.42375 120.24367 112.66448 
    ##       127       128       129       130       131       132       133 
    ## 109.05023 112.55210 117.00528 115.83997 115.77098 114.96209 117.43567 
    ##       134 
    ##  98.55786

    ## # A tibble: 1 x 11
    ##   r.squared adj.r.squared sigma statistic p.value    df logLik   AIC   BIC
    ##       <dbl>         <dbl> <dbl>     <dbl>   <dbl> <int>  <dbl> <dbl> <dbl>
    ## 1     0.182         0.137  10.7      4.01 5.41e-4     8  -504. 1026. 1052.
    ## # … with 2 more variables: deviance <dbl>, df.residual <int>

| term                                          | estimate | p.value |
| :-------------------------------------------- | -------: | ------: |
| (Intercept)                                   |  122.621 |   0.000 |
| fuel\_used\_for\_cooking\_percent\_wood\_dung |    9.547 |   0.655 |
| percent\_public\_source                       |  \-0.099 |   0.298 |
| percent\_private\_toilet                      |    0.023 |   0.350 |
| percent\_employed                             |  \-9.362 |   0.476 |
| percent\_without\_hs\_education               | \-20.426 |   0.002 |
| percent\_caste                                |  \-0.067 |   0.541 |
| percent\_marital\_status                      |  \-0.033 |   0.615 |

Full model:

    ## 
    ## Call:
    ## lm(formula = fbg ~ fuel_used_for_cooking_percent_wood_dung + 
    ##     percent_public_source + percent_private_toilet + percent_employed + 
    ##     percent_without_hs_education + percent_caste + median_age + 
    ##     percent_female + percent_marital_status, data = total)
    ## 
    ## Residuals:
    ##     Min      1Q  Median      3Q     Max 
    ## -20.422  -6.497  -1.782   3.994  38.488 
    ## 
    ## Coefficients:
    ##                                         Estimate Std. Error t value
    ## (Intercept)                             60.73319   14.53770   4.178
    ## fuel_used_for_cooking_percent_wood_dung  1.30336   19.85855   0.066
    ## percent_public_source                   -0.10252    0.08769  -1.169
    ## percent_private_toilet                  -0.01014    0.02357  -0.430
    ## percent_employed                        17.21384   13.43869   1.281
    ## percent_without_hs_education            -5.77267    6.69634  -0.862
    ## percent_caste                           -0.04848    0.10132  -0.479
    ## median_age                               1.05998    0.22620   4.686
    ## percent_female                          -0.52226    1.68840  -0.309
    ## percent_marital_status                  -0.08578    0.06138  -1.397
    ##                                         Pr(>|t|)    
    ## (Intercept)                             5.51e-05 ***
    ## fuel_used_for_cooking_percent_wood_dung    0.948    
    ## percent_public_source                      0.245    
    ## percent_private_toilet                     0.668    
    ## percent_employed                           0.203    
    ## percent_without_hs_education               0.390    
    ## percent_caste                              0.633    
    ## median_age                              7.21e-06 ***
    ## percent_female                             0.758    
    ## percent_marital_status                     0.165    
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 9.964 on 124 degrees of freedom
    ## Multiple R-squared:  0.3052, Adjusted R-squared:  0.2548 
    ## F-statistic: 6.052 on 9 and 124 DF,  p-value: 5.123e-07

    ##                                            Estimate  Std. Error
    ## (Intercept)                             60.73318885 14.53770472
    ## fuel_used_for_cooking_percent_wood_dung  1.30336257 19.85855155
    ## percent_public_source                   -0.10251844  0.08769163
    ## percent_private_toilet                  -0.01014074  0.02357330
    ## percent_employed                        17.21383503 13.43869096
    ## percent_without_hs_education            -5.77267344  6.69634072
    ## percent_caste                           -0.04848333  0.10132171
    ## median_age                               1.05998374  0.22620110
    ## percent_female                          -0.52225928  1.68839899
    ## percent_marital_status                  -0.08578202  0.06138359
    ##                                             t value     Pr(>|t|)
    ## (Intercept)                              4.17763258 5.510873e-05
    ## fuel_used_for_cooking_percent_wood_dung  0.06563231 9.477763e-01
    ## percent_public_source                   -1.16907905 2.446143e-01
    ## percent_private_toilet                  -0.43017894 6.678122e-01
    ## percent_employed                         1.28091606 2.026137e-01
    ## percent_without_hs_education            -0.86206388 3.903164e-01
    ## percent_caste                           -0.47850885 6.331307e-01
    ## median_age                               4.68602370 7.208566e-06
    ## percent_female                          -0.30932220 7.575956e-01
    ## percent_marital_status                  -1.39747472 1.647662e-01

    ##                             (Intercept) 
    ##                             60.73318885 
    ## fuel_used_for_cooking_percent_wood_dung 
    ##                              1.30336257 
    ##                   percent_public_source 
    ##                             -0.10251844 
    ##                  percent_private_toilet 
    ##                             -0.01014074 
    ##                        percent_employed 
    ##                             17.21383503 
    ##            percent_without_hs_education 
    ##                             -5.77267344 
    ##                           percent_caste 
    ##                             -0.04848333 
    ##                              median_age 
    ##                              1.05998374 
    ##                          percent_female 
    ##                             -0.52225928 
    ##                  percent_marital_status 
    ##                             -0.08578202

    ##         1         2         3         4         5         6         7 
    ## 114.06678 115.57422 114.21207 112.23736 121.18293 108.12383 116.01235 
    ##         8         9        10        11        12        13        14 
    ## 105.88505 115.34178 106.36708 112.17025 107.70258 109.94195 106.25038 
    ##        15        16        17        18        19        20        21 
    ## 121.03874 110.48301 114.29795 108.92865 112.38307 110.43857 106.45429 
    ##        22        23        24        25        26        27        28 
    ## 113.40808 109.19063 114.47057 109.54737 110.97657 113.80738 115.21768 
    ##        29        30        31        32        33        34        35 
    ## 107.57748 112.59416 107.37749 113.06674 114.22363 114.42778 114.46944 
    ##        36        37        38        39        40        41        42 
    ## 115.49343 120.22752 117.40932 116.09951 109.85443 126.85755 120.52554 
    ##        43        44        45        46        47        48        49 
    ## 118.08447 118.40984 121.22764 118.44355 122.57948 120.32727 122.01385 
    ##        50        51        52        53        54        55        56 
    ## 121.86478 129.17694 114.88061 127.80889 119.54515 118.91516 105.78771 
    ##        57        58        59        60        61        62        63 
    ## 107.27787 109.64115  98.84106 107.60849 108.16074 112.85151 118.41822 
    ##        64        65        66        67        68        69        70 
    ## 114.97273 107.72768 110.01550 108.28310 108.56672 110.26113 109.94305 
    ##        71        72        73        74        75        76        77 
    ## 120.31906 121.43708 118.74192 104.60401 116.04038 117.62860 110.11143 
    ##        78        79        80        81        82        83        84 
    ## 111.37681 127.23714 125.62820 123.88782 117.07195 105.17462  95.77652 
    ##        85        86        87        88        89        90        91 
    ## 109.26380 111.28940 111.87516 113.53865 109.09485 111.19794 117.71855 
    ##        92        93        94        95        96        97        98 
    ## 114.21384 109.18676 112.14453 117.28343 112.03968 116.24783 119.32084 
    ##        99       100       101       102       103       104       105 
    ## 111.09238 123.68682 103.55908 120.08739 121.11363 118.06051 125.22916 
    ##       106       107       108       109       110       111       112 
    ## 117.84710 107.60455 118.84793 111.77466 124.54342 110.04097 113.49263 
    ##       113       114       115       116       117       118       119 
    ## 102.99557 107.40114 114.31122 119.20767 120.17842 127.72165 122.69408 
    ##       120       121       122       123       124       125       126 
    ## 126.30144 110.74446 111.12721 107.95679 106.12225 119.25870 115.50829 
    ##       127       128       129       130       131       132       133 
    ## 109.15564 115.19371 121.32534 114.74978 118.51131 113.34765 109.98720 
    ##       134 
    ##  97.72000

    ## # A tibble: 1 x 11
    ##   r.squared adj.r.squared sigma statistic p.value    df logLik   AIC   BIC
    ##       <dbl>         <dbl> <dbl>     <dbl>   <dbl> <int>  <dbl> <dbl> <dbl>
    ## 1     0.305         0.255  9.96      6.05 5.12e-7    10  -493. 1008. 1040.
    ## # … with 2 more variables: deviance <dbl>, df.residual <int>

| term                                          | estimate | p.value |
| :-------------------------------------------- | -------: | ------: |
| (Intercept)                                   |   60.733 |   0.000 |
| fuel\_used\_for\_cooking\_percent\_wood\_dung |    1.303 |   0.948 |
| percent\_public\_source                       |  \-0.103 |   0.245 |
| percent\_private\_toilet                      |  \-0.010 |   0.668 |
| percent\_employed                             |   17.214 |   0.203 |
| percent\_without\_hs\_education               |  \-5.773 |   0.390 |
| percent\_caste                                |  \-0.048 |   0.633 |
| median\_age                                   |    1.060 |   0.000 |
| percent\_female                               |  \-0.522 |   0.758 |
| percent\_marital\_status                      |  \-0.086 |   0.165 |

Model 2: BMI

Crude:

    ## 
    ## Call:
    ## lm(formula = bmi ~ fuel_used_for_cooking_percent_wood_dung + 
    ##     percent_public_source + percent_private_toilet + percent_employed + 
    ##     percent_without_hs_education + percent_caste, data = total)
    ## 
    ## Residuals:
    ##     Min      1Q  Median      3Q     Max 
    ## -3.2216 -0.9122  0.1088  0.9730  3.2519 
    ## 
    ## Coefficients:
    ##                                          Estimate Std. Error t value
    ## (Intercept)                             29.372806   0.871821  33.691
    ## fuel_used_for_cooking_percent_wood_dung  4.650046   2.907378   1.599
    ## percent_public_source                   -0.014349   0.012885  -1.114
    ## percent_private_toilet                   0.006950   0.003288   2.114
    ## percent_employed                        -5.941757   1.773671  -3.350
    ## percent_without_hs_education            -7.539730   0.843666  -8.937
    ## percent_caste                            0.006112   0.014875   0.411
    ##                                         Pr(>|t|)    
    ## (Intercept)                              < 2e-16 ***
    ## fuel_used_for_cooking_percent_wood_dung  0.11222    
    ## percent_public_source                    0.26752    
    ## percent_private_toilet                   0.03647 *  
    ## percent_employed                         0.00106 ** 
    ## percent_without_hs_education            3.94e-15 ***
    ## percent_caste                            0.68185    
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 1.465 on 127 degrees of freedom
    ## Multiple R-squared:  0.5966, Adjusted R-squared:  0.5775 
    ## F-statistic:  31.3 on 6 and 127 DF,  p-value: < 2.2e-16

    ##                                             Estimate  Std. Error
    ## (Intercept)                             29.372805864 0.871820727
    ## fuel_used_for_cooking_percent_wood_dung  4.650045739 2.907378010
    ## percent_public_source                   -0.014349199 0.012884605
    ## percent_private_toilet                   0.006950240 0.003287663
    ## percent_employed                        -5.941757261 1.773671068
    ## percent_without_hs_education            -7.539729813 0.843665813
    ## percent_caste                            0.006112094 0.014875423
    ##                                            t value     Pr(>|t|)
    ## (Intercept)                             33.6913369 3.497712e-65
    ## fuel_used_for_cooking_percent_wood_dung  1.5993950 1.122177e-01
    ## percent_public_source                   -1.1136701 2.675241e-01
    ## percent_private_toilet                   2.1140369 3.646757e-02
    ## percent_employed                        -3.3499770 1.064452e-03
    ## percent_without_hs_education            -8.9368678 3.941916e-15
    ## percent_caste                            0.4108854 6.818490e-01

    ##                             (Intercept) 
    ##                            29.372805864 
    ## fuel_used_for_cooking_percent_wood_dung 
    ##                             4.650045739 
    ##                   percent_public_source 
    ##                            -0.014349199 
    ##                  percent_private_toilet 
    ##                             0.006950240 
    ##                        percent_employed 
    ##                            -5.941757261 
    ##            percent_without_hs_education 
    ##                            -7.539729813 
    ##                           percent_caste 
    ##                             0.006112094

    ##        1        2        3        4        5        6        7        8 
    ## 26.65537 25.73986 24.56446 25.72230 25.31174 24.20289 22.87703 24.80557 
    ##        9       10       11       12       13       14       15       16 
    ## 23.33517 24.21287 22.86258 25.05526 24.40507 25.09293 26.91137 21.53903 
    ##       17       18       19       20       21       22       23       24 
    ## 25.22158 24.22949 22.91016 25.13495 20.90412 24.98058 23.37974 24.30462 
    ##       25       26       27       28       29       30       31       32 
    ## 24.66254 23.82928 25.96889 25.47413 21.98021 24.58968 25.08688 25.89220 
    ##       33       34       35       36       37       38       39       40 
    ## 26.33089 24.85747 25.13864 27.25716 26.90705 26.22021 26.13917 22.35177 
    ##       41       42       43       44       45       46       47       48 
    ## 28.26748 27.43980 27.42705 26.38750 26.92907 25.76182 26.52898 27.23842 
    ##       49       50       51       52       53       54       55       56 
    ## 27.40984 26.68728 26.93883 26.80945 27.62122 25.81083 25.94355 24.97843 
    ##       57       58       59       60       61       62       63       64 
    ## 25.69730 24.86552 23.49884 24.59443 21.40742 24.78364 26.90287 25.74809 
    ##       65       66       67       68       69       70       71       72 
    ## 24.59194 23.51432 23.43392 23.95520 23.76582 22.27641 26.82687 26.23397 
    ##       73       74       75       76       77       78       79       80 
    ## 27.04500 20.97455 25.78781 25.15691 22.51648 22.51790 26.01149 26.44865 
    ##       81       82       83       84       85       86       87       88 
    ## 27.90694 27.83967 22.13478 20.04340 24.76968 24.52464 22.69694 24.15274 
    ##       89       90       91       92       93       94       95       96 
    ## 23.88911 23.66849 26.90357 27.13995 24.49135 23.02033 25.16927 25.69894 
    ##       97       98       99      100      101      102      103      104 
    ## 27.12595 26.01695 22.17716 27.35730 21.19828 27.51008 26.40045 25.69912 
    ##      105      106      107      108      109      110      111      112 
    ## 26.64838 27.49875 25.48828 26.78769 25.40460 26.55673 24.68278 24.84081 
    ##      113      114      115      116      117      118      119      120 
    ## 23.84690 22.39042 25.87543 26.02150 26.32537 27.19013 26.89785 26.50012 
    ##      121      122      123      124      125      126      127      128 
    ## 25.31043 26.72489 24.60322 23.92412 27.26072 24.76091 23.27359 24.40096 
    ##      129      130      131      132      133      134 
    ## 26.13969 25.38809 25.50864 25.35756 26.16364 21.91294

    ## # A tibble: 1 x 11
    ##   r.squared adj.r.squared sigma statistic  p.value    df logLik   AIC   BIC
    ##       <dbl>         <dbl> <dbl>     <dbl>    <dbl> <int>  <dbl> <dbl> <dbl>
    ## 1     0.597         0.577  1.46      31.3 7.12e-23     7  -238.  491.  515.
    ## # … with 2 more variables: deviance <dbl>, df.residual <int>

| term                                          | estimate | p.value |
| :-------------------------------------------- | -------: | ------: |
| (Intercept)                                   |   29.373 |   0.000 |
| fuel\_used\_for\_cooking\_percent\_wood\_dung |    4.650 |   0.112 |
| percent\_public\_source                       |  \-0.014 |   0.268 |
| percent\_private\_toilet                      |    0.007 |   0.036 |
| percent\_employed                             |  \-5.942 |   0.001 |
| percent\_without\_hs\_education               |  \-7.540 |   0.000 |
| percent\_caste                                |    0.006 |   0.682 |

Age as a confounder:

    ## 
    ## Call:
    ## lm(formula = bmi ~ fuel_used_for_cooking_percent_wood_dung + 
    ##     percent_public_source + percent_private_toilet + percent_employed + 
    ##     percent_without_hs_education + percent_caste + median_age, 
    ##     data = total)
    ## 
    ## Residuals:
    ##     Min      1Q  Median      3Q     Max 
    ## -3.1828 -0.6472  0.0243  0.6988  3.3596 
    ## 
    ## Coefficients:
    ##                                          Estimate Std. Error t value
    ## (Intercept)                             19.330115   1.862418  10.379
    ## fuel_used_for_cooking_percent_wood_dung  3.288437   2.591229   1.269
    ## percent_public_source                   -0.015332   0.011440  -1.340
    ## percent_private_toilet                   0.001925   0.003039   0.633
    ## percent_employed                        -1.887484   1.716676  -1.099
    ## percent_without_hs_education            -4.956412   0.866503  -5.720
    ## percent_caste                            0.009539   0.013218   0.722
    ## median_age                               0.171751   0.028971   5.928
    ##                                         Pr(>|t|)    
    ## (Intercept)                              < 2e-16 ***
    ## fuel_used_for_cooking_percent_wood_dung    0.207    
    ## percent_public_source                      0.183    
    ## percent_private_toilet                     0.528    
    ## percent_employed                           0.274    
    ## percent_without_hs_education            7.33e-08 ***
    ## percent_caste                              0.472    
    ## median_age                              2.75e-08 ***
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 1.3 on 126 degrees of freedom
    ## Multiple R-squared:  0.6845, Adjusted R-squared:  0.667 
    ## F-statistic: 39.06 on 7 and 126 DF,  p-value: < 2.2e-16

    ##                                             Estimate  Std. Error
    ## (Intercept)                             19.330115186 1.862417726
    ## fuel_used_for_cooking_percent_wood_dung  3.288437265 2.591228557
    ## percent_public_source                   -0.015332053 0.011439532
    ## percent_private_toilet                   0.001925133 0.003039221
    ## percent_employed                        -1.887483664 1.716676096
    ## percent_without_hs_education            -4.956412465 0.866503134
    ## percent_caste                            0.009538560 0.013218324
    ## median_age                               0.171751056 0.028970693
    ##                                            t value     Pr(>|t|)
    ## (Intercept)                             10.3790438 1.288772e-18
    ## fuel_used_for_cooking_percent_wood_dung  1.2690649 2.067572e-01
    ## percent_public_source                   -1.3402693 1.825696e-01
    ## percent_private_toilet                   0.6334298 5.276011e-01
    ## percent_employed                        -1.0994990 2.736468e-01
    ## percent_without_hs_education            -5.7200168 7.334748e-08
    ## percent_caste                            0.7216164 4.718673e-01
    ## median_age                               5.9284414 2.745263e-08

    ##                             (Intercept) 
    ##                            19.330115186 
    ## fuel_used_for_cooking_percent_wood_dung 
    ##                             3.288437265 
    ##                   percent_public_source 
    ##                            -0.015332053 
    ##                  percent_private_toilet 
    ##                             0.001925133 
    ##                        percent_employed 
    ##                            -1.887483664 
    ##            percent_without_hs_education 
    ##                            -4.956412465 
    ##                           percent_caste 
    ##                             0.009538560 
    ##                              median_age 
    ##                             0.171751056

    ##        1        2        3        4        5        6        7        8 
    ## 25.77263 25.47661 24.86138 26.25762 26.46760 23.55377 23.92914 24.85347 
    ##        9       10       11       12       13       14       15       16 
    ## 24.39591 23.40136 23.26681 24.01101 23.99766 23.76268 27.15685 22.20840 
    ##       17       18       19       20       21       22       23       24 
    ## 25.18276 23.64684 23.69632 24.52429 21.51326 24.76986 23.32621 24.71934 
    ##       25       26       27       28       29       30       31       32 
    ## 24.21950 23.83267 25.57131 25.45573 22.37951 24.48003 23.92222 25.48534 
    ##       33       34       35       36       37       38       39       40 
    ## 25.53547 25.04874 25.05835 26.56466 27.24773 26.65438 26.00909 22.71944 
    ##       41       42       43       44       45       46       47       48 
    ## 29.05304 27.44188 26.97233 26.30489 27.29135 25.97007 27.15958 27.18684 
    ##       49       50       51       52       53       54       55       56 
    ## 27.59145 27.21668 28.48218 27.34105 28.69689 26.37657 26.13316 23.64730 
    ##       57       58       59       60       61       62       63       64 
    ## 24.19998 24.15283 21.84194 23.68049 22.07844 24.62518 28.17764 25.64039 
    ##       65       66       67       68       69       70       71       72 
    ## 23.76734 23.55120 23.22147 23.51419 23.58485 22.59412 26.85815 26.76217 
    ##       73       74       75       76       77       78       79       80 
    ## 26.96326 21.24637 25.57110 25.73132 22.91885 23.12650 27.62753 27.50534 
    ##       81       82       83       84       85       86       87       88 
    ## 28.28761 27.13044 21.92166 20.18684 24.00846 24.14334 23.12960 24.34520 
    ##       89       90       91       92       93       94       95       96 
    ## 23.46261 23.72537 26.74372 26.17701 23.91877 23.57896 25.59462 24.92168 
    ##       97       98       99      100      101      102      103      104 
    ## 26.58032 26.41648 22.90229 27.82447 21.16236 27.42790 26.85061 26.09921 
    ##      105      106      107      108      109      110      111      112 
    ## 27.58079 26.98812 24.29293 26.78569 24.90949 27.52092 24.32009 24.72654 
    ##      113      114      115      116      117      118      119      120 
    ## 22.59831 22.53148 25.57082 26.50185 26.73438 28.53448 27.44785 27.88802 
    ##      121      122      123      124      125      126      127      128 
    ## 24.57036 25.45410 23.74142 23.04015 27.06945 25.23524 23.31844 24.80284 
    ##      129      130      131      132      133      134 
    ## 26.78033 25.11839 25.88257 25.05365 24.94843 21.77151

    ## # A tibble: 1 x 11
    ##   r.squared adj.r.squared sigma statistic  p.value    df logLik   AIC   BIC
    ##       <dbl>         <dbl> <dbl>     <dbl>    <dbl> <int>  <dbl> <dbl> <dbl>
    ## 1     0.685         0.667  1.30      39.1 1.09e-28     8  -221.  460.  486.
    ## # … with 2 more variables: deviance <dbl>, df.residual <int>

| term                                          | estimate | p.value |
| :-------------------------------------------- | -------: | ------: |
| (Intercept)                                   |   19.330 |   0.000 |
| fuel\_used\_for\_cooking\_percent\_wood\_dung |    3.288 |   0.207 |
| percent\_public\_source                       |  \-0.015 |   0.183 |
| percent\_private\_toilet                      |    0.002 |   0.528 |
| percent\_employed                             |  \-1.887 |   0.274 |
| percent\_without\_hs\_education               |  \-4.956 |   0.000 |
| percent\_caste                                |    0.010 |   0.472 |
| median\_age                                   |    0.172 |   0.000 |

Gender as a confounder:

    ## 
    ## Call:
    ## lm(formula = bmi ~ fuel_used_for_cooking_percent_wood_dung + 
    ##     percent_public_source + percent_private_toilet + percent_employed + 
    ##     percent_without_hs_education + percent_caste + percent_female, 
    ##     data = total)
    ## 
    ## Residuals:
    ##     Min      1Q  Median      3Q     Max 
    ## -3.2001 -0.9070  0.0894  0.9371  3.2809 
    ## 
    ## Coefficients:
    ##                                          Estimate Std. Error t value
    ## (Intercept)                             29.145781   0.888526  32.802
    ## fuel_used_for_cooking_percent_wood_dung  4.610442   2.901037   1.589
    ## percent_public_source                   -0.014479   0.012856  -1.126
    ## percent_private_toilet                   0.007369   0.003297   2.235
    ## percent_employed                        -6.011034   1.770560  -3.395
    ## percent_without_hs_education            -7.397433   0.849397  -8.709
    ## percent_caste                            0.006399   0.014844   0.431
    ## percent_female                           0.309527   0.246955   1.253
    ##                                         Pr(>|t|)    
    ## (Intercept)                              < 2e-16 ***
    ## fuel_used_for_cooking_percent_wood_dung 0.114512    
    ## percent_public_source                   0.262207    
    ## percent_private_toilet                  0.027180 *  
    ## percent_employed                        0.000918 ***
    ## percent_without_hs_education            1.46e-14 ***
    ## percent_caste                           0.667146    
    ## percent_female                          0.212390    
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 1.461 on 126 degrees of freedom
    ## Multiple R-squared:  0.6015, Adjusted R-squared:  0.5794 
    ## F-statistic: 27.17 on 7 and 126 DF,  p-value: < 2.2e-16

    ##                                             Estimate  Std. Error
    ## (Intercept)                             29.145780821 0.888525821
    ## fuel_used_for_cooking_percent_wood_dung  4.610442300 2.901036774
    ## percent_public_source                   -0.014479049 0.012856157
    ## percent_private_toilet                   0.007369429 0.003297303
    ## percent_employed                        -6.011033551 1.770560486
    ## percent_without_hs_education            -7.397433052 0.849397272
    ## percent_caste                            0.006398898 0.014843861
    ## percent_female                           0.309527127 0.246955074
    ##                                            t value     Pr(>|t|)
    ## (Intercept)                             32.8024016 1.458685e-63
    ## fuel_used_for_cooking_percent_wood_dung  1.5892395 1.145124e-01
    ## percent_public_source                   -1.1262346 2.622067e-01
    ## percent_private_toilet                   2.2349871 2.717975e-02
    ## percent_employed                        -3.3949891 9.182688e-04
    ## percent_without_hs_education            -8.7090379 1.461708e-14
    ## percent_caste                            0.4310804 6.671465e-01
    ## percent_female                           1.2533742 2.123903e-01

    ##                             (Intercept) 
    ##                            29.145780821 
    ## fuel_used_for_cooking_percent_wood_dung 
    ##                             4.610442300 
    ##                   percent_public_source 
    ##                            -0.014479049 
    ##                  percent_private_toilet 
    ##                             0.007369429 
    ##                        percent_employed 
    ##                            -6.011033551 
    ##            percent_without_hs_education 
    ##                            -7.397433052 
    ##                           percent_caste 
    ##                             0.006398898 
    ##                          percent_female 
    ##                             0.309527127

    ##        1        2        3        4        5        6        7        8 
    ## 26.65404 25.68319 24.57052 25.66975 25.30654 24.18368 22.87275 24.80918 
    ##        9       10       11       12       13       14       15       16 
    ## 23.33707 24.21291 22.84457 25.03227 24.38721 25.06714 26.89692 21.54096 
    ##       17       18       19       20       21       22       23       24 
    ## 25.20014 24.20107 22.93576 25.12081 20.92946 24.94363 23.38739 24.29950 
    ##       25       26       27       28       29       30       31       32 
    ## 24.66359 23.82330 25.93478 25.44720 22.01758 24.56315 25.05684 25.86904 
    ##       33       34       35       36       37       38       39       40 
    ## 26.32566 24.84989 25.09848 27.26562 26.87612 28.02603 26.10324 22.34246 
    ##       41       42       43       44       45       46       47       48 
    ## 28.27187 27.44705 27.42254 26.37060 26.94507 25.70706 26.52823 27.23313 
    ##       49       50       51       52       53       54       55       56 
    ## 27.39273 26.64096 26.93889 26.78822 27.60569 25.77897 25.93679 24.95541 
    ##       57       58       59       60       61       62       63       64 
    ## 25.66480 24.84739 23.51939 24.57508 21.43251 24.75345 26.85368 25.71906 
    ##       65       66       67       68       69       70       71       72 
    ## 24.58619 23.51429 23.43749 23.94650 23.74486 22.26935 26.80398 26.17431 
    ##       73       74       75       76       77       78       79       80 
    ## 26.99750 21.01872 25.73403 25.13921 22.51783 22.52681 25.96407 26.44059 
    ##       81       82       83       84       85       86       87       88 
    ## 27.90713 27.83494 22.13646 20.04948 24.73451 24.48897 22.68201 24.12629 
    ##       89       90       91       92       93       94       95       96 
    ## 23.86987 23.65487 26.85845 27.13426 24.47257 23.03009 25.13578 25.64052 
    ##       97       98       99      100      101      102      103      104 
    ## 27.13017 25.98111 22.19574 27.34935 21.23205 27.51198 26.40607 25.72497 
    ##      105      106      107      108      109      110      111      112 
    ## 26.63746 27.49374 25.46864 26.80048 25.38539 26.51029 24.68605 24.84933 
    ##      113      114      115      116      117      118      119      120 
    ## 23.90547 22.40854 25.84573 26.00155 26.28164 27.14434 26.90335 26.47059 
    ##      121      122      123      124      125      126      127      128 
    ## 25.27758 26.72553 24.56963 23.90495 27.25665 24.74935 23.28235 24.37818 
    ##      129      130      131      132      133      134 
    ## 26.08692 25.32610 25.45904 25.32110 26.18119 21.90747

    ## # A tibble: 1 x 11
    ##   r.squared adj.r.squared sigma statistic  p.value    df logLik   AIC   BIC
    ##       <dbl>         <dbl> <dbl>     <dbl>    <dbl> <int>  <dbl> <dbl> <dbl>
    ## 1     0.602         0.579  1.46      27.2 1.96e-22     8  -237.  492.  518.
    ## # … with 2 more variables: deviance <dbl>, df.residual <int>

| term                                          | estimate | p.value |
| :-------------------------------------------- | -------: | ------: |
| (Intercept)                                   |   29.146 |   0.000 |
| fuel\_used\_for\_cooking\_percent\_wood\_dung |    4.610 |   0.115 |
| percent\_public\_source                       |  \-0.014 |   0.262 |
| percent\_private\_toilet                      |    0.007 |   0.027 |
| percent\_employed                             |  \-6.011 |   0.001 |
| percent\_without\_hs\_education               |  \-7.397 |   0.000 |
| percent\_caste                                |    0.006 |   0.667 |
| percent\_female                               |    0.310 |   0.212 |

Marital status as a confounder:

    ## 
    ## Call:
    ## lm(formula = bmi ~ fuel_used_for_cooking_percent_wood_dung + 
    ##     percent_public_source + percent_private_toilet + percent_employed + 
    ##     percent_without_hs_education + percent_caste + percent_marital_status, 
    ##     data = total)
    ## 
    ## Residuals:
    ##     Min      1Q  Median      3Q     Max 
    ## -3.2086 -0.9110  0.0259  0.9358  3.2602 
    ## 
    ## Coefficients:
    ##                                          Estimate Std. Error t value
    ## (Intercept)                             29.403753   0.875240  33.595
    ## fuel_used_for_cooking_percent_wood_dung  4.640155   2.914284   1.592
    ## percent_public_source                   -0.014564   0.012919  -1.127
    ## percent_private_toilet                   0.007059   0.003300   2.139
    ## percent_employed                        -6.094334   1.794056  -3.397
    ## percent_without_hs_education            -7.428263   0.863722  -8.600
    ## percent_caste                            0.006360   0.014916   0.426
    ## percent_marital_status                   0.005634   0.008882   0.634
    ##                                         Pr(>|t|)    
    ## (Intercept)                              < 2e-16 ***
    ## fuel_used_for_cooking_percent_wood_dung 0.113843    
    ## percent_public_source                   0.261755    
    ## percent_private_toilet                  0.034353 *  
    ## percent_employed                        0.000912 ***
    ## percent_without_hs_education            2.66e-14 ***
    ## percent_caste                           0.670568    
    ## percent_marital_status                  0.527010    
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 1.468 on 126 degrees of freedom
    ## Multiple R-squared:  0.5978, Adjusted R-squared:  0.5755 
    ## F-statistic: 26.76 on 7 and 126 DF,  p-value: < 2.2e-16

    ##                                             Estimate  Std. Error
    ## (Intercept)                             29.403753282 0.875240008
    ## fuel_used_for_cooking_percent_wood_dung  4.640155087 2.914284482
    ## percent_public_source                   -0.014564219 0.012919475
    ## percent_private_toilet                   0.007058910 0.003299875
    ## percent_employed                        -6.094333961 1.794055941
    ## percent_without_hs_education            -7.428262867 0.863721758
    ## percent_caste                            0.006359546 0.014915648
    ## percent_marital_status                   0.005634217 0.008882040
    ##                                            t value     Pr(>|t|)
    ## (Intercept)                             33.5950745 9.780827e-65
    ## fuel_used_for_cooking_percent_wood_dung  1.5922108 1.138431e-01
    ## percent_public_source                   -1.1273074 2.617547e-01
    ## percent_private_toilet                   2.1391446 3.435280e-02
    ## percent_employed                        -3.3969587 9.122401e-04
    ## percent_without_hs_education            -8.6002961 2.657572e-14
    ## percent_caste                            0.4263674 6.705677e-01
    ## percent_marital_status                   0.6343381 5.270102e-01

    ##                             (Intercept) 
    ##                            29.403753282 
    ## fuel_used_for_cooking_percent_wood_dung 
    ##                             4.640155087 
    ##                   percent_public_source 
    ##                            -0.014564219 
    ##                  percent_private_toilet 
    ##                             0.007058910 
    ##                        percent_employed 
    ##                            -6.094333961 
    ##            percent_without_hs_education 
    ##                            -7.428262867 
    ##                           percent_caste 
    ##                             0.006359546 
    ##                  percent_marital_status 
    ##                             0.005634217

    ##        1        2        3        4        5        6        7        8 
    ## 26.62243 25.68983 24.56664 26.22294 25.31625 24.19136 22.85285 24.80636 
    ##        9       10       11       12       13       14       15       16 
    ## 23.35970 24.22257 22.83500 25.04348 24.39676 25.07448 26.89525 21.51531 
    ##       17       18       19       20       21       22       23       24 
    ## 25.20856 24.20649 22.94049 25.12631 20.93882 24.94971 23.38664 24.30460 
    ##       25       26       27       28       29       30       31       32 
    ## 24.67469 23.82286 25.95706 25.45722 22.01746 24.57281 25.06622 25.89386 
    ##       33       34       35       36       37       38       39       40 
    ## 26.28942 24.85403 25.10968 27.25537 26.90360 26.18269 26.12168 22.34737 
    ##       41       42       43       44       45       46       47       48 
    ## 28.26751 27.42937 27.40648 26.35607 26.92744 25.71484 26.51033 27.21268 
    ##       49       50       51       52       53       54       55       56 
    ## 27.38844 26.65836 26.92099 27.33101 27.60552 25.79546 25.91552 24.96535 
    ##       57       58       59       60       61       62       63       64 
    ## 25.66139 24.84476 23.52468 24.57769 21.43100 24.76464 27.43375 25.73978 
    ##       65       66       67       68       69       70       71       72 
    ## 24.58673 23.52189 23.44108 23.95100 23.74881 22.25760 26.79058 26.18933 
    ##       73       74       75       76       77       78       79       80 
    ## 27.02073 21.00491 25.73698 25.15355 22.52143 22.52288 25.97686 26.41448 
    ##       81       82       83       84       85       86       87       88 
    ## 27.89737 27.82920 22.14571 20.04515 24.74575 24.49428 22.67073 24.13359 
    ##       89       90       91       92       93       94       95       96 
    ## 23.87047 23.66010 26.88452 27.12122 24.48225 23.02815 25.15187 25.65691 
    ##       97       98       99      100      101      102      103      104 
    ## 27.12046 25.99314 22.18600 27.33485 21.22230 27.50196 26.38416 25.71163 
    ##      105      106      107      108      109      110      111      112 
    ## 26.61783 27.47902 25.48156 26.78115 25.39532 26.51995 24.69665 24.83822 
    ##      113      114      115      116      117      118      119      120 
    ## 23.87446 22.41564 25.86018 26.01371 26.29956 27.17030 26.88650 26.48134 
    ##      121      122      123      124      125      126      127      128 
    ## 25.28376 26.70957 24.57918 23.91120 27.24070 24.77185 23.29022 24.38791 
    ##      129      130      131      132      133      134 
    ## 26.11027 25.33823 25.47161 25.33636 26.15505 21.91021

    ## # A tibble: 1 x 11
    ##   r.squared adj.r.squared sigma statistic  p.value    df logLik   AIC   BIC
    ##       <dbl>         <dbl> <dbl>     <dbl>    <dbl> <int>  <dbl> <dbl> <dbl>
    ## 1     0.598         0.575  1.47      26.8 3.44e-22     8  -237.  493.  519.
    ## # … with 2 more variables: deviance <dbl>, df.residual <int>

| term                                          | estimate | p.value |
| :-------------------------------------------- | -------: | ------: |
| (Intercept)                                   |   29.404 |   0.000 |
| fuel\_used\_for\_cooking\_percent\_wood\_dung |    4.640 |   0.114 |
| percent\_public\_source                       |  \-0.015 |   0.262 |
| percent\_private\_toilet                      |    0.007 |   0.034 |
| percent\_employed                             |  \-6.094 |   0.001 |
| percent\_without\_hs\_education               |  \-7.428 |   0.000 |
| percent\_caste                                |    0.006 |   0.671 |
| percent\_marital\_status                      |    0.006 |   0.527 |

Full model:

    ## 
    ## Call:
    ## lm(formula = bmi ~ fuel_used_for_cooking_percent_wood_dung + 
    ##     percent_public_source + percent_private_toilet + percent_employed + 
    ##     percent_without_hs_education + percent_caste + median_age + 
    ##     percent_female + percent_marital_status, data = total)
    ## 
    ## Residuals:
    ##     Min      1Q  Median      3Q     Max 
    ## -3.1721 -0.6354  0.0234  0.6553  3.3782 
    ## 
    ## Coefficients:
    ##                                          Estimate Std. Error t value
    ## (Intercept)                             19.141890   1.902471  10.062
    ## fuel_used_for_cooking_percent_wood_dung  3.262409   2.598781   1.255
    ## percent_public_source                   -0.015336   0.011476  -1.336
    ## percent_private_toilet                   0.002198   0.003085   0.713
    ## percent_employed                        -1.872661   1.758649  -1.065
    ## percent_without_hs_education            -4.896708   0.876314  -5.588
    ## percent_caste                            0.009649   0.013259   0.728
    ## median_age                               0.171759   0.029602   5.802
    ## percent_female                           0.237280   0.220952   1.074
    ## percent_marital_status                  -0.002502   0.008033  -0.311
    ##                                         Pr(>|t|)    
    ## (Intercept)                              < 2e-16 ***
    ## fuel_used_for_cooking_percent_wood_dung    0.212    
    ## percent_public_source                      0.184    
    ## percent_private_toilet                     0.477    
    ## percent_employed                           0.289    
    ## percent_without_hs_education            1.39e-07 ***
    ## percent_caste                              0.468    
    ## median_age                              5.13e-08 ***
    ## percent_female                             0.285    
    ## percent_marital_status                     0.756    
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 1.304 on 124 degrees of freedom
    ## Multiple R-squared:  0.6878, Adjusted R-squared:  0.6651 
    ## F-statistic: 30.35 on 9 and 124 DF,  p-value: < 2.2e-16

    ##                                             Estimate  Std. Error
    ## (Intercept)                             19.141890064 1.902470572
    ## fuel_used_for_cooking_percent_wood_dung  3.262408550 2.598780939
    ## percent_public_source                   -0.015336165 0.011475728
    ## percent_private_toilet                   0.002198002 0.003084910
    ## percent_employed                        -1.872661013 1.758648602
    ## percent_without_hs_education            -4.896707983 0.876313792
    ## percent_caste                            0.009648699 0.013259422
    ## median_age                               0.171758736 0.029601712
    ## percent_female                           0.237279776 0.220951619
    ## percent_marital_status                  -0.002501728 0.008032938
    ##                                            t value     Pr(>|t|)
    ## (Intercept)                             10.0615959 8.964268e-18
    ## fuel_used_for_cooking_percent_wood_dung  1.2553611 2.117083e-01
    ## percent_public_source                   -1.3364002 1.838656e-01
    ## percent_private_toilet                   0.7125011 4.774931e-01
    ## percent_employed                        -1.0648296 2.890222e-01
    ## percent_without_hs_education            -5.5878477 1.388398e-07
    ## percent_caste                            0.7276862 4.681775e-01
    ## median_age                               5.8023244 5.128032e-08
    ## percent_female                           1.0738992 2.849532e-01
    ## percent_marital_status                  -0.3114338 7.559939e-01

    ##                             (Intercept) 
    ##                            19.141890064 
    ## fuel_used_for_cooking_percent_wood_dung 
    ##                             3.262408550 
    ##                   percent_public_source 
    ##                            -0.015336165 
    ##                  percent_private_toilet 
    ##                             0.002198002 
    ##                        percent_employed 
    ##                            -1.872661013 
    ##            percent_without_hs_education 
    ##                            -4.896707983 
    ##                           percent_caste 
    ##                             0.009648699 
    ##                              median_age 
    ##                             0.171758736 
    ##                          percent_female 
    ##                             0.237279776 
    ##                  percent_marital_status 
    ##                            -0.002501728

    ##        1        2        3        4        5        6        7        8 
    ## 25.78620 25.45537 24.86507 25.99506 26.46166 23.54413 23.93664 24.85589 
    ##        9       10       11       12       13       14       15       16 
    ## 24.38653 23.39706 23.26527 23.99857 23.98765 23.75104 27.15293 22.22045 
    ##       17       18       19       20       21       22       23       24 
    ## 25.17211 23.63523 23.70252 24.51726 21.51730 24.75523 23.32900 24.71544 
    ##       25       26       27       28       29       30       31       32 
    ## 24.21489 23.83094 25.55040 25.44259 22.39163 24.46718 23.90831 25.46683 
    ##       33       34       35       36       37       38       39       40 
    ## 25.54984 25.04446 25.04042 26.57191 27.22556 28.05538 25.98930 22.71427 
    ##       41       42       43       44       45       46       47       48 
    ## 29.05643 27.45206 26.97798 26.30589 27.30436 25.94896 27.16732 27.19421 
    ##       49       50       51       52       53       54       55       56 
    ## 27.58785 27.19403 28.49022 27.09321 28.69200 26.35900 26.14043 23.63540 
    ##       57       58       59       60       61       62       63       64 
    ## 24.19094 24.14811 21.84615 23.67305 22.08723 24.61047 27.90426 25.62182 
    ##       65       66       67       68       69       70       71       72 
    ## 23.76522 23.54782 23.22101 23.50936 23.57633 22.59708 26.85671 26.73628 
    ##       73       74       75       76       77       78       79       80 
    ## 26.93761 21.26676 25.55243 25.71927 22.91771 23.13115 27.60662 27.51439 
    ##       81       82       83       84       85       86       87       88 
    ## 28.29202 27.13143 21.91809 20.19073 23.99209 24.12947 23.12981 24.33344 
    ##       89       90       91       92       93       94       95       96 
    ## 23.45612 23.71866 26.71759 26.18092 23.90839 23.58299 25.57670 24.89553 
    ##       97       98       99      100      101      102      103      104 
    ## 26.58597 26.39960 22.91264 27.82836 21.17758 27.43296 26.86217 26.11349 
    ##      105      106      107      108      109      110      111      112 
    ## 27.58602 26.99302 24.28080 26.79840 24.89886 27.50170 24.31642 24.73422 
    ##      113      114      115      116      117      118      119      120 
    ## 22.63092 22.53418 25.55481 26.49003 26.71233 28.50824 27.45712 27.87379 
    ##      121      122      123      124      125      126      127      128 
    ## 24.55699 25.46134 23.72631 23.03115 27.07521 25.22154 23.31777 24.79118 
    ##      129      130      131      132      133      134 
    ## 26.75298 25.09299 25.86101 25.03510 24.96564 21.76852

    ## # A tibble: 1 x 11
    ##   r.squared adj.r.squared sigma statistic  p.value    df logLik   AIC   BIC
    ##       <dbl>         <dbl> <dbl>     <dbl>    <dbl> <int>  <dbl> <dbl> <dbl>
    ## 1     0.688         0.665  1.30      30.4 2.29e-27    10  -221.  463.  495.
    ## # … with 2 more variables: deviance <dbl>, df.residual <int>

| term                                          | estimate | p.value |
| :-------------------------------------------- | -------: | ------: |
| (Intercept)                                   |   19.142 |   0.000 |
| fuel\_used\_for\_cooking\_percent\_wood\_dung |    3.262 |   0.212 |
| percent\_public\_source                       |  \-0.015 |   0.184 |
| percent\_private\_toilet                      |    0.002 |   0.477 |
| percent\_employed                             |  \-1.873 |   0.289 |
| percent\_without\_hs\_education               |  \-4.897 |   0.000 |
| percent\_caste                                |    0.010 |   0.468 |
| median\_age                                   |    0.172 |   0.000 |
| percent\_female                               |    0.237 |   0.285 |
| percent\_marital\_status                      |  \-0.003 |   0.756 |

Model 3: Systolic Blood Pressure

Crude:

    ## 
    ## Call:
    ## lm(formula = sbp ~ fuel_used_for_cooking_percent_wood_dung + 
    ##     percent_public_source + percent_private_toilet + percent_employed + 
    ##     percent_without_hs_education + percent_caste, data = total)
    ## 
    ## Residuals:
    ##     Min      1Q  Median      3Q     Max 
    ## -10.155  -3.676   0.209   2.577  11.467 
    ## 
    ## Coefficients:
    ##                                           Estimate Std. Error t value
    ## (Intercept)                             134.984480   2.961484  45.580
    ## fuel_used_for_cooking_percent_wood_dung  -9.929177   9.876059  -1.005
    ## percent_public_source                    -0.019037   0.043768  -0.435
    ## percent_private_toilet                   -0.005609   0.011168  -0.502
    ## percent_employed                        -15.362599   6.024975  -2.550
    ## percent_without_hs_education             -6.419725   2.865845  -2.240
    ## percent_caste                             0.021393   0.050530   0.423
    ##                                         Pr(>|t|)    
    ## (Intercept)                               <2e-16 ***
    ## fuel_used_for_cooking_percent_wood_dung   0.3166    
    ## percent_public_source                     0.6643    
    ## percent_private_toilet                    0.6164    
    ## percent_employed                          0.0120 *  
    ## percent_without_hs_education              0.0268 *  
    ## percent_caste                             0.6727    
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 4.975 on 127 degrees of freedom
    ## Multiple R-squared:  0.173,  Adjusted R-squared:  0.134 
    ## F-statistic: 4.429 on 6 and 127 DF,  p-value: 0.000422

    ##                                              Estimate Std. Error
    ## (Intercept)                             134.984479784 2.96148391
    ## fuel_used_for_cooking_percent_wood_dung  -9.929176576 9.87605928
    ## percent_public_source                    -0.019036948 0.04376766
    ## percent_private_toilet                   -0.005609216 0.01116785
    ## percent_employed                        -15.362598819 6.02497527
    ## percent_without_hs_education             -6.419725079 2.86584461
    ## percent_caste                             0.021393020 0.05053026
    ##                                            t value     Pr(>|t|)
    ## (Intercept)                             45.5800146 1.421460e-80
    ## fuel_used_for_cooking_percent_wood_dung -1.0053784 3.166264e-01
    ## percent_public_source                   -0.4349547 6.643335e-01
    ## percent_private_toilet                  -0.5022648 6.163510e-01
    ## percent_employed                        -2.5498194 1.196654e-02
    ## percent_without_hs_education            -2.2400814 2.682417e-02
    ## percent_caste                            0.4233705 6.727411e-01

    ##                             (Intercept) 
    ##                           134.984479784 
    ## fuel_used_for_cooking_percent_wood_dung 
    ##                            -9.929176576 
    ##                   percent_public_source 
    ##                            -0.019036948 
    ##                  percent_private_toilet 
    ##                            -0.005609216 
    ##                        percent_employed 
    ##                           -15.362598819 
    ##            percent_without_hs_education 
    ##                            -6.419725079 
    ##                           percent_caste 
    ##                             0.021393020

    ##        1        2        3        4        5        6        7        8 
    ## 125.9576 125.9208 125.9316 125.5332 127.1293 125.2959 122.7780 126.0048 
    ##        9       10       11       12       13       14       15       16 
    ## 125.5445 126.2025 122.5719 126.5078 125.6989 126.2815 127.0560 120.3626 
    ##       17       18       19       20       21       22       23       24 
    ## 126.7146 123.1044 125.1414 126.7609 121.4444 125.5733 124.8500 125.9037 
    ##       25       26       27       28       29       30       31       32 
    ## 126.9477 123.6495 127.8514 126.9001 124.0405 125.6186 126.1774 128.3165 
    ##       33       34       35       36       37       38       39       40 
    ## 125.1156 126.1643 125.4690 128.1443 129.6200 127.1372 127.8616 122.8248 
    ##       41       42       43       44       45       46       47       48 
    ## 129.7689 128.0645 127.5957 125.5970 127.6847 126.0617 125.7031 127.1080 
    ##       49       50       51       52       53       54       55       56 
    ## 127.5514 128.2075 127.0039 125.9989 128.0978 127.4627 125.1018 126.3570 
    ##       57       58       59       60       61       62       63       64 
    ## 126.4437 125.8637 125.8049 125.6304 118.4161 125.7830 128.5787 127.7099 
    ##       65       66       67       68       69       70       71       72 
    ## 126.0966 124.6223 124.0787 125.2180 124.3583 122.0712 126.0440 126.8464 
    ##       73       74       75       76       77       78       79       80 
    ## 128.9440 120.6972 125.9114 127.0066 123.4483 123.4744 126.9593 125.1737 
    ##       81       82       83       84       85       86       87       88 
    ## 128.8372 128.6626 123.1542 120.8005 125.5535 124.9338 122.4327 124.8554 
    ##       89       90       91       92       93       94       95       96 
    ## 124.4868 124.5724 128.6508 127.2621 125.5223 124.3287 126.4479 126.1554 
    ##       97       98       99      100      101      102      103      104 
    ## 127.7981 127.4081 122.2607 127.4157 121.6502 128.2693 126.2830 126.4825 
    ##      105      106      107      108      109      110      111      112 
    ## 126.0190 127.7814 127.3527 127.2516 126.8862 127.6822 127.0867 124.5455 
    ##      113      114      115      116      117      118      119      120 
    ## 124.3787 124.1532 127.5811 128.1132 127.7719 129.3186 127.2332 128.4078 
    ##      121      122      123      124      125      126      127      128 
    ## 126.2308 125.9917 122.4927 124.7728 126.9267 127.0472 124.6822 125.4614 
    ##      129      130      131      132      133      134 
    ## 127.3729 125.3510 126.0921 126.5640 126.2525 114.3211

    ## # A tibble: 1 x 11
    ##   r.squared adj.r.squared sigma statistic p.value    df logLik   AIC   BIC
    ##       <dbl>         <dbl> <dbl>     <dbl>   <dbl> <int>  <dbl> <dbl> <dbl>
    ## 1     0.173         0.134  4.98      4.43 4.22e-4     7  -402.  819.  842.
    ## # … with 2 more variables: deviance <dbl>, df.residual <int>

| term                                          | estimate | p.value |
| :-------------------------------------------- | -------: | ------: |
| (Intercept)                                   |  134.984 |   0.000 |
| fuel\_used\_for\_cooking\_percent\_wood\_dung |  \-9.929 |   0.317 |
| percent\_public\_source                       |  \-0.019 |   0.664 |
| percent\_private\_toilet                      |  \-0.006 |   0.616 |
| percent\_employed                             | \-15.363 |   0.012 |
| percent\_without\_hs\_education               |  \-6.420 |   0.027 |
| percent\_caste                                |    0.021 |   0.673 |

Age as a confounder:

    ## 
    ## Call:
    ## lm(formula = sbp ~ fuel_used_for_cooking_percent_wood_dung + 
    ##     percent_public_source + percent_private_toilet + percent_employed + 
    ##     percent_without_hs_education + percent_caste + median_age, 
    ##     data = total)
    ## 
    ## Residuals:
    ##      Min       1Q   Median       3Q      Max 
    ## -10.3002  -3.4341   0.2496   2.6973  11.6135 
    ## 
    ## Coefficients:
    ##                                          Estimate Std. Error t value
    ## (Intercept)                             113.72289    6.84481  16.614
    ## fuel_used_for_cooking_percent_wood_dung -12.81187    9.52335  -1.345
    ## percent_public_source                    -0.02112    0.04204  -0.502
    ## percent_private_toilet                   -0.01625    0.01117  -1.455
    ## percent_employed                         -6.77921    6.30917  -1.075
    ## percent_without_hs_education             -0.95053    3.18460  -0.298
    ## percent_caste                             0.02865    0.04858   0.590
    ## median_age                                0.36362    0.10647   3.415
    ##                                         Pr(>|t|)    
    ## (Intercept)                              < 2e-16 ***
    ## fuel_used_for_cooking_percent_wood_dung 0.180941    
    ## percent_public_source                   0.616339    
    ## percent_private_toilet                  0.148258    
    ## percent_employed                        0.284652    
    ## percent_without_hs_education            0.765831    
    ## percent_caste                           0.556456    
    ## median_age                              0.000858 ***
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 4.779 on 126 degrees of freedom
    ## Multiple R-squared:  0.2431, Adjusted R-squared:  0.2011 
    ## F-statistic: 5.781 on 7 and 126 DF,  p-value: 8.008e-06

    ##                                             Estimate Std. Error    t value
    ## (Intercept)                             113.72288569 6.84480771 16.6144749
    ## fuel_used_for_cooking_percent_wood_dung -12.81186685 9.52335288 -1.3453105
    ## percent_public_source                    -0.02111777 0.04204287 -0.5022913
    ## percent_private_toilet                   -0.01624798 0.01116983 -1.4546313
    ## percent_employed                         -6.77920993 6.30917415 -1.0745004
    ## percent_without_hs_education             -0.95052896 3.18459562 -0.2984771
    ## percent_caste                             0.02864726 0.04858034  0.5896884
    ## median_age                                0.36361782 0.10647387  3.4150897
    ##                                             Pr(>|t|)
    ## (Intercept)                             1.532266e-33
    ## fuel_used_for_cooking_percent_wood_dung 1.809412e-01
    ## percent_public_source                   6.163393e-01
    ## percent_private_toilet                  1.482580e-01
    ## percent_employed                        2.846518e-01
    ## percent_without_hs_education            7.658307e-01
    ## percent_caste                           5.564555e-01
    ## median_age                              8.584613e-04

    ##                             (Intercept) 
    ##                            113.72288569 
    ## fuel_used_for_cooking_percent_wood_dung 
    ##                            -12.81186685 
    ##                   percent_public_source 
    ##                             -0.02111777 
    ##                  percent_private_toilet 
    ##                             -0.01624798 
    ##                        percent_employed 
    ##                             -6.77920993 
    ##            percent_without_hs_education 
    ##                             -0.95052896 
    ##                           percent_caste 
    ##                              0.02864726 
    ##                              median_age 
    ##                              0.36361782

    ##        1        2        3        4        5        6        7        8 
    ## 124.0887 125.3635 126.5602 126.6665 129.5764 123.9217 125.0055 126.1062 
    ##        9       10       11       12       13       14       15       16 
    ## 127.7903 124.4844 123.4277 124.2970 124.8364 123.4652 127.5757 121.7798 
    ##       17       18       19       20       21       22       23       24 
    ## 126.6324 121.8709 126.8058 125.4681 122.7340 125.1272 124.7367 126.7817 
    ##       25       26       27       28       29       30       31       32 
    ## 126.0097 123.6567 127.0097 126.8612 124.8858 125.3865 123.7117 127.4551 
    ##       33       34       35       36       37       38       39       40 
    ## 123.4316 126.5692 125.2990 126.6782 130.3412 128.0564 127.5862 123.6032 
    ##       41       42       43       44       45       46       47       48 
    ## 131.4320 128.0689 126.6330 125.4221 128.4517 126.5026 127.0382 126.9988 
    ##       49       50       51       52       53       54       55       56 
    ## 127.9359 129.3283 130.2714 127.1244 130.3751 128.6604 125.5032 123.5388 
    ##       57       58       59       60       61       62       63       64 
    ## 123.2736 124.3548 122.2970 123.6955 119.8367 125.4476 131.2776 127.4819 
    ##       65       66       67       68       69       70       71       72 
    ## 124.3509 124.7003 123.6290 124.2843 123.9752 122.7438 126.1102 127.9646 
    ##       73       74       75       76       77       78       79       80 
    ## 128.7709 121.2727 125.4526 128.2227 124.3002 124.7629 130.3807 127.4108 
    ##       81       82       83       84       85       86       87       88 
    ## 129.6431 127.1610 122.7030 121.1042 123.9419 124.1266 123.3487 125.2629 
    ##       89       90       91       92       93       94       95       96 
    ## 123.5838 124.6928 128.3124 125.2234 124.3100 125.5114 127.3484 124.5098 
    ##       97       98       99      100      101      102      103      104 
    ## 126.6429 128.2539 123.7959 128.4048 121.5741 128.0953 127.2360 127.3296 
    ##      105      106      107      108      109      110      111      112 
    ## 127.9930 126.7004 124.8220 127.2474 125.8380 129.7235 126.3188 124.3035 
    ##      113      114      115      116      117      118      119      120 
    ## 121.7353 124.4519 126.9362 129.1302 128.6378 132.1648 128.3976 131.3462 
    ##      121      122      123      124      125      126      127      128 
    ## 124.6639 123.3013 120.6682 122.9014 126.5217 128.0514 124.7772 126.3122 
    ##      129      130      131      132      133      134 
    ## 128.7292 124.7800 126.8838 125.9206 123.6798 114.0217

    ## # A tibble: 1 x 11
    ##   r.squared adj.r.squared sigma statistic p.value    df logLik   AIC   BIC
    ##       <dbl>         <dbl> <dbl>     <dbl>   <dbl> <int>  <dbl> <dbl> <dbl>
    ## 1     0.243         0.201  4.78      5.78 8.01e-6     8  -396.  809.  835.
    ## # … with 2 more variables: deviance <dbl>, df.residual <int>

| term                                          | estimate | p.value |
| :-------------------------------------------- | -------: | ------: |
| (Intercept)                                   |  113.723 |   0.000 |
| fuel\_used\_for\_cooking\_percent\_wood\_dung | \-12.812 |   0.181 |
| percent\_public\_source                       |  \-0.021 |   0.616 |
| percent\_private\_toilet                      |  \-0.016 |   0.148 |
| percent\_employed                             |  \-6.779 |   0.285 |
| percent\_without\_hs\_education               |  \-0.951 |   0.766 |
| percent\_caste                                |    0.029 |   0.556 |
| median\_age                                   |    0.364 |   0.001 |

Gender as a confounder:

    ## 
    ## Call:
    ## lm(formula = sbp ~ fuel_used_for_cooking_percent_wood_dung + 
    ##     percent_public_source + percent_private_toilet + percent_employed + 
    ##     percent_without_hs_education + percent_caste + percent_female, 
    ##     data = total)
    ## 
    ## Residuals:
    ##      Min       1Q   Median       3Q      Max 
    ## -10.1253  -3.6866   0.1524   2.6001  11.4939 
    ## 
    ## Coefficients:
    ##                                           Estimate Std. Error t value
    ## (Intercept)                             134.867501   3.036556  44.415
    ## fuel_used_for_cooking_percent_wood_dung  -9.949583   9.914356  -1.004
    ## percent_public_source                    -0.019104   0.043936  -0.435
    ## percent_private_toilet                   -0.005393   0.011269  -0.479
    ## percent_employed                        -15.398295   6.050929  -2.545
    ## percent_without_hs_education             -6.346404   2.902834  -2.186
    ## percent_caste                             0.021541   0.050729   0.425
    ## percent_female                            0.159489   0.843974   0.189
    ##                                         Pr(>|t|)    
    ## (Intercept)                               <2e-16 ***
    ## fuel_used_for_cooking_percent_wood_dung   0.3175    
    ## percent_public_source                     0.6644    
    ## percent_private_toilet                    0.6330    
    ## percent_employed                          0.0121 *  
    ## percent_without_hs_education              0.0306 *  
    ## percent_caste                             0.6718    
    ## percent_female                            0.8504    
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 4.994 on 126 degrees of freedom
    ## Multiple R-squared:  0.1733, Adjusted R-squared:  0.1273 
    ## F-statistic: 3.773 on 7 and 126 DF,  p-value: 0.0009525

    ##                                              Estimate Std. Error
    ## (Intercept)                             134.867501149 3.03655619
    ## fuel_used_for_cooking_percent_wood_dung  -9.949582943 9.91435584
    ## percent_public_source                    -0.019103856 0.04393619
    ## percent_private_toilet                   -0.005393221 0.01126860
    ## percent_employed                        -15.398294642 6.05092871
    ## percent_without_hs_education             -6.346404177 2.90283353
    ## percent_caste                             0.021540800 0.05072922
    ## percent_female                            0.159489281 0.84397430
    ##                                            t value     Pr(>|t|)
    ## (Intercept)                             44.4146240 8.037665e-79
    ## fuel_used_for_cooking_percent_wood_dung -1.0035531 3.175174e-01
    ## percent_public_source                   -0.4348091 6.644448e-01
    ## percent_private_toilet                  -0.4786060 6.330484e-01
    ## percent_employed                        -2.5447820 1.214154e-02
    ## percent_without_hs_education            -2.1862791 3.064281e-02
    ## percent_caste                            0.4246232 6.718356e-01
    ## percent_female                           0.1889741 8.504172e-01

    ##                             (Intercept) 
    ##                           134.867501149 
    ## fuel_used_for_cooking_percent_wood_dung 
    ##                            -9.949582943 
    ##                   percent_public_source 
    ##                            -0.019103856 
    ##                  percent_private_toilet 
    ##                            -0.005393221 
    ##                        percent_employed 
    ##                           -15.398294642 
    ##            percent_without_hs_education 
    ##                            -6.346404177 
    ##                           percent_caste 
    ##                             0.021540800 
    ##                          percent_female 
    ##                             0.159489281

    ##        1        2        3        4        5        6        7        8 
    ## 125.9569 125.8916 125.9347 125.5061 127.1267 125.2860 122.7758 126.0067 
    ##        9       10       11       12       13       14       15       16 
    ## 125.5455 126.2025 122.5626 126.4959 125.6897 126.2682 127.0486 120.3636 
    ##       17       18       19       20       21       22       23       24 
    ## 126.7036 123.0898 125.1546 126.7536 121.4574 125.5542 124.8540 125.9011 
    ##       25       26       27       28       29       30       31       32 
    ## 126.9483 123.6465 127.8338 126.8862 124.0597 125.6049 126.1619 128.3046 
    ##       33       34       35       36       37       38       39       40 
    ## 125.1129 126.1604 125.4483 128.1487 129.6041 128.0677 127.8431 122.8200 
    ##       41       42       43       44       45       46       47       48 
    ## 129.7711 128.0683 127.5934 125.5883 127.6930 126.0335 125.7027 127.1053 
    ##       49       50       51       52       53       54       55       56 
    ## 127.5426 128.1836 127.0039 125.9880 128.0898 127.4463 125.0983 126.3451 
    ##       57       58       59       60       61       62       63       64 
    ## 126.4269 125.8543 125.8155 125.6204 118.4290 125.7675 128.5534 127.6949 
    ##       65       66       67       68       69       70       71       72 
    ## 126.0937 124.6222 124.0806 125.2135 124.3475 122.0676 126.0322 126.8156 
    ##       73       74       75       76       77       78       79       80 
    ## 128.9195 120.7200 125.8837 126.9975 123.4490 123.4790 126.9349 125.1695 
    ##       81       82       83       84       85       86       87       88 
    ## 128.8373 128.6601 123.1550 120.8036 125.5353 124.9154 122.4250 124.8418 
    ##       89       90       91       92       93       94       95       96 
    ## 124.4769 124.5654 128.6276 127.2592 125.5126 124.3337 126.4306 126.1253 
    ##       97       98       99      100      101      102      103      104 
    ## 127.8003 127.3896 122.2703 127.4116 121.6676 128.2702 126.2859 126.4959 
    ##      105      106      107      108      109      110      111      112 
    ## 126.0134 127.7788 127.3426 127.2582 126.8763 127.6583 127.0884 124.5499 
    ##      113      114      115      116      117      118      119      120 
    ## 124.4089 124.1626 127.5658 128.1029 127.7494 129.2950 127.2360 128.3926 
    ##      121      122      123      124      125      126      127      128 
    ## 126.2138 125.9920 122.4754 124.7630 126.9246 127.0413 124.6868 125.4497 
    ##      129      130      131      132      133      134 
    ## 127.3457 125.3190 126.0666 126.5452 126.2616 114.3183

    ## # A tibble: 1 x 11
    ##   r.squared adj.r.squared sigma statistic p.value    df logLik   AIC   BIC
    ##       <dbl>         <dbl> <dbl>     <dbl>   <dbl> <int>  <dbl> <dbl> <dbl>
    ## 1     0.173         0.127  4.99      3.77 9.53e-4     8  -402.  821.  847.
    ## # … with 2 more variables: deviance <dbl>, df.residual <int>

| term                                          | estimate | p.value |
| :-------------------------------------------- | -------: | ------: |
| (Intercept)                                   |  134.868 |   0.000 |
| fuel\_used\_for\_cooking\_percent\_wood\_dung |  \-9.950 |   0.318 |
| percent\_public\_source                       |  \-0.019 |   0.664 |
| percent\_private\_toilet                      |  \-0.005 |   0.633 |
| percent\_employed                             | \-15.398 |   0.012 |
| percent\_without\_hs\_education               |  \-6.346 |   0.031 |
| percent\_caste                                |    0.022 |   0.672 |
| percent\_female                               |    0.159 |   0.850 |

Marital status as a confounder:

    ## 
    ## Call:
    ## lm(formula = sbp ~ fuel_used_for_cooking_percent_wood_dung + 
    ##     percent_public_source + percent_private_toilet + percent_employed + 
    ##     percent_without_hs_education + percent_caste + percent_marital_status, 
    ##     data = total)
    ## 
    ## Residuals:
    ##     Min      1Q  Median      3Q     Max 
    ## -9.9417 -3.7377  0.2036  2.7246 11.4671 
    ## 
    ## Coefficients:
    ##                                           Estimate Std. Error t value
    ## (Intercept)                             135.141791   2.967210  45.545
    ## fuel_used_for_cooking_percent_wood_dung  -9.979453   9.879911  -1.010
    ## percent_public_source                    -0.020130   0.043799  -0.460
    ## percent_private_toilet                   -0.005057   0.011187  -0.452
    ## percent_employed                        -16.138174   6.082149  -2.653
    ## percent_without_hs_education             -5.853119   2.928161  -1.999
    ## percent_caste                             0.022651   0.050567   0.448
    ## percent_marital_status                    0.028640   0.030112   0.951
    ##                                         Pr(>|t|)    
    ## (Intercept)                               <2e-16 ***
    ## fuel_used_for_cooking_percent_wood_dung   0.3144    
    ## percent_public_source                     0.6466    
    ## percent_private_toilet                    0.6520    
    ## percent_employed                          0.0090 ** 
    ## percent_without_hs_education              0.0478 *  
    ## percent_caste                             0.6550    
    ## percent_marital_status                    0.3434    
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 4.977 on 126 degrees of freedom
    ## Multiple R-squared:  0.1789, Adjusted R-squared:  0.1333 
    ## F-statistic: 3.923 on 7 and 126 DF,  p-value: 0.0006647

    ##                                              Estimate Std. Error
    ## (Intercept)                             135.141791078 2.96720977
    ## fuel_used_for_cooking_percent_wood_dung  -9.979452543 9.87991101
    ## percent_public_source                    -0.020129938 0.04379918
    ## percent_private_toilet                   -0.005056826 0.01118713
    ## percent_employed                        -16.138173619 6.08214921
    ## percent_without_hs_education             -5.853118547 2.92816098
    ## percent_caste                             0.022650861 0.05056654
    ## percent_marital_status                    0.028639736 0.03011160
    ##                                            t value     Pr(>|t|)
    ## (Intercept)                             45.5450748 4.071996e-80
    ## fuel_used_for_cooking_percent_wood_dung -1.0100751 3.143951e-01
    ## percent_public_source                   -0.4595963 6.465980e-01
    ## percent_private_toilet                  -0.4520219 6.520304e-01
    ## percent_employed                        -2.6533669 8.995660e-03
    ## percent_without_hs_education            -1.9989060 4.777047e-02
    ## percent_caste                            0.4479417 6.549645e-01
    ## percent_marital_status                   0.9511198 3.433645e-01

    ##                             (Intercept) 
    ##                           135.141791078 
    ## fuel_used_for_cooking_percent_wood_dung 
    ##                            -9.979452543 
    ##                   percent_public_source 
    ##                            -0.020129938 
    ##                  percent_private_toilet 
    ##                            -0.005056826 
    ##                        percent_employed 
    ##                           -16.138173619 
    ##            percent_without_hs_education 
    ##                            -5.853118547 
    ##                           percent_caste 
    ##                             0.022650861 
    ##                  percent_marital_status 
    ##                             0.028639736

    ##        1        2        3        4        5        6        7        8 
    ## 125.7901 125.6665 125.9427 128.0780 127.1523 125.2373 122.6551 126.0088 
    ##        9       10       11       12       13       14       15       16 
    ## 125.6692 126.2518 122.4317 126.4479 125.6567 126.1878 126.9741 120.2421 
    ##       17       18       19       20       21       22       23       24 
    ## 126.6484 122.9875 125.2956 126.7170 121.6207 125.4164 124.8851 125.9036 
    ##       25       26       27       28       29       30       31       32 
    ## 127.0095 123.6169 127.7913 126.8141 124.2298 125.5329 126.0724 128.3249 
    ##       33       34       35       36       37       38       39       40 
    ## 124.9048 126.1468 125.3218 128.1352 129.6025 126.9465 127.7727 122.8024 
    ##       41       42       43       44       45       46       47       48 
    ## 129.7690 128.0115 127.4912 125.4372 127.6765 125.8230 125.6083 126.9772 
    ##       49       50       51       52       53       54       55       56 
    ## 127.4426 128.0604 126.9133 128.6501 128.0179 127.3846 124.9593 126.2905 
    ##       57       58       59       60       61       62       63       64 
    ## 126.2611 125.7581 125.9362 125.5453 118.5360 125.6864 131.2773 127.6677 
    ##       65       66       67       68       69       70       71       72 
    ## 126.0701 124.6607 124.1151 125.1967 124.2718 121.9756 125.8595 126.6195 
    ##       73       74       75       76       77       78       79       80 
    ## 128.8206 120.8515 125.6531 126.9895 123.4735 123.4998 126.7833 125.0000 
    ##       81       82       83       84       85       86       87       88 
    ## 128.7886 128.6094 123.2097 120.8094 125.4318 124.7795 122.2995 124.7581 
    ##       89       90       91       92       93       94       95       96 
    ## 124.3920 124.5298 128.5540 127.1669 125.4760 124.3685 126.3594 125.9417 
    ##       97       98       99      100      101      102      103      104 
    ## 127.7702 127.2870 122.3057 127.3016 121.7722 128.2280 126.2002 126.5461 
    ##      105      106      107      108      109      110      111      112 
    ## 125.8637 127.6811 127.3185 127.2183 126.8391 127.4952 127.1572 124.5323 
    ##      113      114      115      116      117      118      119      120 
    ## 124.5188 124.2814 127.5036 128.0736 127.6407 129.2178 127.1755 128.3124 
    ##      121      122      123      124      125      126      127      128 
    ## 126.0952 125.9138 122.3705 124.7072 126.8249 127.1029 124.7668 125.3951 
    ##      129      130      131      132      133      134 
    ## 127.2233 125.0975 125.9039 126.4563 126.2089 114.3072

    ## # A tibble: 1 x 11
    ##   r.squared adj.r.squared sigma statistic p.value    df logLik   AIC   BIC
    ##       <dbl>         <dbl> <dbl>     <dbl>   <dbl> <int>  <dbl> <dbl> <dbl>
    ## 1     0.179         0.133  4.98      3.92 6.65e-4     8  -401.  820.  846.
    ## # … with 2 more variables: deviance <dbl>, df.residual <int>

| term                                          | estimate | p.value |
| :-------------------------------------------- | -------: | ------: |
| (Intercept)                                   |  135.142 |   0.000 |
| fuel\_used\_for\_cooking\_percent\_wood\_dung |  \-9.979 |   0.314 |
| percent\_public\_source                       |  \-0.020 |   0.647 |
| percent\_private\_toilet                      |  \-0.005 |   0.652 |
| percent\_employed                             | \-16.138 |   0.009 |
| percent\_without\_hs\_education               |  \-5.853 |   0.048 |
| percent\_caste                                |    0.023 |   0.655 |
| percent\_marital\_status                      |    0.029 |   0.343 |

Full model:

    ## 
    ## Call:
    ## lm(formula = sbp ~ fuel_used_for_cooking_percent_wood_dung + 
    ##     percent_public_source + percent_private_toilet + percent_employed + 
    ##     percent_without_hs_education + percent_caste + median_age + 
    ##     percent_female + percent_marital_status, data = total)
    ## 
    ## Residuals:
    ##      Min       1Q   Median       3Q      Max 
    ## -10.2922  -3.4318   0.2388   2.7488  11.6443 
    ## 
    ## Coefficients:
    ##                                          Estimate Std. Error t value
    ## (Intercept)                             114.20967    7.02424  16.259
    ## fuel_used_for_cooking_percent_wood_dung -12.77444    9.59514  -1.331
    ## percent_public_source                    -0.02151    0.04237  -0.508
    ## percent_private_toilet                   -0.01577    0.01139  -1.385
    ## percent_employed                         -7.26651    6.49323  -1.119
    ## percent_without_hs_education             -0.83268    3.23550  -0.257
    ## percent_caste                             0.02901    0.04896   0.593
    ## median_age                                0.35598    0.10929   3.257
    ## percent_female                            0.02812    0.81579   0.034
    ## percent_marital_status                    0.01111    0.02966   0.375
    ##                                         Pr(>|t|)    
    ## (Intercept)                              < 2e-16 ***
    ## fuel_used_for_cooking_percent_wood_dung  0.18552    
    ## percent_public_source                    0.61259    
    ## percent_private_toilet                   0.16862    
    ## percent_employed                         0.26526    
    ## percent_without_hs_education             0.79733    
    ## percent_caste                            0.55456    
    ## median_age                               0.00145 ** 
    ## percent_female                           0.97256    
    ## percent_marital_status                   0.70867    
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 4.814 on 124 degrees of freedom
    ## Multiple R-squared:  0.244,  Adjusted R-squared:  0.1891 
    ## F-statistic: 4.446 on 9 and 124 DF,  p-value: 4.616e-05

    ##                                             Estimate Std. Error    t value
    ## (Intercept)                             114.20967014 7.02424392 16.2593542
    ## fuel_used_for_cooking_percent_wood_dung -12.77443949 9.59513986 -1.3313448
    ## percent_public_source                    -0.02150977 0.04237033 -0.5076612
    ## percent_private_toilet                   -0.01577229 0.01139001 -1.3847481
    ## percent_employed                         -7.26650715 6.49322883 -1.1190900
    ## percent_without_hs_education             -0.83268402 3.23549910 -0.2573588
    ## percent_caste                             0.02900884 0.04895604  0.5925488
    ## median_age                                0.35598345 0.10929454  3.2571019
    ## percent_female                            0.02811998 0.81579084  0.0344696
    ## percent_marital_status                    0.01110732 0.02965897  0.3745012
    ##                                             Pr(>|t|)
    ## (Intercept)                             1.568258e-32
    ## fuel_used_for_cooking_percent_wood_dung 1.855180e-01
    ## percent_public_source                   6.125928e-01
    ## percent_private_toilet                  1.686160e-01
    ## percent_employed                        2.652649e-01
    ## percent_without_hs_education            7.973284e-01
    ## percent_caste                           5.545622e-01
    ## median_age                              1.452003e-03
    ## percent_female                          9.725581e-01
    ## percent_marital_status                  7.086711e-01

    ##                             (Intercept) 
    ##                            114.20967014 
    ## fuel_used_for_cooking_percent_wood_dung 
    ##                            -12.77443949 
    ##                   percent_public_source 
    ##                             -0.02150977 
    ##                  percent_private_toilet 
    ##                             -0.01577229 
    ##                        percent_employed 
    ##                             -7.26650715 
    ##            percent_without_hs_education 
    ##                             -0.83268402 
    ##                           percent_caste 
    ##                              0.02900884 
    ##                              median_age 
    ##                              0.35598345 
    ##                          percent_female 
    ##                              0.02811998 
    ##                  percent_marital_status 
    ##                              0.01110732

    ##        1        2        3        4        5        6        7        8 
    ## 124.0629 125.2714 126.5519 127.6249 129.5335 123.9260 124.9106 126.1060 
    ##        9       10       11       12       13       14       15       16 
    ## 127.7916 124.5396 123.3537 124.3181 124.8365 123.4856 127.5317 121.7034 
    ##       17       18       19       20       21       22       23       24 
    ## 126.6065 121.8489 126.8330 125.4769 122.7776 125.0723 124.7534 126.7628 
    ##       25       26       27       28       29       30       31       32 
    ## 126.0535 123.6434 127.0009 126.8262 124.9449 125.3557 123.7200 127.4744 
    ##       33       34       35       36       37       38       39       40 
    ## 123.3847 126.5533 125.2418 126.7062 130.3165 128.1272 127.5542 123.5773 
    ##       41       42       43       44       45       46       47       48 
    ## 131.3975 128.0489 126.6123 125.3623 128.4339 126.3958 126.9733 126.9499 
    ##       49       50       51       52       53       54       55       56 
    ## 127.8841 129.2435 130.1676 128.1270 130.2949 128.6021 125.4389 123.5701 
    ##       57       58       59       60       61       62       63       64 
    ## 123.2664 124.3439 122.4235 123.7014 119.8557 125.4144 132.2630 127.4677 
    ##       65       66       67       68       69       70       71       72 
    ## 124.3767 124.7136 123.6528 124.2949 123.9478 122.6920 126.0352 127.8477 
    ##       73       74       75       76       77       78       79       80 
    ## 128.7224 121.3244 125.3572 128.1889 124.2922 124.7465 130.2363 127.2958 
    ##       81       82       83       84       85       86       87       88 
    ## 129.6074 127.1715 122.7341 121.1018 123.9253 124.0804 123.2764 125.2141 
    ##       89       90       91       92       93       94       95       96 
    ## 123.5643 124.6725 128.2779 125.2288 124.3158 125.5029 127.2921 124.4562 
    ##       97       98       99      100      101      102      103      104 
    ## 126.6567 128.1860 123.7828 128.3390 121.6261 128.0831 127.1844 127.3388 
    ##      105      106      107      108      109      110      111      112 
    ## 127.8904 126.6837 124.8601 127.2357 125.8400 129.6039 126.3626 124.3043 
    ##      113      114      115      116      117      118      119      120 
    ## 121.8505 124.4969 126.9170 129.0916 128.5648 132.0618 128.3513 131.2448 
    ##      121      122      123      124      125      126      127      128 
    ## 124.6413 123.3276 120.6560 122.9135 126.4904 128.0509 124.8088 126.2666 
    ##      129      130      131      132      133      134 
    ## 128.6380 124.6880 126.7896 125.8890 123.7185 114.0221

    ## # A tibble: 1 x 11
    ##   r.squared adj.r.squared sigma statistic p.value    df logLik   AIC   BIC
    ##       <dbl>         <dbl> <dbl>     <dbl>   <dbl> <int>  <dbl> <dbl> <dbl>
    ## 1     0.244         0.189  4.81      4.45 4.62e-5    10  -396.  813.  845.
    ## # … with 2 more variables: deviance <dbl>, df.residual <int>

| term                                          | estimate | p.value |
| :-------------------------------------------- | -------: | ------: |
| (Intercept)                                   |  114.210 |   0.000 |
| fuel\_used\_for\_cooking\_percent\_wood\_dung | \-12.774 |   0.186 |
| percent\_public\_source                       |  \-0.022 |   0.613 |
| percent\_private\_toilet                      |  \-0.016 |   0.169 |
| percent\_employed                             |  \-7.267 |   0.265 |
| percent\_without\_hs\_education               |  \-0.833 |   0.797 |
| percent\_caste                                |    0.029 |   0.555 |
| median\_age                                   |    0.356 |   0.001 |
| percent\_female                               |    0.028 |   0.973 |
| percent\_marital\_status                      |    0.011 |   0.709 |

Model 4: Diastolic Blood Pressure

Crude:

    ## 
    ## Call:
    ## lm(formula = dbp ~ fuel_used_for_cooking_percent_wood_dung + 
    ##     percent_public_source + percent_private_toilet + percent_employed + 
    ##     percent_without_hs_education + percent_caste, data = total)
    ## 
    ## Residuals:
    ##     Min      1Q  Median      3Q     Max 
    ## -6.1543 -1.8922  0.1381  1.5985  7.1545 
    ## 
    ## Coefficients:
    ##                                          Estimate Std. Error t value
    ## (Intercept)                             85.762963   1.623616  52.822
    ## fuel_used_for_cooking_percent_wood_dung -1.577574   5.414491  -0.291
    ## percent_public_source                   -0.019758   0.023995  -0.823
    ## percent_private_toilet                  -0.001706   0.006123  -0.279
    ## percent_employed                        -4.918851   3.303157  -1.489
    ## percent_without_hs_education            -1.702722   1.571182  -1.084
    ## percent_caste                            0.026482   0.027703   0.956
    ##                                         Pr(>|t|)    
    ## (Intercept)                               <2e-16 ***
    ## fuel_used_for_cooking_percent_wood_dung    0.771    
    ## percent_public_source                      0.412    
    ## percent_private_toilet                     0.781    
    ## percent_employed                           0.139    
    ## percent_without_hs_education               0.281    
    ## percent_caste                              0.341    
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 2.728 on 127 degrees of freedom
    ## Multiple R-squared:  0.06741,    Adjusted R-squared:  0.02335 
    ## F-statistic:  1.53 on 6 and 127 DF,  p-value: 0.1735

    ##                                             Estimate  Std. Error
    ## (Intercept)                             85.762962850 1.623616142
    ## fuel_used_for_cooking_percent_wood_dung -1.577574083 5.414491444
    ## percent_public_source                   -0.019758085 0.023995360
    ## percent_private_toilet                  -0.001706308 0.006122706
    ## percent_employed                        -4.918850962 3.303157273
    ## percent_without_hs_education            -1.702722090 1.571182458
    ## percent_caste                            0.026482041 0.027702916
    ##                                            t value     Pr(>|t|)
    ## (Intercept)                             52.8221915 2.660909e-88
    ## fuel_used_for_cooking_percent_wood_dung -0.2913615 7.712502e-01
    ## percent_public_source                   -0.8234128 4.118169e-01
    ## percent_private_toilet                  -0.2786852 7.809397e-01
    ## percent_employed                        -1.4891362 1.389306e-01
    ## percent_without_hs_education            -1.0837202 2.805420e-01
    ## percent_caste                            0.9559297 3.409238e-01

    ##                             (Intercept) 
    ##                            85.762962850 
    ## fuel_used_for_cooking_percent_wood_dung 
    ##                            -1.577574083 
    ##                   percent_public_source 
    ##                            -0.019758085 
    ##                  percent_private_toilet 
    ##                            -0.001706308 
    ##                        percent_employed 
    ##                            -4.918850962 
    ##            percent_without_hs_education 
    ##                            -1.702722090 
    ##                           percent_caste 
    ##                             0.026482041

    ##        1        2        3        4        5        6        7        8 
    ## 82.90197 82.87385 83.03067 82.74385 83.38561 82.76577 81.99485 85.02288 
    ##        9       10       11       12       13       14       15       16 
    ## 82.90327 83.07407 81.92029 83.12958 82.89808 83.05125 83.25891 81.29470 
    ##       17       18       19       20       21       22       23       24 
    ## 83.18988 82.23625 82.80665 83.20958 81.76416 82.80894 82.65391 82.95702 
    ##       25       26       27       28       29       30       31       32 
    ## 83.30149 82.39365 83.52278 83.22773 82.47023 82.84552 83.00740 83.69501 
    ##       33       34       35       36       37       38       39       40 
    ## 82.62177 83.08350 82.81659 83.61078 84.07256 83.25931 83.51567 82.02744 
    ##       41       42       43       44       45       46       47       48 
    ## 84.10257 83.56803 83.40618 82.78597 83.47284 82.91986 82.89953 83.25002 
    ##       49       50       51       52       53       54       55       56 
    ## 83.39249 83.59912 83.23477 82.89490 83.56692 83.40106 82.64635 83.08140 
    ##       57       58       59       60       61       62       63       64 
    ## 83.06548 82.91648 82.98814 82.85930 81.12368 82.88866 83.71202 83.49106 
    ##       65       66       67       68       69       70       71       72 
    ## 83.01034 82.64542 82.50612 82.75602 82.47223 81.78399 82.90932 83.15775 
    ##       73       74       75       76       77       78       79       80 
    ## 83.82897 81.60245 82.86454 83.28897 82.23647 82.23900 83.21174 82.68983 
    ##       81       82       83       84       85       86       87       88 
    ## 83.80386 83.74776 82.15433 80.08776 82.81270 82.62089 81.88400 82.62125 
    ##       89       90       91       92       93       94       95       96 
    ## 82.50547 82.55190 83.77629 83.31068 82.85900 82.50673 83.09217 82.95809 
    ##       97       98       99      100      101      102      103      104 
    ## 83.49841 83.36930 81.96959 83.34830 81.79872 83.63455 83.02405 83.14725 
    ##      105      106      107      108      109      110      111      112 
    ## 82.91572 83.46669 83.38416 83.33073 83.26401 83.42497 83.35019 82.53985 
    ##      113      114      115      116      117      118      119      120 
    ## 82.54727 82.48998 83.43862 83.61198 83.47537 83.94857 83.31724 83.68214 
    ##      121      122      123      124      125      126      127      128 
    ## 83.01530 83.01153 82.13696 82.60384 83.24796 83.33306 82.67624 82.81041 
    ##      129      130      131      132      133      134 
    ## 83.34727 82.70451 82.94891 83.12575 83.03029 78.91998

    ## # A tibble: 1 x 11
    ##   r.squared adj.r.squared sigma statistic p.value    df logLik   AIC   BIC
    ##       <dbl>         <dbl> <dbl>     <dbl>   <dbl> <int>  <dbl> <dbl> <dbl>
    ## 1    0.0674        0.0234  2.73      1.53   0.173     7  -321.  658.  681.
    ## # … with 2 more variables: deviance <dbl>, df.residual <int>

| term                                          | estimate | p.value |
| :-------------------------------------------- | -------: | ------: |
| (Intercept)                                   |   85.763 |   0.000 |
| fuel\_used\_for\_cooking\_percent\_wood\_dung |  \-1.578 |   0.771 |
| percent\_public\_source                       |  \-0.020 |   0.412 |
| percent\_private\_toilet                      |  \-0.002 |   0.781 |
| percent\_employed                             |  \-4.919 |   0.139 |
| percent\_without\_hs\_education               |  \-1.703 |   0.281 |
| percent\_caste                                |    0.026 |   0.341 |

Age as a confounder:

    ## 
    ## Call:
    ## lm(formula = dbp ~ fuel_used_for_cooking_percent_wood_dung + 
    ##     percent_public_source + percent_private_toilet + percent_employed + 
    ##     percent_without_hs_education + percent_caste + median_age, 
    ##     data = total)
    ## 
    ## Residuals:
    ##     Min      1Q  Median      3Q     Max 
    ## -6.1029 -1.7170  0.1546  1.5727  7.1809 
    ## 
    ## Coefficients:
    ##                                          Estimate Std. Error t value
    ## (Intercept)                             83.341642   3.915282  21.286
    ## fuel_used_for_cooking_percent_wood_dung -1.905862   5.447431  -0.350
    ## percent_public_source                   -0.019995   0.024049  -0.831
    ## percent_private_toilet                  -0.002918   0.006389  -0.457
    ## percent_employed                        -3.941354   3.608896  -1.092
    ## percent_without_hs_education            -1.079877   1.821613  -0.593
    ## percent_caste                            0.027308   0.027788   0.983
    ## median_age                               0.041410   0.060904   0.680
    ##                                         Pr(>|t|)    
    ## (Intercept)                               <2e-16 ***
    ## fuel_used_for_cooking_percent_wood_dung    0.727    
    ## percent_public_source                      0.407    
    ## percent_private_toilet                     0.649    
    ## percent_employed                           0.277    
    ## percent_without_hs_education               0.554    
    ## percent_caste                              0.328    
    ## median_age                                 0.498    
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 2.734 on 126 degrees of freedom
    ## Multiple R-squared:  0.07082,    Adjusted R-squared:  0.0192 
    ## F-statistic: 1.372 on 7 and 126 DF,  p-value: 0.2228

    ##                                             Estimate  Std. Error
    ## (Intercept)                             83.341641506 3.915282239
    ## fuel_used_for_cooking_percent_wood_dung -1.905861767 5.447430513
    ## percent_public_source                   -0.019995054 0.024048845
    ## percent_private_toilet                  -0.002917875 0.006389225
    ## percent_employed                        -3.941354044 3.608895757
    ## percent_without_hs_education            -1.079876915 1.821612995
    ## percent_caste                            0.027308172 0.027788326
    ## median_age                               0.041409669 0.060903867
    ##                                            t value     Pr(>|t|)
    ## (Intercept)                             21.2862410 1.489059e-43
    ## fuel_used_for_cooking_percent_wood_dung -0.3498644 7.270246e-01
    ## percent_public_source                   -0.8314351 4.073007e-01
    ## percent_private_toilet                  -0.4566868 6.486825e-01
    ## percent_employed                        -1.0921219 2.768633e-01
    ## percent_without_hs_education            -0.5928136 5.543684e-01
    ## percent_caste                            0.9827210 3.276280e-01
    ## median_age                               0.6799186 4.978033e-01

    ##                             (Intercept) 
    ##                            83.341641506 
    ## fuel_used_for_cooking_percent_wood_dung 
    ##                            -1.905861767 
    ##                   percent_public_source 
    ##                            -0.019995054 
    ##                  percent_private_toilet 
    ##                            -0.002917875 
    ##                        percent_employed 
    ##                            -3.941354044 
    ##            percent_without_hs_education 
    ##                            -1.079876915 
    ##                           percent_caste 
    ##                             0.027308172 
    ##                              median_age 
    ##                             0.041409669

    ##        1        2        3        4        5        6        7        8 
    ## 82.68914 82.81038 83.10226 82.87292 83.66429 82.60927 82.24851 85.03443 
    ##        9       10       11       12       13       14       15       16 
    ## 83.15902 82.87841 82.01775 82.87781 82.79985 82.73052 83.31810 81.45609 
    ##       17       18       19       20       21       22       23       24 
    ## 83.18052 82.09577 82.99619 83.06234 81.91103 82.75814 82.64100 83.05701 
    ##       25       26       27       28       29       30       31       32 
    ## 83.19467 82.39446 83.42692 83.22329 82.56650 82.81909 82.72660 83.59692 
    ##       33       34       35       36       37       38       39       40 
    ## 82.42999 83.12961 82.79723 83.44382 84.15470 83.36398 83.48430 82.11608 
    ##       41       42       43       44       45       46       47       48 
    ## 84.29197 83.56853 83.29654 82.76606 83.56019 82.97007 83.05157 83.23759 
    ##       49       50       51       52       53       54       55       56 
    ## 83.43628 83.72676 83.60688 83.02307 83.82627 83.53746 82.69207 82.76046 
    ##       57       58       59       60       61       62       63       64 
    ## 82.70447 82.74465 82.58865 82.63895 81.28547 82.85046 84.01937 83.46509 
    ##       65       66       67       68       69       70       71       72 
    ## 82.81152 82.65431 82.45490 82.64969 82.42860 81.86059 82.91686 83.28510 
    ##       73       74       75       76       77       78       79       80 
    ## 83.80926 81.66799 82.81230 83.42746 82.33348 82.38573 83.60137 82.94460 
    ##       81       82       83       84       85       86       87       88 
    ## 83.89564 83.57676 82.10295 80.12235 82.62917 82.52896 81.98832 82.66765 
    ##       89       90       91       92       93       94       95       96 
    ## 82.40264 82.56562 83.73775 83.07851 82.72095 82.64142 83.19472 82.77069 
    ##       97       98       99      100      101      102      103      104 
    ## 83.36686 83.46563 82.14442 83.46093 81.79006 83.61474 83.13258 83.24372 
    ##      105      106      107      108      109      110      111      112 
    ## 83.14052 83.34358 83.09595 83.33025 83.14464 83.65744 83.26275 82.51230 
    ##      113      114      115      116      117      118      119      120 
    ## 82.24623 82.52399 83.36518 83.72779 83.57398 84.27270 83.44984 84.01677 
    ##      121      122      123      124      125      126      127      128 
    ## 82.83686 82.70514 81.92918 82.39072 83.20184 83.44743 82.68706 82.90730 
    ##      129      130      131      132      133      134 
    ## 83.50173 82.63948 83.03906 83.05248 82.73730 78.88588

    ## # A tibble: 1 x 11
    ##   r.squared adj.r.squared sigma statistic p.value    df logLik   AIC   BIC
    ##       <dbl>         <dbl> <dbl>     <dbl>   <dbl> <int>  <dbl> <dbl> <dbl>
    ## 1    0.0708        0.0192  2.73      1.37   0.223     8  -321.  660.  686.
    ## # … with 2 more variables: deviance <dbl>, df.residual <int>

| term                                          | estimate | p.value |
| :-------------------------------------------- | -------: | ------: |
| (Intercept)                                   |   83.342 |   0.000 |
| fuel\_used\_for\_cooking\_percent\_wood\_dung |  \-1.906 |   0.727 |
| percent\_public\_source                       |  \-0.020 |   0.407 |
| percent\_private\_toilet                      |  \-0.003 |   0.649 |
| percent\_employed                             |  \-3.941 |   0.277 |
| percent\_without\_hs\_education               |  \-1.080 |   0.554 |
| percent\_caste                                |    0.027 |   0.328 |
| median\_age                                   |    0.041 |   0.498 |

Gender as a confounder:

    ## 
    ## Call:
    ## lm(formula = dbp ~ fuel_used_for_cooking_percent_wood_dung + 
    ##     percent_public_source + percent_private_toilet + percent_employed + 
    ##     percent_without_hs_education + percent_caste + percent_female, 
    ##     data = total)
    ## 
    ## Residuals:
    ##     Min      1Q  Median      3Q     Max 
    ## -6.1550 -1.8908  0.1156  1.6054  7.1658 
    ## 
    ## Coefficients:
    ##                                          Estimate Std. Error t value
    ## (Intercept)                             85.666227   1.664473  51.467
    ## fuel_used_for_cooking_percent_wood_dung -1.594449   5.434505  -0.293
    ## percent_public_source                   -0.019813   0.024083  -0.823
    ## percent_private_toilet                  -0.001528   0.006177  -0.247
    ## percent_employed                        -4.948370   3.316787  -1.492
    ## percent_without_hs_education            -1.642089   1.591174  -1.032
    ## percent_caste                            0.026604   0.027807   0.957
    ## percent_female                           0.131890   0.462620   0.285
    ##                                         Pr(>|t|)    
    ## (Intercept)                               <2e-16 ***
    ## fuel_used_for_cooking_percent_wood_dung    0.770    
    ## percent_public_source                      0.412    
    ## percent_private_toilet                     0.805    
    ## percent_employed                           0.138    
    ## percent_without_hs_education               0.304    
    ## percent_caste                              0.341    
    ## percent_female                             0.776    
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 2.738 on 126 degrees of freedom
    ## Multiple R-squared:  0.06801,    Adjusted R-squared:  0.01624 
    ## F-statistic: 1.314 on 7 and 126 DF,  p-value: 0.2492

    ##                                            Estimate  Std. Error    t value
    ## (Intercept)                             85.66622680 1.664473214 51.4674710
    ## fuel_used_for_cooking_percent_wood_dung -1.59444923 5.434504987 -0.2933936
    ## percent_public_source                   -0.01981342 0.024083407 -0.8226998
    ## percent_private_toilet                  -0.00152769 0.006176829 -0.2473259
    ## percent_employed                        -4.94836980 3.316786564 -1.4919169
    ## percent_without_hs_education            -1.64208902 1.591173802 -1.0319985
    ## percent_caste                            0.02660425 0.027806969  0.9567476
    ## percent_female                           0.13189043 0.462620326  0.2850943
    ##                                             Pr(>|t|)
    ## (Intercept)                             1.817939e-86
    ## fuel_used_for_cooking_percent_wood_dung 7.697040e-01
    ## percent_public_source                   4.122330e-01
    ## percent_private_toilet                  8.050586e-01
    ## percent_employed                        1.382205e-01
    ## percent_without_hs_education            3.040496e-01
    ## percent_caste                           3.405268e-01
    ## percent_female                          7.760400e-01

    ##                             (Intercept) 
    ##                             85.66622680 
    ## fuel_used_for_cooking_percent_wood_dung 
    ##                             -1.59444923 
    ##                   percent_public_source 
    ##                             -0.01981342 
    ##                  percent_private_toilet 
    ##                             -0.00152769 
    ##                        percent_employed 
    ##                             -4.94836980 
    ##            percent_without_hs_education 
    ##                             -1.64208902 
    ##                           percent_caste 
    ##                              0.02660425 
    ##                          percent_female 
    ##                              0.13189043

    ##        1        2        3        4        5        6        7        8 
    ## 82.90140 82.84971 83.03325 82.72145 83.38339 82.75759 81.99302 85.02442 
    ##        9       10       11       12       13       14       15       16 
    ## 82.90408 83.07409 81.91261 83.11979 82.89047 83.04026 83.25275 81.29552 
    ##       17       18       19       20       21       22       23       24 
    ## 83.18075 82.22414 82.81756 83.20355 81.77496 82.79320 82.65717 82.95484 
    ##       25       26       27       28       29       30       31       32 
    ## 83.30193 82.39110 83.50825 83.21625 82.48615 82.83422 82.99460 83.68514 
    ##       33       34       35       36       37       38       39       40 
    ## 82.61954 83.08026 82.79947 83.61438 84.05938 84.02877 83.50036 82.02347 
    ##       41       42       43       44       45       46       47       48 
    ## 84.10444 83.57112 83.40425 82.77877 83.47966 82.89652 82.89921 83.24777 
    ##       49       50       51       52       53       54       55       56 
    ## 83.38520 83.57939 83.23480 82.88585 83.56030 83.38748 82.64347 83.07159 
    ##       57       58       59       60       61       62       63       64 
    ## 83.05163 82.90875 82.99690 82.85105 81.13438 82.87580 83.69106 83.47869 
    ##       65       66       67       68       69       70       71       72 
    ## 83.00789 82.64541 82.50764 82.75232 82.46330 81.78098 82.89957 83.13233 
    ##       73       74       75       76       77       78       79       80 
    ## 83.80873 81.62127 82.84163 83.28143 82.23705 82.24280 83.19153 82.68639 
    ##       81       82       83       84       85       86       87       88 
    ## 83.80394 83.74575 82.15505 80.09035 82.79771 82.60570 81.87764 82.60998 
    ##       89       90       91       92       93       94       95       96 
    ## 82.49727 82.54610 83.75706 83.30826 82.85100 82.51089 83.07790 82.93319 
    ##       97       98       99      100      101      102      103      104 
    ## 83.50021 83.35403 81.97751 83.34491 81.81311 83.63536 83.02644 83.15827 
    ##      105      106      107      108      109      110      111      112 
    ## 82.91107 83.46456 83.37579 83.33618 83.25583 83.40519 83.35159 82.54348 
    ##      113      114      115      116      117      118      119      120 
    ## 82.57223 82.49770 83.42597 83.60347 83.45674 83.92906 83.31958 83.66955 
    ##      121      122      123      124      125      126      127      128 
    ## 83.00130 83.01180 82.12264 82.59568 83.24622 83.32814 82.67997 82.80070 
    ##      129      130      131      132      133      134 
    ## 83.32479 82.67810 82.92777 83.11022 83.03777 78.91765

    ## # A tibble: 1 x 11
    ##   r.squared adj.r.squared sigma statistic p.value    df logLik   AIC   BIC
    ##       <dbl>         <dbl> <dbl>     <dbl>   <dbl> <int>  <dbl> <dbl> <dbl>
    ## 1    0.0680        0.0162  2.74      1.31   0.249     8  -321.  660.  686.
    ## # … with 2 more variables: deviance <dbl>, df.residual <int>

| term                                          | estimate | p.value |
| :-------------------------------------------- | -------: | ------: |
| (Intercept)                                   |   85.666 |   0.000 |
| fuel\_used\_for\_cooking\_percent\_wood\_dung |  \-1.594 |   0.770 |
| percent\_public\_source                       |  \-0.020 |   0.412 |
| percent\_private\_toilet                      |  \-0.002 |   0.805 |
| percent\_employed                             |  \-4.948 |   0.138 |
| percent\_without\_hs\_education               |  \-1.642 |   0.304 |
| percent\_caste                                |    0.027 |   0.341 |
| percent\_female                               |    0.132 |   0.776 |

Marital status as a confounder:

    ## 
    ## Call:
    ## lm(formula = dbp ~ fuel_used_for_cooking_percent_wood_dung + 
    ##     percent_public_source + percent_private_toilet + percent_employed + 
    ##     percent_without_hs_education + percent_caste + percent_marital_status, 
    ##     data = total)
    ## 
    ## Residuals:
    ##     Min      1Q  Median      3Q     Max 
    ## -6.1590 -1.8945  0.1526  1.6045  7.1617 
    ## 
    ## Coefficients:
    ##                                          Estimate Std. Error t value
    ## (Intercept)                             85.776238   1.632447  52.545
    ## fuel_used_for_cooking_percent_wood_dung -1.581817   5.435554  -0.291
    ## percent_public_source                   -0.019850   0.024097  -0.824
    ## percent_private_toilet                  -0.001660   0.006155  -0.270
    ## percent_employed                        -4.984300   3.346169  -1.490
    ## percent_without_hs_education            -1.654908   1.610964  -1.027
    ## percent_caste                            0.026588   0.027820   0.956
    ## percent_marital_status                   0.002417   0.016566   0.146
    ##                                         Pr(>|t|)    
    ## (Intercept)                               <2e-16 ***
    ## fuel_used_for_cooking_percent_wood_dung    0.772    
    ## percent_public_source                      0.412    
    ## percent_private_toilet                     0.788    
    ## percent_employed                           0.139    
    ## percent_without_hs_education               0.306    
    ## percent_caste                              0.341    
    ## percent_marital_status                     0.884    
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 2.738 on 126 degrees of freedom
    ## Multiple R-squared:  0.06757,    Adjusted R-squared:  0.01577 
    ## F-statistic: 1.304 on 7 and 126 DF,  p-value: 0.2535

    ##                                             Estimate  Std. Error
    ## (Intercept)                             85.776237967 1.632446723
    ## fuel_used_for_cooking_percent_wood_dung -1.581816749 5.435553800
    ## percent_public_source                   -0.019850320 0.024096652
    ## percent_private_toilet                  -0.001659693 0.006154735
    ## percent_employed                        -4.984299830 3.346168724
    ## percent_without_hs_education            -1.654907545 1.610963554
    ## percent_caste                            0.026588188 0.027819798
    ## percent_marital_status                   0.002416838 0.016566264
    ##                                            t value     Pr(>|t|)
    ## (Intercept)                             52.5445865 1.500567e-87
    ## fuel_used_for_cooking_percent_wood_dung -0.2910130 7.715199e-01
    ## percent_public_source                   -0.8237792 4.116216e-01
    ## percent_private_toilet                  -0.2696611 7.878621e-01
    ## percent_employed                        -1.4895542 1.388404e-01
    ## percent_without_hs_education            -1.0272781 3.062576e-01
    ## percent_caste                            0.9557290 3.410393e-01
    ## percent_marital_status                   0.1458891 8.842421e-01

    ##                             (Intercept) 
    ##                            85.776237967 
    ## fuel_used_for_cooking_percent_wood_dung 
    ##                            -1.581816749 
    ##                   percent_public_source 
    ##                            -0.019850320 
    ##                  percent_private_toilet 
    ##                            -0.001659693 
    ##                        percent_employed 
    ##                            -4.984299830 
    ##            percent_without_hs_education 
    ##                            -1.654907545 
    ##                           percent_caste 
    ##                             0.026588188 
    ##                  percent_marital_status 
    ##                             0.002416838

    ##        1        2        3        4        5        6        7        8 
    ## 82.88784 82.85239 83.03161 82.95860 83.38755 82.76083 81.98447 85.02322 
    ##        9       10       11       12       13       14       15       16 
    ## 82.91380 83.07823 81.90846 83.12453 82.89451 83.04334 83.25200 81.28453 
    ##       17       18       19       20       21       22       23       24 
    ## 83.18430 82.22639 82.81966 83.20587 81.77905 82.79570 82.65687 82.95701 
    ##       25       26       27       28       29       30       31       32 
    ## 83.30670 82.39089 83.51770 83.22047 82.48620 82.83829 82.99854 83.69572 
    ##       33       34       35       36       37       38       39       40 
    ## 82.60398 83.08202 82.80416 83.61001 84.07108 83.24321 83.50816 82.02555 
    ##       41       42       43       44       45       46       47       48 
    ## 84.10258 83.56356 83.39735 82.77249 83.47214 82.89971 82.89153 83.23898 
    ##       49       50       51       52       53       54       55       56 
    ## 83.38331 83.58672 83.22712 83.11863 83.56018 83.39446 82.63433 83.07579 
    ##       57       58       59       60       61       62       63       64 
    ## 83.05008 82.90757 82.99922 82.85212 81.13380 82.88051 83.93975 83.48749 
    ##       65       66       67       68       69       70       71       72 
    ## 83.00810 82.64867 82.50919 82.75422 82.46493 81.77592 82.89376 83.13860 
    ##       73       74       75       76       77       78       79       80 
    ## 83.81856 81.61548 82.84274 83.28753 82.23859 82.24113 83.19688 82.67517 
    ##       81       82       83       84       85       86       87       88 
    ## 83.79976 83.74327 82.15902 80.08851 82.80243 82.60787 81.87276 82.61303 
    ##       89       90       91       92       93       94       95       96 
    ## 82.49747 82.54830 83.76812 83.30265 82.85510 82.51009 83.08471 82.94006 
    ##       97       98       99      100      101      102      103      104 
    ## 83.49606 83.35908 81.97338 83.33867 81.80903 83.63107 83.01706 83.15262 
    ##      105      106      107      108      109      110      111      112 
    ## 82.90261 83.45823 83.38127 83.32792 83.26003 83.40920 83.35614 82.53874 
    ##      113      114      115      116      117      118      119      120 
    ## 82.55909 82.50080 83.43208 83.60863 83.46430 83.94007 83.31237 83.67408 
    ##      121      122      123      124      125      126      127      128 
    ## 83.00386 83.00496 82.12665 82.59830 83.23937 83.33776 82.68337 82.80481 
    ##      129      130      131      132      133      134 
    ## 83.33465 82.68312 82.93302 83.11666 83.02661 78.91881

    ## # A tibble: 1 x 11
    ##   r.squared adj.r.squared sigma statistic p.value    df logLik   AIC   BIC
    ##       <dbl>         <dbl> <dbl>     <dbl>   <dbl> <int>  <dbl> <dbl> <dbl>
    ## 1    0.0676        0.0158  2.74      1.30   0.254     8  -321.  660.  686.
    ## # … with 2 more variables: deviance <dbl>, df.residual <int>

| term                                          | estimate | p.value |
| :-------------------------------------------- | -------: | ------: |
| (Intercept)                                   |   85.776 |   0.000 |
| fuel\_used\_for\_cooking\_percent\_wood\_dung |  \-1.582 |   0.772 |
| percent\_public\_source                       |  \-0.020 |   0.412 |
| percent\_private\_toilet                      |  \-0.002 |   0.788 |
| percent\_employed                             |  \-4.984 |   0.139 |
| percent\_without\_hs\_education               |  \-1.655 |   0.306 |
| percent\_caste                                |    0.027 |   0.341 |
| percent\_marital\_status                      |    0.002 |   0.884 |

Full model:

    ## 
    ## Call:
    ## lm(formula = dbp ~ fuel_used_for_cooking_percent_wood_dung + 
    ##     percent_public_source + percent_private_toilet + percent_employed + 
    ##     percent_without_hs_education + percent_caste + median_age + 
    ##     percent_female + percent_marital_status, data = total)
    ## 
    ## Residuals:
    ##     Min      1Q  Median      3Q     Max 
    ## -6.1063 -1.7159  0.1151  1.5832  7.1919 
    ## 
    ## Coefficients:
    ##                                          Estimate Std. Error t value
    ## (Intercept)                             83.330946   4.019182  20.733
    ## fuel_used_for_cooking_percent_wood_dung -1.912130   5.490215  -0.348
    ## percent_public_source                   -0.020060   0.024244  -0.827
    ## percent_private_toilet                  -0.002713   0.006517  -0.416
    ## percent_employed                        -4.012456   3.715342  -1.080
    ## percent_without_hs_education            -1.032857   1.851311  -0.558
    ## percent_caste                            0.027418   0.028012   0.979
    ## median_age                               0.040190   0.062537   0.643
    ## percent_female                           0.116323   0.466785   0.249
    ## percent_marital_status                   0.000601   0.016970   0.035
    ##                                         Pr(>|t|)    
    ## (Intercept)                               <2e-16 ***
    ## fuel_used_for_cooking_percent_wood_dung    0.728    
    ## percent_public_source                      0.410    
    ## percent_private_toilet                     0.678    
    ## percent_employed                           0.282    
    ## percent_without_hs_education               0.578    
    ## percent_caste                              0.330    
    ## median_age                                 0.522    
    ## percent_female                             0.804    
    ## percent_marital_status                     0.972    
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 2.755 on 124 degrees of freedom
    ## Multiple R-squared:  0.07129,    Adjusted R-squared:  0.003884 
    ## F-statistic: 1.058 on 9 and 124 DF,  p-value: 0.3989

    ##                                              Estimate  Std. Error
    ## (Intercept)                             83.3309462630 4.019181894
    ## fuel_used_for_cooking_percent_wood_dung -1.9121301016 5.490215435
    ## percent_public_source                   -0.0200598083 0.024243759
    ## percent_private_toilet                  -0.0027130617 0.006517217
    ## percent_employed                        -4.0124558718 3.715341895
    ## percent_without_hs_education            -1.0328574693 1.851310911
    ## percent_caste                            0.0274180151 0.028012013
    ## median_age                               0.0401899198 0.062536927
    ## percent_female                           0.1163227959 0.466785010
    ## percent_marital_status                   0.0006009671 0.016970479
    ##                                            t value     Pr(>|t|)
    ## (Intercept)                             20.7333105 4.066778e-42
    ## fuel_used_for_cooking_percent_wood_dung -0.3482796 7.282208e-01
    ## percent_public_source                   -0.8274216 4.095877e-01
    ## percent_private_toilet                  -0.4162915 6.779164e-01
    ## percent_employed                        -1.0799695 2.822519e-01
    ## percent_without_hs_education            -0.5579060 5.779144e-01
    ## percent_caste                            0.9787949 3.295871e-01
    ## median_age                               0.6426590 5.216319e-01
    ## percent_female                           0.2491999 8.036184e-01
    ## percent_marital_status                   0.0354125 9.718078e-01

    ##                             (Intercept) 
    ##                           83.3309462630 
    ## fuel_used_for_cooking_percent_wood_dung 
    ##                           -1.9121301016 
    ##                   percent_public_source 
    ##                           -0.0200598083 
    ##                  percent_private_toilet 
    ##                           -0.0027130617 
    ##                        percent_employed 
    ##                           -4.0124558718 
    ##            percent_without_hs_education 
    ##                           -1.0328574693 
    ##                           percent_caste 
    ##                            0.0274180151 
    ##                              median_age 
    ##                            0.0401899198 
    ##                          percent_female 
    ##                            0.1163227959 
    ##                  percent_marital_status 
    ##                            0.0006009671

    ##        1        2        3        4        5        6        7        8 
    ## 82.69139 82.78562 83.10266 82.90276 83.65461 82.60543 82.23685 85.03553 
    ##        9       10       11       12       13       14       15       16 
    ## 83.15482 82.88523 82.00517 82.87534 82.79515 82.72831 83.30920 81.44953 
    ##       17       18       19       20       21       22       23       24 
    ## 83.17135 82.08678 83.00347 83.06045 81.91992 82.74245 82.64499 83.05214 
    ##       25       26       27       28       29       30       31       32 
    ## 83.19951 82.39151 83.41566 83.21150 82.58168 82.80810 82.72138 83.59128 
    ##       33       34       35       36       37       38       39       40 
    ## 82.42925 83.12504 82.77962 83.45172 84.14029 84.03554 83.46986 82.10950 
    ##       41       42       43       44       45       46       47       48 
    ## 84.28805 83.57013 83.29588 82.75694 83.56346 82.94300 83.04482 83.23322 
    ##       49       50       51       52       53       54       55       56 
    ## 83.42628 83.70251 83.59404 83.06695 83.81112 83.51983 82.68519 82.75987 
    ##       57       58       59       60       61       62       63       64 
    ## 82.69906 82.74068 82.61090 82.63638 81.29265 82.83821 84.04846 83.45406 
    ##       65       66       67       68       69       70       71       72 
    ## 82.81467 82.65485 82.45851 82.64911 82.42019 81.85368 82.90417 83.25416 
    ##       73       74       75       76       77       78       79       80 
    ## 83.78941 81.68590 82.78820 83.41637 82.33166 82.38529 83.56838 82.93042 
    ##       81       82       83       84       85       86       87       88 
    ## 83.89199 83.57891 82.10626 80.12380 82.61880 82.51503 81.97684 82.65430 
    ##       89       90       91       92       93       94       95       96 
    ## 82.39645 82.55920 83.71990 83.08122 82.71699 82.64195 83.17726 82.74977 
    ##       97       98       99      100      101      102      103      104 
    ## 83.37173 83.44678 82.14720 83.45223 81.80557 83.61517 83.12976 83.25193 
    ##      105      106      107      108      109      110      111      112 
    ## 83.12654 83.34322 83.09634 83.33437 83.13995 83.62922 83.26803 82.51604 
    ##      113      114      115      116      117      118      119      120 
    ## 82.28005 82.53249 83.35455 83.71605 83.55189 84.24383 83.44679 83.99381 
    ##      121      122      123      124      125      126      127      128 
    ## 82.82693 82.71277 81.92011 82.38841 83.19953 83.44088 82.69180 82.89449 
    ##      129      130      131      132      133      134 
    ## 83.47422 82.61278 83.01382 83.03867 82.75161 78.88454

    ## # A tibble: 1 x 11
    ##   r.squared adj.r.squared sigma statistic p.value    df logLik   AIC   BIC
    ##       <dbl>         <dbl> <dbl>     <dbl>   <dbl> <int>  <dbl> <dbl> <dbl>
    ## 1    0.0713       0.00388  2.75      1.06   0.399    10  -321.  663.  695.
    ## # … with 2 more variables: deviance <dbl>, df.residual <int>

| term                                          | estimate | p.value |
| :-------------------------------------------- | -------: | ------: |
| (Intercept)                                   |   83.331 |   0.000 |
| fuel\_used\_for\_cooking\_percent\_wood\_dung |  \-1.912 |   0.728 |
| percent\_public\_source                       |  \-0.020 |   0.410 |
| percent\_private\_toilet                      |  \-0.003 |   0.678 |
| percent\_employed                             |  \-4.012 |   0.282 |
| percent\_without\_hs\_education               |  \-1.033 |   0.578 |
| percent\_caste                                |    0.027 |   0.330 |
| median\_age                                   |    0.040 |   0.522 |
| percent\_female                               |    0.116 |   0.804 |
| percent\_marital\_status                      |    0.001 |   0.972 |
