---
category: general
date: 2026-11-23
description: Como gerar imagens de código de barras em Python com Aspose.BarCode.
  Aprenda a criar um código de barras Planet, ajustar a dimensão X e gerar um PNG
  com barras vazias.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- Python barcode generation
- Aspose.BarCode library
- Planet barcode symbology
- empty bars barcode
- barcode image PNG
language: pt
lastmod: 2026-11-23
og_description: Como gerar código de barras em Python usando Aspose.BarCode. Este
  tutorial orienta você na criação de um código de barras Planet com barras vazias
  e na sua gravação como PNG.
og_image_alt: Screenshot of Python code that generates a Planet barcode with empty
  bars saved as a PNG file
og_title: Como gerar código de barras em Python – guia completo
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: How to generate barcode images in Python with Aspose.BarCode. Learn
    to create a Planet barcode, adjust X‑dimension, and output an empty‑bars PNG.
  headline: How to generate barcode images in Python using Aspose.BarCode
  type: TechArticle
- description: How to generate barcode images in Python with Aspose.BarCode. Learn
    to create a Planet barcode, adjust X‑dimension, and output an empty‑bars PNG.
  name: How to generate barcode images in Python using Aspose.BarCode
  steps:
  - name: Switching to a different symbology
    text: 'If you need a QR code, Code 128, or any other format, replace `EncodeTypes.Planet`
      with the appropriate enum value:'
  - name: Changing the image format
    text: 'Aspose.BarCode supports PNG, JPEG, BMP, and TIFF. To generate a JPEG instead:'
  - name: Adjusting image size without losing quality
    text: 'You can control the overall image dimensions via the `resolution` property
      or by scaling the X‑dimension and Y‑dimension together. For high‑resolution
      prints, set a higher DPI:'
  - name: Handling long data strings
    text: 'The Planet symbology has a limited data capacity (up to 8 characters).
      If you try to encode a longer string, the generator raises an exception. Validate
      the length before creating the barcode:'
  type: HowTo
tags:
- barcode
- Python
- Aspose
title: Como gerar imagens de código de barras em Python usando Aspose.BarCode
url: /pt/python-java/general/how-to-generate-barcode-images-in-python-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como gerar imagens de código de barras em Python usando Aspose.BarCode

Gerar imagens de código de barras em Python é simples com a biblioteca Aspose.BarCode. Este guia mostra passo a passo como gerar um código de barras usando a simbologia Planet, personalizar a dimensão X e produzir um arquivo PNG no estilo barras vazias.

Você verá um script completo e executável que pode copiar para o seu projeto. O tutorial também aborda variações comuns — como mudar para outra simbologia ou formato de saída — para que você possa adaptar a solução às suas necessidades.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

* Python 3.8 ou superior instalado.
* Acesso a um terminal ou prompt de comando.
* Uma licença ativa do Aspose.BarCode for Python (a avaliação gratuita funciona para testes).
* Familiaridade básica com o gerenciamento de pacotes Python (`pip`).

## Etapa 1: Instalar o pacote Aspose.BarCode

A Aspose distribui sua API Python via PyPI. Instale-a com o gerenciador de pacotes padrão:

```bash
pip install asposebarcode
```

> **Dica profissional:** Use um ambiente virtual (`python -m venv venv`) para manter as dependências isoladas de outros projetos.

## Etapa 2: Importar as classes necessárias do Aspose.BarCode

A instrução de importação traz o gerador, a enumeração de simbologias e a enumeração de formatos de imagem.

```python
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

* `BarcodeGenerator` cria o objeto de código de barras.
* `EncodeTypes` enumera todas as simbologias suportadas — aqui usaremos `Planet`.
* `BarCodeImageFormat` define o tipo de arquivo de saída (PNG, JPEG, etc.).

## Etapa 3: Criar um gerador de código de barras para a simbologia Planet

Instancie o gerador com a simbologia desejada e os dados que você quer codificar.

```python
# Create a generator for the Planet symbology with the value "123456"
barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

A simbologia `Planet` produz um padrão circular ideal para fins decorativos ou de branding.

## Etapa 4: Ajustar a dimensão X (largura do módulo)

A dimensão X controla a largura da barra mais estreita (módulo). Definir 4 pixels produz uma imagem clara e de alta resolução.

```python
# Set the module width to 4 pixels
barcode.parameters.barcode.x_dimension.pixels = 4
```

Alterar a dimensão X é útil quando você precisa de um código de barras que escale bem para impressão ou exibição em tela.

## Etapa 5: Desativar as barras preenchidas para o estilo barras vazias

Um código de barras de barras vazias mostra apenas os contornos das barras, o que pode ser útil em aplicações com design intenso.

```python
# Produce an empty‑bars barcode by disabling filled bars
barcode.parameters.barcode.filled_bars = False
```

Quando `filled_bars` está `False`, o gerador desenha formas ocas em vez de sólidas.

## Etapa 6: Salvar a imagem do código de barras como arquivo PNG

Por fim, grave o código de barras no disco. PNG é sem perdas e amplamente suportado.

```python
# Save the barcode as a PNG image
barcode.save("output/PlanetEmptyBars.png", BarCodeImageFormat.Png)
```

O método `save` cria automaticamente o diretório de destino caso ele não exista.

## Exemplo completo – um script completo e executável

Juntando todas as partes, você obtém um programa autônomo que pode ser executado imediatamente:

```python
# -*- coding: utf-8 -*-
"""
Generate a Planet barcode with empty bars and save it as PNG.
Requires: asposebarcode (pip install asposebarcode)
"""

from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# Step 1: Create the generator
barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")

# Step 2: Configure appearance
barcode.parameters.barcode.x_dimension.pixels = 4   # X‑dimension = 4 px
barcode.parameters.barcode.filled_bars = False    # empty‑bars style

# Step 3: Save as PNG
output_path = os.path.join(output_dir, "PlanetEmptyBars.png")
barcode.save(output_path, BarCodeImageFormat.Png)

print(f"Barcode saved to: {output_path}")
```

**Saída esperada:** Após executar o script, `output/PlanetEmptyBars.png` contém uma imagem de 200 × 200 pixels de um código de barras Planet com barras ocas. Abrir o arquivo em qualquer visualizador de imagens exibirá o padrão circular com o valor numérico codificado no interior.

## Variações comuns e casos de borda

### Trocar para outra simbologia

Se precisar de um QR code, Code 128 ou qualquer outro formato, substitua `EncodeTypes.Planet` pelo valor enum apropriado:

```python
barcode = BarcodeGenerator(EncodeTypes.QR, "https://example.com")
```

### Alterar o formato da imagem

Aspose.BarCode suporta PNG, JPEG, BMP e TIFF. Para gerar um JPEG em vez disso:

```python
barcode.save("output/PlanetEmptyBars.jpg", BarCodeImageFormat.Jpeg)
```

### Ajustar o tamanho da imagem sem perder qualidade

Você pode controlar as dimensões gerais da imagem via a propriedade `resolution` ou escalando as dimensões X e Y juntas. Para impressões de alta resolução, defina um DPI maior:

```python
barcode.parameters.image.resolution = 300  # 300 dpi for print quality
```

### Manipular strings de dados longas

A simbologia Planet tem capacidade de dados limitada (até 8 caracteres). Se tentar codificar uma string maior, o gerador lançará uma exceção. Valide o comprimento antes de criar o código de barras:

```python
data = "123456"
if len(data) > 8:
    raise ValueError("Planet barcode supports a maximum of 8 characters.")
```

## Dicas e armadilhas

* **Ativação da licença:** Para uso em produção, aplique seu arquivo de licença logo no início do script com `asposebarcode.License().set_license("Aspose.Total.lic")`. Pular esta etapa inserirá uma marca d'água na imagem de saída.
* **Segurança em threads:** Instâncias de `BarcodeGenerator` não são seguras para uso simultâneo. Crie uma instância separada por thread se gerar códigos de barras em paralelo.
* **Desempenho:** Reutilizar um gerador para múltiplos valores (através de `barcode.value = "new data"`) é mais rápido do que construir um novo objeto a cada vez.
* **Caminhos de arquivo:** Use `os.path.join` para construir caminhos independentes de plataforma, especialmente ao implantar em Linux ou macOS.

## Conclusão

Agora você sabe como gerar imagens de código de barras em Python com Aspose.BarCode, personalizar a dimensão X, produzir um estilo de barras vazias e salvar o resultado como PNG. O exemplo completo pode ser adaptado para outras simbologias, formatos de saída e estilos visuais, oferecendo uma base flexível para qualquer recurso relacionado a códigos de barras em suas aplicações.

**Próximos passos:** Explore palavras‑chave secundárias como *Python barcode generation* experimentando diferentes codificações, teste as configurações de compressão *barcode image PNG* ou integre as imagens geradas a um serviço web usando Flask ou FastAPI. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [How to create planet barcode PNG with Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)
- [How to create barcode image in Python with Aspose.BarCode](/barcode/english/python-java/general/how-to-create-barcode-image-in-python-with-aspose-barcode/)
- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}