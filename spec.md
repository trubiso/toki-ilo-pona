# toki ilo pona spec v0.0.11

toki ilo is a programming language made to be somewhat compatible with toki
pona's syntax while still being useful

## kule (types)

| Type | Keyword | Literal | Comments |
|---|---|---|---|
| **string** | `lipu` | <p align="center">`te {insa} to`<br>**or**<br>`"{insa}"`</p> | Substitute `{insa}` with whatever you want inside the string. |
| **boolean** | `lili` | <p align="center">`lon` (`true`)<br>**or**<br>`ala` (`false`)</p> | <p align="center">The choice of the keyword `lili` was made<br> because a boolean is a small piece of data.<p> |
| **number** | `nanpa` | `0`, `1`, `2`, `1.1`, `-1`, etc. | <p align="center">***weka***</p> |


## toki (print)

```
o toki te toki a! to
```

### toki tawa lipu pakala (printing to `stderr`)

```
o toki te a ike! to tawa lipu pakala
```

## lipu namako (comments)

```
; this is a comment

o toki te polinpin li epiku! to ; they also work inline.
```


## lipu insa (interpolated strings)

toki ilo pona supports string interpolation.

This is achieved using the `insa` keyword.

```
; define a variable, more on this below.
lipu Teto li te hola! aaaaa kokosila ;-; to

insa te toki! mi toki e ni: [lipu Teto] to ; ensure you use headnouns for your variables
```

## Variables

Variable names must comply with toki pona phonetics and phonotactics.

The compiler will throw a `pakala kokosila` if this is not the case.

### lili (boolean)

```
lili Pulijan li lon
lili Pulijan2 li ala
```

### lipu (string)

```
lipu Po li te ni li lipu mi :) to
lipu Sensa li "ni li lipu mi kin a :)"
```

#### lipu insa (interpolated string)

```
lipu Pa li insa te tenpo poka la mi sitelen e ni: [lipu Po] to
lipu Senso li insa "tenpo poka la mi sitelen e ni kin a: [lipu Sensa]"
```

### nanpa (number)

```
nanpa Ja li 5
```


### kon (dynamic)

Dynamic type infers the type of the variable from the value.

```
kon Su li 5 ; nanpa
```

### kulupu (array)

```
kulupu nanpa Owe li 1, li 9, li 8, li 4  ; the commas are optional

kulupu lipu SonaKala li te kala li moku to, li te kala li pona to

; dynamic array ~ with optional indentation for readability.
kulupu kon NiLiWawa li 1,
                    li 2,
                    li te owe to,
                    li insa te ni li nanpa: [nanpa Ja] to
```

#### kulupu lili (tuples)

```
; this creates a tuple of 3 numbers
kulupu nanpa pi ijo 3 taso Mija li 1, li 2, li 3
```

# WIP after this point


## labels and goto
To make a label, the `ma [label name]:` syntax is used.

To jump to it (goto), the `o tawa ma [label name]` construction is used.

```
o toki te kijetesantakalu li toki e to
o tawa ma Konsu

o toki te mu to ; this code will not be executed

ma Konsu:
o toki te toki a! to
```

## if/else statements
For if/else statements, the la particle from toki pona is used.

```
lipu Sawento li te soweli to

lipu Sawento li te waso to la
  ; insa

  ; else if (otherwise, ...)
ante la, lipu Sawento li te pipi la
  ; insa

  ; else (otherwise)
ante la
  ; insa
pini ; it is important to finish the if statement with the pini keyword
```

## while/for loops
While and for loops do not exist explicitly in toki ilo pona. This is
because we already have what we need: goto and if/else statements.

```
; while loops

; uses labels
nimi Mu:
Pulijan li lon la
  ; insa
  o tawa Mu
pini
; when we exit the while loop, we'll be here
```

```
; for loops

; we have to figure out +- <> still
; come back later for good for loops

; have a consolation kijetesantakalu
; and a consolation palisa jelo
```

## funcs
Functions are defined with the `pali [name] li kepeken e [type] [name] e [type] [name]... (li pana e [type])` syntax. The `e [type] [name]` part defines the arguments of the function. The last part defines the return type, and is optional (it will be inferred from the return statements otherwise). Indentation for readability may be added.

To return, the `o pana e [type] [value]` syntax is used.

To throw errors, the pakala type is used with the type of pakala afterwards (example: `pakala PakalaKokosila`).

```
pali Tuntutu li kepeken e nanpa Mimi, 
                        e nanpa Waki, 
                        e lipu  Pili,
             li pana e lipu:
  ; return
  o pana e lipu te mi tawa to

  ; throw
  o pana e pakala PakalaKokosila
pini
```

To call the function, the `o pali [name] kepeken [value] kepeken [value]...` syntax is used.

```
o pali Tuntutu kepeken nanpa Ja, kepeken 5, kepeken te toki a! to
```

## nasin pi lawa wawa (strict mode)

Enable strict mode to enforce strings to use valid toki pona
and enforce `te` and `to` quotation marks.

Enabling strict mode can be done by adding this to the top of
the file using it.

```
o kepeken nasin pi lawa wawa
```

### Proposed toggle

Similarly, strict mode may be disabled anywhere in the file
by doing the following:

```
o kepeken ala nasin pi lawa wawa
```
