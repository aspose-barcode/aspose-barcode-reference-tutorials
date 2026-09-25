---
category: general
date: 2026-08-12
description: Configure rapidamente o layout de código de barras Databar em Python.
  Aprenda a definir colunas, linhas e salvar imagens com a biblioteca geradora de
  códigos de barras.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- configure databar barcode layout
- Databar Expanded Stacked
- barcode generator Python
- set barcode columns
- set barcode rows
language: pt
lastmod: 2026-08-12
og_description: Configure o layout do código de barras Databar em Python para controlar
  colunas, linhas e a saída de imagem. Siga este guia para uma solução pronta‑para‑usar.
og_image_alt: Screenshot of a Databar Expanded Stacked barcode with custom column
  layout
og_title: Configure o layout do código de barras Databar em Python – tutorial completo
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Configure Databar barcode layout in Python quickly. Learn to set columns,
    rows, and save images with the barcode generator library.
  headline: Configure Databar barcode layout in Python – step‑by‑step guide
  type: TechArticle
- description: Configure Databar barcode layout in Python quickly. Learn to set columns,
    rows, and save images with the barcode generator library.
  name: Configure Databar barcode layout in Python – step‑by‑step guide
  steps:
  - name: Import the required classes
    text: '```python from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
      ```'
  - name: Create a barcode generator for Databar Expanded Stacked
    text: '```python # Initialize the generator with the desired symbology and value
      barcode_generator = BarcodeGenerator( EncodeTypes.DatabarExpandedStacked, "Databar
      Expanded Stacked long" ) ```'
  - name: Set the number of columns (horizontal layout)
    text: '```python # Configure the layout to use 4 columns barcode_generator.parameters.barcode.data_bar.columns
      = 4 ```'
  - name: Save the barcode image with the column layout
    text: '```python # Save the image as a PNG file barcode_generator.save("output/ExpandedCols4.png",
      BarCodeImageFormat.Png) ```'
  - name: Create a second generator for the same barcode type (row layout)
    text: If you prefer a vertical stack, you work with rows instead of columns. The
      code below re‑uses the same value but creates a fresh `BarcodeGenerator` instance
      to avoid mixing column and row settings.
  - name: Set the number of rows (vertical layout)
    text: '```python # Configure the layout to use 3 rows barcode_generator.parameters.barcode.data_bar.rows
      = 3 ```'
  - name: Save the barcode image with the row layout
    text: '```python # Save the vertically stacked barcode barcode_generator.save("output/ExpandedRows3.png",
      BarCodeImageFormat.Png) ```'
  type: HowTo
tags:
- barcode
- Python
- Databar
- image generation
title: Configure o layout de código de barras Databar em Python – guia passo a passo
url: /pt/python-java/general/configure-databar-barcode-layout-in-python-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configure o layout de código de barras Databar em Python – guia passo a passo

Se você precisa **configurar o layout de código de barras Databar em Python**, este guia o conduzirá por todo o processo. Você verá como definir o número de colunas ou linhas para um código de barras Databar Expanded Stacked e como salvar a imagem resultante com uma única chamada à biblioteca geradora de códigos de barras.

Controlar o layout é essencial ao incorporar códigos de barras em embalagens estreitas, recibos ou telas móveis. Nas seções abaixo, abordaremos as importações necessárias, as duas opções de layout (colunas e linhas) e as melhores práticas para salvar uma imagem PNG limpa.

## O que você precisará

* Python 3.8 ou superior
* `aspose.barcode` (ou qualquer pacote compatível de geração de códigos de barras) instalado  
  ```bash
  pip install aspose-barcode
  ```
* Permissão de escrita em uma pasta onde os arquivos PNG serão armazenados

Nenhuma ferramenta externa adicional é necessária — a biblioteca lida com renderização, dimensionamento e codificação de imagem internamente.

## Como configurar o layout de código de barras Databar em Python

O núcleo da solução é a classe `BarcodeGenerator`. Ela aceita um enum `EncodeTypes` que identifica a simbologia do código de barras — neste caso `EncodeTypes.DatabarExpandedStacked`. Após criar o gerador, você pode ajustar o layout definindo as propriedades `columns` ou `rows` no objeto de parâmetro `data_bar`.

### Etapa 1: Importar as classes necessárias

```python
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

Essas importações dão acesso ao gerador, ao enum para tipos Databar e à constante de formato de imagem PNG.

### Etapa 2: Criar um gerador de código de barras para Databar Expanded Stacked

```python
# Initialize the generator with the desired symbology and value
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
```

*Por que esta etapa?*  
`EncodeTypes.DatabarExpandedStacked` indica à biblioteca que ela deve produzir a simbologia **Databar Expanded Stacked**, que suporta sequências numéricas mais longas mantendo uma pegada compacta. O segundo argumento é o dado a ser codificado; pode ser qualquer string que atenda à especificação Databar.

### Etapa 3: Definir o número de colunas (layout horizontal)

```python
# Configure the layout to use 4 columns
barcode_generator.parameters.barcode.data_bar.columns = 4
```

**set barcode columns** é a frase‑chave para esta operação. Quando você aumenta a contagem de colunas, o código de barras se expande horizontalmente, o que pode ser útil para rótulos largos. A biblioteca recalcula automaticamente a largura do módulo para manter o tamanho geral consistente.

#### Dica profissional
A contagem máxima de colunas para Databar Expanded Stacked é 8. Definir um valor acima do limite o limitará ao máximo, mas é melhor validar sua entrada antecipadamente.

### Etapa 4: Salvar a imagem do código de barras com o layout de colunas

```python
# Save the image as a PNG file
barcode_generator.save("output/ExpandedCols4.png", BarCodeImageFormat.Png)
```

**save barcode image** é a ação que grava o código de barras renderizado no disco. PNG é sem perdas, o que preserva as bordas nítidas necessárias para uma leitura confiável.

### Etapa 5: Criar um segundo gerador para o mesmo tipo de código de barras (layout de linhas)

Se você prefere uma pilha vertical, trabalha com linhas em vez de colunas. O código abaixo reutiliza o mesmo valor, mas cria uma nova instância de `BarcodeGenerator` para evitar misturar configurações de colunas e linhas.

```python
# New generator instance for row configuration
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
```

### Etapa 6: Definir o número de linhas (layout vertical)

```python
# Configure the layout to use 3 rows
barcode_generator.parameters.barcode.data_bar.rows = 3
```

**set barcode rows** organiza os módulos do código de barras verticalmente. Um layout de três linhas reduz a altura de cada pilha individual, tornando o código de barras adequado para recibos estreitos ou telas móveis.

#### Caso de borda
Se você definir `rows` como 1, a biblioteca gera um Databar de linha única (equivalente a um Databar padrão). Valores abaixo de 1 são ignorados e redefinidos para o padrão (1 linha).

### Etapa 7: Salvar a imagem do código de barras com o layout de linhas

```python
# Save the vertically stacked barcode
barcode_generator.save("output/ExpandedRows3.png", BarCodeImageFormat.Png)
```

Novamente, usamos **save barcode image** com PNG para manter a saída nítida.

## Exemplo completo executável

Juntando todas as peças, você obtém um script autônomo que pode ser inserido em qualquer projeto Python.

```python
# ------------------------------------------------------------
# configure_databar_layout.py
# Demonstrates how to configure Databar barcode layout in Python
# ------------------------------------------------------------

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# -----------------------------------------------------------------
# 1️⃣ Column layout – 4 columns
# -----------------------------------------------------------------
col_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
col_generator.parameters.barcode.data_bar.columns = 4   # set barcode columns
col_path = os.path.join(output_dir, "ExpandedCols4.png")
col_generator.save(col_path, BarCodeImageFormat.Png)   # save barcode image
print(f"Column layout saved to {col_path}")

# -----------------------------------------------------------------
# 2️⃣ Row layout – 3 rows
# -----------------------------------------------------------------
row_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
row_generator.parameters.barcode.data_bar.rows = 3      # set barcode rows
row_path = os.path.join(output_dir, "ExpandedRows3.png")
row_generator.save(row_path, BarCodeImageFormat.Png)   # save barcode image
print(f"Row layout saved to {row_path}")
```

**Saída esperada**

Executar o script cria dois arquivos PNG:

* `output/ExpandedCols4.png` – um código de barras estendido em quatro colunas
* `output/ExpandedRows3.png` – um código de barras comprimido em três linhas

Ambas as imagens podem ser abertas em qualquer visualizador de imagens ou importadas diretamente em faturas PDF, modelos de etiquetas ou páginas da web.

## Perguntas comuns e solução de problemas

| Pergunta | Resposta |
|----------|----------|
| *E se o código de barras parecer borrado?* | Aumente a resolução da imagem definindo `barcode_generator.parameters.image_width` e `image_height` antes de chamar `save`. |
| *Posso usar outros formatos de imagem?* | Sim. Substitua `BarCodeImageFormat.Png` por `Jpeg`, `Bmp` ou `Gif` conforme necessário. |
| *Existe um limite para o comprimento dos dados?* | Databar Expanded Stacked suporta até 74 caracteres numéricos. Exceder o limite gera uma `ArgumentException`. |
| *Como altero a cor de primeiro plano?* | Use `barcode_generator.parameters.barcode.color = Color.Blue` (importe `System.Drawing.Color`). |
| *Posso combinar colunas e linhas?* | Não. A API trata colunas e linhas como modos de layout mutuamente exclusivos. Escolha um por instância de código de barras. |

## Próximos passos

Agora que você pode **configurar o layout de código de barras Databar**, considere explorar estes tópicos relacionados:

* **Adicionar legendas de texto** – use `barcode_generator.parameters.barcode.code_text` para exibir o valor codificado abaixo da imagem.
* **Incorporar o código de barras em um PDF** – combine o PNG gerado com `aspose.pdf` para criar documentos imprimíveis.
* **Dimensionamento dinâmico** – calcule a contagem ótima de colunas ou linhas com base nas dimensões da etiqueta em tempo de execução.
* **Processamento em lote** – percorra um CSV de códigos de produto para gerar automaticamente uma biblioteca de imagens de códigos de barras.

Experimente diferentes valores de colunas e linhas para ver como eles afetam a confiabilidade da leitura em seus dispositivos-alvo. Quanto mais você testar, melhor compreenderá as compensações entre tamanho do código de barras, legibilidade e restrições de espaço.

---

*Feliz codificação! Se você achou este tutorial útil, compartilhe com colegas ou deixe um comentário sobre os desafios de layout que enfrentou.*

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá-lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Criar imagem de código de barras DotCode – linhas e colunas (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Criar imagem de código de barras c# – Configurar linhas e colunas do Codablock F](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Ajuste de altura do código de barras Databar unidimensional](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}