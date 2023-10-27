## Random sampling from 3 normally distributed poplulations with
  # SAME means (10) and the SAME standard deviations (30).
  # --> Null hypothesis that mu1=mu2 is TRUE.
  # Repeat operation 10,000 times, a sample size of 20, alpha=.05

Groups <- c(rep(1, each=20), rep(2, each=20), rep(3, each=20))  # rep(a, b): repeat a * b times.
Groups
alpha <- 0.05
n.tests <- 10000
data.simul_homode <- data.frame(replicate(n.tests, c(rnorm(n=20, mean=10,sd=30),
                                              rnorm(n=20, mean=10, sd=30),
                                              rnorm(n=20, mean=10, sd=30))))
dim(data.simul_homode) # Result of one sampling -> recorded in one column. 
                       # One sampling with size=20 -> 20 rows per column.
                       # One sampling with size=20 of THREE group -> 60 rows per column. 
                       # One column per one sampling. Repeat sampling 10,000 times, thus 10,000 columns.

lm.results_homode <- lapply(data.simul_homode, function(x) {# Apply function to each column in dataframe.
              lm(x~Groups, data=data.simul_homode)}  )      # Compare x per Group.
ANOVA.results_homode <- lapply(lm.results_homode, anova)
P.values_homode<- sapply(ANOVA.results_homode, function(x) {x$"Pr(>F)"[1]})

# Type I error = (# of tests when P <=0.05) /(# of total tests) 
TypeIerror_homode <- length(which(P.values_homode<=0.05))/n.tests
TypeIerror_homode  # Long run type I error rate, that is \alpha.

hist(P.values_homode,col="firebrick")                      
