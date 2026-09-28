---
category: general
date: 2026-08-12
description: Como gerar códigos de barras rapidamente usando Python. Aprenda a criar
  códigos de barras a partir de dados e exportar a imagem do código de barras com
  uma única biblioteca.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode from data
- export barcode image
- Python barcode generation
- Aspose.BarCode tutorial
language: pt
lastmod: 2026-08-12
og_description: Como gerar código de barras em Python com Aspose.BarCode. Siga este
  guia para criar código de barras a partir de dados e exportar a imagem do código
  de barras como PNG.
og_image_alt: Screenshot showing how to generate barcode with Python code
og_title: Como gerar código de barras em Python – guia rápido e confiável
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: How to generate barcode quickly using Python. Learn to create barcode
    from data and export barcode image with a single library.
  headline: How to generate barcode in Python – complete step‑by‑step guide
  type: TechArticle
- description: How to generate barcode quickly using Python. Learn to create barcode
    from data and export barcode image with a single library.
  name: How to generate barcode in Python – complete step‑by‑step guide
  steps:
  - name: 1. Import the required classes
    text: '```python from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
      ```'
  - name: 2. Create barcode from data
    text: The first step is to **create barcode from data**. The `BarcodeGenerator`
      constructor takes the symbology and the raw string you want to encode.
  - name: 3. Adjust the X‑dimension (module width)
    text: The X‑dimension controls the width of each barcode module (the thin bar).
      Setting it to 4 pixels gives a clear, readable image without making the file
      too large.
  - name: 4. Export barcode image (filled style)
    text: Now you can **export barcode image** using the `save` method. The example
      saves a PNG file, but you can choose JPEG, BMP, or TIFF by changing the `BarCodeImageFormat`
      enum.
  - name: 5. Create a second generator for an outline‑only barcode
    text: If you need an outline version (empty bars), you must create a new generator
      because the `filled_bars` flag cannot be toggled after the image is saved.
  - name: 6. Apply the same X‑dimension setting
    text: When you create a second generator, you must repeat any visual settings
      you want to keep consistent.
  - name: 7. Disable filled bars for an outline barcode
    text: Setting `filled_bars` to `False` tells the renderer to draw only the outlines
      of each module, producing a lighter image that can be useful for design purposes.
  - name: 8. Export the outline barcode image
    text: Finally, **export barcode image** again, this time storing the outline version.
  - name: Next steps
    text: '* Explore other symbologies such as QR, Code‑128, or DataMatrix by swapping
      `EncodeTypes.Planet` with the desired value. * Integrate the generated PNG files
      into PDF reports using libraries like `ReportLab` or `PyPDF2`. * Experiment
      with dynamic X‑dimension values to adapt barcode size based on scre'
  type: HowTo
tags:
- barcode
- Python
- image export
title: Como gerar código de barras em Python – guia completo passo a passo
url: /pt/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como gerar código de barras em Python – guia completo passo a passo

Se você precisa **gerar código de barras** em uma aplicação Python, este tutorial mostra o código exato que você precisa. Você aprenderá a **criar código de barras a partir de dados**, ajustar sua aparência e **exportar a imagem do código de barras** como um arquivo PNG — tudo em menos de dez linhas de código.

Gerar um código de barras pode parecer uma preocupação separada da lógica de negócio, mas com uma única biblioteca você pode manter o processo integrado ao seu código existente. Nas seções a seguir você verá um exemplo completo e executável, entenderá por que cada linha é importante e descobrirá variações comuns, como mudar a largura do módulo ou desenhar um código de barras apenas com contorno.

## Como gerar código de barras com a biblioteca Aspose.BarCode

A biblioteca Aspose.BarCode para Python (via .NET) fornece uma API direta para muitas simbologias, incluindo o código de barras Planet usado neste guia. Antes de começar, certifique‑se de que o pacote está instalado:

```bash
pip install aspose-barcode
```

> **Dica profissional:** Use um ambiente virtual para evitar conflitos de versão com outros projetos.

### 1. Importar as classes necessárias

```python
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

Essas importações dão acesso à classe geradora, à enumeração dos tipos de código de barras e à enumeração de formatos de imagem usada ao salvar o resultado.

### 2. Criar código de barras a partir de dados

O primeiro passo é **criar código de barras a partir de dados**. O construtor `BarcodeGenerator` recebe a simbologia e a string bruta que você deseja codificar.

```python
# Step 1: Create a barcode generator for the Planet symbology with data "123456"
barcode_filled = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

O valor `EncodeTypes.Planet` seleciona o código de barras Planet, enquanto `"123456"` é a carga útil que aparecerá na imagem final.

### 3. Ajustar a dimensão X (largura do módulo)

A dimensão X controla a largura de cada módulo do código de barras (a barra fina). Definir 4 pixels fornece uma imagem clara e legível sem tornar o arquivo muito grande.

```python
# Step 2: Set the X‑dimension (module width) to 4 pixels
barcode_filled.parameters.barcode.x_dimension.pixels = 4
```

> **Por que isso importa:** Uma dimensão X maior melhora a confiabilidade da leitura em impressoras de baixa resolução, enquanto um valor menor reduz o tamanho do arquivo para uso na web.

### 4. Exportar imagem do código de barras (estilo preenchido)

Agora você pode **exportar a imagem do código de barras** usando o método `save`. O exemplo salva um arquivo PNG, mas você pode escolher JPEG, BMP ou TIFF alterando a enumeração `BarCodeImageFormat`.

```python
# Step 3: Save the barcode using the default filled‑bars style
barcode_filled.save("YOUR_DIRECTORY/PlanetFilled.png", BarCodeImageFormat.Png)
```

O arquivo `PlanetFilled.png` contém um código de barras Planet totalmente preenchido, pronto para impressão ou incorporação em um PDF.

### 5. Criar um segundo gerador para um código de barras apenas com contorno

Se precisar de uma versão de contorno (barras vazias), deve criar um novo gerador porque a flag `filled_bars` não pode ser alterada após a imagem ser salva.

```python
# Step 4: Create a second generator for the same data to illustrate empty bars
barcode_empty = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

### 6. Aplicar a mesma configuração de dimensão X

Ao criar um segundo gerador, você deve repetir todas as configurações visuais que deseja manter consistentes.

```python
# Step 5: Apply the same X‑dimension setting
barcode_empty.parameters.barcode.x_dimension.pixels = 4
```

### 7. Desativar barras preenchidas para um código de barras de contorno

Definir `filled_bars` como `False` indica ao renderizador que desenhe apenas os contornos de cada módulo, produzindo uma imagem mais leve que pode ser útil para fins de design.

```python
# Step 6: Disable filled bars to produce an outline‑only barcode
barcode_empty.parameters.barcode.filled_bars = False
```

### 8. Exportar a imagem do código de barras de contorno

Finalmente, **exporte a imagem do código de barras** novamente, desta vez armazenando a versão de contorno.

```python
# Step 7: Save the outline barcode
barcode_empty.save("YOUR_DIRECTORY/PlanetEmpty.png", BarCodeImageFormat.Png)
```

Agora você tem dois arquivos PNG: um com barras sólidas (`PlanetFilled.png`) e outro apenas com contornos (`PlanetEmpty.png`).

## Exportar imagem do código de barras em outros formatos (opcional)

O método `save` suporta vários formatos. Para exportar como JPEG com 90 % de qualidade:

```python
barcode_filled.save(
    "YOUR_DIRECTORY/PlanetFilled.jpg",
    BarCodeImageFormat.Jpeg,
    quality=90
)
```

Se precisar de fundo transparente para uso na web, escolha PNG com canal alfa:

```python
barcode_filled.parameters.background_color = None  # disables background fill
barcode_filled.save("YOUR_DIRECTORY/PlanetTransparent.png", BarCodeImageFormat.Png)
```

## Variações comuns e casos de borda

| Cenário | Alteração necessária | Trecho de código |
|----------|----------------------|------------------|
| **Simbologia diferente** (ex.: QR) | Use um valor diferente de `EncodeTypes` | `BarcodeGenerator(EncodeTypes.QR, "https://example.com")` |
| **Cor de primeiro plano personalizada** | Defina `fore_color` | `barcode_filled.parameters.barcode.fore_color = Color.Blue` |
| **Resolução mais alta** | Aumente DPI via `image_width` e `image_height` | `barcode_filled.parameters.image_width = 300; barcode_filled.parameters.image_height = 150` |
| **Strings de dados grandes** | Garanta que o comprimento dos dados se ajuste à especificação da simbologia | Valide o comprimento antes de criar o gerador |

> **Atenção:** Fornecer dados que excedam o comprimento máximo para a simbologia escolhida gera uma exceção em tempo de execução. Sempre valide o tamanho da string ou capture `ArgumentException`.

## Exemplo completo e executável

Abaixo está o script completo que você pode copiar‑colar em um arquivo chamado `generate_planet_barcode.py`. Ajuste `YOUR_DIRECTORY` para uma pasta que exista na sua máquina.

```python
# generate_planet_barcode.py
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def generate_barcodes(output_dir: str):
    # Filled‑bars barcode
    filled = BarcodeGenerator(EncodeTypes.Planet, "123456")
    filled.parameters.barcode.x_dimension.pixels = 4
    filled.save(f"{output_dir}/PlanetFilled.png", BarCodeImageFormat.Png)

    # Outline‑only barcode
    empty = BarcodeGenerator(EncodeTypes.Planet, "123456")
    empty.parameters.barcode.x_dimension.pixels = 4
    empty.parameters.barcode.filled_bars = False
    empty.save(f"{output_dir}/PlanetEmpty.png", BarCodeImageFormat.Png)

if __name__ == "__main__":
    import os
    output_path = "YOUR_DIRECTORY"
    os.makedirs(output_path, exist_ok=True)
    generate_barcodes(output_path)
    print("Barcodes generated successfully.")
```

Executar este script produz dois arquivos PNG no diretório especificado. Verifique a saída abrindo as imagens em qualquer visualizador; ambas devem exibir um código de barras Planet codificando a string `123456`.

## Conclusão

Agora você sabe **como gerar código de barras** em Python usando Aspose.BarCode, como **criar código de barras a partir de dados** e como **exportar a imagem do código de barras** tanto em estilo preenchido quanto em contorno. O mesmo padrão se aplica a outras simbologias, formatos de imagem e personalizações visuais, oferecendo uma base flexível para qualquer recurso relacionado a códigos de barras em sua aplicação.

### Próximos passos

* Explore outras simbologias como QR, Code‑128 ou DataMatrix substituindo `EncodeTypes.Planet` pelo valor desejado.  
* Integre os arquivos PNG gerados em relatórios PDF usando bibliotecas como `ReportLab` ou `PyPDF2`.  
* Experimente valores dinâmicos de dimensão X para adaptar o tamanho do código de barras com base na resolução da tela ou DPI da impressora.

Feliz codificação, e sinta‑se à vontade para adaptar o exemplo às necessidades do seu próprio projeto!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Como gerar imagem de código de barras em Java com Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [Como gerar código de barras Java – Guia completo de configuração](/barcode/english/java/barcode-configuration/)
- [Como criar imagens de código de barras code128 em Java com Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}