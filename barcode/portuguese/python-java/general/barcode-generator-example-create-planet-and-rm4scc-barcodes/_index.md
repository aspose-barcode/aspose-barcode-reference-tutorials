---
category: general
date: 2026-10-24
description: Exemplo de gerador de código de barras que demonstra como criar o código
  de barras Planet e como definir a altura do código de barras usando Python. Siga
  o guia passo a passo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to create planet barcode
- how to set barcode height
language: pt
lastmod: 2026-10-24
og_description: Exemplo de gerador de código de barras que demonstra como criar o
  código de barras Planet e como definir a altura do código de barras em Python. Obtenha
  uma solução completa e executável.
og_image_alt: Barcode generator example showing Planet and RM4SCC barcodes with different
  heights
og_title: Exemplo de gerador de código de barras – crie códigos de barras Planet e
  RM4SCC
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Barcode generator example that shows how to create Planet barcode and
    how to set barcode height using Python. Follow the step‑by‑step guide.
  headline: Barcode generator example – create Planet and RM4SCC barcodes with custom
    height
  type: TechArticle
- description: Barcode generator example that shows how to create Planet barcode and
    how to set barcode height using Python. Follow the step‑by‑step guide.
  name: Barcode generator example – create Planet and RM4SCC barcodes with custom
    height
  steps:
  - name: '**Instantiate** a `BarcodeGenerator` with the desired `EncodeTypes` value
      and the data string.'
    text: '**Instantiate** a `BarcodeGenerator` with the desired `EncodeTypes` value
      and the data string.'
  - name: '**Configure** the X‑dimension (module width) and, when needed, the barcode
      height.'
    text: '**Configure** the X‑dimension (module width) and, when needed, the barcode
      height.'
  - name: '**Save** the image to disk in PNG format.'
    text: '**Save** the image to disk in PNG format.'
  type: HowTo
tags:
- barcode
- Python
- image generation
title: Exemplo de gerador de código de barras – crie códigos de barras Planet e RM4SCC
  com altura personalizada
url: /pt/python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Exemplo de gerador de código de barras – crie códigos Planet e RM4SCC com altura personalizada

Se você está procurando um **exemplo de gerador de código de barras**, este guia oferece uma solução completa e pronta‑para‑executar. Você verá **como criar imagens de código de barras Planet**, aprenderá **como definir a altura do código de barras** e entenderá as pequenas diferenças entre dimensionamento automático e manual.

O tutorial percorre dois cenários realistas: um código Planet que usa a altura padrão (automática) e um código RM4SCC onde a altura é forçada a 100 px. Ao final, você poderá gerar arquivos PNG para qualquer tipo de código de barras suportado com uma única API consistente.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

* Python 3.8 ou mais recente instalado.
* O pacote `aspose-barcode` (ou qualquer biblioteca que forneça `BarcodeGenerator`, `EncodeTypes` e `BarCodeImageFormat`). Instale‑o com  

  ```bash
  pip install aspose-barcode
  ```
* Permissão de gravação em uma pasta onde os arquivos PNG serão salvos.

Nenhuma dependência de sistema adicional é necessária.

## Visão geral da solução

O núcleo do **exemplo de gerador de código de barras** consiste em três etapas reutilizáveis:

1. **Instanciar** um `BarcodeGenerator` com o valor desejado de `EncodeTypes` e a string de dados.
2. **Configurar** a dimensão X (largura do módulo) e, quando necessário, a altura do código de barras.
3. **Salvar** a imagem no disco no formato PNG.

Ambos os exemplos compartilham as etapas 1 e 3; apenas a etapa 2 difere porque o código Planet depende do cálculo automático de altura da biblioteca, enquanto o código RM4SCC demonstra **como definir a altura do código de barras** manualmente.

Abaixo está um diagrama de alto nível que ilustra o fluxo:

![Exemplo de gerador de código de barras mostrando códigos Planet e RM4SCC](barcode-example.png)

*Texto alternativo: Exemplo de gerador de código de barras mostrando códigos Planet e RM4SCC com alturas diferentes.*

## Como criar código Planet – altura automática

O código Planet faz parte da família postal usada por muitos serviços postais nacionais. Na maioria dos casos, você deixa o SDK decidir a altura, o que mantém as proporções visuais corretas para diferentes comprimentos de dados.

```python
# Step 1: Create a generator for the Planet barcode with the data "123456"
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

planet_gen = BarcodeGenerator(EncodeTypes.Planet, "123456")

# Step 2: Define the X‑dimension (module width) as 4 pixels
planet_gen.parameters.barcode.x_dimension.pixels = 4

# Step 3: Save the barcode image as a PNG file
planet_gen.save("PostalPlanetBarHeightAuto.png", BarCodeImageFormat.Png)
```

**Por que isso funciona**

* `EncodeTypes.Planet` indica à biblioteca que deve usar a simbologia Planet.
* Definir `x_dimension.pixels` para 4 dá a cada módulo uma largura de 4 px, que é um padrão comum para etiquetas impressas.
* Nenhuma altura explícita é definida; o SDK calcula a altura ideal com base nos dados e na dimensão X, razão pela qual este é o **exemplo de gerador de código de barras** mais simples para códigos postais.

**Resultado esperado**

Um arquivo PNG 2‑D chamado `PostalPlanetBarHeightAuto.png` que contém um código Planet nítido. A altura ficará em torno de 30 px (dependendo da versão da biblioteca) e a largura será 4 px × número de módulos.

## Como definir a altura do código de barras – exemplo RM4SCC personalizado

RM4SCC é outro código postal que frequentemente requer uma altura fixa para corresponder a modelos de etiquetas. Esta parte do tutorial mostra **como definir a altura do código de barras** para um número exato de pixels.

```python
# Step 1: Create a generator for the RM4SCC barcode with the data "123456"
rm4scc_gen = BarcodeGenerator(EncodeTypes.RM4SCC, "123456")

# Step 2: Set the X‑dimension to 4 pixels (same as the Planet example)
rm4scc_gen.parameters.barcode.x_dimension.pixels = 4

# Step 3: Specify the barcode height as 100 pixels
rm4scc_gen.parameters.barcode.bar_height.pixels = 100

# Step 4: Save the barcode image as a PNG file
rm4scc_gen.save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png)
```

**Por que isso funciona**

* `EncodeTypes.RM4SCC` seleciona a simbologia RM4SCC.
* A dimensão X permanece em 4 px para manter o tamanho do módulo consistente entre os dois códigos.
* `bar_height.pixels = 100` força o código de barras a ter exatamente 100 px de altura, sobrescrevendo o cálculo automático. Esta é a forma recomendada de **como definir a altura do código de barras** quando seu layout exige um tamanho específico.

**Resultado esperado**

Um arquivo PNG chamado `PostalRM4SCCBarHeight100Pixels.png` que exibe um código RM4SCC alto. A largura ainda é determinada pela dimensão X, enquanto a altura fica fixa em 100 px, tornando‑o adequado para impressoras de etiquetas de alta resolução.

## Script completo – combine ambos os exemplos

Se preferir um único script que gera ambas as imagens, copie o código a seguir para `generate_barcodes.py` e execute‑o.

```python
"""
Full barcode generator example that creates:
* a Planet barcode with automatic height
* an RM4SCC barcode with a custom 100 px height
"""

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def create_planet_barcode(data: str, x_dim: int, out_path: str):
    """Generate a Planet barcode using the default height."""
    gen = BarcodeGenerator(EncodeTypes.Planet, data)
    gen.parameters.barcode.x_dimension.pixels = x_dim
    gen.save(out_path, BarCodeImageFormat.Png)

def create_rm4scc_barcode(data: str, x_dim: int, height_px: int, out_path: str):
    """Generate an RM4SCC barcode with a fixed height."""
    gen = BarcodeGenerator(EncodeTypes.RM4SCC, data)
    gen.parameters.barcode.x_dimension.pixels = x_dim
    gen.parameters.barcode.bar_height.pixels = height_px
    gen.save(out_path, BarCodeImageFormat.Png)

if __name__ == "__main__":
    # Planet barcode – auto height
    create_planet_barcode(
        data="123456",
        x_dim=4,
        out_path="PostalPlanetBarHeightAuto.png"
    )

    # RM4SCC barcode – custom 100 px height
    create_rm4scc_barcode(
        data="123456",
        x_dim=4,
        height_px=100,
        out_path="PostalRM4SCCBarHeight100Pixels.png"
    )
```

**Explicação do script**

* Duas funções auxiliares mantêm o código DRY (Don’t Repeat Yourself) e facilitam a extensão do script para outras simbologias.
* A proteção `if __name__ == "__main__":` permite que o arquivo seja importado como módulo sem executar a lógica de geração, o que é útil para testes unitários.
* Todos os parâmetros (string de dados, dimensão X, altura) são explícitos, portanto o script serve como referência de **exemplo de gerador de código de barras** para projetos futuros.

## Perguntas frequentes e casos de borda

| Pergunta | Resposta |
|----------|----------|
| *E se eu precisar de uma dimensão X diferente?* | Altere `x_dimension.pixels` para a largura de módulo desejada. Valores maiores aumentam o tamanho geral do código de barras proporcionalmente. |
| *Posso gerar outros formatos de imagem?* | Sim. Substitua `BarCodeImageFormat.Png` por `Jpg`, `Bmp` ou `Gif`, conforme o enum da biblioteca. |
| *O que acontece se a string de dados contiver caracteres inválidos?* | O gerador lança uma `ArgumentException`. Valide os dados contra o conjunto de caracteres da simbologia antes de chamar o construtor. |
| *É possível definir uma altura mínima mantendo o dimensionamento automático?* | Use `gen.parameters.barcode.bar_height.min_pixels = <valor>` (se o SDK expuser a propriedade `min_pixels`). Isso impede que o código de barras fique menor que um tamanho legível. |
| *Preciso liberar o gerador?* | A classe `BarcodeGenerator` implementa `IDisposable` no .NET; em Python o coletor de lixo cuida disso, mas você pode chamar `gen.dispose()` se criar muitas instâncias dentro de um loop. |

## Dicas para uso em produção

* **Dica profissional:** Armazene os valores de dimensão X e altura em um arquivo de configuração para que você possa ajustá‑los sem recompilar.
* **Cuidado com:** Usar uma altura muito pequena para a simbologia selecionada; scanners podem falhar ao ler o código de barras.
* **Observação de desempenho:** Gerar um grande lote de códigos de barras é mais rápido quando você reutiliza uma única instância de `BarcodeGenerator` e altera apenas a propriedade `code_text` entre as gravações.

## Conclusão

Este **exemplo de gerador de código de barras** demonstra tanto **como criar imagens de código Planet** com dimensionamento automático quanto **como definir a altura do código de barras** manualmente para códigos RM4SCC. Seguindo o guia passo a passo, você pode integrar a criação de códigos de barras em qualquer aplicação Python, personalizar dimensões e produzir arquivos PNG prontos para impressão ou exibição digital.

### Próximos passos

* Explore simbologias adicionais como `EncodeTypes.Postnet` ou `EncodeTypes.Code128` – o mesmo padrão se aplica.
* Experimente **como definir a altura do código de barras** para códigos QR ou símbolos DataMatrix; a maioria das bibliotecas expõe uma propriedade `bar_height` semelhante.
* Combine o gerador com uma biblioteca PDF para incorporar códigos de barras diretamente em faturas ou etiquetas de envio.

Sinta‑se à vontade para adaptar o script, compartilhar seus resultados e nos contar quais tipos de código de barras você adicionará a seguir!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Como salvar PNG a partir de um exemplo de gerador de código de barras em Python](/barcode/english/python-java/general/how-to-save-png-from-a-barcode-generator-example-in-python/)
- [Como criar PNG de código Planet com Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)
- [Como usar um gerador de código de barras C# para criar um código Planet](/barcode/english/python-java/general/how-to-use-a-c-barcode-generator-to-create-a-planet-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}