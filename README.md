# Using-SQL-for-R-data.frames-with-sqldf

Let’s create a data.frame with some sample data. I will use iris dataset.

iris <- iris

And load both packages:

library(dplyr)
library(sqldf)

So let’s say we want to get a particular column from dataset that has filtered values. In base R:

iris[iris$Sepal.Width >= 3.0,]$Sepal.Width

using dplyr:

iris %>%
  select(Sepal.Width) %>%
  filter(Sepal.Width>=3.0)

and using sqldf:

sqldf("select [Sepal.Width] from iris
      where
        [Sepal.Width]  >= 3.0")

All in all, it is your flavour of choice, but for convenience, up to you, which one to use.
