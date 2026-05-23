---
icon: simple/go
---

# Arrays, Slices e Maps

## Arrays

Arrays possuem tamanho fixo em Go.

```go
package main

import "fmt"

func main() {
    numeros := [3]int{10, 20, 30}

    fmt.Println(numeros)
}
```

!!! warning
    Arrays possuem tamanho fixo após a criação.

---

## Slices

Slices são estruturas dinâmicas baseadas em arrays.

```go
package main

import "fmt"

func main() {
    nomes := []string{"Ana", "Carlos"}

    nomes = append(nomes, "Maria")

    fmt.Println(nomes)
}
```

!!! tip
    Use slices quando precisar adicionar ou remover elementos.

---

## Maps

Maps armazenam dados em formato chave e valor.

```go
package main

import "fmt"

func main() {
    idades := map[string]int{
        "Ana": 20,
        "Carlos": 30,
    }

    fmt.Println(idades)
}
```

| Estrutura | Característica |
|---|---|
| Array | Tamanho fixo |
| Slice | Tamanho dinâmico |
| Map | Chave e valor |