# go-rand

A painless convenience wrapper around math/rand and crypto/rand

Ínstallation: `go get github.com/cat-dealer/go-rand`

Full documentation: [godoc](https://godoc.org/github.com/cat-dealer/go-rand)


## Examples


#### Pseudo-random

Generating pseudo-random integers, booleans and bytes

```
bytes := rand.Bytes(16)   // returns 16 bytes
int   := rand.Int(1, 3)   // returns 1, 2 or 3
bool  := rand.Bool()      // returns true or false
```

Strings and runes can only be generated from a predefined pool of allowed characters; you
can either provide your own pool:

`str := rand.String(4, []rune{'a', 'b', 'c'}) // returns 4 random characters from the []rune slice`

or use one of the built-in pools:

`str := rand.String(4, rand.AlphanumericPool) // returns 4 letters or numbers`


#### Cryptographically random

Generating cryptographically secure random values isn't any harder than generating pseudo-random ones:

```
bytes, err := rand.SecureBytes(16) // returns 16 bytes
int, err   := rand.SecureInt(1, 3) // return 1, 2 or 3
bool, err  := rand.SecureBool()    // returns true or false
```

Strings are just as easy:

`str, err := rand.SecureString(4, rand.AlphanumericPool) // returns 4 letters or numbers`

### Important note

This package may panic if called with impossible parameters (e.g. `rand.Int(0, -1)`) or using empty pool slices for rune/string generation!

### Licensing

None. Do whatever you want with it.
This software distribution has no copyright or conditions.