###Transminances to Absrobances in R
```r
load(file="C:/IGP Vittelone/Data/1.0_Data_Edited_labspec.RData")

X.a = matrix(NA, nrow = nrow(X), ncol = ncol(X))

for (i in 1:ncol(X)){
  for (j in 1:nrow(X)){
    
    X.a[j,i]= log10(1/X[j,i])
    print(paste0("Running for WL ",j))
    
  }
}
```