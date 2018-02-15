lecture 11 section 6
================

``` r
library(bio3d)
library(devtools)
```

    ## Warning: package 'devtools' was built under R version 3.4.2

``` r
devtools::install_bitbucket("Grantlab/bio3d", subdir="ver_devel/bio3d/")
```

    ## Downloading bitbucket repo Grantlab/bio3d@master

    ## Installing bio3d

    ## '/Library/Frameworks/R.framework/Resources/bin/R' --no-site-file  \
    ##   --no-environ --no-save --no-restore --quiet CMD INSTALL  \
    ##   '/private/var/folders/qy/7_f0t6md4xd25wh5v225pfjwzrx9r3/T/RtmpA9Bx0w/devtoolsd3a409f500c/Grantlab-bio3d-64bda8da2ef0/ver_devel/bio3d'  \
    ##   --library='/Users/ktw005/Library/R/3.4/library' --install-tests

    ## 

    ## Reloading installed bio3d

get adenylate kinase stuctures
------------------------------

``` r
aa <- get.seq("1ake_A")
```

    ## Warning in get.seq("1ake_A"): Removing existing file: seqs.fasta

    ## Fetching... Please wait. Done.

``` r
b <- hmmer(aa)
```

Plot search results
-------------------

``` r
hits <- plot(b)
```

    ##   * Possible cutoff values:    180 0 
    ##             Yielding Nhits:    39 174 
    ## 
    ##   * Chosen cutoff value of:    180 
    ##             Yielding Nhits:    39

![](class11-section6_files/figure-markdown_github/unnamed-chunk-2-1.png)

Parse and align structures'
---------------------------

``` r
files <- get.pdb(hits$pdb.id, path = "pdbs", split = TRUE, gzip = TRUE)
```

    ## Warning in get.pdb(hits$pdb.id, path = "pdbs", split = TRUE, gzip = TRUE):
    ## pdbs/3hpq.pdb.gz exists. Skipping download

    ## Warning in get.pdb(hits$pdb.id, path = "pdbs", split = TRUE, gzip = TRUE):
    ## pdbs/4jzk.pdb.gz exists. Skipping download

    ## Warning in get.pdb(hits$pdb.id, path = "pdbs", split = TRUE, gzip = TRUE):
    ## pdbs/1ake.pdb.gz exists. Skipping download

    ## Warning in get.pdb(hits$pdb.id, path = "pdbs", split = TRUE, gzip = TRUE):
    ## pdbs/3hpr.pdb.gz exists. Skipping download

    ## Warning in get.pdb(hits$pdb.id, path = "pdbs", split = TRUE, gzip = TRUE):
    ## pdbs/4x8m.pdb.gz exists. Skipping download

    ## Warning in get.pdb(hits$pdb.id, path = "pdbs", split = TRUE, gzip = TRUE):
    ## pdbs/4x8o.pdb.gz exists. Skipping download

    ## Warning in get.pdb(hits$pdb.id, path = "pdbs", split = TRUE, gzip = TRUE):
    ## pdbs/4x8l.pdb.gz exists. Skipping download

    ## Warning in get.pdb(hits$pdb.id, path = "pdbs", split = TRUE, gzip = TRUE):
    ## pdbs/1e4v.pdb.gz exists. Skipping download

    ## Warning in get.pdb(hits$pdb.id, path = "pdbs", split = TRUE, gzip = TRUE):
    ## pdbs/4ake.pdb.gz exists. Skipping download

    ## Warning in get.pdb(hits$pdb.id, path = "pdbs", split = TRUE, gzip = TRUE):
    ## pdbs/1ank.pdb.gz exists. Skipping download

    ## Warning in get.pdb(hits$pdb.id, path = "pdbs", split = TRUE, gzip = TRUE):
    ## pdbs/5eje.pdb.gz exists. Skipping download

    ## Warning in get.pdb(hits$pdb.id, path = "pdbs", split = TRUE, gzip = TRUE):
    ## pdbs/2eck.pdb.gz exists. Skipping download

    ## Warning in get.pdb(hits$pdb.id, path = "pdbs", split = TRUE, gzip = TRUE):
    ## pdbs/4x8h.pdb.gz exists. Skipping download

    ## Warning in get.pdb(hits$pdb.id, path = "pdbs", split = TRUE, gzip = TRUE):
    ## pdbs/1e4y.pdb.gz exists. Skipping download

    ## Warning in get.pdb(hits$pdb.id, path = "pdbs", split = TRUE, gzip = TRUE):
    ## pdbs/3x2s.pdb.gz exists. Skipping download

    ## Warning in get.pdb(hits$pdb.id, path = "pdbs", split = TRUE, gzip = TRUE):
    ## pdbs/4np6.pdb.gz exists. Skipping download

    ## Warning in get.pdb(hits$pdb.id, path = "pdbs", split = TRUE, gzip = TRUE):
    ## pdbs/4k46.pdb.gz exists. Skipping download

    ## Warning in get.pdb(hits$pdb.id, path = "pdbs", split = TRUE, gzip = TRUE):
    ## pdbs/3gmt.pdb.gz exists. Skipping download

    ## Warning in get.pdb(hits$pdb.id, path = "pdbs", split = TRUE, gzip = TRUE):
    ## pdbs/4pzl.pdb.gz exists. Skipping download

    ## 
      |                                                                       
      |                                                                 |   0%
      |                                                                       
      |==                                                               |   3%
      |                                                                       
      |===                                                              |   5%
      |                                                                       
      |=====                                                            |   8%
      |                                                                       
      |=======                                                          |  11%
      |                                                                       
      |=========                                                        |  13%
      |                                                                       
      |==========                                                       |  16%
      |                                                                       
      |============                                                     |  18%
      |                                                                       
      |==============                                                   |  21%
      |                                                                       
      |=================                                                |  26%
      |                                                                       
      |===================                                              |  29%
      |                                                                       
      |=====================                                            |  32%
      |                                                                       
      |======================                                           |  34%
      |                                                                       
      |========================                                         |  37%
      |                                                                       
      |==========================                                       |  39%
      |                                                                       
      |===========================                                      |  42%
      |                                                                       
      |=============================                                    |  45%
      |                                                                       
      |===============================                                  |  47%
      |                                                                       
      |================================                                 |  50%
      |                                                                       
      |==================================                               |  53%
      |                                                                       
      |====================================                             |  55%
      |                                                                       
      |======================================                           |  58%
      |                                                                       
      |=======================================                          |  61%
      |                                                                       
      |=========================================                        |  63%
      |                                                                       
      |============================================                     |  68%
      |                                                                       
      |==============================================                   |  71%
      |                                                                       
      |================================================                 |  74%
      |                                                                       
      |==================================================               |  76%
      |                                                                       
      |===================================================              |  79%
      |                                                                       
      |====================================================             |  80%
      |                                                                       
      |=====================================================            |  82%
      |                                                                       
      |======================================================           |  83%
      |                                                                       
      |=======================================================          |  84%
      |                                                                       
      |==========================================================       |  89%
      |                                                                       
      |============================================================     |  92%
      |                                                                       
      |==============================================================   |  95%
      |                                                                       
      |==============================================================   |  96%
      |                                                                       
      |===============================================================  |  97%
      |                                                                       
      |================================================================ |  99%
      |                                                                       
      |=================================================================| 100%

``` r
pdbs <- pdbaln(files)
```

    ## Reading PDB files:
    ## pdbs/split_chain/3hpq_A.pdb
    ## pdbs/split_chain/3hpq_B.pdb
    ## pdbs/split_chain/4jzk_A.pdb
    ## pdbs/split_chain/4jzk_B.pdb
    ## pdbs/split_chain/1ake_A.pdb
    ## pdbs/split_chain/1ake_B.pdb
    ## pdbs/split_chain/3hpr_A.pdb
    ## pdbs/split_chain/3hpr_B.pdb
    ## pdbs/split_chain/4x8m_A.pdb
    ## pdbs/split_chain/4x8o_B.pdb
    ## pdbs/split_chain/4x8o_A.pdb
    ## pdbs/split_chain/4x8l_B.pdb
    ## pdbs/split_chain/4x8l_A.pdb
    ## pdbs/split_chain/1e4v_B.pdb
    ## pdbs/split_chain/1e4v_A.pdb
    ## pdbs/split_chain/4ake_A.pdb
    ## pdbs/split_chain/4ake_B.pdb
    ## pdbs/split_chain/1ank_A.pdb
    ## pdbs/split_chain/1ank_B.pdb
    ## pdbs/split_chain/5eje_A.pdb
    ## pdbs/split_chain/5eje_B.pdb
    ## pdbs/split_chain/2eck_B.pdb
    ## pdbs/split_chain/2eck_A.pdb
    ## pdbs/split_chain/4x8h_A.pdb
    ## pdbs/split_chain/1e4y_B.pdb
    ## pdbs/split_chain/1e4y_A.pdb
    ## pdbs/split_chain/3x2s_A.pdb
    ## pdbs/split_chain/3x2s_B.pdb
    ## pdbs/split_chain/4np6_A.pdb
    ## pdbs/split_chain/4np6_B.pdb
    ## pdbs/split_chain/4np6_C.pdb
    ## pdbs/split_chain/4np6_D.pdb
    ## pdbs/split_chain/4k46_A.pdb
    ## pdbs/split_chain/3gmt_A.pdb
    ## pdbs/split_chain/3gmt_B.pdb
    ## pdbs/split_chain/4pzl_A.pdb
    ## pdbs/split_chain/4pzl_B.pdb
    ## pdbs/split_chain/4pzl_D.pdb
    ## pdbs/split_chain/4pzl_C.pdb
    ## .   PDB has ALT records, taking A only, rm.alt=TRUE
    ## ...   PDB has ALT records, taking A only, rm.alt=TRUE
    ## ..   PDB has ALT records, taking A only, rm.alt=TRUE
    ## .   PDB has ALT records, taking A only, rm.alt=TRUE
    ## ..   PDB has ALT records, taking A only, rm.alt=TRUE
    ## .   PDB has ALT records, taking A only, rm.alt=TRUE
    ## .   PDB has ALT records, taking A only, rm.alt=TRUE
    ## .   PDB has ALT records, taking A only, rm.alt=TRUE
    ## .......   PDB has ALT records, taking A only, rm.alt=TRUE
    ## .   PDB has ALT records, taking A only, rm.alt=TRUE
    ## ..........   PDB has ALT records, taking A only, rm.alt=TRUE
    ## .   PDB has ALT records, taking A only, rm.alt=TRUE
    ## .   PDB has ALT records, taking A only, rm.alt=TRUE
    ## ....   PDB has ALT records, taking A only, rm.alt=TRUE
    ## ...
    ## 
    ## Extracting sequences
    ## 
    ## pdb/seq: 1   name: pdbs/split_chain/3hpq_A.pdb 
    ## pdb/seq: 2   name: pdbs/split_chain/3hpq_B.pdb 
    ##    PDB has ALT records, taking A only, rm.alt=TRUE
    ## pdb/seq: 3   name: pdbs/split_chain/4jzk_A.pdb 
    ## pdb/seq: 4   name: pdbs/split_chain/4jzk_B.pdb 
    ## pdb/seq: 5   name: pdbs/split_chain/1ake_A.pdb 
    ##    PDB has ALT records, taking A only, rm.alt=TRUE
    ## pdb/seq: 6   name: pdbs/split_chain/1ake_B.pdb 
    ## pdb/seq: 7   name: pdbs/split_chain/3hpr_A.pdb 
    ##    PDB has ALT records, taking A only, rm.alt=TRUE
    ## pdb/seq: 8   name: pdbs/split_chain/3hpr_B.pdb 
    ##    PDB has ALT records, taking A only, rm.alt=TRUE
    ## pdb/seq: 9   name: pdbs/split_chain/4x8m_A.pdb 
    ## pdb/seq: 10   name: pdbs/split_chain/4x8o_B.pdb 
    ##    PDB has ALT records, taking A only, rm.alt=TRUE
    ## pdb/seq: 11   name: pdbs/split_chain/4x8o_A.pdb 
    ##    PDB has ALT records, taking A only, rm.alt=TRUE
    ## pdb/seq: 12   name: pdbs/split_chain/4x8l_B.pdb 
    ##    PDB has ALT records, taking A only, rm.alt=TRUE
    ## pdb/seq: 13   name: pdbs/split_chain/4x8l_A.pdb 
    ##    PDB has ALT records, taking A only, rm.alt=TRUE
    ## pdb/seq: 14   name: pdbs/split_chain/1e4v_B.pdb 
    ## pdb/seq: 15   name: pdbs/split_chain/1e4v_A.pdb 
    ## pdb/seq: 16   name: pdbs/split_chain/4ake_A.pdb 
    ## pdb/seq: 17   name: pdbs/split_chain/4ake_B.pdb 
    ## pdb/seq: 18   name: pdbs/split_chain/1ank_A.pdb 
    ## pdb/seq: 19   name: pdbs/split_chain/1ank_B.pdb 
    ## pdb/seq: 20   name: pdbs/split_chain/5eje_A.pdb 
    ##    PDB has ALT records, taking A only, rm.alt=TRUE
    ## pdb/seq: 21   name: pdbs/split_chain/5eje_B.pdb 
    ##    PDB has ALT records, taking A only, rm.alt=TRUE
    ## pdb/seq: 22   name: pdbs/split_chain/2eck_B.pdb 
    ## pdb/seq: 23   name: pdbs/split_chain/2eck_A.pdb 
    ## pdb/seq: 24   name: pdbs/split_chain/4x8h_A.pdb 
    ## pdb/seq: 25   name: pdbs/split_chain/1e4y_B.pdb 
    ## pdb/seq: 26   name: pdbs/split_chain/1e4y_A.pdb 
    ## pdb/seq: 27   name: pdbs/split_chain/3x2s_A.pdb 
    ## pdb/seq: 28   name: pdbs/split_chain/3x2s_B.pdb 
    ## pdb/seq: 29   name: pdbs/split_chain/4np6_A.pdb 
    ## pdb/seq: 30   name: pdbs/split_chain/4np6_B.pdb 
    ## pdb/seq: 31   name: pdbs/split_chain/4np6_C.pdb 
    ##    PDB has ALT records, taking A only, rm.alt=TRUE
    ## pdb/seq: 32   name: pdbs/split_chain/4np6_D.pdb 
    ##    PDB has ALT records, taking A only, rm.alt=TRUE
    ## pdb/seq: 33   name: pdbs/split_chain/4k46_A.pdb 
    ##    PDB has ALT records, taking A only, rm.alt=TRUE
    ## pdb/seq: 34   name: pdbs/split_chain/3gmt_A.pdb 
    ## pdb/seq: 35   name: pdbs/split_chain/3gmt_B.pdb 
    ## pdb/seq: 36   name: pdbs/split_chain/4pzl_A.pdb 
    ## pdb/seq: 37   name: pdbs/split_chain/4pzl_B.pdb 
    ##    PDB has ALT records, taking A only, rm.alt=TRUE
    ## pdb/seq: 38   name: pdbs/split_chain/4pzl_D.pdb 
    ## pdb/seq: 39   name: pdbs/split_chain/4pzl_C.pdb

``` r
ids <- basename.pdb(pdbs$id)

plot(pdbs, labels=ids)
```

![](class11-section6_files/figure-markdown_github/parse/align-1.png)

Sequence consercation analysis
------------------------------

``` r
cons <- conserv(pdbs, method="entropy22")

sse <- pdbs2sse(pdbs, ind=1, rm.gaps=FALSE)
```

    ## Extracting SSE from pdbs$sse attribute

``` r
plotb3(cons, sse=sse, ylab="Sequence entropy")
```

![](class11-section6_files/figure-markdown_github/sequence-1.png)

Annotate pdb structures
-----------------------

``` r
anno <- pdb.annotate(ids)
```

    ## Warning in pdb.annotate(ids): ids should be standard 4 character PDB-IDs:
    ## trying first 4 characters...

``` r
print(unique(anno$source))
```

    ## [1] "Escherichia coli"          "Vibrio cholerae"          
    ## [3] "Photobacterium profundum"  "Burkholderia pseudomallei"
    ## [5] "Francisella tularensis"
