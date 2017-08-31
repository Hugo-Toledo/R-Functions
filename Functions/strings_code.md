
```sprintf()``` is a useful printing function for precise control of the output. It is a wrapper for the C function sprintf and returns a 
character vector containing a formatted combination of text and variable values.

To substitute in a string or string variable, use ```%s```:
```R
x <- "print strings"

# substitute a single string/variable
sprintf("Learning to %s in R", x)    
## [1] "Learning to print strings in R"

# substitute multiple strings/variables
y <- "in R"
sprintf("Learning to %s %s", x, y)   
## [1] "Learning to print strings in R"
For integers, use %d or a variant:

version <- 3

# substitute integer
sprintf("This is R version:%d", version)
## [1] "This is R version:3"

# print with leading spaces
sprintf("This is R version:%4d", version)   
## [1] "This is R version:   3"

# can also lead with zeros
sprintf("This is R version:%04d", version)   
## [1] "This is R version:0003"
```
For floating-point numbers, use %f for standard notation, and %e or %E for exponential notation:
```
sprintf("%f", pi)         # '%f' indicates 'fixed point' decimal notation
## [1] "3.141593"

sprintf("%.3f", pi)       # decimal notation with 3 decimal digits
## [1] "3.142"

sprintf("%1.0f", pi)      # 1 integer and 0 decimal digits
## [1] "3"

sprintf("%5.1f", pi)      # decimal notation with 5 total decimal digits and 
## [1] "  3.1"            # only 1 to the right of the decimal point

sprintf("%05.1f", pi)     # same as above but fill empty digits with zeros
## [1] "003.1"

sprintf("%+f", pi)        # print with sign (positive)
## [1] "+3.141593"

sprintf("% f", pi)        # prefix a space
## [1] " 3.141593"

sprintf("%e", pi)         # exponential decimal notation 'e'
## [1] "3.141593e+00"

sprintf("%E", pi)         # exponential decimal notation 'E'
## [1] "3.141593E+00"
```
It is posible to create sequences combining numbers and strings
```R
sprintf("_%d",seq(1,15))
tmp<-paste((sprintf("_%d",seq(1,15))),sep = "", collapse = "|")
tmp1=grep(pattern = dobles,x = tmp)
```
