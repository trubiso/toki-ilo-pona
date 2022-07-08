# toki ilo pona spec v0.0.6

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

insa te toki! mi toki e ni: [lipu Teto] to ; where ijo is a variable
```

## Variables

Variable names must comply with toki pona phonetics.

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
                    li insa te ni li nanpa: [Ja] to
```

#### kulupu taso (tuples)

```
; this creates a tuple of 3 numbers
kulupu nanpa pi taso 3 Mija li 1, li 2, li 3

; this will throw an error
; kulupu kon pi taso 2 NiLiPakala li 1, li 2
```

# WIP after this point


## labels and goto
; while statements

; uses labels
nimi Mu: Pulijan li lon la
  ; jmp
  o tawa Mu
pini

; if statements
Pulijan li lon la
  ; insa

  ; else statements
ante la, Pulijan2 li ala la
  ; insa
pini

; funcs
pali Tuntutu li kepeken e nanpa Mimi, e nanpa Waki, e lipu Pili
  ; return
  o pana e lipu te mi tawa to

  ; throw
  o pana e pakala kokosila
pini

; call func
o pali Tuntutu kepeken Ja, kepeken 5, kepeken te toki a! to

; print
o toki te toki to

; print to stderr
o toki te toki to tawa lipu pakala
