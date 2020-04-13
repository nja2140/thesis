Data Cleaning
================

Loading the exposure data

``` r
neighbor_data = 
  read_excel("./Data/temp_data.xlsx", sheet = 2) %>%
  janitor::clean_names() %>% 
  select(-c(x1)) %>% 
    mutate(ceb = as.numeric(ceb),
           median_age = as.numeric(median_age),
           percent_female = as.numeric(percent_female),
           fuel_used_for_cooking_percent_wood_dung = as.numeric(fuel_used_for_cooking_percent_wood_dung),
           percent_public_source = as.numeric(percent_public_source),
           percent_private_toilet = as.numeric(percent_private_toilet),
           percent_employed = as.numeric(percent_employed),
           percent_without_hs_education = as.numeric(percent_without_hs_education),
           percent_marital_status = as.numeric(percent_marital_status),
           percent_caste = as.numeric(percent_caste)
         ) 
```

    ## New names:
    ## * `` -> ...1

``` r
head(neighbor_data)
```

    ## # A tibble: 6 x 10
    ##     ceb median_age percent_female fuel_used_for_c… percent_public_…
    ##   <dbl>      <dbl>          <dbl>            <dbl>            <dbl>
    ## 1     1       43.1          0.702           0                0.0270
    ## 2     2       42.9          0.667           0                0.0789
    ## 3     3       45.3          0.714           0.0278           0.0556
    ## 4     4       47.1          0.7             0                0.154 
    ## 5     5       52.5          0.691           0.0278           0.194 
    ## 6   108       49.8          0.689           0                0.075 
    ## # … with 5 more variables: percent_private_toilet <dbl>,
    ## #   percent_employed <dbl>, percent_without_hs_education <dbl>,
    ## #   percent_marital_status <dbl>, percent_caste <dbl>

Loading and cleaning the outcome data

``` r
outcome_data = 
  read_excel("./Data/temp_data.xlsx", sheet = 3) %>%
  separate(sbp, into = c("sbp", "sbp_sd")) %>% 
  separate(dbp, into = c("dbp", "dbp_sd")) %>% 
  separate(  bmi, into = c("bmi", "bmi_sd")) %>% 
  janitor::clean_names() %>% 
  mutate(ceb = as.numeric(ceb),
         fbg = as.numeric(fbg),
         fbg_sd = as.numeric(fbg_sd),
         sbp = as.numeric(sbp),
         sbp_sd = as.numeric(sbp_sd),
         dbp = as.numeric(dbp),
         dbp_sd = as.numeric(dbp_sd),
         bmi = as.numeric(bmi),
         bmi_sd = as.numeric(bmi_sd),
         hypertension = as.numeric(hypertension),
         diabetes = as.numeric(diabetes)
         ) %>% 
  select(ceb, fbg, sbp, dbp, bmi)
outcome_data
```

    ## # A tibble: 134 x 5
    ##      ceb   fbg   sbp   dbp   bmi
    ##    <dbl> <dbl> <dbl> <dbl> <dbl>
    ##  1     1 123.    127    85    26
    ##  2     2 110.    126    82    26
    ##  3     3 111.    127    84    25
    ##  4     4 113.    137    84    26
    ##  5     5 113.    132    86    24
    ##  6   108 117     134    85    27
    ##  7   110 118.    130    85    29
    ##  8     6  98.6   126    83    23
    ##  9     7 154.    132    85    24
    ## 10     8 106.    126    85    25
    ## # … with 124 more rows

Categorizing BMI, FBG

``` r
outcome_two_data=
  outcome_data %>% 
  mutate(bmi_cat = ifelse(bmi >=25, "obese", 
                          ifelse(bmi>=23 & bmi<=24.9, "overweight",
                          "normal")),
         fbg_cat = ifelse(fbg >=126, "diabetes", 
                          ifelse(fbg>=110 & fbg<=125.9, "prediabetes",
                          "normal")),
         hyp_cat = ifelse(sbp <120 | dbp<80, "normal", 
                          ifelse(sbp>=120 & fbg<=155.9 | dbp>=90 & fbg<=99.9, "hypertensive",
                          "hypertension"))
         )
outcome_two_data
```

    ## # A tibble: 134 x 8
    ##      ceb   fbg   sbp   dbp   bmi bmi_cat    fbg_cat     hyp_cat     
    ##    <dbl> <dbl> <dbl> <dbl> <dbl> <chr>      <chr>       <chr>       
    ##  1     1 123.    127    85    26 obese      prediabetes hypertensive
    ##  2     2 110.    126    82    26 obese      normal      hypertensive
    ##  3     3 111.    127    84    25 obese      prediabetes hypertensive
    ##  4     4 113.    137    84    26 obese      prediabetes hypertensive
    ##  5     5 113.    132    86    24 overweight prediabetes hypertensive
    ##  6   108 117     134    85    27 obese      prediabetes hypertensive
    ##  7   110 118.    130    85    29 obese      prediabetes hypertensive
    ##  8     6  98.6   126    83    23 overweight normal      hypertensive
    ##  9     7 154.    132    85    24 overweight diabetes    hypertensive
    ## 10     8 106.    126    85    25 obese      normal      hypertensive
    ## # … with 124 more rows

Merge outcome\_two\_data and neighbor\_data

``` r
total= merge(neighbor_data, outcome_two_data, by="ceb") %>% 
  mutate(bmi_cat = factor(bmi_cat, levels = c("normal", "overweight", "obese")),
         fbg_cat = factor(fbg_cat, levels = c("normal", "prediabetes", "diabetes")),
         hyp_cat = factor(hyp_cat, levels = c("normal", "hypertensive", "hypertension"))
         )

head(total)
```

    ##   ceb median_age percent_female fuel_used_for_cooking_percent_wood_dung
    ## 1   1   43.08108      0.7017544                              0.00000000
    ## 2   2   42.89474      0.6666667                              0.00000000
    ## 3   3   45.33333      0.7142857                              0.02777778
    ## 4   4   47.07692      0.7000000                              0.00000000
    ## 5   5   52.50000      0.6909091                              0.02777778
    ## 6   6   38.35897      0.6551724                              0.00000000
    ##   percent_public_source percent_private_toilet percent_employed
    ## 1            0.02702703            100.0000000        0.5405405
    ## 2            0.07894737              0.7368421        0.5789474
    ## 3            0.05555556              0.4722222        0.4444444
    ## 4            0.15384615              0.7692308        0.6153846
    ## 5            0.19444444              0.8333333        0.3888889
    ## 6            0.30769231              0.7435897        0.5128205
    ##   percent_without_hs_education percent_marital_status percent_caste   fbg
    ## 1                   0.02702703              0.8108108     0.5675676 123.4
    ## 2                   0.02631579              0.7631579     0.2368421 109.8
    ## 3                   0.30555556              0.8947368     0.7500000 111.4
    ## 4                   0.00000000            100.0000000     0.4615385 113.1
    ## 5                   0.25000000              0.9166667     0.3888889 112.8
    ## 6                   0.28205128              0.7435897     0.4871795  98.6
    ##   sbp dbp bmi    bmi_cat     fbg_cat      hyp_cat
    ## 1 127  85  26      obese prediabetes hypertensive
    ## 2 126  82  26      obese      normal hypertensive
    ## 3 127  84  25      obese prediabetes hypertensive
    ## 4 137  84  26      obese prediabetes hypertensive
    ## 5 132  86  24 overweight prediabetes hypertensive
    ## 6 126  83  23 overweight      normal hypertensive
