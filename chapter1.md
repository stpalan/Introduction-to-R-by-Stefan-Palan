---
title       : Simple plots
description : This chapter will cover how to create simple plots.
---
## Your first plot in R

```yaml
type: NormalExercise
key: 82cd86ba50
lang: r
xp: 100
skills: 1
```

Now that you understand variables and data structures in R, it is time we started presenting information. Know the proverb *a picture says more than a thousand words*? Well, I agree. So let's start exploring R's capabilities when it comes to illustrating data.


`@instructions`
I have created a vector called `EvenNumbers`, which contains the values 0, 2, 4, 6, 8 and 10. Don't believe me? Type `EvenNumbers` to check!

You should now try to plot the contents of `EvenNumbers`. To do so, simply type `plot(EvenNumbers)` and see what happens!

`@hint`
First type `EvenNumbers`, then type `plot(EvenNumbers)`. Make sure you capitalize the E and the N in `EvenNumbers`. Then run your code!

`@pre_exercise_code`
```{r}
EvenNumbers<-seq(0,10,2)
```

`@sample_code`
```{r}
# First view the contents of EvenNumbers.


# Then use 'plot(EvenNumbers)' to graphically present the numbers in 'EvenNumbers'.

```

`@solution`
```{r}
EvenNumbers
plot(EvenNumbers)
```

`@sct`
```{r}
test_error()
test_output_contains("EvenNumbers", incorrect_msg = "You have not displayed the contents of `EvenNumbers`. Make sure you do so under the first instruction.")
test_function("plot", incorrect_msg = "You have forgotten to plot EvenNumbers!")
success_msg("Excellent, your first R plot! R has taken the contents of `EvenNumbers` and plotted it on the vertical axis, using a simple index (running from 1 to 6, for the six numbers in `EvenNumbers`) for the horizontal axis.

Now - despite this success, you are not happy with how the figure looks? Well, let's see about that in the next exercise ...")
```

---
## Plotting a sine wave

```yaml
type: NormalExercise
key: 9476388da9
lang: r
xp: 100
skills: 1
```

Now that you have whet your appetite with a first plot, let's plot something nicer to look at than six simple numbers. How about that sine wave you learnt about in highschool? Let's try to plot that!

`@instructions`
First we need to create the *grid*, i.e., the x-coordinates over which we are going to plot our function. We are going to do this by creating a variable `x` which we will fill by numbers incrementing from zero to two times pi (yes, the same pi we use to calculate the area of a circle). Why two times pi? Because that will give us one full sine wave. We do this by assigning to `x` the numbers 0, 0.1, 0.2, etc.

Once that is done, we can define `y` as the sine of `x` and plot the outcome.

`@hint`
First, calculate and save in `y` the sine of `x` by assigning the outcome of `sin(x)` to `y`.

Then, plot the outcome using `plot(x,y)`.

`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}
# First we fill x by numbers running from 0 to two times pi in steps of 0.1.
x <- seq(from = 0, by = 0.1, to = 2 * pi)

# Then, we calculate y as the sine of `x`, using the built-in function `sin()`.


# Finally, we plot the result, sending both the x and the y variables to the `plot()` function. The first argument of the function (the first variable name there) will be interpreted as the x-coordinate, the second as the y-coordinate.

```

`@solution`
```{r}
x <- seq(from = 0, by = 0.1, to = 2 * pi)
y <- sin(x)
plot(x, y)
```

`@sct`
```{r}
test_function("sin", incorrect_msg = "You need to use the `sin()` function to calculate the sine of `x`!")
#test_function("plot", incorrect_msg = "You need to use the `plot()` function to plot your sine wave!")
test_object("y", incorrect_msg = "Something is wrong with `y`. Make sure you've assigned the sine of x to the variable.")
test_function("plot", args = c("x", "y"))
#test_output_contains("plot(x,y)", incorrect_msg = "You have not correctly plotted the sine wave. Make sure you specify both the `x` and the `y` coordinate in the `plot()` function.")
success_msg("Good work! Your highschool teacher would be proud of you!")
```

---
## Changing plot format

```yaml
type: NormalExercise
key: 4429362060
lang: r
xp: 100
skills: 1
```

While it is nice to see that sine function plot, nobody plots continuous functions using separate dots. Let's use a continuous line instead, why don't we?

`@instructions`
To change the appeareance of a plot, we can add *options* to the plot function call. These are additional parameters, telling R how to format the plot output.

Here, we want R to format your data as a line instead of as individual dots. You do this by specifying the `type` parameter as `type="l"`. Note that this is a lower case "L" in the quotes, not the number "one". I have already prepared this for you in the script window. Put your cursor into the first line of code and hit <CTRL>-<ENTER> to run this piece of code.

`@hint`
The solution in this case is already prepared for you and you just need to submit it.

`@pre_exercise_code`
```{r}
x <- seq(from = 0, by = 0.1, to = 2 * pi)
y <- sin(x)
```

`@sample_code`
```{r}
plot(x, y, type = "l") #Plots y over x as a line graph

```

`@solution`
```{r}
plot(x, y, type = "l")
```

`@sct`
```{r}
test_function("plot", args = c("x", "y", "type"))

success_msg("Very nice - this looks like a proper graph of a sine wave!")
```

---
## Adding labels

```yaml
type: NormalExercise
key: 4429362060
lang: r
xp: 100
skills: 1
```

Now that our plot looks like a proper sine wave, we should add a title and particularly axis labels to your plot - remember how your highschool teacher used to nag you about those?

`@instructions`
Add a graph title and axis labels to your plot.
  * Add the graph title "Sine wave", using the option `main`
  * Add a label "X" for the horizontal axis, using the option `xlab`
  * Add a label "sin(X)" for the vertical axis, using the option `ylab`

`@hint`
You can add the title and axis label options by using the argument name and assigning it a value. For the plot title, this would look as follows: `main = "Sine wave"`.

`@pre_exercise_code`
```{r}
x <- seq(from = 0, by = 0.1, to = 2 * pi)
y <- sin(x)
```

`@sample_code`
```{r}
# Add a main title "Sine wave", an x-axis label "X" and a y-axis label "sin(X)" to your plot. Complete the following line of code (don't forget to close the brackets!):
plot(x, y, type = "l", 

```

`@solution`
```{r}
plot(x, y, type = "l", main = "Sine wave", xlab = "X", ylab = "sin(X)")
```

`@sct`
```{r}
test_function("plot", args = c("x","y","type", "main","xlab","ylab"))

success_msg("Good job, your highschool teacher would be proud of you!")
```

---
## Colored lines

```yaml
type: NormalExercise
key: c740f8f7a3
lang: r
xp: 100
skills: 1
```

We will soon add another plot to our graph. If we do so and again use a black, thin line, it will be hard to distinguish the two plots. So before we add another plot, let's make the sine wave a bit more distinctive by assigning it a color.

`@instructions`
R offers a number of different ways to specify colors. One of them is simply to use one of several pre-defined color names. By assigning a color to our line (in this case "red"), we can cause it to turn red. The relevant parameter in the `plot` function is `col`.

`@hint`
Using `col="blue"` makes the line turn blue. Can you now make the line red?

`@pre_exercise_code`
```{r}
x <- seq(from = 0, by = 0.1, to = 2 * pi)
y <- sin(x)
```

`@sample_code`
```{r}
#Modify the plot function call to plot the line in red
plot(x, y, type = "l", main = "Sine wave", xlab = "X", ylab = "sin(X)")

```

`@solution`
```{r}
plot(x, y, type = "l", main = "Sine wave", xlab = "X", ylab = "sin(X)", col="red")
#plot(x, y, type = "l", main = "Sine wave", xlab = "X", ylab = "sin(X)", col="red", lwd=4)
```

`@sct`
```{r}
test_function("plot", args = c("x","y","type", "main","xlab","ylab","col"))

success_msg("You did it!")
```

---
## Specifying line width

```yaml
type: NormalExercise
key: c740f8f7a3
lang: r
xp: 100
skills: 1
```

The sine wave looks smooth and the color will help distinguish it from the next plot we will add. However, the line would be easier to see if it were a bit thicker. So before we go on, let's make the sine wave a bit more distinctive by increasing line width.

`@instructions`
We can specify the parameter `lwd` to assign a line width to our sine function plot to make it somewhat bolder and more distinctive. The default width is 1. How about setting it to 4 instead?

`@hint`
Using `lwd=2` sets the line's width to 2. Can you now make the line width 4?

`@pre_exercise_code`
```{r}
x <- seq(from = 0, by = 0.1, to = 2 * pi)
y <- sin(x)
```

`@sample_code`
```{r}
#Modify the plot function call to make the line width equal 4
plot(x, y, type = "l", main = "Sine wave", xlab = "X", ylab = "sin(X)")


```

`@solution`
```{r}
#plot(x, y, type = "l", main = "Sine wave", xlab = "X", ylab = "sin(X)", col="red")
plot(x, y, type = "l", main = "Sine wave", xlab = "X", ylab = "sin(X)", col="red", lwd=4)
```

`@sct`
```{r}
test_function("plot", args = c("x","y","type", "main","xlab","ylab","col","lwd"))

success_msg("Excellent, this looks beautiful!")
```

---
## Calculating the cosine

```yaml
type: NormalExercise
key: 9146d0b9e5
lang: r
xp: 100
skills: 1
```

Now that we have a nice plot of the sine function, let's add a cosine function for contrast. To do so, we first need to calculate the cosine.

`@instructions`
We need to calculate the results of the cosine function, `cos()`, evaluated at every element of `x`. Remember that for the sine function, we used `y<-sin(x)`. Can you now do it for the cosine function?

`@hint`
You calculated the sine function using `sin(x)` and assigned it to the variable `x` using the line of code `x <- sin(x)`. Now do the same for the cosine function `cos()` and the variable `z`.

`@pre_exercise_code`
```{r}
x <- seq(from = 0, by = 0.1, to = 2 * pi)
```

`@sample_code`
```{r}
#Calculate the cosine function for all values in x and save it in a vector called z
z <-

```

`@solution`
```{r}
z<-cos(x)
```

`@sct`
```{r}
test_function("cos")
test_object("z")
success_msg("Very good - now we are set to add a second plot to our graph!")
```

---
## Adding a cosine plot

```yaml
type: NormalExercise
key: 9146d0b9e5
lang: r
xp: 100
skills: 1
```

Now that we have calculated the cosine, let's add it to our plot. If we simply used `plot()`, this would create a new plot that would contain *only* the cosine plot, not the sine plot as well. To add a new line to an existing plot, we need the function `lines()`. This function takes the same arguments as `plot()`, yet we do not need to specify the title and axis labels a second time. Making it blue will set it off nicely from the sine function.

`@instructions`
The sample code already contains the correct solution. Make sure you study the solution before submitting it, to understand what we have done.

*Note that here on datacamp, you always need to execute the entire plot-related code at once, since otherwise the later function `lines()` does not have a plot to refer to. Thus, always highlight everything from `plot(...)` down to the line you are working on before pressing <CTRL>-<ENTER> to test your code.*

`@pre_exercise_code`
```{r}
x <- seq(from = 0, by = 0.1, to = 2 * pi)
y <- sin(x)
z <- cos(x)
```

`@sample_code`
```{r}
#We first set up the graph as before, by plotting the sine function
plot(x, y, type = "l", main = "Sine and cosine", xlab = "X", ylab = "sin(X) and cos(x)", col="red", lwd=4)

#The following line then adds a plot of the cosine function (in blue) to the existing plot
lines(x, z, type = "l", col = "blue", lwd = 4)

```

`@solution`
```{r}
plot(x, y, type = "l", main = "Sine and cosine", xlab = "X", ylab = "sin(X) and cos(x)", col="red", lwd=4)
lines(x, z, type = "l", col = "blue", lwd = 4)
```

`@sct`
```{r}
test_function("plot", args = c("x","y","type", "main","xlab","ylab","col","lwd"))
test_function("lines", args = c("x","y","type", "col","lwd"))
success_msg("Awesome, this is quite the plot already!")
```

---
## Adding a legend

```yaml
type: NormalExercise
key: a9cc1d0c87
lang: r
xp: 100
skills: 1
```

Once you have more than one plot in your graph, it is good practice to use a legend to tell viewers what these plots show. So let's add a legend to our graph!

`@instructions`
Drawing a legend in R requires the use of the `legend()`function. Now this function requires multiple pieces of information to produce what we want it to.

1. Where we want the legend to go in the graph. We tell R by specifying the coordinates the upper left corner of the legend should be positioned. In this case: `legend(x=pi, y=1 ...`
2. The labels of the different elements shown in the legend. In this case, our two functions, i.e.: `legend(x=pi, y=1, legend=c("sin(X)", "cos(X)") ...`. Note that we use the `c()` function to combine the two texts into a vector.
3. The colors of the lines to be drawn. In this case: `legend(x=pi, y=1, legend=c("sin(X)", "cos(X)"), col=c("red", "blue") ...`
4. The line width of the lines to be drawn. In this case: `legend(x=pi, y=1, legend=c("sin(X)", "cos(X)"), col=c("red", "blue"), lwd=4)`

Phew, sounds a bit complicated, but you can always use this legend as a reference for future work.

*Note that here on datacamp, you always need to execute the entire plot-related code at once, since otherwise the later functions (`lines()`, `legend()`) do not have a plot to refer to. Thus, always highlight everything from `plot(...)` down to the line you are working on before pressing <CTRL>-<ENTER> to test your code.*

`@pre_exercise_code`
```{r}
x <- seq(from = 0, by = 0.1, to = 2 * pi)
y <- sin(x)
z <- cos(x)
```

`@sample_code`
```{r}
#Re-execute the below two lines to draw the plot
plot(x, y, type = "l", main = "Sine and cosine", xlab = "X", ylab = "sin(X) and cos(x)", col="red", lwd=4)
lines(x, z, type = "l", col = "blue", lwd = 4)

#Study and run the below line of code to add a legend to the plot
legend(x=pi, y=1, legend=c("sin(X)", "cos(X)"), col=c("red", "blue"), lwd=4)

```

`@solution`
```{r}
plot(x, y, type = "l", main = "Sine and cosine", xlab = "X", ylab = "sin(X) and cos(x)", col="red", lwd=4)
lines(x, z, type = "l", col = "blue", lwd = 4)
legend(pi, 1, c("sin(X)", "cos(X)"), col=c("red", "blue"), lwd=4)
```

`@sct`
```{r}
test_function("plot", args = c("x","y","type", "main","xlab","ylab","col","lwd"))
test_function("lines", args = c("x","y","type", "col","lwd"))
test_function("legend", args = c("x","y","legend","col","lwd"))

success_msg("Well done. Now for the final leg of our first excursion through R's plotting capabilities ...")
```

---
## Adding a reference line

```yaml
type: NormalExercise
key: 6a67763317
lang: r
xp: 100
skills: 1
```

As a final flourish, let's add a reference line at y = 0 to the plot.

`@instructions`
Using the `abline()` function lets you quickly draw horizontal or vertical reference lines. You can specify either version by using the `h = Y` or the `v = X` options, where `X` and `Y` stand for the x- and y- coordinate where the line should be positioned.

To make the line a little less prominent, you can specify the line type by using `lty=2` and color it gray.

*Note that here on datacamp, you always need to execute the entire plot-related code at once, since otherwise the later functions (`lines()`, `legend()`, `abline()`) do not have a plot to refer to. Thus, always highlight everything from `plot(...)` down to the line you are working on before pressing <CTRL>-<ENTER> to test your code.*

`@hint`
  * You can specify the position of the line by using the argument `h=0` in the `abline()` call.
  * The line type needs to be specified using the argument `lty=2`.
  * The color of the line can again be specified using the color name, as in `col="gray"`.

*Note that here on datacamp, you always need to execute the entire plot-related code at once, since otherwise the later functions (`lines()`, `legend()`, `abline()`) do not have a plot to refer to. Thus, always highlight everything from `plot(...)` down to the line you are working on before pressing <CTRL>-<ENTER> to test your code.*

`@pre_exercise_code`
```{r}
x <- seq(from = 0, by = 0.1, to = 2 * pi)
y <- sin(x)
z <- cos(x)

#legend(pi, 1, c("sin(X)", "cos(X)"), col=c("red", "blue"), lwd=4)
```

`@sample_code`
```{r}
#Re-execute the below three lines to draw the plot
plot(x, y, type = "l", main = "Sine and cosine", xlab = "X", ylab = "sin(X) and cos(x)", col="red", lwd=4)
lines(x, z, type = "l", col = "blue", lwd = 4)
legend(pi, 1, c("sin(X)", "cos(X)"), col=c("red", "blue"), lwd=4)

#Now draw a horizontal line at Y = 0 with color gray and line type 2
abline( )

```

`@solution`
```{r}
plot(x, y, type = "l", main = "Sine and cosine", xlab = "X", ylab = "sin(X) and cos(x)", col="red", lwd=4)
lines(x, z, type = "l", col = "blue", lwd = 4)
legend(pi, 1, c("sin(X)", "cos(X)"), col=c("red", "blue"), lwd=4)
abline(h = 0, lty = 2, col="gray")
```

`@sct`
```{r}
test_function("plot", args = c("x","y","type", "main","xlab","ylab","col","lwd"))
test_function("lines", args = c("x","y","type", "col","lwd"))
test_function("legend", args = c("x","y","legend","col","lwd"))
test_function("abline", args = c("h","lty","col"))

success_msg("Excellent! You have mastered the essentials of simple plots!")
```
