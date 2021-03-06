## Test environments
* local OS X install, R 3.2.0
* ubuntu 12.04 (on travis-ci), R 3.2.0
* win-builder (devel and release)

## R CMD check results
There were no ERRORs or WARNINGs. 

There was 1 NOTE:

* checking R code for possible problems ... NOTE
  Found the following calls to attach():
    File 'devtools/R/package-env.r':
      attach(NULL, name = pkg_env_name(pkg))
    File 'devtools/R/shims.r':
      attach(e, name = "devtools_shims", warn.conflicts = FALSE)

  These are needed because devtools simulates package loading, and hence
  needs to attach environments to the search path.

## Downstream dependencies
I have also run R CMD check on all 29 downstream dependencies of devtools 
(https://github.com/hadley/devtools/blob/master/revdep/summary.md):

* There were 2 failures: 
  
  * REDCapR: This looks to be an SSL connection problem
  * NMF: this failed in the same way previously.

* As far as I can tell, there were no new failures related to changes in 
  devtools.
  
