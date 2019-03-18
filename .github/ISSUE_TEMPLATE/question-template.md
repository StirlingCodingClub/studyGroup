---
name: Question template
about: Use this template to structure questions in a way that makes finding solutions
  easier
title: ''
labels: question
assignees: ''

---

Enter a short descriptive title in the title box above.

I suggest keeping some of the headers below and altering the text under each heading.
However, can alter this template in any way you like, but hitting all the points covered will make it easier to get a useful response quickly.

### Issue description

Brief outline of the issue - but try and be precise.
Include any clues you can, such as error messages

### What I have tried

An outline of the things you have tried but failed might serve as a useful start point, or other insight into the problem.

### Reproduce the problem

For the best chance of finding a solution, it helps if others can actually try their ideas on their own computer before offering a solution.
This will often require some representative data, and possibly also any code or functions you have written yourself.

### Including data

Try to include data that can reproduce the problem.
You need not paste your whole research data, instead one of the following options woul be prefered.

+ Suggest a dataset with similar properties that comes with R
  + eg iris / mtcars etc.
  + Benefit:
    + Quick and easy for you
    + Everyone already has these datasets
    
+ Provide code that will create a similar dataset
  + See how below
  + Benefits:
    + In doing this you will often hit on the solution yourself
    + Anyone can copy/paste to reproduce
    
+ If you still prefer to use your own data:
  + Post the minimum subset of your own data
  + Trim it down as small as possible.
  + Include only the columns that are directly relevant.
  + Include enough rows to produce either:
    + the same problem.
    + the desired result.
  + If your data is in some way sensitive, you can change the actual data values if you like by:
    + adding some random noise
    + replacing with arbitrary values
  + Often least prefered because others will have to download
    + the `dput` function might be helpful eg `dput(head(data))`


#### How to fake your data

The code chunk below gives an example of how to create a fake dataset that resembles your own data. 
The fake data doesn't have to make sense.
It needs only to have character, number, factors or boolean columns that correspond to the dataset you are currently causing you a problem.
Remember, try to reduce the number of columns to the minimum than reproduces the problem.
Customizing the code below will sometimes be enough, bearing in mind the points just mentioned above.
There are lots of functions and packages that might be useful: `gl`, `combn`, `sample`, `dput`, `data.frame`, `c`, `matrix`, `list`, `package:reprex`

```{r example-fake-data}

d <- expand.grid(id = 1:5, spp = LETTERS[1:5], year = 2000:2004,
                 stringsAsFactors = TRUE) # or FALSE?
d$response  <- rpois(nrow(d), lambda = 100)
d$predicor1 <- rnorm(nrow(d))
d$prdictor2 <- runif(nrow(d))

head(d)

```

### Desired outcome

Finally, it can be really helpful if you can provide an example of your desired result / output.
One option here could be to just create a markdown table:

spp   | year  | value
------|------:|------:
A     | 2000  | 0.1
B     | 2000  | 0.2
C     | 2000  | 0.3
