# Math-All-MCP Tools文档

本文档详细介绍了Math-All-MCP 的所有Tools，包括它们的功能、实现方式、参数和返回值，并提供了使用示例。

## 目录

- [BasicMathService](#basicmathservice)
  - [基本运算](#基本运算)
  - [幂运算和根运算](#幂运算和根运算)
  - [值操作](#值操作)
  - [集合操作](#集合操作)
  - [三角函数](#三角函数)
  - [对数函数](#对数函数)
- [AdvancedMathService](#advancedmathservice)
  - [表达式处理](#表达式处理)
  - [微积分](#微积分)
  - [方程求解](#方程求解)
  - [级数展开](#级数展开)
  - [函数性质](#函数性质)
  - [格式转换](#格式转换)

## BasicMathService

BasicMathService提供基础数学运算功能，包括基本算术运算、幂运算、三角函数、对数函数等。该服务使用Java的BigDecimal和Apache Commons Math库实现高精度计算。

### 基本运算

#### add

- **功能**：计算两个数的和
- **实现**：使用BigDecimal的add方法
- **参数**：
  - a: 第一个加数（字符串表示的数值）
  - b: 第二个加数（字符串表示的数值）
- **返回值**：字符串表示的两数之和
- **示例**：
  ```java
  add("1", "1") // 返回 "2"
  add("0.1", "0.2") // 返回 "0.3"
  add("-1", "1") // 返回 "0"
  ```

#### subtract

- **功能**：计算两个数的差
- **实现**：使用BigDecimal的subtract方法
- **参数**：
  - a: 被减数（字符串表示的数值）
  - b: 减数（字符串表示的数值）
- **返回值**：字符串表示的两数之差
- **示例**：
  ```java
  subtract("1", "1") // 返回 "0"
  subtract("0.5", "0.3") // 返回 "0.2"
  subtract("-1", "1") // 返回 "-2"
  ```

#### multiply

- **功能**：计算两个数的乘积
- **实现**：使用BigDecimal的multiply方法
- **参数**：
  - a: 第一个因数（字符串表示的数值）
  - b: 第二个因数（字符串表示的数值）
- **返回值**：字符串表示的两数之积
- **示例**：
  ```java
  multiply("2", "3") // 返回 "6"
  multiply("0.1", "0.1") // 返回 "0.01"
  multiply("-1", "1") // 返回 "-1"
  ```

#### divide

- **功能**：计算两个数的商
- **实现**：使用BigDecimal的divide方法，精度为10位，四舍五入
- **参数**：
  - a: 被除数（字符串表示的数值）
  - b: 除数（字符串表示的数值）
- **返回值**：字符串表示的两数之商
- **示例**：
  ```java
  divide("6", "2") // 返回 "3"
  divide("1", "3") // 返回 "0.3333333333"
  divide("10", "3") // 返回 "3.3333333333"
  ```

#### remainder

- **功能**：计算两个数的余数
- **实现**：使用BigDecimal的remainder方法
- **参数**：
  - a: 被除数（字符串表示的数值）
  - b: 除数（字符串表示的数值）
- **返回值**：字符串表示的余数
- **示例**：
  ```java
  remainder("10", "3") // 返回 "1"
  remainder("10", "2") // 返回 "0"
  remainder("5.5", "2") // 返回 "1.5"
  ```

### 幂运算和根运算

#### power

- **功能**：计算一个数的幂
- **实现**：使用FastMath.pow方法
- **参数**：
  - base: 底数（字符串表示的数值）
  - exponent: 指数（字符串表示的数值）
- **返回值**：字符串表示的幂运算结果
- **示例**：
  ```java
  power("2", "3") // 返回 "8"
  power("2", "0") // 返回 "1"
  power("10", "-2") // 返回 "0.01"
  ```

#### square

- **功能**：计算一个数的平方
- **实现**：使用FastMath.pow方法，指数为2
- **参数**：
  - a: 底数（字符串表示的数值）
- **返回值**：字符串表示的平方结果
- **示例**：
  ```java
  square("2") // 返回 "4"
  square("-2") // 返回 "4"
  square("0.5") // 返回 "0.25"
  ```

#### squareRoot

- **功能**：计算一个数的平方根
- **实现**：使用FastMath.sqrt方法
- **参数**：
  - a: 被开方数（字符串表示的非负数值）
- **返回值**：字符串表示的平方根结果
- **示例**：
  ```java
  squareRoot("4") // 返回 "2"
  squareRoot("2") // 返回 "1.4142135623730951"
  squareRoot("0.25") // 返回 "0.5"
  ```

#### cubeRoot

- **功能**：计算一个数的立方根
- **实现**：使用FastMath.cbrt方法
- **参数**：
  - a: 被开方数（字符串表示的数值）
- **返回值**：字符串表示的立方根结果
- **示例**：
  ```java
  cubeRoot("8") // 返回 "2"
  cubeRoot("-8") // 返回 "-2"
  cubeRoot("0.125") // 返回 "0.5"
  ```

#### nthRoot

- **功能**：计算一个数的n次根
- **实现**：使用FastMath.pow方法，指数为1/n
- **参数**：
  - a: 被开方数（字符串表示的数值）
  - n: 根次（字符串表示的非零数值）
- **返回值**：字符串表示的n次根结果
- **示例**：
  ```java
  nthRoot("16", "2") // 返回 "4"
  nthRoot("16", "4") // 返回 "2"
  nthRoot("-32", "5") // 返回 "-2"
  ```

### 值操作

#### absoluteValue

- **功能**：计算一个数的绝对值
- **实现**：使用FastMath.abs方法
- **参数**：
  - a: 输入数值（字符串表示的数值）
- **返回值**：字符串表示的绝对值结果
- **示例**：
  ```java
  absoluteValue("5") // 返回 "5"
  absoluteValue("-5") // 返回 "5"
  absoluteValue("0") // 返回 "0"
  ```

#### ceilingValue

- **功能**：计算一个数的向上取整值
- **实现**：使用FastMath.ceil方法
- **参数**：
  - a: 输入数值（字符串表示的数值）
- **返回值**：字符串表示的向上取整结果
- **示例**：
  ```java
  ceilingValue("1.1") // 返回 "2"
  ceilingValue("-1.1") // 返回 "-1"
  ceilingValue("1.0") // 返回 "1"
  ```

#### floorValue

- **功能**：计算一个数的向下取整值
- **实现**：使用FastMath.floor方法
- **参数**：
  - a: 输入数值（字符串表示的数值）
- **返回值**：字符串表示的向下取整结果
- **示例**：
  ```java
  floorValue("1.9") // 返回 "1"
  floorValue("-1.1") // 返回 "-2"
  floorValue("1.0") // 返回 "1"
  ```

#### roundValue

- **功能**：计算一个数的四舍五入值
- **实现**：使用BigDecimal的setScale方法，精度为0，四舍五入
- **参数**：
  - a: 输入数值（字符串表示的数值）
- **返回值**：字符串表示的四舍五入结果
- **示例**：
  ```java
  roundValue("1.4") // 返回 "1"
  roundValue("1.5") // 返回 "2"
  roundValue("-1.5") // 返回 "-2"
  ```

#### fractionalPart

- **功能**：获取一个数的小数部分
- **实现**：使用BigDecimal的subtract方法减去整数部分
- **参数**：
  - a: 输入数值（字符串表示的数值）
- **返回值**：字符串表示的小数部分
- **示例**：
  ```java
  fractionalPart("1.23") // 返回 "0.23"
  fractionalPart("-1.23") // 返回 "-0.23"
  fractionalPart("5") // 返回 "0"
  ```

### 集合操作

#### maximum

- **功能**：计算多个数中的最大值
- **实现**：使用Java Stream API和BigDecimal的compareTo方法
- **参数**：
  - values: 数值数组（字符串表示的数值可变参数）
- **返回值**：字符串表示的最大值
- **示例**：
  ```java
  maximum("1", "2", "3") // 返回 "3"
  maximum("-1", "-2", "-3") // 返回 "-1"
  maximum("1.1", "1.2", "1.3") // 返回 "1.3"
  ```

#### minimum

- **功能**：计算多个数中的最小值
- **实现**：使用Java Stream API和BigDecimal的compareTo方法
- **参数**：
  - values: 数值数组（字符串表示的数值可变参数）
- **返回值**：字符串表示的最小值
- **示例**：
  ```java
  minimum("1", "2", "3") // 返回 "1"
  minimum("-1", "-2", "-3") // 返回 "-3"
  minimum("1.1", "1.2", "1.3") // 返回 "1.1"
  ```

#### average

- **功能**：计算多个数的平均值
- **实现**：使用Java Stream API计算总和，然后除以数量
- **参数**：
  - values: 数值数组（字符串表示的数值可变参数）
- **返回值**：字符串表示的平均值
- **示例**：
  ```java
  average("1", "2", "3") // 返回 "2"
  average("-1", "-2", "-3") // 返回 "-2"
  average("1.1", "1.2", "1.3") // 返回 "1.2"
  ```

#### sum

- **功能**：计算多个数的总和
- **实现**：使用Java Stream API和BigDecimal的add方法
- **参数**：
  - values: 数值数组（字符串表示的数值可变参数）
- **返回值**：字符串表示的总和
- **示例**：
  ```java
  sum("1", "2", "3") // 返回 "6"
  sum("-1", "-2", "-3") // 返回 "-6"
  sum("1.1", "1.2", "1.3") // 返回 "3.6"
  ```

#### product

- **功能**：计算多个数的乘积
- **实现**：使用Java Stream API和BigDecimal的multiply方法
- **参数**：
  - values: 数值数组（字符串表示的数值可变参数）
- **返回值**：字符串表示的乘积
- **示例**：
  ```java
  product("1", "2", "3") // 返回 "6"
  product("-1", "-2", "-3") // 返回 "-6"
  product("1.1", "1.2", "1.3") // 返回 "1.716"
  ```

### 三角函数

#### sine

- **功能**：计算正弦值
- **实现**：使用FastMath.sin方法
- **参数**：
  - angle: 角度（字符串表示的弧度值）
- **返回值**：字符串表示的正弦值
- **示例**：
  ```java
  sine("0") // 返回 "0"
  sine("1.5707963267948966") // 返回 "1" (π/2的正弦值)
  sine("3.141592653589793") // 返回 "0" (π的正弦值)
  ```

#### cosine

- **功能**：计算余弦值
- **实现**：使用FastMath.cos方法
- **参数**：
  - angle: 角度（字符串表示的弧度值）
- **返回值**：字符串表示的余弦值
- **示例**：
  ```java
  cosine("0") // 返回 "1"
  cosine("1.5707963267948966") // 返回 "0" (π/2的余弦值)
  cosine("3.141592653589793") // 返回 "-1" (π的余弦值)
  ```

#### tangent

- **功能**：计算正切值
- **实现**：使用FastMath.tan方法
- **参数**：
  - angle: 角度（字符串表示的弧度值）
- **返回值**：字符串表示的正切值
- **示例**：
  ```java
  tangent("0") // 返回 "0"
  tangent("0.7853981633974483") // 返回 "1" (π/4的正切值)
  tangent("3.141592653589793") // 返回 "0" (π的正切值)
  ```

#### arcsine

- **功能**：计算反正弦值
- **实现**：使用FastMath.asin方法
- **参数**：
  - value: 正弦值（字符串表示的-1到1之间的数值）
- **返回值**：字符串表示的弧度值
- **示例**：
  ```java
  arcsine("0") // 返回 "0"
  arcsine("1") // 返回 "1.5707963267948966" (π/2)
  arcsine("0.5") // 返回 "0.5235987755982989" (π/6)
  ```

#### arccosine

- **功能**：计算反余弦值
- **实现**：使用FastMath.acos方法
- **参数**：
  - value: 余弦值（字符串表示的-1到1之间的数值）
- **返回值**：字符串表示的弧度值
- **示例**：
  ```java
  arccosine("1") // 返回 "0"
  arccosine("0") // 返回 "1.5707963267948966" (π/2)
  arccosine("0.5") // 返回 "1.0471975511965976" (π/3)
  ```

#### arctangent

- **功能**：计算反正切值
- **实现**：使用FastMath.atan方法
- **参数**：
  - value: 正切值（字符串表示的数值）
- **返回值**：字符串表示的弧度值
- **示例**：
  ```java
  arctangent("0") // 返回 "0"
  arctangent("1") // 返回 "0.7853981633974483" (π/4)
  arctangent("-1") // 返回 "-0.7853981633974483" (-π/4)
  ```

### 对数函数

#### naturalLogarithm

- **功能**：计算自然对数
- **实现**：使用FastMath.log方法
- **参数**：
  - a: 输入数值（字符串表示的正数值）
- **返回值**：字符串表示的自然对数值
- **示例**：
  ```java
  naturalLogarithm("1") // 返回 "0"
  naturalLogarithm("2.718281828459045") // 返回 "1" (e的自然对数)
  naturalLogarithm("10") // 返回 "2.302585092994046"
  ```

#### commonLogarithm

- **功能**：计算以10为底的对数
- **实现**：使用FastMath.log10方法
- **参数**：
  - a: 输入数值（字符串表示的正数值）
- **返回值**：字符串表示的常用对数值
- **示例**：
  ```java
  commonLogarithm("1") // 返回 "0"
  commonLogarithm("10") // 返回 "1"
  commonLogarithm("100") // 返回 "2"
  ```

#### logarithm

- **功能**：计算以指定底数的对数
- **实现**：使用对数换底公式 log_b(x) = log_e(x) / log_e(b)
- **参数**：
  - a: 输入数值（字符串表示的正数值）
  - base: 底数（字符串表示的正数值，不等于1）
- **返回值**：字符串表示的对数值
- **示例**：
  ```java
  logarithm("8", "2") // 返回 "3"
  logarithm("9", "3") // 返回 "2"
  logarithm("100", "10") // 返回 "2"
  ```

#### exponential

- **功能**：计算e的幂
- **实现**：使用FastMath.exp方法
- **参数**：
  - a: 指数（字符串表示的数值）
- **返回值**：字符串表示的e^a的值
- **示例**：
  ```java
  exponential("0") // 返回 "1"
  exponential("1") // 返回 "2.718281828459045" (e)
  exponential("2") // 返回 "7.38905609893065" (e^2)
  ```

## AdvancedMathService

AdvancedMathService提供高级数学功能，包括表达式处理、微积分、方程求解等。该服务使用Symja库实现符号计算。

### 表达式处理

#### simplifyExpression

- **功能**：简化数学表达式
- **实现**：使用Symja的Simplify函数
- **参数**：
  - expression: 要简化的表达式（字符串）
- **返回值**：简化后的表达式（字符串）
- **示例**：
  ```java
  simplifyExpression("x^2+2*x+1") // 返回 "(x+1)^2"
  simplifyExpression("sin(x)^2+cos(x)^2") // 返回 "1"
  simplifyExpression("a+a") // 返回 "2*a"
  ```

#### expandExpression

- **功能**：展开数学表达式
- **实现**：使用Symja的ExpandAll和HornerForm函数
- **参数**：
  - expression: 要展开的表达式（字符串）
- **返回值**：展开后的表达式（字符串）
- **示例**：
  ```java
  expandExpression("(x+1)^2") // 返回 "1+x*(2+x)"
  expandExpression("(x+1)*(x-1)") // 返回 "-1+x^2"
  expandExpression("(a+b)*(c+d)") // 返回 "a*c+a*d+b*c+b*d"
  ```

#### factorExpression

- **功能**：因式分解表达式
- **实现**：使用Symja的Factor函数
- **参数**：
  - expression: 要因式分解的表达式（字符串）
- **返回值**：因式分解后的表达式（字符串）
- **示例**：
  ```java
  factorExpression("x^2-1") // 返回 "(x-1)*(x+1)"
  factorExpression("x^2+2*x+1") // 返回 "(1+x)^2"
  factorExpression("x^3-1") // 返回 "(x-1)*(1+x+x^2)"
  ```

#### substituteVariable

- **功能**：替换表达式中的变量
- **实现**：使用Symja的ReplaceAll函数
- **参数**：
  - expression: 原表达式（字符串）
  - variable: 要替换的变量（字符串）
  - value: 替换的值（字符串）
- **返回值**：替换后的表达式（字符串）
- **示例**：
  ```java
  substituteVariable("x^2+y^2", "x", "2") // 返回 "4+y^2"
  substituteVariable("x+y", "y", "x") // 返回 "x+x"
  substituteVariable("sin(x)", "x", "0") // 返回 "0"
  ```

#### parseExpression

- **功能**：解析表达式
- **实现**：使用Symja的eval方法直接计算
- **参数**：
  - expression: 要解析的表达式（字符串）
- **返回值**：解析后的表达式（字符串）
- **示例**：
  ```java
  parseExpression("1+1") // 返回 "2"
  parseExpression("sin(0)") // 返回 "0"
  parseExpression("2^3") // 返回 "8"
  ```

#### executeCommand

- **功能**：执行Symja命令
- **实现**：使用Symja的eval方法执行命令，并进行安全性验证
- **参数**：
  - command: 要执行的Symja命令（字符串）
- **返回值**：命令执行结果（字符串）
- **示例**：
  ```java
  executeCommand("Solve(x^2-1==0, x)") // 返回 "{{x->-1},{x->1}}"
  executeCommand("FactorInteger(100)") // 返回 "{{2,2},{5,2}}"
  executeCommand("Sum(k, {k,1,10})") // 返回 "55"
  ```

### 微积分

#### differentiate

- **功能**：计算单变量函数的导数
- **实现**：使用Symja的D函数
- **参数**：
  - expression: 函数表达式（字符串）
  - variable: 变量（字符串）
- **返回值**：导数表达式（字符串）
- **示例**：
  ```java
  differentiate("x^2", "x") // 返回 "2*x"
  differentiate("Sin(x)", "x") // 返回 "Cos(x)"
  differentiate("e^x", "x") // 返回 "e^x*Log(e)"
  ```

#### partialDerivative

- **功能**：计算多变量函数的偏导数
- **实现**：使用Symja的D函数，指定变量和阶数
- **参数**：
  - expression: 函数表达式（字符串）
  - variable: 变量（字符串）
  - order: 导数阶数（字符串）
- **返回值**：偏导数表达式（字符串）
- **示例**：
  ```java
  partialDerivative("x^2*y^3", "x", "1") // 返回 "2*x*y^3"
  partialDerivative("x^2*y^3", "y", "1") // 返回 "3*x^2*y^2"
  partialDerivative("x^2*y^3", "x", "2") // 返回 "2*y^3"
  ```

#### indefiniteIntegral

- **功能**：计算不定积分
- **实现**：使用Symja的Integrate函数
- **参数**：
  - expression: 被积函数表达式（字符串）
  - variable: 积分变量（字符串）
- **返回值**：不定积分表达式（字符串）
- **示例**：
  ```java
  indefiniteIntegral("x", "x") // 返回 "x^2/2"
  indefiniteIntegral("x^2", "x") // 返回 "x^3/3"
  indefiniteIntegral("Sin(x)", "x") // 返回 "-Cos(x)"
  ```

#### definiteIntegral

- **功能**：计算定积分
- **实现**：使用Symja的Integrate函数，指定积分上下限
- **参数**：
  - expression: 被积函数表达式（字符串）
  - variable: 积分变量（字符串）
  - lowerBound: 积分下限（字符串）
