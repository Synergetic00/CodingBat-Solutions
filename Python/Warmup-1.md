# Warmup-1

Simple warmup problems to get started, no loops

## sleep_in

The parameter weekday is True if it is a weekday, and the parameter vacation is True if we are on vacation. We sleep in if it is not a weekday or we're on vacation. Return True if we sleep in.

* sleep_in(False, False) → True
* sleep_in(True, False) → False
* sleep_in(False, True) → True

```python
def sleep_in(weekday, vacation):
    return not weekday or vacation
```

## monkey_trouble

We have two monkeys, a and b, and the parameters a_smile and b_smile indicate if each is smiling. We are in trouble if they are both smiling or if neither of them is smiling. Return True if we are in trouble.

* monkey_trouble(True, True) → True
* monkey_trouble(False, False) → True
* monkey_trouble(True, False) → False

```python
def monkey_trouble(a_smile, b_smile):
    return a_smile is b_smile
```

## sum_double

Given two int values, return their sum. Unless the two values are the same, then return double their sum.

* sum_double(1, 2) → 3
* sum_double(3, 2) → 5
* sum_double(2, 2) → 8

```python
def sum_double(a, b):
    return (a+b)*2 if a is b else a+b
```

## diff21

Given an int n, return the absolute difference between n and 21, except return double the absolute difference if n is over 21.

* diff21(19) → 2
* diff21(10) → 11
* diff21(21) → 0

```python
def diff21(n):
    return (n-21)*2 if n > 21 else 21-n
```

## parrot_trouble

We have a loud talking parrot. The "hour" parameter is the current hour time in the range 0..23. We are in trouble if the parrot is talking and the hour is before 7 or after 20. Return True if we are in trouble.

* parrot_trouble(True, 6) → True
* parrot_trouble(True, 7) → False
* parrot_trouble(False, 6) → False

```python
def parrot_trouble(talking, hour):
    return talking and (hour < 7 or hour > 20)
```

## makes10

```python
```

## near_hundred

```python
```

## pos_neg

```python
```

## not_string

```python
```

## missing_char

```python
```

## front_back

```python
```

## front3

```python
```