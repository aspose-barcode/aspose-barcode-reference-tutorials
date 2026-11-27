---
category: general
date: 2026-11-27
description: Tutorial de gerador de código de barras que mostra como gerar PNG de
  código de barras, mudar o tamanho do código de barras e criar um código de barras
  Planet em Python com código passo a passo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator tutorial
- how to generate barcode
- change barcode size
- create barcode png
- create planet barcode
language: pt
lastmod: 2026-11-27
og_description: O tutorial do gerador de códigos de barras mostra como gerar um PNG
  de código de barras, mudar o tamanho do código de barras e criar um código de barras
  Planet usando Python.
og_image_alt: Screenshot of a Planet barcode PNG generated in a barcode generator
  tutorial
og_title: Tutorial de gerador de código de barras – crie um código de barras Planet
  PNG
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Barcode generator tutorial that shows how to generate barcode PNG,
    change barcode size, and create a Planet barcode in Python with step‑by‑step code.
  headline: Barcode generator tutorial – create a Planet PNG barcode
  type: TechArticle
tags:
- barcode
- Python
- image-generation
title: Tutorial de gerador de código de barras – crie um código de barras Planet PNG
url: /pt/python-java/general/barcode-generator-tutorial-create-a-planet-png-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tutorial de gerador de código de barras – crie um código de barras Planet PNG

Se você está procurando um **tutorial de gerador de código de barras**, este guia mostra exatamente como gerar um código de barras Planet (POSTNET), alterar o tamanho do código de barras e salvá‑lo como uma imagem PNG usando Python. Seja para etiquetas de envio ou rastreamento de inventário, você obterá um exemplo completo e executável em apenas alguns passos.

Este tutorial cobre tudo, desde a instalação da biblioteca necessária até a personalização da dimensão X e da altura da barra. Ao final, você entenderá **como gerar imagens de código de barras** programaticamente e estará pronto para adaptar o código para outras simbologias ou formatos de saída.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

* Python 3.8 ou mais recente instalado.
* Acesso à internet para instalar o pacote `aspose-barcode` (a biblioteca usada neste tutorial).
* Um diretório gravável onde o PNG gerado será salvo.

> **Dica profissional:** Use um ambiente virtual (`python -m venv venv`) para manter as dependências isoladas.

## Etapa 1: Instalar a biblioteca Aspose.BarCode para Python

A maneira mais fácil de trabalhar com códigos de barras em Python é o pacote oficial **Aspose.BarCode**, que oferece suporte à simbologia Planet nativamente.

```bash
pip install aspose-barcode
```

O pacote inclui as classes `BarcodeGenerator`, `EncodeTypes` e `BarCodeImageFormat` que você precisará mais adiante.

## Etapa 2: Importar as classes necessárias e configurar o gerador

Crie um novo arquivo Python (por exemplo, `planet_barcode.py`) e importe os símbolos necessários.

```python
# planet_barcode.py
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# The data to encode – Planet (POSTNET) expects a numeric string.
postal_code = "123456"
```

A constante `EncodeTypes.Planet` indica ao gerador que ele deve usar a simbologia **Planet**, ideal para os serviços postais dos EUA.

## Etapa 3: Criar o gerador de código de barras (como gerar código de barras)

Instancie o gerador com os dados desejados. Esta é a parte central do processo **como gerar código de barras**.

```python
# Initialize the generator with Planet symbology and the data string.
barcode_generator = BarcodeGenerator(EncodeTypes.Planet, postal_code)
```

Neste ponto, `barcode_generator` contém uma imagem de código de barras padrão (geralmente largura de módulo de 2 px e altura de barra de 50 px). Para tornar a imagem adequada para impressão ou uso digital, você desejará **alterar o tamanho do código de barras**.

## Etapa 4: Alterar o tamanho do código de barras – ajustar a dimensão X e a altura da barra

### 4.1 Ajustar a dimensão X (largura do módulo)

A dimensão X controla a largura de cada barra individual (módulo). Definir 4 pixels produz um código de barras mais fino e de alta resolução.

```python
# Set the X dimension (module width) to 4 pixels.
barcode_generator.parameters.barcode.x_dimension.pixels = 4
```

### 4.2 Definir a altura da barra

A altura da barra determina o tamanho vertical total do código de barras. Uma altura de 100 pixels funciona bem para a maioria dos dispositivos de leitura.

```python
# Set the bar height to 100 pixels.
barcode_generator.parameters.barcode.bar_height.pixels = 100
```

Ambas as propriedades fazem parte da hierarquia `parameters.barcode`, que agrupa todas as configurações visuais do código de barras.

## Etapa 5: Salvar o código de barras como imagem PNG (criar código de barras png)

Agora que o tamanho está configurado, exporte a imagem. O método `save` aceita um caminho de arquivo e um enum de formato de imagem.

```python
# Define the output path – adjust the directory as needed.
output_path = "output/PostalPlanetBarHeight100Pixels.png"

# Save the barcode as a PNG file.
barcode_generator.save(output_path, BarCodeImageFormat.Png)

print(f"Barcode saved to {output_path}")
```

Executar o script gerará um arquivo chamado `PostalPlanetBarHeight100Pixels.png` na pasta `output`. A imagem contém um código de barras Planet limpo, pronto para impressão ou incorporação em PDFs.

## Etapa 6: Verificar o código de barras gerado (criar código de barras planet)

Abra o PNG com qualquer visualizador de imagens para confirmar que o código de barras está correto. Você também pode escaneá‑lo com um aplicativo móvel de leitura de códigos de barras; ele deve retornar os dados originais (`123456`).

Se o código de barras não for lido:

* Certifique‑se de que a dimensão X não esteja definida muito baixa (abaixo de 2 px pode causar problemas de legibilidade).
* Verifique se a altura da barra é de pelo menos 50 px para uma leitura confiável.
* Confira se a string de dados cumpre os requisitos do Planet (apenas numérica, comprimento adequado).

## Script completo – tudo junto

Abaixo está o script completo e autocontido que você pode copiar‑colar e executar imediatamente.

```python
# planet_barcode.py
"""
Barcode generator tutorial: create a Planet PNG barcode.
This script demonstrates how to generate a barcode, change barcode size,
and save the result as a PNG image using Aspose.BarCode for Python.
"""

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

def main():
    # 1️⃣ Define the data to encode.
    postal_code = "123456"

    # 2️⃣ Create the generator for Planet symbology.
    barcode_generator = BarcodeGenerator(EncodeTypes.Planet, postal_code)

    # 3️⃣ Change barcode size.
    #    - X dimension (module width) = 4 pixels for higher resolution.
    #    - Bar height = 100 pixels for a larger visual footprint.
    barcode_generator.parameters.barcode.x_dimension.pixels = 4
    barcode_generator.parameters.barcode.bar_height.pixels = 100

    # 4️⃣ Prepare the output directory.
    output_dir = "output"
    os.makedirs(output_dir, exist_ok=True)
    output_path = os.path.join(output_dir, "PostalPlanetBarHeight100Pixels.png")

    # 5️⃣ Save the barcode as PNG.
    barcode_generator.save(output_path, BarCodeImageFormat.Png)

    print(f"✅ Barcode generated and saved to: {output_path}")

if __name__ == "__main__":
    main()
```

Executar `python planet_barcode.py` produz o PNG mostrado abaixo.

![Planet barcode PNG generated by the barcode generator tutorial](https://example.com/planet_barcode.png "Planet barcode PNG generated by the barcode generator tutorial")

*Texto alternativo da imagem:* **Planet barcode PNG generated by the barcode generator tutorial** (corresponde ao comprimento de texto alternativo exigido).

## Variações comuns e casos de borda

| Situação | O que ajustar | Por que importa |
|-----------|----------------|----------------|
| **Comprimento de dados diferente** | Certifique‑se de que a string de dados corresponde à contagem de dígitos exigida pelo Planet (5, 9 ou 11 dígitos). | Comprimentos inválidos causam `ArgumentException`. |
| **Saída com DPI mais alto** | Defina `barcode_generator.parameters.image_resolution.dpi = 300`. | Melhora a qualidade de impressão em impressoras de alta resolução. |
| **Outros formatos de imagem** | Substitua `BarCodeImageFormat.Png` por `Jpeg`, `Bmp` ou `Gif`. | Escolha um formato que atenda ao processamento subsequente. |
| **Múltiplos códigos de barras em uma imagem** | Use `barcode_generator.save_multiple([...])` (disponível em versões mais recentes). | Útil para geração em lote de etiquetas. |

## Lista de verificação de solução de problemas

* **Código de barras não aparece** – Verifique se o diretório de saída existe e se você tem permissão de gravação.
* **Leitor não consegue ler o código de barras** – Aumente a dimensão X ou a altura da barra; evite defini‑las abaixo dos limites mínimos legíveis.
* **ImportError** – Confirme que você instalou `aspose-barcode` no mesmo ambiente Python em que está executando o script.

## Conclusão

Este **tutorial de gerador de código de barras** guiou você por todo o processo de criação de um PNG de código de barras Planet, desde a instalação da biblioteca até **alterar o tamanho do código de barras** e salvar a imagem. Agora você tem uma base sólida para **como gerar código de barras** programaticamente e pode expandir o código para outras simbologias, formatos ou operações em lote.

**Próximos passos**

* Explore outras simbologias como `EncodeTypes.Code128` ou `EncodeTypes.QR` (cobre a palavra‑chave secundária *create barcode png* para tipos diferentes).
* Integre o PNG gerado em PDFs usando `reportlab` ou `PyPDF2`.
* Automatize a geração em lote para uma lista de códigos postais (retorna ao *create planet barcode* em escala).

Feliz codificação, e que seus códigos de barras sempre sejam lidos na primeira tentativa!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [How to create planet barcode PNG with Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)
- [Complete barcode generator tutorial for creating a Planet barcode in Python](/barcode/english/python-java/general/complete-barcode-generator-tutorial-for-creating-a-planet-ba/)
- [How to save PNG from a barcode generator example in Python](/barcode/english/python-java/general/how-to-save-png-from-a-barcode-generator-example-in-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}