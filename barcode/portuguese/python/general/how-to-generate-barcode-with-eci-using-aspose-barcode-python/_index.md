---
category: general
date: 2026-08-19
description: Como gerar código de barras com ECI usando Aspose.Barcode para Python.
  Aprenda como adicionar dados ECI, combinar texto simples e salvar a imagem em um
  guia claro.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to add eci
- Aspose.Barcode Python
- extended codetext barcode
- ECI encoding Python
language: pt
lastmod: 2026-08-19
og_description: Como gerar código de barras com ECI usando Aspose.Barcode para Python.
  Siga este tutorial para aprender a adicionar dados ECI, personalizar a aparência
  e salvar o resultado.
og_image_alt: Screenshot showing a barcode generated with how to generate barcode
  example
og_title: Como gerar código de barras com ECI usando Aspose.Barcode Python – passo
  a passo
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  headline: How to generate barcode with ECI using Aspose.Barcode Python
  type: TechArticle
- description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  name: How to generate barcode with ECI using Aspose.Barcode Python
  steps:
  - name: Expected result
    text: When you open `extended_codetext.png`, you should see a Code 128 barcode
      that encodes the numeric string `1234567890` followed by the Chinese characters
      “特殊字符”. Scanning the barcode with a modern scanner that respects ECI will return
      the original mixed string.
  - name: What if I need a different character set?
    text: Choose the appropriate ECI value from the ISO/IEC 18004 table. For example,
      ECI 27 represents ISO‑8859‑1 (Latin‑1). Replace the numeric identifier in `add_eci_codetext`
      accordingly.
  - name: Can I embed more than one ECI block?
    text: Yes. Call `add_eci_codetext` multiple times. The builder inserts the necessary
      ECI switch codes between blocks, preserving the order you add them.
  - name: Does the generator support QR codes with ECI?
    text: Absolutely. Replace `barcode.Symbology.CODE_128` with `barcode.Symbology.QR`
      and adjust any QR‑specific parameters (e.g., error correction level) via `generator.parameters.qr`.
  - name: How to handle very long data strings?
    text: For linear barcodes like Code 128, the maximum length is about 80 characters
      when using extended codetext. If you exceed that, consider switching to a two‑dimensional
      symbology such as QR or Data Matrix, which can store thousands of characters.
  type: HowTo
tags:
- barcode
- Python
- Aspose
title: Como gerar código de barras com ECI usando Aspose.Barcode Python
url: /pt/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como gerar código de barras com ECI usando Aspose.Barcode Python

Se você precisa saber **como gerar código de barras** que contenha tanto caracteres simples quanto dados codificados em ECI, este guia mostra o processo completo. Você verá exatamente **como adicionar eci** nas seções, ajustar o tamanho e gravar a imagem no disco com um único script executável.

O tutorial aborda:

* Recuperar a versão da biblioteca Aspose.Barcode (opcional, mas útil para depuração).  
* Construir uma string de codetexto estendido que mistura caracteres simples e codificados em ECI.  
* Criar um gerador de código de barras para uma simbologia que suporte codetexto estendido.  
* Personalizar as dimensões do código de barras e salvar o arquivo PNG final.

Nenhuma documentação externa é necessária; copie o código, execute-o e você terá uma imagem de código de barras que inclui caracteres chineses codificados com ECI 26 (UTF‑8).

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

* Python 3.8 ou superior instalado.  
* Pacote `aspose-barcode` instalado (`pip install aspose-barcode`).  
* Permissão de escrita na pasta onde pretende salvar o arquivo PNG.

Se estiver usando um ambiente virtual, ative‑o primeiro para manter as dependências isoladas.

## Etapa 1: Verificar a versão do Aspose.Barcode (opcional)

Saber a versão exata da biblioteca ajuda quando você precisa relatar bugs ou comparar recursos entre versões.

```python
import aspose.barcode as barcode
from aspose.barcode.generation import BuildVersionInfo

ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)
```

*Por que isso importa*: A saída da versão confirma que o runtime corresponde à documentação que você está seguindo. Versões diferentes podem suportar valores de ECI diferentes, portanto é uma verificação rápida de sanidade.

## Etapa 2: Construir um codetexto estendido com partes simples e codificadas em ECI

Aspose.Barcode fornece `ExtCodetextBuilder` para concatenar dados simples e segmentos codificados em ECI. Neste exemplo misturamos uma string numérica com caracteres chineses.

```python
from aspose.barcode.generation import ExtCodetextBuilder

builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using ECI 26 (UTF‑8)
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)
```

*Explicação*:  
* `add_plain_codetext` insere dados que a simbologia do código de barras trata como caracteres ordinários.  
* `add_eci_codetext` indica ao gerador que ele deve preceder o texto fornecido com um indicador ECI (aqui **26**, que corresponde ao UTF‑8). Isso é exatamente **como adicionar eci** a um código de barras.

Você pode chamar `add_eci_codetext` várias vezes para incorporar vários blocos de idiomas diferentes. O builder lida automaticamente com as sequências de escape necessárias.

## Etapa 3: Escolher uma simbologia que suporte codetexto estendido

Nem todo tipo de código de barras pode armazenar segmentos ECI. Code 128, QR e Data Matrix são escolhas comuns. O exemplo usa Code 128 porque é amplamente suportado e funciona bem para dados alfanuméricos mistos.

```python
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,   # Code128 supports extended codetext
    extended_codetext
)
```

*Por que Code 128?*: Ele aceita toda a faixa ASCII e as sequências de escape ECI produzidas pelo builder, tornando‑o ideal para o cenário “como gerar código de barras” que mistura texto simples e codificado.

## Etapa 4: Ajustar a aparência do código de barras

Você pode controlar tamanho, altura, margens e muitos outros aspectos visuais via o objeto `parameters`.

```python
# Width of a single module (the smallest bar)
generator.parameters.barcode.x_dimension = 2   # 2 pixels per module

# Height of the bars (for linear barcodes)
generator.parameters.barcode.bar_height = 50  # 50 pixels tall

# Optional: add quiet zone (margin) if required by a scanner
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10   # 10 pixels margin on each side
```

*Dica*: Se planeja imprimir o código de barras, aumente `x_dimension` e `bar_height` proporcionalmente para manter a legibilidade no DPI alvo.

## Etapa 5: Salvar a imagem do código de barras

Por fim, grave a imagem gerada em um arquivo. Aspose.Barcode suporta PNG, JPEG, BMP e muitos outros formatos.

```python
output_path = "output/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

Certifique‑se de que a pasta `output` exista ou crie‑a com `os.makedirs("output", exist_ok=True)` antes de chamar `save`.

### Resultado esperado

Ao abrir `extended_codetext.png`, você deverá ver um código de barras Code 128 que codifica a string numérica `1234567890` seguida dos caracteres chineses “特殊字符”. Escaneando o código de barras com um leitor moderno que respeite ECI, o texto misto original será retornado.

![Barcode generated with how to generate barcode example](https://example.com/images/barcode-sample.png){: .align-center alt="Barcode generated with how to generate barcode example"}

## Perguntas comuns e casos de borda

### E se eu precisar de um conjunto de caracteres diferente?

Escolha o valor ECI apropriado na tabela ISO/IEC 18004. Por exemplo, ECI 27 representa ISO‑8859‑1 (Latin‑1). Substitua o identificador numérico em `add_eci_codetext` de acordo.

### Posso incorporar mais de um bloco ECI?

Sim. Chame `add_eci_codetext` várias vezes. O builder insere os códigos de troca ECI necessários entre os blocos, preservando a ordem em que você os adiciona.

### O gerador suporta códigos QR com ECI?

Absolutamente. Substitua `barcode.Symbology.CODE_128` por `barcode.Symbology.QR` e ajuste quaisquer parâmetros específicos de QR (por exemplo, nível de correção de erro) via `generator.parameters.qr`.

```python
generator.parameters.qr.error_correction_level = barcode.QRErrorLevel.H
```

### Como lidar com strings de dados muito longas?

Para códigos de barras lineares como Code 128, o comprimento máximo é cerca de 80 caracteres ao usar codetexto estendido. Se você ultrapassar esse limite, considere mudar para uma simbologia bidimensional como QR ou Data Matrix, que pode armazenar milhares de caracteres.

## Script completo e executável

Abaixo está o programa completo que você pode copiar‑colar em um arquivo chamado `generate_extended_barcode.py` e executar diretamente.

```python
import os
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# ------------------------------------------------------------------
# Optional: print library version – useful for troubleshooting
# ------------------------------------------------------------------
ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)

# ------------------------------------------------------------------
# Build extended codetext: plain numbers + Chinese characters (ECI 26)
# ------------------------------------------------------------------
builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using UTF‑8
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)

# ------------------------------------------------------------------
# Create a Code128 generator – supports the extended codetext format
# ------------------------------------------------------------------
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,
    extended_codetext
)

# ------------------------------------------------------------------
# Customize appearance (size, quiet zone, etc.)
# ------------------------------------------------------------------
generator.parameters.barcode.x_dimension = 2
generator.parameters.barcode.bar_height = 50
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10

# ------------------------------------------------------------------
# Ensure output directory exists and save the image
# ------------------------------------------------------------------
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)
output_path = os.path.join(output_dir, "extended


## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Como gerar imagem de código de barras com personalização de espaço suplementar usando Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [Como gerar imagem de código de barras em Java com Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [Como gerar código de barras DataMatrix com Aspose.BarCode para .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}