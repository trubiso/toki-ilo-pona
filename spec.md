# toki ilo pona spec v0.0.4

## basics
toki ilo is a programming language made to be somewhat compatible with toki
pona's syntax while still being useful

## defining vars

* define a boolean (they are lili because they are small data)
```
lili Pulijan li lon
lili Pulijan2 li ala
```

* define a string
```
lipu Po li te ni li lipu mi :) to
lipu Sensa li "ni li lipu mi kin a :)"
```

* interpolate a string
```
lipu Pa li lipu insa te tenpo poka la mi sitelen e ni: [lipu Po] to
lipu Senso li lipu insa "tenpo poka la mi sitelen e ni kin a: [lipu Sensa]"
```

* define a number
```
nanpa Ja li 5
```

* create a tuple. in this case, a tuple of 3 numbers.
```
kulupu pi nanpa 3 Mija li 1, li 2, li 3 ; the commas are optional
```

* dynamic. it infers the type of the variable from the value
```
kon Su li 5 ; nanpa
```

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
  o pana pakala e PakalaKokosila
pini

; call func
o Tuntutu kepeken Ja, kepeken 5, kepeken te toki to

; print
o toki te toki to

; print to stderr
o toki te toki to tawa lipu pakala