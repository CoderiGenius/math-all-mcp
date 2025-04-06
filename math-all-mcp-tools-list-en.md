# Mathematical Services Documentation

This document provides detailed information about all functions in BasicMathService and AdvancedMathService, including their functionality, implementation methods, parameters, return values, and usage examples.

## Table of Contents

- [BasicMathService](#basicmathservice)
  - [Basic Operations](#basic-operations)
  - [Power and Root Operations](#power-and-root-operations)
  - [Value Operations](#value-operations)
  - [Set Operations](#set-operations)
  - [Trigonometric Functions](#trigonometric-functions)
  - [Logarithmic Functions](#logarithmic-functions)
- [AdvancedMathService](#advancedmathservice)
  - [Expression Processing](#expression-processing)
  - [Calculus](#calculus)
  - [Equation Solving](#equation-solving)
  - [Series Expansion](#series-expansion)
  - [Function Properties](#function-properties)
  - [Format Conversion](#format-conversion)

## BasicMathService

BasicMathService provides basic mathematical operation functionality, including arithmetic operations, power operations, trigonometric functions, logarithmic functions, etc. This service uses Java's BigDecimal and Apache Commons Math library to implement high-precision calculations.

### Basic Operations

#### add

- **Functionality**: Calculate the sum of two numbers
- **Implementation**: Uses BigDecimal's add method
- **Parameters**:
  - a: First addend (number represented as a string)
  - b: Second addend (number represented as a string)
- **Return Value**: Sum of the two numbers represented as a string
- **Examples**:
  ```java
  add("1", "1") // Returns "2"
  add("0.1", "0.2") // Returns "0.3"
  add("-1", "1") // Returns "0"
  ```

#### subtract

- **Functionality**: Calculate the difference between two numbers
- **Implementation**: Uses BigDecimal's subtract method
- **Parameters**:
  - a: Minuend (number represented as a string)
  - b: Subtrahend (number represented as a string)
- **Return Value**: Difference between the two numbers represented as a string
- **Examples**:
  ```java
  subtract("1", "1") // Returns "0"
  subtract("0.5", "0.3") // Returns "0.2"
  subtract("-1", "1") // Returns "-2"
  ```

#### multiply

- **Functionality**: Calculate the product of two numbers
- **Implementation**: Uses BigDecimal's multiply method
- **Parameters**:
  - a: First factor (number represented as a string)
  - b: Second factor (number represented as a string)
- **Return Value**: Product of the two numbers represented as a string
- **Examples**:
  ```java
  multiply("2", "3") // Returns "6"
  multiply("0.1", "0.1") // Returns "0.01"
  multiply("-1", "1") // Returns "-1"
  ```

#### divide

- **Functionality**: Calculate the quotient of two numbers
- **Implementation**: Uses BigDecimal's divide method, with precision of 10 digits, rounding
- **Parameters**:
  - a: Dividend (number represented as a string)
  - b: Divisor (number represented as a string)
- **Return Value**: Quotient of the two numbers represented as a string
- **Examples**:
  ```java
  divide("6", "2") // Returns "3"
  divide("1", "3") // Returns "0.3333333333"
  divide("10", "3") // Returns "3.3333333333"
  ```

#### remainder

- **Functionality**: Calculate the remainder of division between two numbers
- **Implementation**: Uses BigDecimal's remainder method
- **Parameters**:
  - a: Dividend (number represented as a string)
  - b: Divisor (number represented as a string)
- **Return Value**: Remainder represented as a string
- **Examples**:
  ```java
  remainder("10", "3") // Returns "1"
  remainder("10", "2") // Returns "0"
  remainder("5.5", "2") // Returns "1.5"
  ```

### Power and Root Operations

#### power

- **Functionality**: Calculate the power of a number
- **Implementation**: Uses FastMath.pow method
- **Parameters**:
  - base: Base (number represented as a string)
  - exponent: Exponent (number represented as a string)
- **Return Value**: Result of the power operation represented as a string
- **Examples**:
  ```java
  power("2", "3") // Returns "8"
  power("2", "0") // Returns "1"
  power("10", "-2") // Returns "0.01"
  ```

#### square

- **Functionality**: Calculate the square of a number
- **Implementation**: Uses FastMath.pow method with exponent 2
- **Parameters**:
  - a: Base (number represented as a string)
- **Return Value**: Square result represented as a string
- **Examples**:
  ```java
  square("2") // Returns "4"
  square("-2") // Returns "4"
  square("0.5") // Returns "0.25"
  ```

#### squareRoot

- **Functionality**: Calculate the square root of a number
- **Implementation**: Uses FastMath.sqrt method
- **Parameters**:
  - a: Radicand (non-negative number represented as a string)
- **Return Value**: Square root result represented as a string
- **Examples**:
  ```java
  squareRoot("4") // Returns "2"
  squareRoot("2") // Returns "1.4142135623730951"
  squareRoot("0.25") // Returns "0.5"
  ```

#### cubeRoot

- **Functionality**: Calculate the cube root of a number
- **Implementation**: Uses FastMath.cbrt method
- **Parameters**:
  - a: Radicand (number represented as a string)
- **Return Value**: Cube root result represented as a string
- **Examples**:
  ```java
  cubeRoot("8") // Returns "2"
  cubeRoot("-8") // Returns "-2"
  cubeRoot("0.125") // Returns "0.5"
  ```

#### nthRoot

- **Functionality**: Calculate the nth root of a number
- **Implementation**: Uses FastMath.pow method with exponent 1/n
- **Parameters**:
  - a: Radicand (number represented as a string)
  - n: Root degree (non-zero number represented as a string)
- **Return Value**: Nth root result represented as a string
- **Examples**:
  ```java
  nthRoot("16", "2") // Returns "4"
  nthRoot("16", "4") // Returns "2"
  nthRoot("-32", "5") // Returns "-2"
  ```

### Value Operations

#### absoluteValue

- **Functionality**: Calculate the absolute value of a number
- **Implementation**: Uses FastMath.abs method
- **Parameters**:
  - a: Input value (number represented as a string)
- **Return Value**: Absolute value result represented as a string
- **Examples**:
  ```java
  absoluteValue("5") // Returns "5"
  absoluteValue("-5") // Returns "5"
  absoluteValue("0") // Returns "0"
  ```

#### ceilingValue

- **Functionality**: Calculate the ceiling value of a number
- **Implementation**: Uses FastMath.ceil method
- **Parameters**:
  - a: Input value (number represented as a string)
- **Return Value**: Ceiling value result represented as a string
- **Examples**:
  ```java
  ceilingValue("1.1") // Returns "2"
  ceilingValue("-1.1") // Returns "-1"
  ceilingValue("1.0") // Returns "1"
  ```

#### floorValue

- **Functionality**: Calculate the floor value of a number
- **Implementation**: Uses FastMath.floor method
- **Parameters**:
  - a: Input value (number represented as a string)
- **Return Value**: Floor value result represented as a string
- **Examples**:
  ```java
  floorValue("1.9") // Returns "1"
  floorValue("-1.1") // Returns "-2"
  floorValue("1.0") // Returns "1"
  ```

#### roundValue

- **Functionality**: Calculate the rounded value of a number
- **Implementation**: Uses BigDecimal's setScale method with precision 0, rounding
- **Parameters**:
  - a: Input value (number represented as a string)
- **Return Value**: Rounded value result represented as a string
- **Examples**:
  ```java
  roundValue("1.4") // Returns "1"
  roundValue("1.5") // Returns "2"
  roundValue("-1.5") // Returns "-2"
  ```

#### fractionalPart

- **Functionality**: Get the fractional part of a number
- **Implementation**: Uses BigDecimal's subtract method to subtract the integer part
- **Parameters**:
  - a: Input value (number represented as a string)
- **Return Value**: Fractional part represented as a string
- **Examples**:
  ```java
  fractionalPart("1.23") // Returns "0.23"
  fractionalPart("-1.23") // Returns "-0.23"
  fractionalPart("5") // Returns "0"
  ```

### Set Operations

#### maximum

- **Functionality**: Calculate the maximum value among multiple numbers
- **Implementation**: Uses Java Stream API and BigDecimal's compareTo method
- **Parameters**:
  - values: Array of values (variable number of values represented as strings)
- **Return Value**: Maximum value represented as a string
- **Examples**:
  ```java
  maximum("1", "2", "3") // Returns "3"
  maximum("-1", "-2", "-3") // Returns "-1"
  maximum("1.1", "1.2", "1.3") // Returns "1.3"
  ```

#### minimum

- **Functionality**: Calculate the minimum value among multiple numbers
- **Implementation**: Uses Java Stream API and BigDecimal's compareTo method
- **Parameters**:
  - values: Array of values (variable number of values represented as strings)
- **Return Value**: Minimum value represented as a string
- **Examples**:
  ```java
  minimum("1", "2", "3") // Returns "1"
  minimum("-1", "-2", "-3") // Returns "-3"
  minimum("1.1", "1.2", "1.3") // Returns "1.1"
  ```

#### average

- **Functionality**: Calculate the average of multiple numbers
- **Implementation**: Uses Java Stream API to calculate the sum, then divides by the count
- **Parameters**:
  - values: Array of values (variable number of values represented as strings)
- **Return Value**: Average value represented as a string
- **Examples**:
  ```java
  average("1", "2", "3") // Returns "2"
  average("-1", "-2", "-3") // Returns "-2"
  average("1.1", "1.2", "1.3") // Returns "1.2"
  ```

#### sum

- **Functionality**: Calculate the sum of multiple numbers
- **Implementation**: Uses Java Stream API and BigDecimal's add method
- **Parameters**:
  - values: Array of values (variable number of values represented as strings)
- **Return Value**: Sum represented as a string
- **Examples**:
  ```java
  sum("1", "2", "3") // Returns "6"
  sum("-1", "-2", "-3") // Returns "-6"
  sum("1.1", "1.2", "1.3") // Returns "3.6"
  ```

#### product

- **Functionality**: Calculate the product of multiple numbers
- **Implementation**: Uses Java Stream API and BigDecimal's multiply method
- **Parameters**:
  - values: Array of values (variable number of values represented as strings)
- **Return Value**: Product represented as a string
- **Examples**:
  ```java
  product("1", "2", "3") // Returns "6"
  product("-1", "-2", "-3") // Returns "-6"
  product("1.1", "1.2", "1.3") // Returns "1.716"
  ```

### Trigonometric Functions

#### sine

- **Functionality**: Calculate the sine value
- **Implementation**: Uses FastMath.sin method
- **Parameters**:
  - angle: Angle (radian value represented as a string)
- **Return Value**: Sine value represented as a string
- **Examples**:
  ```java
  sine("0") // Returns "0"
  sine("1.5707963267948966") // Returns "1" (sine of π/2)
  sine("3.141592653589793") // Returns "0" (sine of π)
  ```

#### cosine

- **Functionality**: Calculate the cosine value
- **Implementation**: Uses FastMath.cos method
- **Parameters**:
  - angle: Angle (radian value represented as a string)
- **Return Value**: Cosine value represented as a string
- **Examples**:
  ```java
  cosine("0") // Returns "1"
  cosine("1.5707963267948966") // Returns "0" (cosine of π/2)
  cosine("3.141592653589793") // Returns "-1" (cosine of π)
  ```

#### tangent

- **Functionality**: Calculate the tangent value
- **Implementation**: Uses FastMath.tan method
- **Parameters**:
  - angle: Angle (radian value represented as a string)
- **Return Value**: Tangent value represented as a string
- **Examples**:
  ```java
  tangent("0") // Returns "0"
  tangent("0.7853981633974483") // Returns "1" (tangent of π/4)
  tangent("3.141592653589793") // Returns "0" (tangent of π)
  ```

#### arcsine

- **Functionality**: Calculate the arcsine value
- **Implementation**: Uses FastMath.asin method
- **Parameters**:
  - value: Sine value (number between -1 and 1 represented as a string)
- **Return Value**: Angle in radians represented as a string
- **Examples**:
  ```java
  arcsine("0") // Returns "0"
  arcsine("1") // Returns "1.5707963267948966" (π/2)
  arcsine("0.5") // Returns "0.5235987755982989" (π/6)
  ```

#### arccosine

- **Functionality**: Calculate the arccosine value
- **Implementation**: Uses FastMath.acos method
- **Parameters**:
  - value: Cosine value (number between -1 and 1 represented as a string)
- **Return Value**: Angle in radians represented as a string
- **Examples**:
  ```java
  arccosine("1") // Returns "0"
  arccosine("0") // Returns "1.5707963267948966" (π/2)
  arccosine("0.5") // Returns "1.0471975511965976" (π/3)
  ```

#### arctangent

- **Functionality**: Calculate the arctangent value
- **Implementation**: Uses FastMath.atan method
- **Parameters**:
  - value: Tangent value (number represented as a string)
- **Return Value**: Angle in radians represented as a string
- **Examples**:
  ```java
  arctangent("0") // Returns "0"
  arctangent("1") // Returns "0.7853981633974483" (π/4)
  arctangent("-1") // Returns "-0.7853981633974483" (-π/4)
  ```

### Logarithmic Functions

#### naturalLogarithm

- **Functionality**: Calculate the natural logarithm
- **Implementation**: Uses FastMath.log method
- **Parameters**:
  - a: Input value (positive number represented as a string)
- **Return Value**: Natural logarithm value represented as a string
- **Examples**:
  ```java
  naturalLogarithm("1") // Returns "0"
  naturalLogarithm("2.718281828459045") // Returns "1" (natural logarithm of e)
  naturalLogarithm("10") // Returns "2.302585092994046"
  ```

#### commonLogarithm

- **Functionality**: Calculate the common logarithm (base 10)
- **Implementation**: Uses FastMath.log10 method
- **Parameters**:
  - a: Input value (positive number represented as a string)
- **Return Value**: Common logarithm value represented as a string
- **Examples**:
  ```java
  commonLogarithm("1") // Returns "0"
  commonLogarithm("10") // Returns "1"
  commonLogarithm("100") // Returns "2"
  ```

#### logarithm

- **Functionality**: Calculate the logarithm with specified base
- **Implementation**: Uses the logarithm change of base formula log_b(x) = log_e(x) / log_e(b)
- **Parameters**:
  - a: Input value (positive number represented as a string)
  - base: Base (positive number not equal to 1, represented as a string)
- **Return Value**: Logarithm value represented as a string
- **Examples**:
  ```java
  logarithm("8", "2") // Returns "3"
  logarithm("9", "3") // Returns "2"
  logarithm("100", "10") // Returns "2"
  ```

#### exponential

- **Functionality**: Calculate e raised to a power
- **Implementation**: Uses FastMath.exp method
- **Parameters**:
  - a: Exponent (number represented as a string)
- **Return Value**: Value of e^a represented as a string
- **Examples**:
  ```java
  exponential("0") // Returns "1"
  exponential("1") // Returns "2.718281828459045" (e)
  exponential("2") // Returns "7.38905609893065" (e^2)
  ```

## AdvancedMathService

AdvancedMathService provides advanced mathematical functionality, including expression processing, calculus, equation solving, etc. This service uses the Symja library to implement symbolic computation.

### Expression Processing

#### simplifyExpression

- **Functionality**: Simplify mathematical expressions
- **Implementation**: Uses Symja's Simplify function
- **Parameters**:
  - expression: Expression to simplify (string)
- **Return Value**: Simplified expression (string)
- **Examples**:
  ```java
  simplifyExpression("x^2+2*x+1") // Returns "(x+1)^2"
  simplifyExpression("sin(x)^2+cos(x)^2") // Returns "1"
  simplifyExpression("a+a") // Returns "2*a"
  ```

#### expandExpression

- **Functionality**: Expand mathematical expressions
- **Implementation**: Uses Symja's ExpandAll and HornerForm functions
- **Parameters**:
  - expression: Expression to expand (string)
- **Return Value**: Expanded expression (string)
- **Examples**:
  ```java
  expandExpression("(x+1)^2") // Returns "1+x*(2+x)"
  expandExpression("(x+1)*(x-1)") // Returns "-1+x^2"
  expandExpression("(a+b)*(c+d)") // Returns "a*c+a*d+b*c+b*d"
  ```

#### factorExpression

- **Functionality**: Factor expressions
- **Implementation**: Uses Symja's Factor function
- **Parameters**:
  - expression: Expression to factor (string)
- **Return Value**: Factored expression (string)
- **Examples**:
  ```java
  factorExpression("x^2-1") // Returns "(x-1)*(x+1)"
  factorExpression("x^2+2*x+1") // Returns "(1+x)^2"
  factorExpression("x^3-1") // Returns "(x-1)*(1+x+x^2)"
  ```

#### substituteVariable

- **Functionality**: Substitute variables in expressions
- **Implementation**: Uses Symja's ReplaceAll function
- **Parameters**:
  - expression: Original expression (string)
  - variable: Variable to replace (string)
  - value: Replacement value (string)
- **Return Value**: Expression after substitution (string)
- **Examples**:
  ```java
  substituteVariable("x^2+y^2", "x", "2") // Returns "4+y^2"
  substituteVariable("x+y", "y", "x") // Returns "x+x"
  substituteVariable("sin(x)", "x", "0") // Returns "0"
  ```

#### parseExpression

- **Functionality**: Parse expressions
- **Implementation**: Uses Symja's eval method for direct calculation
- **Parameters**:
  - expression: Expression to parse (string)
- **Return Value**: Parsed expression (string)
- **Examples**:
  ```java
  parseExpression("1+1") // Returns "2"
  parseExpression("sin(0)") // Returns "0"
  parseExpression("2^3") // Returns "8"
  ```

#### executeCommand

- **Functionality**: Execute Symja commands
- **Implementation**: Uses Symja's eval method to execute commands with security validation
- **Parameters**:
  - command: The Symja command to execute (string)
- **Return Value**: Command execution result (string)
- **Examples**:
  ```java
  executeCommand("Solve(x^2-1==0, x)") // Returns "{{x->-1},{x->1}}"
  executeCommand("FactorInteger(100)") // Returns "{{2,2},{5,2}}"
  executeCommand("Sum(k, {k,1,10})") // Returns "55"
  ```

### Calculus

#### differentiate

- **Functionality**: Calculate the derivative of a single-variable function
- **Implementation**: Uses Symja's D function
- **Parameters**:
  - expression: Function expression (string)
  - variable: Variable (string)
- **Return Value**: Derivative expression (string)
- **Examples**:
  ```java
  differentiate("x^2", "x") // Returns "2*x"
  differentiate("Sin(x)", "x") // Returns "Cos(x)"
  differentiate("e^x", "x") // Returns "e^x*Log(e)"
  ```

#### partialDerivative

- **Functionality**: Calculate the partial derivative of a multi-variable function
- **Implementation**: Uses Symja's D function, specifying variable and order
- **Parameters**:
  - expression: Function expression (string)
  - variable: Variable (string)
  - order: Derivative order (string)
- **Return Value**: Partial derivative expression (string)
- **Examples**:
  ```java
  partialDerivative("x^2*y^3", "x", "1") // Returns "2*x*y^3"
  partialDerivative("x^2*y^3", "y", "1") // Returns "3*x^2*y^2"
  partialDerivative("x^2*y^3", "x", "2") // Returns "2*y^3"
  ```

#### indefiniteIntegral

- **Functionality**: Calculate indefinite integrals
- **Implementation**: Uses Symja's Integrate function
- **Parameters**:
  - expression: Integrand expression (string)
  - variable: Integration variable (string)
- **Return Value**: Indefinite integral expression (string)
- **Examples**:
  ```java
  indefiniteIntegral("x", "x") // Returns "x^2/2"
  indefiniteIntegral("x^2", "x") // Returns "x^3/3"
  indefiniteIntegral("Sin(x)", "x") // Returns "-Cos(x)"
  ```

#### definiteIntegral

- **Functionality**: Calculate definite integrals
- **Implementation**: Uses Symja's Integrate function, specifying integration limits
- **Parameters**:
  - expression: Integrand expression (string)
  - variable: Integration variable (string)
  - lowerBound: Lower integration limit (string)
  - upperBound: Upper integration limit (string)
- **Return Value**: Definite integral result (string)
- **Examples**:
  ```java
  definiteIntegral("x", "x", "0", "1") // Returns "0.5"
  definiteIntegral("x^2", "x", "0", "1") // Returns "0.33333"
  definiteIntegral("Sin(x)", "x", "0", "Pi") // Returns "2.0"
  ```

#### gradientVector

- **Functionality**: Calculate the gradient vector
- **Implementation**: Uses Symja's Grad function
- **Parameters**:
  - expression: Function expression (string)
  - variables: List of variables, comma-separated (string)
- **Return Value**: Gradient vector (string)
- **Examples**:
  ```java
  gradientVector("x^2+y^2", "x,y") // Returns "{2*x,2*y}"
  gradientVector("x*y+z", "x,y,z") // Returns "{y,x,1}"
  gradientVector("Sin(x)*Cos(y)", "x,y") // Returns "{Cos(x)*Cos(y),-Sin(x)*Sin(y)}"
  ```

#### limit

- **Functionality**: Calculate limits
- **Implementation**: Uses Symja's Limit function
- **Parameters**:
  - expression: Function expression (string)
  - variable: Variable (string)
  - limit: Approaching value (string)
- **Return Value**: Limit value (string)
- **Examples**:
  ```java
  limit("Sin(x)/x", "x", "0") // Returns "1"
  limit("(1+x)^(1/x)", "x", "0") // Returns "E"
  limit("(x^2-1)/(x-1)", "x", "1") // Returns "2"
  ```

#### infiniteLimit

- **Functionality**: Calculate infinite limits
- **Implementation**: Uses Symja's Limit function, with approaching value as infinity
- **Parameters**:
  - expression: Function expression (string)
  - variable: Variable (string)
  - direction: Direction ("Infinity" or "-Infinity")
- **Return Value**: Infinite limit value (string)
- **Examples**:
  ```java
  infiniteLimit("1/x", "x", "Infinity") // Returns "0"
  infiniteLimit("x^2", "x", "Infinity") // Returns "Infinity"
  infiniteLimit("Sin(1/x)", "x", "Infinity") // Returns "0"
  ```

### Equation Solving

#### solveEquation

- **Functionality**: Solve algebraic equations
- **Implementation**: Uses Symja's Solve function
- **Parameters**:
  - equation: Equation expression (string, containing == operator)
  - variable: Variable to solve for (string)
- **Return Value**: Equation solution (string)
- **Examples**:
  ```java
  solveEquation("x^2-1==0", "x") // Returns "{{x->-1},{x->1}}"
  solveEquation("x+1==0", "x") // Returns "{{x->-1}}"
  solveEquation("x^2+1==0", "x") // Returns "{{x->-I},{x->I}}"
  ```

#### solveNonlinearEquation

- **Functionality**: Solve nonlinear equations
- **Implementation**: Uses Symja's NSolve function
- **Parameters**:
  - equation: Equation expression (string, containing == operator)
  - variable: Variable to solve for (string)
- **Return Value**: Numerical solution of the equation (string)
- **Examples**:
  ```java
  solveNonlinearEquation("x^2-2==0", "x") // Returns something like "{{x->-1.4142},{x->1.4142}}"
  solveNonlinearEquation("sin(x)==0.5", "x") // Returns something like "{{x->0.5236}}"
  solveNonlinearEquation("e^x-3==0", "x") // Returns something like "{{x->1.0986}}"
  ```

#### solveSystemOfEquations

- **Functionality**: Solve systems of equations
- **Implementation**: Uses Symja's Solve function, processing multiple equations and variables
- **Parameters**:
  - equations: System of equations, comma-separated (string, each equation containing == operator)
  - variables: List of variables, comma-separated (string)
- **Return Value**: Solution of the system of equations (string)
- **Examples**:
  ```java
  solveSystemOfEquations("x+y==3,x-y==1", "x,y") // Returns "{{x->2,y->1}}"
  solveSystemOfEquations("x+y+z==6,x+y-z==0,x-y+z==2", "x,y,z") // Returns "{{x->1,y->2,z->3}}"
  ```

#### numericalSolve

- **Functionality**: Numerically solve equations
- **Implementation**: Uses Symja's NSolve function
- **Parameters**:
  - equation: Equation expression (string, containing == operator)
  - variable: Variable to solve for (string)
- **Return Value**: Numerical solution of the equation (string)
- **Examples**:
  ```java
  numericalSolve("x^2-2==0", "x") // Returns something like "{x->1.4142}"
  numericalSolve("sin(x)==0.5", "x") // Returns something like "{x->0.5236}"
  numericalSolve("x^3-x-1==0", "x") // Returns something like "{x->1.3247}"
  ```

#### findExtremum

- **Functionality**: Find function extrema
- **Implementation**: Calculates derivative and solves for where derivative equals zero
- **Parameters**:
  - expression: Function expression (string)
  - variable: Variable (string)
- **Return Value**: Function extrema points (string)
- **Examples**:
  ```java
  findExtremum("x^2", "x") // Returns "{{x->0}}"
  findExtremum("x^3-3*x", "x") // Returns "{{x->-1},{x->1}}"
  findExtremum("x^2+2*x+1", "x") // Returns "{{x->-1}}"
  ```

### Series Expansion

#### taylorExpansion

- **Functionality**: Calculate Taylor expansion
- **Implementation**: Uses Symja's Series function
- **Parameters**:
  - expression: Function expression (string)
  - variable: Variable (string)
  - point: Expansion point (string)
  - order: Expansion order (string)
- **Return Value**: Taylor expansion (string)
- **Examples**:
  ```java
  taylorExpansion("sin(x)", "x", "0", "3") // Returns "x-x^3/6+O(x)^4"
  taylorExpansion("cos(x)", "x", "0", "2") // Returns "1-x^2/2+O(x)^3"
  taylorExpansion("e^x", "x", "0", "3") // Returns "1+Log(e)*x+1/2*Log(e)^2*x^2+1/6*Log(e)^3*x^3+O(x)^4"
  ```

#### powerSeriesExpansion

- **Functionality**: Calculate power series expansion
- **Implementation**: Uses Symja's Series function, with expansion point at 0
- **Parameters**:
  - expression: Function expression (string)
  - variable: Variable (string)
  - order: Expansion order (string)
- **Return Value**: Power series expansion (string)
- **Examples**:
  ```java
  powerSeriesExpansion("sin(x)", "x", "3") // Returns "x-x^3/6+O(x)^4"
  powerSeriesExpansion("1/(1-x)", "x", "3") // Returns "1+x+x^2+x^3+O(x)^4"
  powerSeriesExpansion("log(1+x)", "x", "2") // Returns "x-x^2/2+O(x)^3"
  ```

### Function Properties

#### isOddFunction

- **Functionality**: Determine if a function is odd
- **Implementation**: Checks if f(x) = -f(-x) holds
- **Parameters**:
  - expression: Function expression (string)
  - variable: Variable (string)
- **Return Value**: Result of determination ("True" or "False")
- **Examples**:
  ```java
  isOddFunction("x", "x") // Returns "True"
  isOddFunction("x^3", "x") // Returns "True"
  isOddFunction("sin(x)", "x") // Returns "True"
  isOddFunction("x^2", "x") // Returns "False"
  ```

#### isEvenFunction

- **Functionality**: Determine if a function is even
- **Implementation**: Checks if f(x) = f(-x) holds
- **Parameters**:
  - expression: Function expression (string)
  - variable: Variable (string)
- **Return Value**: Result of determination ("True" or "False")
- **Examples**:
  ```java
  isEvenFunction("x^2", "x") // Returns "True"
  isEvenFunction("cos(x)", "x") // Returns "True"
  isEvenFunction("x^4", "x") // Returns "True"
  isEvenFunction("x", "x") // Returns "False"
  ```

#### isDifferentiable

- **Functionality**: Determine if a function is differentiable
- **Implementation**: Checks if left and right derivatives are equal
- **Parameters**:
  - expression: Function expression (string)
  - variable: Variable (string)
  - point: Point to check (string)
- **Return Value**: Result of determination ("True" or "False")
- **Examples**:
  ```java
  isDifferentiable("x^2", "x", "0") // Returns "True"
  isDifferentiable("abs(x)", "x", "0") // Returns "False"
  isDifferentiable("sin(x)", "x", "0") // Returns "True"
  ```

### Format Conversion

#### toLatex

- **Functionality**: Convert to LaTeX format output
- **Implementation**: Uses Symja's TeXForm function
- **Parameters**:
  - expression: Expression (string)
- **Return Value**: Expression in LaTeX format (string)
- **Examples**:
  ```java
  toLatex("x^2+y^2") // Returns LaTeX formatted expression
  toLatex("sin(x)") // Returns "\sin(x)"
  toLatex("a/b") // Returns "\frac{a}{b}"
  ```

#### toMathString

- **Functionality**: Convert to mathematical string output
- **Implementation**: Uses Symja's ToString function
- **Parameters**:
  - expression: Expression (string)
- **Return Value**: Expression in mathematical string format (string)
- **Examples**:
  ```java
  toMathString("x^2+y^2") // Returns "x^2 + y^2"
  toMathString("sin(x)") // Returns "Sin(x)"
  toMathString("a/b") // Returns "a/b"
  ```

#### getAbstractSyntaxTree

- **Functionality**: Get the abstract syntax tree of an expression
- **Implementation**: Uses Symja's FullForm function
- **Parameters**:
  - expression: Expression (string)
- **Return Value**: Abstract syntax tree representation (string)
- **Examples**:
  ```java
  getAbstractSyntaxTree("x+y") // Returns "Plus(x, y)"
  getAbstractSyntaxTree("x*y") // Returns "Times(x, y)"
  getAbstractSyntaxTree("sin(x)") // Returns "Sin(x)"
  ```