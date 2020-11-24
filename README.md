# polyglot
Test speed for different programming languages. 
In most cases the bottleneck of the system is database and network, not the language itself, but it was interesting to find out how fast different languages can perform a simple calculations on float numbers.


Docker image: 
[alexvaitsekhovich/polyglot](https://cloud.docker.com/repository/docker/alexvaitsekhovich/polyglot)

1. In _run.sh_ define the list of languages you want to test:
```
declare -a langs (<your list>)
```

2. In _run.sh_ define the name of the programm that will be executed for every language:
```
programm="<your script>"
```
Expected file extensions are lsited below.


3. Start with:

```
sh run.sh
```


File extensions for languages:

language | File extension
------------ | -------------
ADA | .adb
C | .c
Clojure | .clj
C# | .cs
Elixir | .ex
F# | .fs
Go | .go
Groovy | .groovy
Java | .java
Julia | .jl
Kotlin | .kt
Lua | .lua
Nim | .nim
Node.js | .js
OCaml | .ml
Pascal | .p
Perl | .pl
PHP | .php
Python | .py
R | .R
Ruby | .rb
Rust | .rs
Scala | .scala

## Example code ## 
In the example all languages perform the same calculations on float number with two nested loops (here in pseudocode for 10 billions operations):

```
arrayOfFloats = [ < 1000 hardcoded floats> ]
total = 0
foreach (v in arrayOfFloats) {
	tmpSum = 0;
	for (x = 1; x <= 10_000_000; x++) {
		tmpSum += x*37.0/12347.0 + v*61.0/101.0;
	} 
	total += tmpSum/53.0;
}
```
The correct value is considered the value, that was delivered by the most languages.

<p align="center">
<img src="https://github.com/alexvaitsekhovich/polyglot/blob/master/img/Speed.png" width="100%" height="100%" alt="Speed graph">

<img src="https://github.com/alexvaitsekhovich/polyglot/blob/master/img/Full_data.png" width="70%" height="70%" alt="Correctness and versions">
</p>

