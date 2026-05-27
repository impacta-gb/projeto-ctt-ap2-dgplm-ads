# Gerenciamento de Pacotes (Go Modules)

## Introdução

O Go Modules é o sistema oficial de gerenciamento de dependências da linguagem Go. Ele permite organizar projetos e controlar versões de bibliotecas utilizadas na aplicação.

---

## Inicializando um Projeto

Para iniciar um projeto Go com módulos:

```bash
go mod init nome-do-projeto
```

Exemplo:

```bash
go mod init github.com/diego/meuprojeto
```

Isso criará o arquivo:

```text
go.mod
```

---

## Arquivo go.mod

Exemplo de conteúdo:

```go
module github.com/diego/meuprojeto

go 1.22
```

### Função do arquivo

| Elemento | Descrição                     |
| -------- | ----------------------------- |
| `module` | Nome do módulo/projeto        |
| `go`     | Versão da linguagem utilizada |

---

## Instalando Dependências

Para adicionar bibliotecas externas:

```bash
go get github.com/gin-gonic/gin
```

---

## Arquivo go.sum

Após instalar dependências, o Go cria automaticamente:

```text
go.sum
```

Esse arquivo registra verificações de segurança e versões das bibliotecas.

> [!IMPORTANT]
> Nunca apague o arquivo `go.sum` sem necessidade.

---

## Atualizando Dependências

Para atualizar pacotes:

```bash
go get -u
```

---

## Removendo Dependências Não Utilizadas

```bash
go mod tidy
```

Esse comando limpa dependências desnecessárias do projeto.

---

## Estrutura de Projeto

Exemplo:

```text
meuprojeto/
│
├── go.mod
├── go.sum
├── main.go
└── internal/
```

---

## Exemplo Completo

```go
package main

import (
    "fmt"
    "github.com/google/uuid"
)

func main() {
    id := uuid.New()
    fmt.Println(id)
}
```

Instalação da dependência:

```bash
go get github.com/google/uuid
```

---

## Vantagens do Go Modules

* Controle de versões
* Facilidade no compartilhamento de projetos
* Segurança nas dependências
* Melhor organização do código

---

## Boas Práticas

> [!TIP]
> Utilize `go mod tidy` frequentemente para manter o projeto limpo.

> [!WARNING]
> Evite instalar dependências desnecessárias.

---

## Conclusão

O Go Modules simplifica o gerenciamento de dependências em Go, permitindo criar aplicações mais organizadas, seguras e fáceis de manter.
