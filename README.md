# Javascript vs Python

### Print
```python
# PY
print()
```
```javascript
// JS
console.log();
```

### Input
```python
# PY
value = input('입력: ')
print(type(value)) # <class 'str'>
```

### Type Check
```python
# PY
type('abcde') # <type 'str'>
type(5) # <type 'int'>
type(4.7) # <type 'float'>
```
```javascript
// JS
typeof 'abcde'; // 'string'
```

### Type Casting
```python
# PY
a = int('52')
b = float('52.2')
c = int('abc')

print(a) # 52
print(b) # 52.2
print(c) # Value Error

print(type(a)) # <class 'int'>
print(type(b)) # <class 'float'>
```
```javascript
// JS
var a = '52';
var b = '52.2';
var c = 'abc';

parseInt(a); // 52
parseFloat(b); // 52.2
parseInt(c); // NaN
```

### String
- len('str')
```python
# PY
len('abcde')
```
```javascript
// JS
'abcde'.length;
```

- line break
```python
# PY
multiline = '''
Life is too short
You need python
'''
```

- str.slice()
```python
# PY
'abcde'[0:2] # ab
'abcde'[2:] # cde
'abcde'[:2] # ab
'abcde'[3:-1] # d
```
```javascript
// JS
'abcde'.slice(0, 2); // ab
```

- str.format()
```python
# PY
result = '{}'.format(11)
result # '11'
print(type(result)) # <class 'str'>

a = '{}원'.format(3000)
print(a) # '3000원'

b = '{} {} {}'.format(1, 2, 3)
print(b) # '1 2 3'

c = '{} {} {}'.format(1, '문자', True)
print(c) # '1 문자 True'

# '{}' 개수가 format() 함수의 매개변수 개수보다 많으면 에러
'{} {}'.format(1, 2, 3, 4) # '1 2'
'{} {} {}'.format(1, 2) # Index Error

'Hey, {name}. It\'s {num}PM.'.format(name='Hank', num=3)
# "Hey, Hank. It's 3PM."

'Hey, {0}. It\'s {1}PM.'.format('Hank', 3)
# "Hey, Hank. It's 3PM."
```

- f-string (3.6v+)
```python
# PY
name = 'Sarah'
sister = '\'s sister'
age = 27

f'{name} is {age} years old.' 
# 'Sarah is 27 years old.'
f'{name} will be {age + 1} years old next year.' 
# 'Sarah will be 28 years old next year.'
f'{name + add} will be {age + 3} years old next year.'
# "Sarah's sister will be 30 years old next year."

d = {'name': 'Sarah', 'age': 27} # dictionary
f'{d["name"]} will be {d["age"] + 1} years old next year.' 
# 'Sarah will be 28 years old next year.'

sentence = f'I like {fruit}.'
fruit = 'mango'
```

- str.upper() / str.lower()
```python
# PY
word = 'abcde'
word.upper() # 'ABCDE'
print(word) # 'abcde'

WORD = 'ABCDE'
WORD.lower() # 'abcde'
print(WORD) # 'ABCDE'

# 원본을 변화시키지 않는 '비파괴적 함수'
```
```javascript
// JS
var str = 'abc';
str.toUpperCase(); // 'ABC'
console.log(str); // 'abc'
```

- str.strip()
```python
# PY
a = '''
  hello        '''
a.strip() # 'hello'
print(a) # '\n  hello        '
```
```javascript
// JS
var str = '    abc  ';
str.trim(); // 'abc'
```

- str.count()
```python
# PY
fruit = 'banana'
fruit.count('a') # 3
```
```javascript
// JS
var fruit = 'banana';
var result = fruit.match(/a/g); // ["a", "a", "a"]
result.length; //3
```

- str.find() / str.rfind()
```python
# PY
fruit = 'banana'
fruit.find('n') # 2
fruit.rfind('n') # 4
fruit.find('c') # 없으면 -1 
```

- str.index()
```python
# PY
fruit = 'banana'
fruit.index('a') # 1
fruit.index('c') # 없으면 Value Error
```
```javascript
// JS
var fruit = 'banana';
fruit.indexOf('n'); // 2
fruit.indexOf('c'); // -1
```

- str.replace()
```python
# PY
a = 'Life is too short'
a.replace('Life', 'Your leg') # 'Your leg is too short'
a.replace('Like', 'Your leg') # 'Life is too short'
```
```javascript
// JS
var a = 'Life is too short';
a.replace('Life', 'Your leg'); // 'Your leg is too short'
```

- str.split()
```python
# PY
a = 'Life is too short'
a.split() # ['Life', 'is', 'too', 'short']
a.split( ) # ['Life', 'is', 'too', 'short']
a.split('') # Value Error: empty separator
a.split(' ') # ['Life', 'is', 'too', 'short']
a.split('i') # ['L', 'fe ', 's too short']
```
```javascript
// JS
var a = 'Life is too short';
a.split(); // ["Life is too short"]
a.split(''); //  ["L", "i", "f", "e", " ", "i", "s", " ", "t", "o", "o", " ", "s", "h", "o", "r", "t"]
a.split(' '); // ["Life", "is", "too", "short"]
a.split('i'); // ["L", "fe ", "s too short"]
```

- join
```python
# PY
','.join('abcd') # 'a,b,c,d'
' '.join('abcd') # 'a b c d'
','.join(['a', 'b', 'c', 'd']) # 'a,b,c,d'
''.join(['a', 'b', 'c', 'd']) # 'abcd'
```
```javascript
// JS
var arr = ['a', 'b' ,'c' ,'d'];
arr.join(); // 'a,b,c,d'
arr.join(''); // 'abcd'
arr.join(' '); // 'a b c d'
```

- str1 in str2
```python
# PY
a = 'Life is too short'
'Life' in a # True
'life' in a # False
'Like' in a # False
```
```javascript
// JS
var a = 'Life is too short';
a.includes('Life'); // true
a.includes('life'); // false
a.includes('Like'); // false
```

- str.is~~()
```python
# PY
a = '12ab@#'
b = '12abc'
c = 'abcde'
d = '123'
e = 'aBCdE'
f = 'ABC'

a.isalnum() # False
b.isalnum() # True
c.isalpha() # True
c.isdigit() # False
d.isdigit() # True
e.islower() # False
f.isupper() # True
```

### Number
- // (나눗셈 후 몫 반환)
```python
# PY
print(3 // 2) # 1
```
```javascript
// JS
var num = 3.23123;
Math.floor(num); // 3
```

- ** (제곱 연산자)
```python
# PY
print(2 ** 3) # 8
```
```javascript
// JS
Math.pow(2, 3); // 8
```

### Boolean
- not
```python
# PY
not True # False
not False # True
not not True # True
```
```javascript
// JS
!true // false
!false // true
!!true // true
```

### Conditional Statement
```python
# PY
month = 7
if 3 <= month <= 5:
  print('spring')
elif 6 <= month <= 8:
  print('summer')
elif 9 <= month <= 11:
  print('autumn')
else:
  print('winter')
# summer
```
