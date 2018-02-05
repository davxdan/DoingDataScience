Swirl Output
Selection: 12

  |                                                                                                  |   0%

| Whenever you're working with a new dataset, the first thing you should do is look at it! What is the
| format of the data? What are the dimensions? What are the variable names? How are the variables stored?
| Are there missing data? Are there any flaws in the data?

...

  |====                                                                                              |   4%
| This lesson will teach you how to answer these questions and more using R's built-in functions. We'll be
| using a dataset constructed from the United States Department of Agriculture's PLANTS Database
| (http://plants.usda.gov/adv_search.html).

...

  |========                                                                                          |   8%
| I've stored the data for you in a variable called plants. Type ls() to list the variables in your
| workspace, among which should be plants.

> ls()
[1] "ints"   "plants"

| You are really on a roll!

  |============                                                                                      |  12%
| Let's begin by checking the class of the plants variable with class(plants). This will give us a clue as
| to the overall structure of the data.

> class(plants)
[1] "data.frame"

| You are really on a roll!

  |================                                                                                  |  16%
| It's very common for data to be stored in a data frame. It is the default class for data read into R
| using functions like read.csv() and read.table(), which you'll learn about in another lesson.

...

  |====================                                                                              |  20%
| Since the dataset is stored in a data frame, we know it is rectangular. In other words, it has two
| dimensions (rows and columns) and fits neatly into a table or spreadsheet. Use dim(plants) to see exactly
| how many rows and columns we're dealing with.

> dim(plants)
[1] 5166   10

| Keep working like that and you'll get there!

  |========================                                                                          |  24%
| The first number you see (5166) is the number of rows (observations) and the second number (10) is the
| number of columns (variables).

...

  |===========================                                                                       |  28%
| You can also use nrow(plants) to see only the number of rows. Try it out.

> nrow(plants)
[1] 5166

| Your dedication is inspiring!

  |===============================                                                                   |  32%
| ... And ncol(plants) to see only the number of columns.

> ncol(plants)
[1] 10

| You nailed it! Good job!

  |===================================                                                               |  36%
| If you are curious as to how much space the dataset is occupying in memory, you can use
| object.size(plants).

> object.size(plants)
644232 bytes

| You got it!

  |=======================================                                                           |  40%
| Now that we have a sense of the shape and size of the dataset, let's get a feel for what's inside.
| names(plants) will return a character vector of column (i.e. variable) names. Give it a shot.

> names(plants)
 [1] "Scientific_Name"      "Duration"             "Active_Growth_Period" "Foliage_Color"       
 [5] "pH_Min"               "pH_Max"               "Precip_Min"           "Precip_Max"          
 [9] "Shade_Tolerance"      "Temp_Min_F"          

| You nailed it! Good job!

  |===========================================                                                       |  44%
| We've applied fairly descriptive variable names to this dataset, but that won't always be the case. A
| logical next step is to peek at the actual data. However, our dataset contains over 5000 observations
| (rows), so it's impractical to view the whole thing all at once.

...

  |===============================================                                                   |  48%
| The head() function allows you to preview the top of the dataset. Give it a try with only one argument.

> head(plants)
               Scientific_Name          Duration Active_Growth_Period Foliage_Color pH_Min pH_Max
1                  Abelmoschus              <NA>                 <NA>          <NA>     NA     NA
2       Abelmoschus esculentus Annual, Perennial                 <NA>          <NA>     NA     NA
3                        Abies              <NA>                 <NA>          <NA>     NA     NA
4               Abies balsamea         Perennial    Spring and Summer         Green      4      6
5 Abies balsamea var. balsamea         Perennial                 <NA>          <NA>     NA     NA
6                     Abutilon              <NA>                 <NA>          <NA>     NA     NA
  Precip_Min Precip_Max Shade_Tolerance Temp_Min_F
1         NA         NA            <NA>         NA
2         NA         NA            <NA>         NA
3         NA         NA            <NA>         NA
4         13         60        Tolerant        -43
5         NA         NA            <NA>         NA
6         NA         NA            <NA>         NA

| All that hard work is paying off!

  |===================================================                                               |  52%
| Take a minute to look through and understand the output above. Each row is labeled with the observation
| number and each column with the variable name. Your screen is probably not wide enough to view all 10
| columns side-by-side, in which case R displays as many columns as it can on each line before continuing
| on the next.

...

  |=======================================================                                           |  56%
| By default, head() shows you the first six rows of the data. You can alter this behavior by passing as a
| second argument the number of rows you'd like to view. Use head() to preview the first 10 rows of plants.

> head(plants,10)
                     Scientific_Name          Duration Active_Growth_Period Foliage_Color pH_Min pH_Max
1                        Abelmoschus              <NA>                 <NA>          <NA>     NA     NA
2             Abelmoschus esculentus Annual, Perennial                 <NA>          <NA>     NA     NA
3                              Abies              <NA>                 <NA>          <NA>     NA     NA
4                     Abies balsamea         Perennial    Spring and Summer         Green      4    6.0
5       Abies balsamea var. balsamea         Perennial                 <NA>          <NA>     NA     NA
6                           Abutilon              <NA>                 <NA>          <NA>     NA     NA
7               Abutilon theophrasti            Annual                 <NA>          <NA>     NA     NA
8                             Acacia              <NA>                 <NA>          <NA>     NA     NA
9                  Acacia constricta         Perennial    Spring and Summer         Green      7    8.5
10 Acacia constricta var. constricta         Perennial                 <NA>          <NA>     NA     NA
   Precip_Min Precip_Max Shade_Tolerance Temp_Min_F
1          NA         NA            <NA>         NA
2          NA         NA            <NA>         NA
3          NA         NA            <NA>         NA
4          13         60        Tolerant        -43
5          NA         NA            <NA>         NA
6          NA         NA            <NA>         NA
7          NA         NA            <NA>         NA
8          NA         NA            <NA>         NA
9           4         20      Intolerant        -13
10         NA         NA            <NA>         NA

| You are doing so well!

  |===========================================================                                       |  60%
| The same applies for using tail() to preview the end of the dataset. Use tail() to view the last 15 rows.

> tail(plants, 15)
                      Scientific_Name  Duration Active_Growth_Period Foliage_Color pH_Min pH_Max Precip_Min
5152                          Zizania      <NA>                 <NA>          <NA>     NA     NA         NA
5153                 Zizania aquatica    Annual               Spring         Green    6.4    7.4         30
5154   Zizania aquatica var. aquatica    Annual                 <NA>          <NA>     NA     NA         NA
5155                Zizania palustris    Annual                 <NA>          <NA>     NA     NA         NA
5156 Zizania palustris var. palustris    Annual                 <NA>          <NA>     NA     NA         NA
5157                      Zizaniopsis      <NA>                 <NA>          <NA>     NA     NA         NA
5158             Zizaniopsis miliacea Perennial    Spring and Summer         Green    4.3    9.0         35
5159                            Zizia      <NA>                 <NA>          <NA>     NA     NA         NA
5160                     Zizia aptera Perennial                 <NA>          <NA>     NA     NA         NA
5161                      Zizia aurea Perennial                 <NA>          <NA>     NA     NA         NA
5162                 Zizia trifoliata Perennial                 <NA>          <NA>     NA     NA         NA
5163                          Zostera      <NA>                 <NA>          <NA>     NA     NA         NA
5164                   Zostera marina Perennial                 <NA>          <NA>     NA     NA         NA
5165                           Zoysia      <NA>                 <NA>          <NA>     NA     NA         NA
5166                  Zoysia japonica Perennial                 <NA>          <NA>     NA     NA         NA
     Precip_Max Shade_Tolerance Temp_Min_F
5152         NA            <NA>         NA
5153         50      Intolerant         32
5154         NA            <NA>         NA
5155         NA            <NA>         NA
5156         NA            <NA>         NA
5157         NA            <NA>         NA
5158         70      Intolerant         12
5159         NA            <NA>         NA
5160         NA            <NA>         NA
5161         NA            <NA>         NA
5162         NA            <NA>         NA
5163         NA            <NA>         NA
5164         NA            <NA>         NA
5165         NA            <NA>         NA
5166         NA            <NA>         NA

| Your dedication is inspiring!

  |===============================================================                                   |  64%
| After previewing the top and bottom of the data, you probably noticed lots of NAs, which are R's
| placeholders for missing values. Use summary(plants) to get a better feel for how each variable is
| distributed and how much of the dataset is missing.

> summary(plants)
                     Scientific_Name              Duration              Active_Growth_Period
 Abelmoschus                 :   1   Perennial        :3031   Spring and Summer   : 447     
 Abelmoschus esculentus      :   1   Annual           : 682   Spring              : 144     
 Abies                       :   1   Annual, Perennial: 179   Spring, Summer, Fall:  95     
 Abies balsamea              :   1   Annual, Biennial :  95   Summer              :  92     
 Abies balsamea var. balsamea:   1   Biennial         :  57   Summer and Fall     :  24     
 Abutilon                    :   1   (Other)          :  92   (Other)             :  30     
 (Other)                     :5160   NA's             :1030   NA's                :4334     
      Foliage_Color      pH_Min          pH_Max         Precip_Min      Precip_Max         Shade_Tolerance
 Dark Green  :  82   Min.   :3.000   Min.   : 5.100   Min.   : 4.00   Min.   : 16.00   Intermediate: 242  
 Gray-Green  :  25   1st Qu.:4.500   1st Qu.: 7.000   1st Qu.:16.75   1st Qu.: 55.00   Intolerant  : 349  
 Green       : 692   Median :5.000   Median : 7.300   Median :28.00   Median : 60.00   Tolerant    : 246  
 Red         :   4   Mean   :4.997   Mean   : 7.344   Mean   :25.57   Mean   : 58.73   NA's        :4329  
 White-Gray  :   9   3rd Qu.:5.500   3rd Qu.: 7.800   3rd Qu.:32.00   3rd Qu.: 60.00                      
 Yellow-Green:  20   Max.   :7.000   Max.   :10.000   Max.   :60.00   Max.   :200.00                      
 NA's        :4334   NA's   :4327    NA's   :4327     NA's   :4338    NA's   :4338                        
   Temp_Min_F    
 Min.   :-79.00  
 1st Qu.:-38.00  
 Median :-33.00  
 Mean   :-22.53  
 3rd Qu.:-18.00  
 Max.   : 52.00  
 NA's   :4328    

| That's correct!

  |===================================================================                               |  68%
| summary() provides different output for each variable, depending on its class. For numeric data such as
| Precip_Min, summary() displays the minimum, 1st quartile, median, mean, 3rd quartile, and maximum. These
| values help us understand how the data are distributed.

..

  |=======================================================================                           |  72%
| For categorical variables (called 'factor' variables in R), summary() displays the number of times each
| value (or 'level') occurs in the data. For example, each value of Scientific_Name only appears once,
| since it is unique to a specific plant. In contrast, the summary for Duration (also a factor variable)
| tells us that our dataset contains 3031 Perennial plants, 682 Annual plants, etc.

...

  |==========================================================================                        |  76%
| You can see that R truncated the summary for Active_Growth_Period by including a catch-all category
| called 'Other'. Since it is a categorical/factor variable, we can see how many times each value actually
| occurs in the data with table(plants$Active_Growth_Period).

> table(plants$Active_Growth_Period)

Fall, Winter and Spring                  Spring         Spring and Fall       Spring and Summer 
                     15                     144                      10                     447 
   Spring, Summer, Fall                  Summer         Summer and Fall              Year Round 
                     95                      92                      24                       5 

| Great job!

  |==============================================================================                    |  80%
| Each of the functions we've introduced so far has its place in helping you to better understand the
| structure of your data. However, we've left the best for last....

...

  |==================================================================================                |  84%
| Perhaps the most useful and concise function for understanding the *str*ucture of your data is str().
| Give it a try now.

> str(plants)
'data.frame':	5166 obs. of  10 variables:
 $ Scientific_Name     : Factor w/ 5166 levels "Abelmoschus",..: 1 2 3 4 5 6 7 8 9 10 ...
 $ Duration            : Factor w/ 8 levels "Annual","Annual, Biennial",..: NA 4 NA 7 7 NA 1 NA 7 7 ...
 $ Active_Growth_Period: Factor w/ 8 levels "Fall, Winter and Spring",..: NA NA NA 4 NA NA NA NA 4 NA ...
 $ Foliage_Color       : Factor w/ 6 levels "Dark Green","Gray-Green",..: NA NA NA 3 NA NA NA NA 3 NA ...
 $ pH_Min              : num  NA NA NA 4 NA NA NA NA 7 NA ...
 $ pH_Max              : num  NA NA NA 6 NA NA NA NA 8.5 NA ...
 $ Precip_Min          : int  NA NA NA 13 NA NA NA NA 4 NA ...
 $ Precip_Max          : int  NA NA NA 60 NA NA NA NA 20 NA ...
 $ Shade_Tolerance     : Factor w/ 3 levels "Intermediate",..: NA NA NA 3 NA NA NA NA 2 NA ...
 $ Temp_Min_F          : int  NA NA NA -43 NA NA NA NA -13 NA ...

| You are really on a roll!

  |======================================================================================            |  88%
| The beauty of str() is that it combines many of the features of the other functions you've already seen,
| all in a concise and readable format. At the very top, it tells us that the class of plants is
| 'data.frame' and that it has 5166 observations and 10 variables. It then gives us the name and class of
| each variable, as well as a preview of its contents.

...

  |==========================================================================================        |  92%
| str() is actually a very general function that you can use on most objects in R. Any time you want to
| understand the structure of something (a dataset, function, etc.), str() is a good place to start.

...

  |==============================================================================================    |  96%
| In this lesson, you learned how to get a feel for the structure and contents of a new dataset using a
| collection of simple and useful functions. Taking the time to do this upfront can save you time and
| frustration later on in your analysis.

...

  |==================================================================================================| 100%
| Would you like to receive credit for completing this course on Coursera.org?

1: Yes
2: No

Selection: 
ion: 1

| You can exit swirl and return to the R prompt (>) at any time by pressing the Esc key. If you are already at the prompt,
| type bye() to exit and save your progress. When you exit properly, you'll see a short message letting you know you've done
| so.

| When you are at the R prompt (>):
| -- Typing skip() allows you to skip the current question.
| -- Typing play() lets you experiment with R on your own; swirl will ignore what you do...
| -- UNTIL you type nxt() which will regain swirl's attention.
| -- Typing bye() causes swirl to exit. Your progress will be saved.
| -- Typing main() returns you to swirl's main menu.
| -- Typing info() displays these options again.

| Let's get started!

...

| Please choose a course, or type 0 to exit swirl.

1: R Programming
2: Take me to the swirl course repository!

Selection: 1

| Please choose a lesson, or type 0 to return to course menu.

 1: Basic Building Blocks      2: Workspace and Files        3: Sequences of Numbers       4: Vectors                 
 5: Missing Values             6: Subsetting Vectors         7: Matrices and Data Frames   8: Logic                   
 9: Functions                 10: lapply and sapply         11: vapply and tapply         12: Looking at Data         
13: Simulation                14: Dates and Times           15: Base Graphics             

Selection: 13

  |                                                                                                                     |   0%

| One of the great advantages of using a statistical programming language like R is its vast collection of tools for
| simulating random numbers.

...Selection: 13

  |====                                                                                                                 |   3%
| This lesson assumes familiarity with a few common probability distributions, but these topics will only be discussed with
| respect to random number generation. Even if you have no prior experience with these concepts, you should be able to
| complete the lesson and understand the main ideas.

...

  |=======                                                                                                              |   6%
| The first function we'll use to generate random numbers is sample(). Use ?sample to pull up the documentation.

> sample?
+ 
+ f
Error in `?`(sample, f) : 
  no documentation of type ‘sample’ and topic ‘f’ (or error in processing help)
> ?sample

| You are quite good my friend!

  |===========                                                                                                          |   9%
| Let's simulate rolling four six-sided dice: sample(1:6, 4, replace = TRUE).

> sample(1:6, 4 replace=TRUE)
Error: unexpected symbol in "sample(1:6, 4 replace"
> sample(1:6, 4, replace=TRUE)
[1] 1 6 1 2

| You got it!

  |==============                                                                                                       |  12%
| Now repeat the command to see how your result differs. (The probability of rolling the exact same result is (1/6)^4 =
| 0.00077, which is pretty small!)

> sample(1:6, 4, replace=TRUE)
[1] 4 6 1 3

| Keep up the great work!

  |==================                                                                                                   |  15%
| sample(1:6, 4, replace = TRUE) instructs R to randomly select four numbers between 1 and 6, WITH replacement. Sampling with
| replacement simply means that each number is "replaced" after it is selected, so that the same number can show up more than
| once. This is what we want here, since what you roll on one die shouldn't affect what you roll on any of the others.

...

  |=====================                                                                                                |  18%
| Now sample 10 numbers between 1 and 20, WITHOUT replacement. To sample without replacement, simply leave off the 'replace'
| argument.

> sample(1:20, 10)
 [1] 18 17  7 11  5  4 15  9 20 12

| Excellent work!

  |=========================                                                                                            |  21%
| Since the last command sampled without replacement, no number appears more than once in the output.

...

  |============================                                                                                         |  24%
| LETTERS is a predefined variable in R containing a vector of all 26 letters of the English alphabet. Take a look at it now.

> letters
 [1] "a" "b" "c" "d" "e" "f" "g" "h" "i" "j" "k" "l" "m" "n" "o" "p" "q" "r" "s" "t" "u" "v" "w" "x" "y" "z"

| Almost! Try again. Or, type info() for more options.

| Type LETTERS to print its contents to the console.

> LETTERS
 [1] "A" "B" "C" "D" "E" "F" "G" "H" "I" "J" "K" "L" "M" "N" "O" "P" "Q" "R" "S" "T" "U" "V" "W" "X" "Y" "Z"

| You got it right!

  |================================                                                                                     |  27%
| The sample() function can also be used to permute, or rearrange, the elements of a vector. For example, try sample(LETTERS)
| to permute all 26 letters of the English alphabet.

> sample(LETTERS)
 [1] "P" "Z" "H" "I" "K" "N" "F" "X" "V" "Y" "W" "L" "G" "B" "R" "T" "J" "O" "U" "Q" "E" "M" "A" "C" "D" "S"

| You nailed it! Good job!

  |===================================                                                                                  |  30%
| This is identical to taking a sample of size 26 from LETTERS, without replacement. When the 'size' argument to sample() is
| not specified, R takes a sample equal in size to the vector from which you are sampling.

...

  |=======================================                                                                              |  33%
| Now, suppose we want to simulate 100 flips of an unfair two-sided coin. This particular coin has a 0.3 probability of
| landing 'tails' and a 0.7 probability of landing 'heads'.

...

  |===========================================                                                                          |  36%
| Let the value 0 represent tails and the value 1 represent heads. Use sample() to draw a sample of size 100 from the vector
| c(0,1), with replacement. Since the coin is unfair, we must attach specific probabilities to the values 0 (tails) and 1
| (heads) with a fourth argument, prob = c(0.3, 0.7). Assign the result to a new variable called flips.

> flips<-sample(c(0,1),100,replace=TRUE,prob = c(0.3, 0.7))

| Keep working like that and you'll get there!

  |==============================================                                                                       |  39%
| View the contents of the flips variable.

> flips
  [1] 1 0 1 1 1 0 0 0 0 1 1 1 1 1 1 1 1 1 1 0 0 1 1 0 1 1 1 1 0 0 1 1 1 1 1 1 1 0 1 0 1 1 0 1 0 1 1 0 0 0 1 1 1 0 1 1 1 0 0 1 1
 [62] 1 1 1 0 1 1 0 0 1 1 1 1 1 1 1 1 0 1 0 1 1 0 1 0 1 1 1 1 1 1 1 1 1 1 1 0 1 1 1

| Excellent job!

  |==================================================                                                                   |  42%
| Since we set the probability of landing heads on any given flip to be 0.7, we'd expect approximately 70 of our coin flips to
| have the value 1. Count the actual number of 1s contained in flips using the sum() function.

> sum(flips)
[1] 72

| That's a job well done!

  |=====================================================                                                                |  45%
| A coin flip is a binary outcome (0 or 1) and we are performing 100 independent trials (coin flips), so we can use rbinom()
| to simulate a binomial random variable. Pull up the documentation for rbinom() using ?rbinom.

> ?rbinom

| Excellent work!

  |=========================================================                                                            |  48%
| Each probability distribution in R has an r*** function (for "random"), a d*** function (for "density"), a p*** (for
| "probability"), and q*** (for "quantile"). We are most interested in the r*** functions in this lesson, but I encourage you
| to explore the others on your own.

...

  |============================================================                                                         |  52%
| A binomial random variable represents the number of 'successes' (heads) in a given number of independent 'trials' (coin
| flips). Therefore, we can generate a single random variable that represents the number of heads in 100 flips of our unfair
| coin using rbinom(1, size = 100, prob = 0.7). Note that you only specify the probability of 'success' (heads) and NOT the
| probability of 'failure' (tails). Try it now.

> rbinom(1, size = 100, prob = 0.7)
[1] 65

| Excellent job!

  |================================================================                                                     |  55%
| Equivalently, if we want to see all of the 0s and 1s, we can request 100 observations, each of size 1, with success
| probability of 0.7. Give it a try, assigning the result to a new variable called flips2.

> flips2<-rbinom(, size = 100, prob = 0.7)
Error in rbinom(, size = 100, prob = 0.7) : 
  argument "n" is missing, with no default
> flips2<-rbinom(100, size = 1, prob = 0.7)

| You got it right!

  |===================================================================                                                  |  58%
| View the contents of flips2.

> flips2
  [1] 0 1 1 1 0 1 0 0 1 0 1 1 0 1 0 1 1 0 1 1 1 0 1 1 1 1 0 1 1 1 1 0 1 1 1 1 1 1 1 1 0 1 0 1 0 0 1 1 1 0 1 1 1 0 1 0 1 1 0 1 1
 [62] 1 1 1 1 1 0 1 1 0 1 1 1 0 1 1 0 1 1 1 1 0 1 0 1 1 0 1 1 1 1 0 1 1 0 1 0 1 1 1

| Keep up the great work!

  |=======================================================================                                              |  61%
| Now use sum() to count the number of 1s (heads) in flips2. It should be close to 70!

> sum(flips2)
[1] 71

| Perseverance, that's the answer.

  |==========================================================================                                           |  64%
| Similar to rbinom(), we can use R to simulate random numbers from many other probability distributions. Pull up the
| documentation for rnorm() now.

> ?rnorm

| You are amazing!

  |==============================================================================                                       |  67%
| The standard normal distribution has mean 0 and standard deviation 1. As you can see under the 'Usage' section in the
| documentation, the default values for the 'mean' and 'sd' arguments to rnorm() are 0 and 1, respectively. Thus, rnorm(10)
| will generate 10 random numbers from a standard normal distribution. Give it a try.

> rnorm(10)
 [1]  0.081022745  0.101771014  0.535928389 -0.318893359 -0.527325667 -0.005847288 -1.453954824  0.706617670 -1.246200138
[10] -0.194265984

| You're the best!

  |==================================================================================                                   |  70%
| Now do the same, except with a mean of 100 and a standard deviation of 25.

> rnorm(10,mean=100,sd=25)
 [1]  54.95954 104.70780 117.82858 108.33111  85.19262  94.22296 117.89356 112.71117 105.81597 104.04823

| Nice work!

  |=====================================================================================                                |  73%
| Finally, what if we want to simulate 100 *groups* of random numbers, each containing 5 values generated from a Poisson
| distribution with mean 10? Let's start with one group of 5 numbers, then I'll show you how to repeat the operation 100 times
| in a convenient and compact way.

...

  |=========================================================================================                            |  76%
| Generate 5 random values from a Poisson distribution with mean 10. Check out the documentation for rpois() if you need help.

> ?rpois
> rpois(5,mean=10)
Error in rpois(5, mean = 10) : unused argument (mean = 10)
> rpois(5,10)
[1] 10  6 10  8  8

| You got it right!

  |============================================================================================                         |  79%
| Now use replicate(100, rpois(5, 10)) to perform this operation 100 times. Store the result in a new variable called my_pois.

> replicate(100,rpois(5,10))
     [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10] [,11] [,12] [,13] [,14] [,15] [,16] [,17] [,18] [,19] [,20] [,21]
[1,]    5   11    7    9    5   11   11   11    9     7     5    10     6     6    16    13    10    12    12     8     7
[2,]    8    7    8    8    6    9    8    7   14    10     7     8    11    12    12     9    14    10    10     6    11
[3,]   10    7   16   13   17    9    3   13   11    11     9     9    12    15     9     5     6     9    12     6    13
[4,]    8    8   14   11    4    8    7    8   10     8    12     9     9     8     8     7     9    14     9    11     7
[5,]   12   15   10   14   13   14   10    6   10    12    10     7    12     5     8    16    11    14     9    11    10
     [,22] [,23] [,24] [,25] [,26] [,27] [,28] [,29] [,30] [,31] [,32] [,33] [,34] [,35] [,36] [,37] [,38] [,39] [,40] [,41]
[1,]     8    14    11     9    15    13    10     6    12     8    12     6    12    17    10    11     9    10    15     5
[2,]    16    13    16    13     7    17    13     6     7     7    12     9     9    11     5    12    11     3    10    10
[3,]     8    13    12     8    10     7    14    10     9     9     8    18     9     8     8    12    10     5     8    11
[4,]    11     6    11    14    12     6    15    12    13     7    14    10     9     9    10    14     7    13     4     6
[5,]     9    16     6    14    11    15    13     8     6     6     8     8     9     5     4    15    13    15    10     8
     [,42] [,43] [,44] [,45] [,46] [,47] [,48] [,49] [,50] [,51] [,52] [,53] [,54] [,55] [,56] [,57] [,58] [,59] [,60] [,61]
[1,]     6     7    11     7     9    12     3     9    10    12     9     7     4    11    12    11    12    11    14    11
[2,]    11     7     7     6    11     8    11     9    10    16     5    12    10     9     6    13     8    13     8     9
[3,]    10    12    10    13     7    10     9     8     8    14    10     6     9     4    10    13     6    13    12     7
[4,]     9    16     9     9     7     9    12    11    11    11    12    16    12    10     9     9     5    15     7    15
[5,]     5    11     9    11     9     6     9    10     9    15    15    12     9    12     9     2    14    14    10     8
     [,62] [,63] [,64] [,65] [,66] [,67] [,68] [,69] [,70] [,71] [,72] [,73] [,74] [,75] [,76] [,77] [,78] [,79] [,80] [,81]
[1,]     8     7    13     6    10    15     9    11    10    10    10     5    15     7    16    11     8    11     8     3
[2,]    10     9     7    12    13     9    15    12    10     7    10    10     9    16     7    15    11    10    10     8
[3,]    13     6    10    10     8     6     7     9     6    10     5    19     7     8    10     9    13     8     7     9
[4,]     9     8     7     5    11    10    13     8    11    14     9     7    15     4    15    13    13     6    11    10
[5,]    11    10     8     9     6     6    12     8    13    12     9     9    13    10    10     9     8    11     6    12
     [,82] [,83] [,84] [,85] [,86] [,87] [,88] [,89] [,90] [,91] [,92] [,93] [,94] [,95] [,96] [,97] [,98] [,99] [,100]
[1,]     9    15     9    11    11    11    11    17    12    14    12    12     6     5    10    12     7    15     11
[2,]    14     8    11    14     9    10    12    12    12    16    11    14    16     9    11     8    11     7     13
[3,]    14     7    10     5     7    12     9     8    10    15     7     8    13    12    15    15     7     6      7
[4,]     3    13     6    11    10    16     8     9     8     8    10    11    16    13    11     6    14     7      8
[5,]    11     7    11     9     7     6     9     9    15    14    18     9    10    12     6    11     9    14     12

| Try again. Getting it right on the first try is boring anyway! Or, type info() for more options.

| my_pois <- replicate(100, rpois(5, 10)) will repeat the operation 100 times and store the result.

> my_pois<-replicate(100,rpois(5,10))

| That's a job well done!

  |================================================================================================                     |  82%
| Take a look at the contents of my_pois.

> my_pois
     [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10] [,11] [,12] [,13] [,14] [,15] [,16] [,17] [,18] [,19] [,20] [,21]
[1,]   11   17    6    7   13   12    6   10    7     5    10     5     6    13     9     8    11    12    17    10    11
[2,]   18    8    6    7   16   15   12   14   16    10     8     6    12     7    11    11     7    10     6    13    12
[3,]   16    5   14    8    9   11   11   11   11     9    10     7    13     5    14    11    15     7    10     5    14
[4,]    7    8    6   14    8    9   13    4    8    11    13     8    10    11     6     7    14     8     5     8    11
[5,]   11   13    7   12    8    6    7   12   16    14    10    15    14    13    15     7     8     6    10    16    10
     [,22] [,23] [,24] [,25] [,26] [,27] [,28] [,29] [,30] [,31] [,32] [,33] [,34] [,35] [,36] [,37] [,38] [,39] [,40] [,41]
[1,]    13    11     5    15    11    11    13    10     6    12     8     5    11    12     8     8    10     9    17    11
[2,]    13    10    12    13    12     9    11     9     8    11     4     7    10     7     7     7     8    12    13     4
[3,]    12     8    10    16     7     4    10     8     7    13    19    10     9    14     3    11     7     4     6    13
[4,]    13    14     8     8    15    14    14    13    10    14     6    11    11    13    12     6     8    14     5    12
[5,]     7     7    11    10     7     7    10    12    11    14     8    14    10     5     7    12    12    16    11     6
     [,42] [,43] [,44] [,45] [,46] [,47] [,48] [,49] [,50] [,51] [,52] [,53] [,54] [,55] [,56] [,57] [,58] [,59] [,60] [,61]
[1,]     9     9    11     4    15    10    12     8    11     9     7     3    15     9     7     4    13     7     9    13
[2,]     8     6     7    10    10    10    12     9    11     8     6     6     9     9    12    11    10    13     7    10
[3,]    11     7    10    10    15    10    14     9     4     6    10    11     8     9    13     5    11     6    12     8
[4,]    14     7     8    13     7     7    17    11     8    14    10     5    10    15    13     8    11    11     4    13
[5,]     9     9    10    12     6     8    13    10    10     8     8     9    11    13     8     8     5    15    10    13
     [,62] [,63] [,64] [,65] [,66] [,67] [,68] [,69] [,70] [,71] [,72] [,73] [,74] [,75] [,76] [,77] [,78] [,79] [,80] [,81]
[1,]     7     8    10     8     3     9    10     9     7     7    10     8    16    14     9    10    11    14     8    13
[2,]    11    10    12     6     9     7     7    11     8     7    12    10     7    10     4     7     9     7    11    12
[3,]    17    12    10     9    11     8    17    12    10     6     8     7     8    13     5     6     7    12     7    11
[4,]     7    13     6     9     8    10    12    11     5     7    11    10     7    14     9    17    10    16    10    11
[5,]    11     6     8     6    15    11    10     6     5    13     4    11    10    11    10     8    12     5     8     6
     [,82] [,83] [,84] [,85] [,86] [,87] [,88] [,89] [,90] [,91] [,92] [,93] [,94] [,95] [,96] [,97] [,98] [,99] [,100]
[1,]     8    20    12    10     9    13     7    15     9    10     9     9    15    10    10     6    15     9      3
[2,]     7     9    14    15     2    18    11     7    10    11     7     7    10     6    13    14     5    11      3
[3,]    10    13    11    12    13     5     8    10     6    11    22    14    13     9    11    15     7    13     10
[4,]     8    10    17    10    16     7     3    15     7    13     8    13     9     5     6    10    14     8     12
[5,]    11     8    15    10     8    13    13    16     7    10     9     8     6     9    11    14     4    12      7

| You got it!

  |===================================================================================================                  |  85%
| replicate() created a matrix, each column of which contains 5 random numbers generated from a Poisson distribution with mean
| 10. Now we can find the mean of each column in my_pois using the colMeans() function. Store the result in a variable called
| cm.

> cm<-colMeans(my_pois)

| That's the answer I was looking for.

  |=======================================================================================================              |  88%
| And let's take a look at the distribution of our column means by plotting a histogram with hist(cm).

> hist(cm)

| Keep working like that and you'll get there!

  |==========================================================================================================           |  91%
| Looks like our column means are almost normally distributed, right? That's the Central Limit Theorem at work, but that's a
| lesson for another day!

...

  |==============================================================================================================       |  94%
| All of the standard probability distributions are built into R, including exponential (rexp()), chi-squared (rchisq()),
| gamma (rgamma()), .... Well, you see the pattern.

...

  |=================================================================================================================    |  97%
| Simulation is practically a field of its own and we've only skimmed the surface of what's possible. I encourage you to
| explore these and other functions further on your own.

...

  |=====================================================================================================================| 100%
| Would you like to receive credit for completing this course on Coursera.org?

Selection: 14

  |                                                                                                                     |   0%

| R has a special way of representing dates and times, which can be helpful if you're working with data that show how
| something changes over time (i.e. time-series data) or if your data contain some other temporal information, like dates of
| birth.

...

  |===                                                                                                                  |   3%
| Dates are represented by the 'Date' class and times are represented by the 'POSIXct' and 'POSIXlt' classes. Internally,
| dates are stored as the number of days since 1970-01-01 and times are stored as either the number of seconds since
| 1970-01-01 (for 'POSIXct') or a list of seconds, minutes, hours, etc. (for 'POSIXlt').

...

  |======                                                                                                               |   6%
| Let's start by using d1 <- Sys.Date() to get the current date and store it in the variable d1. (That's the letter 'd' and
| the number 1.)

> d1<-sys.date()
Error in sys.date() : could not find function "sys.date"
> d1<-Sys.Date()

| Great job!

  |==========                                                                                                           |   8%
| Use the class() function to confirm d1 is a Date object.

> class(d1)
[1] "Date"

| You are really on a roll!

  |=============                                                                                                        |  11%
| We can use the unclass() function to see what d1 looks like internally. Try it out.

> unclass(d1)
[1] 17559

| You are amazing!

  |================                                                                                                     |  14%
| That's the exact number of days since 1970-01-01!

...

  |====================                                                                                                 |  17%
| However, if you print d1 to the console, you'll get today's date -- YEAR-MONTH-DAY. Give it a try.

> print(d1)
[1] "2018-01-28"

| Almost! Try again. Or, type info() for more options.

| Type d1 to print its contents.

> d1
[1] "2018-01-28"

| All that practice is paying off!

  |=======================                                                                                              |  19%
| What if we need to reference a date prior to 1970-01-01? Create a variable d2 containing as.Date("1969-01-01").

> d2<-as.Date("1969-01-01")

| You nailed it! Good job!

  |==========================                                                                                           |  22%
| Now use unclass() again to see what d2 looks like internally.

> unclass(d2)
[1] -365

| Keep up the great work!

  |=============================                                                                                        |  25%
| As you may have anticipated, you get a negative number. In this case, it's -365, since 1969-01-01 is exactly one calendar
| year (i.e. 365 days) BEFORE 1970-01-01.

...

  |================================                                                                                     |  28%
| Now, let's take a look at how R stores times. You can access the current date and time using the Sys.time() function with no
| arguments. Do this and store the result in a variable called t1.

> Sys.time()
[1] "2018-01-28 12:49:04 EST"

| You almost had it, but not quite. Try again. Or, type info() for more options.

| t1 <- Sys.time() will store the current date and time in a variable called t1.

> t1<-Sys.time()

| Keep up the great work!

  |====================================                                                                                 |  31%
| View the contents of t1.

> t1
[1] "2018-01-28 12:49:11 EST"

| That's a job well done!

  |=======================================                                                                              |  33%
| And check the class() of t1.

> class(t1)
[1] "POSIXct" "POSIXt" 

| Keep up the great work!

  |==========================================                                                                           |  36%
| As mentioned earlier, POSIXct is just one of two ways that R represents time information. (You can ignore the second value
| above, POSIXt, which just functions as a common language between POSIXct and POSIXlt.) Use unclass() to see what t1 looks
| like internally -- the (large) number of seconds since the beginning of 1970.

> unclass(t1)
[1] 1517161752

| Your dedication is inspiring!

  |=============================================                                                                        |  39%
| By default, Sys.time() returns an object of class POSIXct, but we can coerce the result to POSIXlt with
| as.POSIXlt(Sys.time()). Give it a try and store the result in t2.

> t2<- as.POSIXlt(Sys.time())

| You're the best!

  |=================================================                                                                    |  42%
| Check the class of t2.

> class(t2)
[1] "POSIXlt" "POSIXt" 

| All that hard work is paying off!

  |====================================================                                                                 |  44%
| Now view its contents.

> t2
[1] "2018-01-28 12:50:50 EST"

| That's a job well done!

  |=======================================================                                                              |  47%
| The printed format of t2 is identical to that of t1. Now unclass() t2 to see how it is different internally.

> unclass(t2)
$sec
[1] 50.71797

$min
[1] 50

$hour
[1] 12

$mday
[1] 28

$mon
[1] 0

$year
[1] 118

$wday
[1] 0

$yday
[1] 27

$isdst
[1] 0

$zone
[1] "EST"

$gmtoff
[1] -18000

attr(,"tzone")
[1] ""    "EST" "EDT"

| You got it!

  |==========================================================                                                           |  50%
| t2, like all POSIXlt objects, is just a list of values that make up the date and time. Use str(unclass(t2)) to have a more
| compact view.

> str(unclass(t2))
List of 11
 $ sec   : num 50.7
 $ min   : int 50
 $ hour  : int 12
 $ mday  : int 28
 $ mon   : int 0
 $ year  : int 118
 $ wday  : int 0
 $ yday  : int 27
 $ isdst : int 0
 $ zone  : chr "EST"
 $ gmtoff: int -18000
 - attr(*, "tzone")= chr [1:3] "" "EST" "EDT"

| That's correct!

  |==============================================================                                                       |  53%
| If, for example, we want just the minutes from the time stored in t2, we can access them with t2$min. Give it a try.

> t2$min
[1] 50

| You got it!

  |=================================================================                                                    |  56%
| Now that we have explored all three types of date and time objects, let's look at a few functions that extract useful
| information from any of these objects -- weekdays(), months(), and quarters().

...

  |====================================================================                                                 |  58%
| The weekdays() function will return the day of week from any date or time object. Try it out on d1, which is the Date object
| that contains today's date.

> weekdays(d1)
[1] "Sunday"

| All that hard work is paying off!

  |=======================================================================                                              |  61%
| The months() function also works on any date or time object. Try it on t1, which is the POSIXct object that contains the
| current time (well, it was the current time when you created it).

> months(t1)
[1] "January"

| Nice work!

  |===========================================================================                                          |  64%
| The quarters() function returns the quarter of the year (Q1-Q4) from any date or time object. Try it on t2, which is the
| POSIXlt object that contains the time at which you created it.

> quarters(t2)
[1] "Q1"

| That's a job well done!

  |==============================================================================                                       |  67%
| Often, the dates and times in a dataset will be in a format that R does not recognize. The strptime() function can be
| helpful in this situation.

...

  |=================================================================================                                    |  69%
| strptime() converts character vectors to POSIXlt. In that sense, it is similar to as.POSIXlt(), except that the input
| doesn't have to be in a particular format (YYYY-MM-DD).

...

  |====================================================================================                                 |  72%
| To see how it works, store the following character string in a variable called t3: "October 17, 1986 08:24" (with the
| quotes).

> t3<- "October 17, 1986 08:24"

| You nailed it! Good job!

  |========================================================================================                             |  75%
| Now, use strptime(t3, "%B %d, %Y %H:%M") to help R convert our date/time object to a format that it understands. Assign the
| result to a new variable called t4. (You should pull up the documentation for strptime() if you'd like to know more about
| how it works.)

> strptime(t3, "%B %d, %Y %H:%M")
[1] "1986-10-17 08:24:00 EDT"

| You're close...I can feel it! Try it again. Or, type info() for more options.

| t4 <- strptime(t3, "%B %d, %Y %H:%M") will convert our date/time object to a format that R understands.

> t4<-strptime(t3, "%B %d, %Y %H:%M")

| Nice work!

  |===========================================================================================                          |  78%
| Print the contents of t4.

> t4
[1] "1986-10-17 08:24:00 EDT"

| Great job!

  |==============================================================================================                       |  81%
| That's the format we've come to expect. Now, let's check its class().

> class(t4)
[1] "POSIXlt" "POSIXt" 

| You are doing so well!

  |=================================================================================================                    |  83%
| Finally, there are a number of operations that you can perform on dates and times, including arithmetic operations (+ and -)
| and comparisons (<, ==, etc.)

...

  |=====================================================================================================                |  86%
| The variable t1 contains the time at which you created it (recall you used Sys.time()). Confirm that some time has passed
| since you created t1 by using the 'greater than' operator to compare it to the current time: Sys.time() > t1

> Sys.time() > t1
[1] TRUE

| All that practice is paying off!

  |========================================================================================================             |  89%
| So we know that some time has passed, but how much? Try subtracting t1 from the current time using Sys.time() - t1. Don't
| forget the parentheses at the end of Sys.time(), since it is a function.

> Sys.time() - t1
Time difference of 7.849498 mins

| You got it right!

  |===========================================================================================================          |  92%
| The same line of thinking applies to addition and the other comparison operators. If you want more control over the units
| when finding the above difference in times, you can use difftime(), which allows you to specify a 'units' parameter.

...

  |==============================================================================================================       |  94%
| Use difftime(Sys.time(), t1, units = 'days') to find the amount of time in DAYS that has passed since you created t1.

> difftime(Sys.time(), t1, units = 'days')
Time difference of 0.006003699 days

| Nice work!

  |==================================================================================================================   |  97%
| In this lesson, you learned how to work with dates and times in R. While it is important to understand the basics, if you
| find yourself working with dates and times often, you may want to check out the lubridate package by Hadley Wickham.

...

  |=====================================================================================================================| 100%
| Would you like to receive credit for completing this course on Coursera.org?