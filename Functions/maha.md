## Mahalanobis Distances for Spectral Data

```r

maha <-function(X,std=TRUE){
  library(MASS)
  if (std){
    print("The data is Standardized")
    S<-cov(X)
    SInv<-ginv(S)
    maha_dist<-rep(NA,nrow(X))
    center<-rep(0,ncol(X))
    for(i in 1:nrow(X)){
      maha_dist[i]<-mahalanobis(X[i,],center = center,cov = SInv, inverted = TRUE)
      print(paste0("Mahalanobis distance for row ",i," is ",maha_dist[i]))
    }
  } 
  else {
    print("The data is Not Standardized")
    Xs=scale(X, center = TRUE,scale = TRUE)
    S<-cov(X)
    SInv<-ginv(S)
    maha_dist<-rep(NA,nrow(X))
    center<-rep(0,ncol(X))
    for(i in 1:nrow(X)){
      maha_dist[i]<-mahalanobis(Xs[i,],center = center,cov = SInv, inverted = TRUE)
      print(paste0("Mahalanobis distance for row ",i," is ",maha_dist[i]))
    }
  }
  return(maha_dist)
}
```
