---
category: general
date: 2026-10-28
description: Aprenda a criar codetexto estendido em Python usando ExtCodetextBuilder.
  Inclui dados simples e codificados em ECI, código passo a passo e dicas de boas
  práticas.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create extended codetext
- ExtCodetextBuilder Python
- add plain codetext
- add eci codetext
- extended‑codetext example
language: pt
lastmod: 2026-10-28
og_description: Crie codetexto estendido em Python com ExtCodetextBuilder. Este tutorial
  mostra o tratamento de dados simples e codificados em ECI, código completo e executável,
  e armadilhas comuns.
og_image_alt: Diagram showing how to create extended codetext using ExtCodetextBuilder
  in Python
og_title: Crie texto de código estendido em Python – guia completo
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Learn how to create extended codetext in Python using ExtCodetextBuilder.
    Includes plain and ECI‑encoded data, step‑by‑step code and best‑practice tips.
  headline: How to create extended codetext in Python with ExtCodetextBuilder
  type: TechArticle
- description: Learn how to create extended codetext in Python using ExtCodetextBuilder.
    Includes plain and ECI‑encoded data, step‑by‑step code and best‑practice tips.
  name: How to create extended codetext in Python with ExtCodetextBuilder
  steps:
  - name: Prerequisites
    text: '* Python 3.8 or newer. * The `extcodetext` package (or a similar library
      that provides `ExtCodetextBuilder`). Install it with:'
  - name: Handling other encodings
    text: 'If you need ISO‑8859‑1 (Western European) you would use `add_eci_codetext(4,
      "¡Hola!")`. For Shift‑JIS (Japanese) the ECI value is 20:'
  - name: 'Edge case: Empty strings'
    text: Calling `add_plain_codetext("")` or `add_eci_codetext(3, "")` is harmless;
      the builder simply ignores the empty fragment. However, repeated empty calls
      can lead to unnecessary ECI markers. Guard against this by checking string length
      before adding.
  type: HowTo
tags:
- Python
- encoding
- data‑serialization
title: Como criar codetexto estendido em Python com ExtCodetextBuilder
url: /pt/python/general/how-to-create-extended-codetext-in-python-with-extcodetextbu/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar codetext estendido em Python com ExtCodetextBuilder

Se você precisa **criar codetext estendido** para aplicações de código de barras ou data‑matrix, este guia mostra exatamente como fazer isso em Python. Você verá como combinar texto simples, adicionar seções ECI (Extended Channel Interpretation) para caracteres Unicode e obter uma única string formatada corretamente pronta para codificação.

O tutorial cobre tudo, desde a instalação da biblioteca necessária até o tratamento de casos extremos, como valores de ECI não suportados. Ao final, você terá um padrão reutilizável que pode ser inserido em qualquer projeto que precise **criar codetext estendido**.

## O que você aprenderá

* O papel do `ExtCodetextBuilder` ao construir strings de codificação mista.  
* Como **adicionar codetext simples** e **adicionar codetext ECI** em uma única instância do builder.  
* Como verificar a saída final e solucionar armadilhas comuns.  
* Variações para outros conjuntos de caracteres (por exemplo, ISO‑8859‑1, Shift‑JIS).  

### Pré‑requisitos

* Python 3.8 ou superior.  
* O pacote `extcodetext` (ou uma biblioteca similar que forneça `ExtCodetextBuilder`). Instale‑o com:

```bash
pip install extcodetext
```

* Familiaridade básica com Unicode e valores de ECI – ECI 3 corresponde a UTF‑8, ECI 4 a ISO‑8859‑1, etc.

> **Dica profissional:** Mantenha uma tabela de referência dos números de ECI à mão. Ela evita incompatibilidades acidentais entre a codificação declarada e a sequência de bytes real.

## Entendendo ExtCodetextBuilder

`ExtCodetextBuilder` é uma pequena utilidade que concatena múltiplos fragmentos de texto enquanto insere automaticamente os marcadores ECI necessários. Um marcador ECI informa ao codificador de código de barras qual conjunto de caracteres usar para os bytes subsequentes. Sem o marcador, caracteres não‑ASCII seriam interpretados incorretamente.

O builder funciona em três fases simples:

1. **Create** a instância do builder.  
2. **Append** fragmentos simples ou codificados com ECI.  
3. **Retrieve** a string combinada de codetext estendido.

A seguir, percorremos cada fase com código concreto.

## Etapa 1: Crie uma instância de ExtCodetextBuilder

A primeira linha constrói o objeto que armazenará todos os fragmentos. Não há configuração necessária neste ponto.

```python
from extcodetext import ExtCodetextBuilder

# Step 1: Create an ExtCodetextBuilder instance
codetext_builder = ExtCodetextBuilder()
```

*Por que isso importa*: Instanciar o builder aloca um buffer interno. Todas as chamadas subsequentes a `add_*` operam nesse buffer, garantindo a ordem que você especificar.

## Etapa 2: Anexe dados simples (não codificados)

Dados simples consistem em caracteres que pertencem ao conjunto de caracteres padrão (geralmente ASCII). Use `add_plain_codetext` para esses fragmentos.

```python
# Step 2: Append plain (un‑encoded) data to the builder
codetext_builder.add_plain_codetext("ABC123")
```

*Explicação*: A string `"ABC123"` contém apenas caracteres ASCII, portanto nenhum marcador ECI é necessário. O método simplesmente anexa os bytes brutos ao buffer interno.

## Etapa 3: Anexe dados que devem ser precedidos por um ECI

Quando você precisa incorporar caracteres Unicode — como cirílico, japonês ou emojis — deve informar ao codificador qual charset usar. Isso é feito com `add_eci_codetext(eci, text)`. O primeiro argumento é o valor numérico do ECI; o segundo é o texto real.

```python
# Step 3: Append data that must be preceded by an ECI (e.g., 3 for UTF‑8)
# This ensures the text "Привет" is correctly interpreted as UTF‑8
codetext_builder.add_eci_codetext(3, "Привет")
```

*Por que ECI 3*: De acordo com a especificação ISO/IEC 18004, ECI 3 mapeia para UTF‑8. Ao inserir esse marcador, o leitor de código de barras sabe decodificar os bytes seguintes como UTF‑8, preservando os caracteres cirílicos.

### Manipulando outras codificações

Se precisar de ISO‑8859‑1 (Europeu Ocidental) use `add_eci_codetext(4, "¡Hola!")`. Para Shift‑JIS (japonês) o valor ECI é 20:

```python
codetext_builder.add_eci_codetext(20, "こんにちは")
```

Sempre verifique se a biblioteca de código de barras alvo suporta o valor de ECI escolhido; ECIs não suportados causarão falhas de codificação.

## Etapa 4: Recupere a string de codetext estendido combinada

Depois que todos os fragmentos forem adicionados, chame `get_extended_codetext()` para obter a string final. Essa string inclui quaisquer sequências de escape ECI necessárias.

```python
# Step 4: Retrieve the combined extended‑codetext string
extended_codetext = codetext_builder.get_extended_codetext()

print("Extended codetext:", extended_codetext)
```

**Saída esperada** (exibida como `repr` do Python para clareza):

```
Extended codetext: 'ABC123\x1B\x1D\x03Привет'
```

*Detalhamento*:

* `ABC123` – segmento ASCII simples.  
* `\x1B\x1D\x03` – a sequência de escape ECI para UTF‑8 (ESC GS 0x03).  
* `Привет` – a palavra cirílica codificada em UTF‑8.

Os bytes de escape exatos podem variar dependendo da implementação da biblioteca, mas a ordem lógica será sempre *simples → marcador ECI → texto Unicode*.

## Exemplo completo executável

Juntando tudo, aqui está um script autônomo que você pode copiar‑colar em um arquivo chamado `create_extended_codetext.py` e executar imediatamente.

```python
#!/usr/bin/env python3
"""
Create extended codetext in Python using ExtCodetextBuilder.
Demonstrates plain text, UTF‑8 ECI, and how to retrieve the final string.
"""

from extcodetext import ExtCodetextBuilder

def main() -> None:
    # 1️⃣ Create the builder
    builder = ExtCodetextBuilder()

    # 2️⃣ Add a plain ASCII segment
    builder.add_plain_codetext("ABC123")

    # 3️⃣ Add a UTF‑8 segment (ECI 3) containing Cyrillic characters
    builder.add_eci_codetext(3, "Привет")

    # 4️⃣ Retrieve and display the extended codetext
    result = builder.get_extended_codetext()
    print("Extended codetext:", result)

if __name__ == "__main__":
    main()
```

Executar o script imprime a string combinada, pronta para qualquer codificador de código de barras que aceite entrada de codetext estendido.

## Armadilhas comuns e como evitá‑las

| Sintoma | Causa provável | Correção |
|---|---|---|
| `UnicodeEncodeError` ao chamar `add_eci_codetext` | Fornecer uma string que contém caracteres não representáveis no ECI escolhido | Verifique se o ECI corresponde à codificação real da string (por exemplo, use ECI 3 para qualquer texto UTF‑8). |
| Marcador ECI ausente na saída final | Uso acidental de `add_plain_codetext` para dados não‑ASCII | Troque para `add_eci_codetext` para qualquer caractere fora do intervalo ASCII. |
| Leitor de código de barras exibe caracteres corrompidos | O leitor não suporta o valor de ECI selecionado | Escolha um ECI universalmente suportado (UTF‑8 tem amplo suporte) ou recorra ao ISO‑8859‑1 se o idioma de destino permitir. |
| `get_extended_codetext` retorna string vazia | Nenhum fragmento foi adicionado antes da chamada | Garanta que ao menos uma chamada `add_*` seja executada. |

### Caso de borda: Strings vazias

Chamar `add_plain_codetext("")` ou `add_eci_codetext(3, "")` não causa problemas; o builder simplesmente ignora o fragmento vazio. Contudo, chamadas vazias repetidas podem gerar marcadores ECI desnecessários. Evite isso verificando o comprimento da string antes de adicionar.

```python
text = "data"
if text:
    builder.add_plain_codetext(text)
```

## Estendendo o padrão para dados dinâmicos

Em aplicações reais você costuma construir o codetext estendido a partir de entrada do usuário ou de um registro de banco de dados. O trecho abaixo mostra um loop que processa uma lista de tuplas `(type, value)`, onde `type` é `"plain"` ou `"eci"`.

```python
fragments = [
    ("plain", "Order#"),
    ("plain", "98765"),
    ("eci", (3, "商品")),   # Japanese word "商品" (product) encoded as UTF‑8
]

for kind, payload in fragments:
    if kind == "plain":
        builder.add_plain_codetext(payload)
    elif kind == "eci":
        eci_val, text = payload
        builder.add_eci_codetext(eci_val, text)
    else:
        raise ValueError(f"Unsupported fragment type: {kind}")

print(builder.get_extended_codetext())
```

Essa abordagem escala bem: você pode ler as definições de fragmentos de JSON, CSV ou de uma API sem mudar a lógica central de construção.

## Testando a saída

Um teste unitário rápido garante que o builder se comporte como esperado. Usando `pytest`:

```python
def test_extended_codetext():
    b = ExtCodetextBuilder()
    b.add_plain_codetext("X")
    b.add_eci_codetext(3, "✓")   # Check mark in UTF‑8
    result = b.get_extended_codetext()
    assert result.startswith("X")
    assert "\x1B\x1D\x03".encode() in result.encode()
```

Executar `pytest` deve passar, confirmando que o marcador ECI aparece exatamente onde deveria.

## Conceitos relacionados que você pode explorar a seguir

* **Bibliotecas de codificação de código de barras** – por exemplo, `python-barcode`, bindings do `zxing`, que aceitam a string de codetext estendido diretamente.  
* **Referência da tabela ECI** – uma lista completa de valores numéricos de ECI é publicada pela ISO/IEC 18004 e pode ser armazenada como um dicionário Python para consulta.  
* **Níveis de correção de erro** – ao gerar QR codes, combine o codetext estendido com o nível de correção adequado (L, M, Q, H) para uma leitura robusta.

## Conclusão

Agora você sabe como **criar codetext estendido** em Python usando `ExtCodetextBuilder`. O processo é simples:

1. Instancie o builder.  
2. Anexe fragmentos simples e codificados com ECI conforme necessário.  
3. Recupere a string final e alimente seu gerador de códigos de barras.

Seguindo o padrão acima, você pode lidar com qualquer mistura de dados ASCII e Unicode, evitar erros comuns de codificação e produzir strings prontas para códigos de barras que funcionam em uma ampla variedade de leitores. Experimente diferentes ECIs, integre o builder ao seu pipeline de dados e você terá uma base sólida para todas as suas necessidades de codetext estendido.

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}