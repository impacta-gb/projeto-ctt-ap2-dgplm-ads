# Instalação do Go

Este guia apresenta o processo de instalação da linguagem Go nos principais sistemas operacionais.

## Download do Go

Acesse o site oficial:

https://go.dev/dl/

Baixe a versão correspondente ao seu sistema operacional.

---

# Instalação no Windows

## Passo 1

Baixe o instalador `.msi`.

## Passo 2

Execute o instalador e siga as instruções.

## Passo 3

Abra o Prompt de Comando e execute:

```bash
go version
```

Se a instalação estiver correta, será exibida a versão instalada.

---

# Instalação no Linux

## Ubuntu/Debian

```bash
sudo apt update
sudo apt install golang-go
```

## Verificação

```bash
go version
```

---

# Instalação no macOS

## Utilizando Homebrew

```bash
brew install go
```

## Verificação

```bash
go version
```

---

# Configurando o Workspace

Crie uma pasta para projetos Go:

```bash
mkdir projetos-go
cd projetos-go
```

Inicialize um módulo:

```bash
go mod init meu-projeto
```

---

# Primeiro Teste

Crie um arquivo chamado `main.go`:

```go
package main

import "fmt"

func main() {
    fmt.Println("Go instalado com sucesso!")
}
```

Execute:

```bash
go run main.go
```

---

# Conclusão

Após a instalação, o ambiente estará pronto para desenvolver aplicações utilizando Go.
