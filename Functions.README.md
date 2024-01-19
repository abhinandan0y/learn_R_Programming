#Functions in R: <br />
1. Simple Arithmetic Function:
```R
# Function to add two numbers
add_numbers <- function(a, b) {
  result <- a + b
  return(result)
}

# Usage:
result_sum <- add_numbers(3, 5)
print(result_sum)
```
2. Function with Default Argument:
```R
# Function to calculate the square of a number with a default value
square <- function(x, power = 2) {
  result <- x^power
  return(result)
}

# Usage:
result_square <- square(4)
print(result_square)
```
3. Function with Condition:
```R
# Function to check if a number is even or odd
check_even_odd <- function(x) {
  if (x %% 2 == 0) {
    return("Even")
  } else {
    return("Odd")
  }
}

# Usage:
result_check <- check_even_odd(7)
print(result_check)
```
4. Function Returning Multiple Values:
```R
# Function to calculate mean and standard deviation
calculate_stats <- function(data) {
  mean_val <- mean(data)
  sd_val <- sd(data)
  return(list(mean = mean_val, sd = sd_val))
}

# Usage:
data <- c(2, 4, 6, 8, 10)
result_stats <- calculate_stats(data)
print(result_stats$mean)
print(result_stats$sd)
```
5. Recursive Function:
```R
# Recursive function to calculate factorial
factorial <- function(n) {
  if (n == 0 || n == 1) {
    return(1)
  } else {
    return(n * factorial(n - 1))
  }
}

# Usage:
result_factorial <- factorial(5)
print(result_factorial)
```
6. Function with Variable Arguments:
```R
# Function to calculate the sum of variable arguments
sum_variable_args <- function(...) {
  args <- list(...)
  result <- sum(unlist(args))
  return(result)
}

# Usage:
result_sum_args <- sum_variable_args(1, 2, 3, 4, 5)
print(result_sum_args)
```
7. Function with Data Frame Input:
```R
# Function to filter data frame based on a condition
filter_data <- function(data_frame, condition_column, threshold) {
  filtered_data <- data_frame[data_frame[[condition_column]] > threshold, ]
  return(filtered_data)
}

# Usage:
input_data <- data.frame(ID = 1:5, Value = c(10, 25, 5, 30, 15))
result_filtered_data <- filter_data(input_data, "Value", 15)
print(result_filtered_data)
```
8. Anonymous Function (Using function()):
```R
# Anonymous function to calculate the square of a number
square_anonymous <- function(x) {
  return(x^2)
}

# Usage:
result_square_anonymous <- square_anonymous(3)
print(result_square_anonymous)
```
9. Function with Error Handling:
```R
# Function to divide two numbers with error handling
divide_numbers <- function(a, b) {
  if (b == 0) {
    stop("Cannot divide by zero.")
  }
  result <- a / b
  return(result)
}

# Usage:
tryCatch({
  result_division <- divide_numbers(10, 0)
  print(result_division)
}, error = function(e) {
  print(paste("Error: ", e))
})
```
10. Function with Side Effect (Modifying Global Variable):
```R
# Function to update a global variable
global_variable <- 0

update_global_variable <- function(value) {
  global_variable <<- value
}

# Usage:
update_global_variable(42)
print(global_variable)
```
