# JSLisp
（this document fix： 2020/11/27 create: 2020/11/5）

## Status
Creation Period：2020.7~
Version： -

## About program
I am developing it as a graduation research project of "Special Research on Computer Science and Engineering IIA/IIB" in Department of Computer Science and Engineering, Kyoto Sangyo University. 

It is under development as of November 27, 2020.
## Execution environment
### OS
```
$ sw_vers
ProductName:	Mac OS X
ProductVersion:	10.15.7
BuildVersion:	19H2
```

### NVM
```
$ nvm --version
0.35.3
```

### Node.js
```
$ node --version
v12.18.3
```

If the OS and Node.js versions match, the following software will be installed automatically when you build your environment.
### Node module
```
$ npm list --depth=0
JSLisp@1.0.0 ~/JSLisp
├── @babel/core@7.12.9
├── @babel/plugin-proposal-class-properties@7.12.1
├── @babel/preset-env@7.12.7
├── babel-loader@8.2.2
├── expose-gc@1.0.0
├── ramda@0.27.1
├── readline@1.3.0
├── webpack@4.44.2
└── webpack-cli@3.3.12

```

## Quick start
### Install
```
$ git clone https://github.com/ike-keichan/JSLisp.git
```

### Build & Launch
```
$ cd ./JSLisp
$ make test
```

### Syntax
+ [Atom](./README_Atom.md)
+ [Cons](./README_Cons.md)
+ [Function](./README_Function.md)

### Example
#### example1
```
>> 1
1

>> -1.2
-1.2

>> a
a

>> nil
nil
```

#### example2
```
>> ()
nil

>> (+ 1 2)
3

>> (+ 1 2.3)
3.3

>> (+ 1.2 3)
4.2

>> (+ 1.2 3.4)
4.6

>> (+ 1.2 -3.4)
-2.2

>> (+ 1 nil)
Can not apply "add" to "nil"
nil

>> (+ nil 1)
Can not apply "add" to "nil"
nil

>> (+ 1.2 nil)
Can not apply "add" to "nil"
nil

>> (+ nil 1.2)
Can not apply "add" to "nil"
nil

```

#### example3
```
>> '(1 . 2)
(1 . 2)

>> '(1 . 2.3)
(1 . 2.3)

>> '(1.2 . 3)
(1.2 . 3)

>> '(1.2 . 3.4)
(1.2 . 3.4)

>> '(1 . nil)
(1)

>> '(nil . 1)
(nil . 1)

>> '(1.2 nil)
(1.2)

>> '(nil 1.2)
(nil 1.2)
```

#### example4
```
>> (car '(1 (2 (3 (4 5) 6) 7 (8 9))))
1

>> (cdr '(1 (2 (3 (4 5) 6) 7 (8 9))))
((2 (3 (4 5) 6) 7 (8 9)))

>> (+ (- (* 1 2) (* 3 4)) (- (* 5 6) (* 7 8)))
-36

>> (+
     1
  2
      )(+ (- (* 1 2) (* 3 4)) (- (* 5 6) (* 7 8)))(
   -
   4
3

)
3
-36
1
```

### example 5
```
>> (defun tasu (a b) (+ a b))
tasu

>> (tasu 7 8)
15

```

---

### Clean
```
$ make clean
```

### Wipe
```
$ make wipe
```

### Lint
```
$ make lint
```

### JSDoc
```
$ make doc
```


