# Python vs Javascript

- 파이썬과 자바스크립트의 기초 문법을 비교합니다. 
- 자바스크립트를 먼저 학습한 상태에서 둘의 다른 점 위주로 정리했습니다. 
- 내용 추가 중입니다. 

## Index
- [Print](#Print)
- [Input](#Input)
- [Type Check](#Type-Check)
- [Type Casting](#Type-Casting)
- [String](#String)
  - [line break](#line-break)
  - [len('str')](#len('str'))
  - [str.slice()](#str.slice())
  - [str.format()](#str.format())
  - [f-string (3.6v+)](#f-string-(3.6v+))
  - [str.upper() / str.lower()](#str.upper()-/-str.lower())
  - [str.capitalize()](#str.capitalize())
  - [str.title()](#str.title())
  - [str.swapcase()](#str.swapcase())
  - [str.strip()](#str.strip())
  - [str.count()](#str.count())
  - [str.find() / str.rfind()](#str.find()-/-str.rfind())
  - [str.index()](#str.index())
  - [str.replace()](#str.replace())
  - [str.split()](#str.split())
  - [join](#join)
  - [str1 in str2](#str1-in-str2)
  - [str.is~~()](#str.is~~())
- [Number](#Number)
  - [/](#/)
  - [//](#//)
  - [\*\*](#\*\*)
  - [abs](#abs)
- [Boolean](#Boolean)
  - [not](#not)
- [List](#List)
  - [create list](#create-list)
  - [index](#index)
  - [slice](#slice)
  - [list.append()](#list.append())
  - [list.extend()](#list.extend()-/-+=)
  - [list.insert()](#list.insert())
  - [list.remove()](#list.remove())
  - [list.pop()](#list.pop())
  - [del (list)](#del-(list))
  - [list.clear()](#list.clear())
  - [list.index()](#list.index())
  - [in (list)](#in-(list))
  - [list.count()](#list.count())
  - [list.sort() / sorted(list)](#list.sort()-/-sorted(list))
  - [len(list)](#len(list))
  - [list.copy()](#list.copy())
- [Tuple](#Tuple)
  - [create tuple](#create-tuple)
  - [unpacking](#unpacking)
- [Dictionary](#Dictionary)
  - [create dictionary](#create-dictionary)
  - [dict.update()](#dict.update())
  - [del (dict)](#del-(dict))
  - [dict.clear()](#dict.clear())
  - [in (dict)](#in-(dict))
  - [dict.get()](#dict.get())
  - [dict.keys()](#dict.keys())
  - [dict.values()](#dict.values())
  - [dict.items()](#dict.items())
  - [dict.copy()](#dict.copy())
- [Conditions](#Conditions)
  - [If statement](#If-statement)
  - [short hand If](#short-hand-If)
  - [short hand If ... Else](#short-hand-If-...-Else)
  - [Ternary](#Ternary)
- [Loop](#Loop)
  - [While loop](#While-loop)
<br />

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
type(value) # <class 'str'>
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

## String
### line break
```python
# PY
multiline = '''
Life is too short
You need python
'''
```

### len('str')
```python
# PY
len('abcde') # 5
```
```javascript
// JS
'abcde'.length; // 5
```

### str.slice()
```python
# PY
'abcde'[0:2] # 'ab'
'abcde'[2:] # 'cde'
'abcde'[:2] # 'ab'
'abcde'[3:-1] # 'd'
'abcde'[::2] # 'ace'
'abcde'[::-1] # 'edcba'
```
```javascript
// JS
'abcde'.slice(0, 2); // 'ab'
```

### str.format()
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

### f-string (3.6v+)
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
```

### str.upper() / str.lower()
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

### str.capitalize()
```python
# PY
a = 'a duck goes into a bar'
a.capitalize() # 'A duck goes into a bar'
```

### str.title()
```python
# PY
a = 'a duck goes into a bar'
a.title() # 'A Duck Goes Into A Bar'
```

### str.swapcase()
```python
# PY
a = 'abCDEfg'
a.swapcase() # 'ABcdeFG'
```

### str.strip()
```python
# PY
a = '''
  hello        '''
a.strip() # 'hello'
print(a) # '\n  hello        '

b = 'aaabbcca'
b.strip('a') # 'bbcc'
```
```javascript
// JS
var str = '    abc  ';
str.trim(); // 'abc'
```

### str.count()
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

### str.find() / str.rfind()
```python
# PY
fruit = 'banana'
fruit.find('n') # 2
fruit.rfind('n') # 4
fruit.find('c') # 없으면 -1
```

### str.index()
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

### str.replace()
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

### str.split()
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

### join
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

### str1 in str2
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

### str.is~~()
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

## Number
### / 
```python
# PY
print(5 / 0) # ZeroDivisionError: division by zero
```
```javascript
// JS
console.log(5 / 0); // Infinity
```

### //
```python
# PY
3 // 2 # 1
```
```javascript
// JS
var num = 3.23123;
Math.floor(num); // 3
```

### **
```python
# PY
2 ** 3 # 8
pow(2, 3) # 8
```
```javascript
// JS
Math.pow(2, 3); // 8
```

### abs
```python
# PY
abs(-1) # 1

import math
math.fabs(-1) # 1.0
```
```javascript
// JS
Math.abs(-1); // 1
```

## Boolean
### not
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

## List
### create list
```python
# PY
empty_list = []
another_empty_list = list()

weekdays = ['Mon', 'Tue', 'Wed', 'Thu', 'Fri']

list('cat') # ['c', 'a', 't']

t = ('a', 'b', 'c') # tuple
list(t) # ['a', 'b', 'c']
```
```javascript
// JS
var empty_array = []
var another_empty_array = new Array()

var weekdays = ['Mon', 'Tue', 'Wed', 'Thu', 'Fri']
```

### index
```python
# PY
weekdays = ['Mon', 'Tue', 'Wed', 'Thu', 'Fri']
weekdays[0] # 'Mon'
weekdays[-1] # 'Fri'
```
```javascript
// JS
var weekdays = ['Mon', 'Tue', 'Wed', 'Thu', 'Fri'];
weekdays[0]; // 'Mon'
weekdays[-1]; // undefined
weekdays[weekdays.length - 1]; // 'Fri'
```

### slice
```python
# PY
weekdays = ['Mon', 'Tue', 'Wed', 'Thu', 'Fri']
weekdays[0:2] # ['Mon', 'Tue']
weekdays[::2] # ['Mon', 'Wed', 'Fri']
weekdays[::-1] # ['Fri', 'Thu', 'Wed', 'Tue', 'Mon']

weekdays # ['Mon', 'Tue', 'Wed', 'Thu', 'Fri'] -> 원본 그대로 유지
```
```javascript
// JS
var weekdays = ['Mon', 'Tue', 'Wed', 'Thu', 'Fri'];

weekdays.slice(0, 2); // ["Mon", "Tue"]
weekdays // ["Mon", "Tue", "Wed", "Thu", "Fri"] -> 원본 그대로 유지

weekdays.reverse(); // ["Fri", "Thu", "Wed", "Tue", "Mon"]
weekdays // ["Fri", "Thu", "Wed", "Tue", "Mon"] -> 원본 변경
```

### list.append()
```python
# PY
week = ['Mon', 'Tue', 'Wed', 'Thu', 'Fri']
week.append('Sat') 
week # ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat']
```
```javascript
// JS
var week = ['Mon', 'Tue', 'Wed', 'Thu', 'Fri'];
week.push('Sat'); // 6
week // ["Mon", "Tue", "Wed", "Thu", "Fri", "Sat"]
```

### list.extend() / +=
```python
# PY
weekdays = ['Mon', 'Tue', 'Wed', 'Thu', 'Fri']
weekend = ['Sat', 'Sun']

weekdays.extend(weekend) 
weekdays # ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun']

weekdays += weekend 
weekdays # ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun']
```
```javascript
// JS
var weekdays = ['Mon', 'Tue', 'Wed', 'Thu', 'Fri'];
var weekend = ['Sat', 'Sun'];

weekdays.concat(weekend); // ["Mon", "Tue", "Wed", "Thu", "Fri", "Sat", "Sun"]
weekdays; // ["Mon", "Tue", "Wed", "Thu", "Fri"] -> 원본 그대로 유지

weekdays.push(...weekend); // 7
weekdays; // ["Mon", "Tue", "Wed", "Thu", "Fri", "Sat", "Sun"]
```

### list.insert()
```python
# PY
alphabet = ['a', 'c', 'd', 'e']
alphabet.insert(1, 'b') 
alphabet # ['a', 'b', 'c', 'd', 'e']
alphabet.insert(10, 'z')
alphabet # ['a', 'b', 'c', 'd', 'e', 'z']
```
```javascript
// JS
var alphabet = ['a', 'c', 'd', 'e'];
alphabet.splice(1, 0, 'b'); // []
alphabet; // ["a", "b", "c", "d", "e"]
```

### list.remove()
```python
# PY
alphabet = ['a', 'a', 'b', 'c', 'd', 'e']
alphabet.remove('b') 
alphabet # ['a', 'a', 'c', 'd', 'e']
alphabet.remove('a')
alphabet # ['a', 'c', 'd', 'e']
alphabet.remove('b') # ValueError: list.remove(x): x not in list
```

### list.pop()
```python
# PY
alphabet = ['a', 'b', 'c', 'd', 'e']
alphabet.pop() # 'e'
alphabet # ['a', 'b', 'c', 'd']
alphabet.pop(-1) # 'd'
alphabet # ['a', 'b', 'c']
alphabet.pop(0) # 'a'
alphabet # ['b', 'c']

empty_list = []
empty_list.pop() # IndexError: pop from empty list
```
```javascript
// JS
var alphabet = ['a', 'b', 'c', 'd', 'e'];
alphabet.pop(); // "e"
alphabet; // ["a", "b", "c", "d"]
alphabet.shift(); // "a"
alphabet; // ["b", "c", "d"]

var empty_array = [];
empty_array.pop(); // undefined
```

### del (list)
```python
# PY
alphabet = ['a', 'b', 'c', 'd', 'e']
del(alphabet[2])
alphabet # ['a', 'b', 'd', 'e']

alphabet = ['a', 'b', 'c', 'd', 'e']
del(alphabet[0:2])
alphabet # ['c', 'd', 'e']

alphabet = ['a', 'b', 'c', 'd', 'e']
del(alphabet[:])
alphabet # []
```

```javascript
// JS
var alphabet = ['a', 'b', 'c', 'd', 'e'];
alphabet.splice(0, 2); // ["a", "b"]
alphabet; // ["c", "d", "e"]

alphabet.splice(0); // ["c", "d", "e"]
alphabet; // []
```

### list.clear()
```python
# PY
alphabet = ['a', 'b', 'c', 'd', 'e']
alphabet.clear()
alphabet # []
```

### list.index()
```python
# PY
names = ['Smith', 'Maria', 'John', 'Tracy']
names.index('Maria') # 1
```
```javascript
// JS
var names = ['Smith', 'Maria', 'John', 'Tracy'];
names.indexOf('Maria'); // 1
```

### in (list)
```python
# PY
names = ['Smith', 'Maria', 'John', 'Tracy']
'John' in names # True
'Emily' in names # False
```
```javascript
// JS
var names = ['Smith', 'Maria', 'John', 'Tracy'];
names.includes('John'); // true
names.includes('Emily'); // false
```

### list.count()
```python
names = ['Smith', 'Maria', 'John', 'Tracy']
names.count('John') # 1
names.count('Emily') # 0

hellos = ['hello', 'hello', 'hello']
hellos.count('hello') # 3
```
```javascript
// JS
var names = ['Smith', 'Maria', 'John', 'Tracy'];
var count = 0;
for (var i = 0; i < names.length; i++) {
	if (names[i] === 'John') {
		count++;
	}
}
console.log('count', count); # 1
```

### list.sort() / sorted(list)
```python
# PY
alphabet = ['d', 'a', 'b', 'c']
alphabet.sort()
alphabet # ['a', 'b', 'c', 'd'] -> 원본 배열 수정

alphabet = ['d', 'a', 'b', 'c']
sorted(alphabet) # ['a', 'b', 'c', 'd'] -> 복사본 반환
alphabet # ['d', 'a', 'b', 'c']

numbers = [10, 1, 13, 1.3, 2, 2.222]
numbers.sort
numbers # [1, 1.3, 2, 2.222, 10, 13]

numbers = [10, 1, 13, 1.3, 2, 2.222]
numbers.sort(reverse=True)
numbers # [13, 10, 2.222, 2, 1.3, 1]
```
```javascript
// JS
var alphabet = ['d', 'a', 'b', 'c'];
alphabet.sort(); // ["a", "b", "c", "d"]
alphabet; // ["a", "b", "c", "d"] -> 원본 배열 수정

var numbers = [10, 1, 13, 3, 2, 22];
numbers.sort(); // [1, 10, 13, 2, 22, 3]
numbers.sort((a, b) => a - b); // [1, 2, 3, 10, 13, 22]
numbers.sort((a, b) => b - a); // [22, 13, 10, 3, 2, 1]
```

### len(list)
```python
# PY
names = ['Smith', 'Maria', 'John', 'Tracy']
len(names) # 4
```
```javascript
// JS
var names = ['Smith', 'Maria', 'John', 'Tracy'];
names.length // 4 
```

### list.copy()
```python
# PY
a = [1, 2, 3]
b = a 
b # [1, 2, 3]
a[0] = 'a'
a # ['a', 2, 3]
b # ['a', 2, 3]

a = [1, 2, 3]
b = a.copy()
c = list(a)
d = a[:]
a[0] = 'a'
a # ['a', 2, 3]
b # [1, 2, 3]
c # [1, 2, 3]
d # [1, 2, 3]
```
```javascript
// JS
var a = [1, 2, 3];
b = a;
b; // [1, 2, 3]
a[0] = 'a';
a; // ['a', 2, 3]
b; // ['a', 2, 3]

var a = [1, 2, 3];
b = a.slice();
c = [...a];
a[0] = 'a';
a; // ['a', 2, 3]
b; // [1, 2, 3]
c; // [1, 2, 3]
```

## Tuple
### create tuple
```python
# PY
empty_tuple = ()
names = ('Emily', 'Sally', 'Tom')
```

### unpacking
```python
# PY
names = ('Emily', 'Sally', 'Tom')
a, b, c = names
a # 'Emily'
b # 'Sally'
c # 'Tom'
d # NameError: name 'x' is not defined

a, b, c = c, a, b
a # 'Tom'
b # 'Emily'
c # 'Sally'
```

## Dictionary
### create dictionary
```python
# PY
empty_dict = {}
another_empty_dict = dict()

lol = [['a', 'b'], ['c', 'd'], ['e', 'f']]
dict(lol) # {'a': 'b', 'c': 'd', 'e': 'f'}

lot = [('a', 'b'), ('c', 'd'), ('e', 'f')]
dict(lot) # {'a': 'b', 'c': 'd', 'e': 'f'}

tol = (['a', 'b'], ['c', 'd'], ['e', 'f'])
dict(tol) # {'a': 'b', 'c': 'd', 'e': 'f'}

los = ['ab', 'cd', 'ef']
dict(los) # {'a': 'b', 'c': 'd', 'e': 'f'}

tos = ('ab', 'cd', 'ef')
dict(tos) # {'a': 'b', 'c': 'd', 'e': 'f'}
```
```javascript
// JS
var empty_obj = {};
var another_empty_obj = new Object();
var obj = {'a': 'b', 'c': 'd', 'e': 'f'}
```

### dict.update()
```python
# PY
dict1 = {'a': 1}
dict2 = {'b': 2}
dict1.update(dict2)

dict1 # {'a': 1, 'b': 2}
dict2 # {'b': 2}
```
```javascript
// JS
var obj1 = {'a': 1};
var obj2 = {'b': 2};
Object.assign(obj1, obj2);

obj1; // {a: 1, b: 2}
obj2; // {b: 2}
```

### del (dict)
```python
# PY
dict1 = {'a': 1, 'b': 2}
del dict1['a']
dict1 # {'b': 2}

del dict1['c'] # KeyError: 'c'
```
```javascript
// JS
var obj = {'a': 1, 'b': 2}
delete obj.a // true
obj // {b: 2}

delete obj.c // true
obj // {b: 2}
```

### dict.clear()
```python
# PY
dict1 = {'a': 1, 'b': 2}
dict1.clear()
dict1 # {}

dict1 = {'a': 1, 'b': 2}
dict1 = {}
dict1 # {}
```

### in (dict)
```python
# PY
dict1 = {'a': 1, 'b': 2, 'c': 3}
'a' in dict1 # True
'd' in dict1 # False
```
```javascript
// JS
var obj = {'a': 1, 'b': 2, 'c': 3}
Object.keys(obj).includes('a') // true
Object.keys(obj).includes('d') // false
```

### dict.get()
```python
# PY
dict1 = {'a': 1, 'b': 2, 'c': 3}

dict1['a'] # 1
dict1['c'] # KeyError: 'd'

dict1.get('a') # 1
dict1.get('d') # 아무것도 출력 안됨
dict1.get('d', 'Nope') # 'Nope' -> 옵션값 지정 가능
```
```javascript
// JS
var obj = {'a': 1, 'b': 2, 'c': 3};
obj.a; // a
obj.d; // undefined
```

### dict.keys()
```python
# PY
dict1 = {'a': 1, 'b': 2, 'c': 3}
dict1.keys() # dict_keys(['a', 'b', 'c'])
```
```javascript
// JS
var obj = {'a': 1, 'b': 2, 'c': 3};
Object.keys(obj); // ["a", "b", "c"]
```

### dict.values()
```python
# PY
dict1 = {'a': 1, 'b': 2, 'c': 3}
dict1.values() # dict_values([1, 2, 3])
```
```javascript
// JS
var obj = {'a': 1, 'b': 2, 'c': 3};
Object.values(obj); // [1, 2, 3]
```

### dict.items()
```python
# PY
dict1 = {'a': 1, 'b': 2, 'c': 3}
dict1.items() # dict_items([('a', 1), ('b', 2), ('c', 3)])
```

### dict.copy()
```python
# PY
dict1 = {'a': 1, 'b': 2}
dict2 = dict1
dict1['b'] = 3
dict1 # {'a': 1, 'b': 3}
dict2 # {'a': 1, 'b': 3}

dict1 = {'a': 1, 'b': 2}
dict2 = dict1.copy()
dict1['b'] = 3
dict1 # {'a': 1, 'b': 3}
dict2 # {'a': 1, 'b': 2}
```
```javascript
// JS
var obj1 = {'a': 1, 'b': 2};
obj2 = obj1;
obj1.b = 3;
obj1; // {a: 1, b: 3}
obj2; // {a: 1, b: 3}

var obj1 = {'a': 1, 'b': 2};
obj2 = {...obj1};
obj1.b = 3;
obj1; // {a: 1, b: 3}
obj2; // {a: 1, b: 2}
```

## Conditions
### If statement
```python
# PY
a = 200
b = 33

if b > a:
  print("b is greater than a")
elif a == b:
  print("a and b are equal")
else:
  print("a is greater than b")
```

### short hand If
```python
# PY
a = 200
b = 33

if a > b: print('a is greater than b') # 'a is greater than b'
```
```javascript
// JS
var a = 200;
var b = 33;

if (a > b) console.log('a is greater than b'); // 'a is greater than b'
```

### short hand If ... Else
```python
# PY
a = 200
b = 33

print('A') if a > b else print('B') # A
```
```javascript
// JS
var a = 200;
var b = 33;

a > b ? console.log('A') : console.log('B'); // A
```

### Ternary
```python
# PY
a = 200
b = 33

print('A') if a > b else print('=') if a == b else print('B')
```
```javascript
// JS
var a = 200;
var b = 33;

a > b ? console.log('A') : a === b ? console.log('=') : console.log('B');
```

## Loop
### While loop
```python
# PY
i = 1
while i < 6:
  print(i)
  i += 1

# 1 2 3 4 5
```
