AWS EC2 R Shiny Server

```r
─ Session info ───────────────────────────────────────────────────────────────
 setting  value
 version  R version 4.0.2 (2020-06-22)
 os       Ubuntu 18.04.4 LTS
 system   x86_64, linux-gnu
 ui       X11
 language (EN)
 collate  C.UTF-8
 ctype    C.UTF-8
 tz       Etc/UTC
 date     2020-07-21

─ Packages ───────────────────────────────────────────────────────────────────
 package       * version     date       lib source
 askpass         1.1         2019-01-13 [2] CRAN (R 4.0.1)
 assertthat      0.2.1       2019-03-21 [2] CRAN (R 4.0.1)
 backports       1.1.8       2020-06-17 [2] CRAN (R 4.0.1)
 base64enc       0.1-3       2015-07-28 [2] CRAN (R 4.0.1)
 BH              1.72.0-3    2020-01-08 [2] CRAN (R 4.0.1)
 blob            1.2.1       2020-01-20 [2] CRAN (R 4.0.1)
 brew            1.0-6       2011-04-13 [1] CRAN (R 4.0.1)
 broom           0.7.0       2020-07-09 [1] CRAN (R 4.0.2)
 callr           3.4.3       2020-03-28 [2] CRAN (R 4.0.1)
 cellranger      1.1.0       2016-07-27 [2] CRAN (R 4.0.1)
 cli             2.0.2       2020-02-28 [2] CRAN (R 4.0.1)
 clipr           0.7.0       2019-07-23 [2] CRAN (R 4.0.1)
 colorspace      1.4-1       2019-03-18 [2] CRAN (R 4.0.1)
 commonmark      1.7         2018-12-01 [2] CRAN (R 4.0.1)
 compiler        4.0.2       2020-06-23 [4] local
 covr            3.5.0       2020-03-06 [2] CRAN (R 4.0.1)
 crayon          1.3.4       2017-09-16 [2] CRAN (R 4.0.1)
 crosstalk       1.1.0.1     2020-03-13 [2] CRAN (R 4.0.1)
 curl            4.3         2019-12-02 [2] CRAN (R 4.0.1)
 data.table      1.12.8      2019-12-09 [2] CRAN (R 4.0.1)
 DBI             1.1.0       2019-12-15 [2] CRAN (R 4.0.1)
 dbplyr          1.4.4       2020-05-27 [2] CRAN (R 4.0.1)
 desc            1.2.0       2018-05-01 [2] CRAN (R 4.0.1)
 devtools        2.3.0       2020-04-10 [1] CRAN (R 4.0.1)
 digest          0.6.25      2020-02-23 [2] CRAN (R 4.0.1)
 dplyr           1.0.0       2020-05-29 [2] CRAN (R 4.0.1)
 DT              0.14        2020-06-24 [2] CRAN (R 4.0.1)
 ellipsis        0.3.1       2020-05-15 [2] CRAN (R 4.0.1)
 evaluate        0.14        2019-05-28 [2] CRAN (R 4.0.1)
 fansi           0.4.1       2020-01-08 [2] CRAN (R 4.0.1)
 farver          2.0.3       2020-01-16 [2] CRAN (R 4.0.1)
 fastmap         1.0.1       2019-10-08 [2] CRAN (R 4.0.1)
 forcats         0.5.0       2020-03-01 [2] CRAN (R 4.0.1)
 fs              1.4.2       2020-06-30 [2] CRAN (R 4.0.2)
 generics        0.0.2       2018-11-29 [2] CRAN (R 4.0.1)
 ggplot2         3.3.2       2020-06-19 [2] CRAN (R 4.0.1)
 gh              1.1.0       2020-01-24 [1] CRAN (R 4.0.1)
 git2r           0.27.1      2020-05-03 [1] CRAN (R 4.0.1)
 glue            1.4.1       2020-05-13 [2] CRAN (R 4.0.1)
 graphics      * 4.0.2       2020-06-23 [4] local
 grDevices     * 4.0.2       2020-06-23 [4] local
 grid            4.0.2       2020-06-23 [4] local
 gtable          0.3.0       2019-03-25 [2] CRAN (R 4.0.1)
 haven           2.3.1       2020-06-01 [1] CRAN (R 4.0.1)
 highr           0.8         2019-03-20 [2] CRAN (R 4.0.1)
 hms             0.5.3       2020-01-08 [2] CRAN (R 4.0.1)
 htmltools       0.5.0       2020-06-16 [2] CRAN (R 4.0.1)
 htmlwidgets     1.5.1       2019-10-08 [2] CRAN (R 4.0.1)
 httpuv          1.5.4       2020-06-06 [1] CRAN (R 4.0.1)
 httr            1.4.1       2019-08-05 [2] CRAN (R 4.0.1)
 ini             0.3.1       2018-05-20 [1] CRAN (R 4.0.1)
 isoband         0.2.2       2020-06-20 [2] CRAN (R 4.0.1)
 jsonlite        1.7.0       2020-06-25 [2] CRAN (R 4.0.2)
 knitr           1.29        2020-06-23 [2] CRAN (R 4.0.1)
 labeling        0.3         2014-08-23 [2] CRAN (R 4.0.1)
 later           1.1.0.1     2020-06-05 [2] CRAN (R 4.0.1)
 lattice         0.20-41     2020-04-02 [4] CRAN (R 4.0.0)
 lazyeval        0.2.2       2019-03-15 [2] CRAN (R 4.0.1)
 lifecycle       0.2.0       2020-03-06 [2] CRAN (R 4.0.1)
 lubridate       1.7.9       2020-06-08 [2] CRAN (R 4.0.1)
 magrittr        1.5         2014-11-22 [2] CRAN (R 4.0.1)
 markdown        1.1         2019-08-07 [2] CRAN (R 4.0.1)
 MASS            7.3-51.6    2020-04-26 [4] CRAN (R 4.0.0)
 Matrix          1.2-18      2019-11-27 [4] CRAN (R 4.0.0)
 memoise         1.1.0       2017-04-21 [2] CRAN (R 4.0.1)
 methods       * 4.0.2       2020-06-23 [4] local
 mgcv            1.8-31      2019-11-09 [4] CRAN (R 4.0.0)
 mime            0.9         2020-02-04 [2] CRAN (R 4.0.1)
 modelr          0.1.8       2020-05-19 [1] CRAN (R 4.0.1)
 mrgsolve        0.10.4      2020-06-19 [1] CRAN (R 4.0.2)
 munsell         0.5.0       2018-06-12 [2] CRAN (R 4.0.1)
 nlme            3.1-148     2020-05-24 [4] CRAN (R 4.0.1)
 NonCompart      0.4.7       2020-05-07 [1] CRAN (R 4.0.2)
 openssl         1.4.2       2020-06-27 [2] CRAN (R 4.0.2)
 parallel        4.0.2       2020-06-23 [4] local
 pillar          1.4.6       2020-07-10 [2] CRAN (R 4.0.2)
 pkgbuild        1.1.0       2020-07-13 [2] CRAN (R 4.0.2)
 pkgconfig       2.0.3       2019-09-22 [2] CRAN (R 4.0.1)
 pkgload         1.1.0       2020-05-29 [2] CRAN (R 4.0.1)
 PKPDmisc        2.1.2       2020-04-07 [1] Github (cran/PKPDmisc@d99608f)
 plyr            1.8.6       2020-03-03 [2] CRAN (R 4.0.1)
 praise          1.0.0       2015-08-11 [2] CRAN (R 4.0.1)
 prettyunits     1.1.1       2020-01-24 [2] CRAN (R 4.0.1)
 processx        3.4.3       2020-07-05 [2] CRAN (R 4.0.2)
 progress        1.2.2       2019-05-16 [2] CRAN (R 4.0.1)
 promises        1.1.1       2020-06-09 [1] CRAN (R 4.0.1)
 ps              1.3.3       2020-05-08 [2] CRAN (R 4.0.1)
 purrr           0.3.4       2020-04-17 [2] CRAN (R 4.0.1)
 R6              2.4.1       2019-11-12 [2] CRAN (R 4.0.1)
 rcmdcheck       1.3.3       2019-05-07 [1] CRAN (R 4.0.1)
 RColorBrewer    1.1-2       2014-12-07 [2] CRAN (R 4.0.1)
 Rcpp            1.0.5       2020-07-06 [1] CRAN (R 4.0.2)
 RcppArmadillo   0.9.900.1.0 2020-06-09 [1] CRAN (R 4.0.2)
 readr           1.3.1       2018-12-21 [1] CRAN (R 4.0.1)
 readxl          1.3.1       2019-03-13 [1] CRAN (R 4.0.1)
 rematch         1.0.1       2016-04-21 [2] CRAN (R 4.0.1)
 rematch2        2.1.2       2020-05-01 [1] CRAN (R 4.0.1)
 remotes         2.1.1       2020-02-15 [1] CRAN (R 4.0.1)
 reprex          0.3.0       2019-05-16 [2] CRAN (R 4.0.1)
 reshape2        1.4.4       2020-04-09 [1] CRAN (R 4.0.1)
 rex             1.2.0       2020-04-21 [2] CRAN (R 4.0.1)
 rlang           0.4.7       2020-07-09 [2] CRAN (R 4.0.2)
 rmarkdown       2.3         2020-06-18 [2] CRAN (R 4.0.1)
 roxygen2        7.1.1       2020-06-27 [1] CRAN (R 4.0.2)
 rprojroot       1.3-2       2018-01-03 [2] CRAN (R 4.0.1)
 rstudioapi      0.11        2020-02-07 [2] CRAN (R 4.0.1)
 rversions       2.0.2       2020-05-25 [1] CRAN (R 4.0.1)
 rvest           0.3.5       2019-11-08 [2] CRAN (R 4.0.1)
 scales          1.1.1       2020-05-11 [2] CRAN (R 4.0.1)
 selectr         0.4-2       2019-11-20 [2] CRAN (R 4.0.1)
 sessioninfo     1.1.1       2018-11-05 [1] CRAN (R 4.0.1)
 shiny           1.5.0       2020-06-23 [1] CRAN (R 4.0.1)
 sourcetools     0.1.7       2018-04-25 [2] CRAN (R 4.0.1)
 splines         4.0.2       2020-06-23 [4] local
 stats         * 4.0.2       2020-06-23 [4] local
 stringi         1.4.6       2020-02-17 [2] CRAN (R 4.0.1)
 stringr         1.4.0       2019-02-10 [2] CRAN (R 4.0.1)
 sys             3.3         2019-08-21 [2] CRAN (R 4.0.1)
 testthat        2.3.2       2020-03-02 [2] CRAN (R 4.0.1)
 tibble          3.0.3       2020-07-10 [2] CRAN (R 4.0.2)
 tidyr           1.1.0       2020-05-20 [1] CRAN (R 4.0.1)
 tidyselect      1.1.0       2020-05-11 [2] CRAN (R 4.0.1)
 tidyverse       1.3.0       2019-11-21 [1] CRAN (R 4.0.1)
 tinytex         0.24        2020-06-20 [2] CRAN (R 4.0.1)
 tools           4.0.2       2020-06-23 [4] local
 usethis         1.6.1       2020-04-29 [1] CRAN (R 4.0.1)
 utf8            1.1.4       2018-05-24 [2] CRAN (R 4.0.1)
 utils         * 4.0.2       2020-06-23 [4] local
 vctrs           0.3.1       2020-06-05 [2] CRAN (R 4.0.1)
 viridisLite     0.3.0       2018-02-01 [2] CRAN (R 4.0.1)
 whisker         0.4         2019-08-28 [2] CRAN (R 4.0.1)
 withr           2.2.0       2020-04-20 [2] CRAN (R 4.0.1)
 xfun            0.15        2020-06-21 [2] CRAN (R 4.0.1)
 xml2            1.3.2       2020-04-23 [2] CRAN (R 4.0.1)
 xopen           1.0.0       2018-09-17 [1] CRAN (R 4.0.1)
 xtable          1.8-4       2019-04-21 [2] CRAN (R 4.0.1)
 yaml            2.2.1       2020-02-01 [2] CRAN (R 4.0.1)
```
