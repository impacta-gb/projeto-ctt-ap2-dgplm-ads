---
icon: simple/go
---

# Testes Automatizados em Go

Go possui suporte nativo para testes automatizados através do pacote `testing`.

Os testes ajudam a garantir:
- qualidade do código;
- prevenção de erros;
- manutenção mais segura.

## Estrutura de Testes

Os arquivos de teste devem terminar com:

```txt
_test.go
```

Exemplo:

```txt
calculadora_test.go
```

---

# Criando uma Função

Arquivo `calculadora.go`:

```go
package main

func Soma(a int, b int) int {
    return a + b
}
```

---

# Criando um Teste

Arquivo `calculadora_test.go`:

```go
package main

import "testing"

func TestSoma(t *testing.T) {
    resultado := Soma(2, 3)

    if resultado != 5 {
        t.Errorf("Resultado esperado: 5")
    }
}
```

---

# Executando Testes

No terminal:

```bash
go test
```

---

# Testando Todos os Pacotes

```bash
go test ./...
```

---

# Cobertura de Testes

Para verificar a cobertura:

```bash
go test -cover
```

Exemplo de saída:

```txt
coverage: 100.0% of statements
```

---

# Benefícios dos Testes Automatizados

| Benefício | Descrição |
|-----------|-----------|
| Confiabilidade | Reduz falhas no sistema |
| Manutenção | Facilita alterações futuras |
| Segurança | Detecta erros rapidamente |
| Qualidade | Melhora a estabilidade do código |

---

# Boas Práticas

- Criar testes simples e objetivos;
- Nomear corretamente os testes;
- Testar diferentes cenários;
- Automatizar testes no CI/CD.

---

# Conclusão

Os testes automatizados são fundamentais para garantir qualidade, estabilidade e segurança em aplicações desenvolvidas com Go.
