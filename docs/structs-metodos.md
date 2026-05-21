---
icon: simple/go
---

# Structs e Métodos

## Structs

Structs permitem agrupar dados relacionados.

```go
package main

import "fmt"

type Pessoa struct {
    Nome  string
    Idade int
}

func main() {
    pessoa := Pessoa{
        Nome:  "João",
        Idade: 25,
    }

    fmt.Println(pessoa)
}
```

!!! note
    Structs são muito utilizadas para representar objetos e entidades.

---

## Métodos

Métodos adicionam comportamentos às structs.

```go
package main

import "fmt"

type Pessoa struct {
    Nome string
}

func (p Pessoa) Apresentar() {
    fmt.Println("Olá, meu nome é", p.Nome)
}

func main() {
    pessoa := Pessoa{
        Nome: "Maria",
    }

    pessoa.Apresentar()
}
```

| Conceito | Função |
|---|---|
| Struct | Armazenar dados |
| Método | Definir comportamento |