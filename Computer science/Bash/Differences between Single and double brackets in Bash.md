---
URL: https://www.baeldung.com/linux/bash-single-vs-double-brackets#:~:text=The%20single%20bracket%20is%20a,brackets%20is%20generally%20more%20convenient.
---

## 1. Overview
- For comparing variables in Bash, 
```
[ 3 -eq 3 ] equal to [[ 3 -eq 3 ]]
```
## 2. Main Differences

### 2.1 Single Brackets
- Single Brakets is a shell buit-in command
- Single Brackets is an alternative command for the *test* built-in command
### 2.2 Double Brackets
- Double brackets is a shell keyword
- Double brakets aren't [[POSIX]] compliant
## 3. Other Differences
### 3.1 Comparison operators
- It's possible to use the comparison operators with the double brackets
```
# Double Bracket
$ [[ 1 < 2 ]] && echo “1 is less than 2” 
-> 1 is less than 2

#Single Bracket
$ [ 1 < 2 ] && echo “1 is less than 2” 
-> bash: 2: No such file or directory
```
-  In this case, Bash treated the < operator as a file redirection operator. Hence, we must use escape character (\) before the < operator.
```
$ [ 1 \< 2 ] && echo “1 is less than 2” 
1 is less than 2
```
### 3.2 Boolean operators
- && operator for the logical AND operation and the // operator for logical OR operation while using the **double brackets**
- However we must use the -o and -a test operators for the logical OR and logical AND operations. 
### 3.3 Grouping Expressions
```
[[ 3 -eq 3 && (2 -eq 2 && 1 -eq 1) ]] && echo “Parentheses can be used”
Parentheses can be used
```

```
$ [ 3 -eq 3 -a (2 -eq 2 -a 1 -eq 1) ] && echo “Parentheses can be used” bash: syntax error near unexpected token ‘(‘
```

```
[ 3 -eq 3 -a \( 2 -eq 2 -a 1 -eq 1 \) ] && echo “Parentheses can be used”
Parentheses can be used
```

### 3.4 Pattern Matching
- **It's possible to use pattern matching with the double brackets**
```
name=”Alice”
[[ $name = *c* ]] && echo “Name includes c”
Name includes c
echo $?
0
```
- Not possible with single bracket
### 3.5 Regular expression
- **It's possible to use [[Regular expression]] within the double brackets** but not with single bracket
```
name=”Alice”
[[ $name =~ ^Ali ]] && echo ”Regular expressions can be used”
Regular expressions can be used
```
### 3.6 Word splitting
