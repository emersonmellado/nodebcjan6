# Exercise 5

* Create the following folder/file structure:
```
/ex_5
  |-- index.js
  |-- numbers.js
```

* Init an NPM project inside the ex_5 folder
* Use ex_5 as project name
* Add a start script to run the index.js file

## numbers.js
* Define a isEven function
* This function accepts a number as parameter
* Return a boolean value whether the number is even (true) or not (false)
* Export the isEven function

## index.js
* Install the [logplease module documentation](https://github.com/haadcode/logplease) module as dev dependency
* Import the logplease module
* Import the numbers module
* Call the isEven function with the following values: 2, 3, 101, 201, 202, 100 (one call for each number)
* Show the following message using the `info method` if the number is even:
```
%number% is even
```
* Show the following message using the error method if the number is not even:
```
%number% is odd
```
