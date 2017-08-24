### Transform Transminances to Absrobances of Spectral Data

```r
TA <-function(X){
    X.a = matrix(NA, nrow = nrow(X), ncol = ncol(X))
    for (i in 1:ncol(X)){
      for (j in 1:nrow(X)){
        X.a[j,i]= log10(1/X[j,i])
        print(paste0("Absorbance for WL ",j))
      }
    }
 return(X.a)
} 
```
