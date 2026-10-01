---
category: general
date: 2026-07-30
description: Como gerar código de barras usando Aspose.BarCode em Python – aprenda
  a definir dimensões, alterar o preenchimento e salvar imagens PNG em minutos.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to set dimensions
- how to change fill
- generate barcode with aspose
language: pt
lastmod: 2026-07-30
og_description: Como gerar código de barras rapidamente com Aspose.BarCode em Python.
  Descubra como definir dimensões, alterar o preenchimento e exportar arquivos PNG
  para qualquer aplicativo.
og_image_alt: Screenshot showing a filled Planet barcode and an empty Planet barcode
  generated with Aspose.BarCode
og_title: Como gerar código de barras com Aspose.BarCode – Guia Python
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: How to generate barcode using Aspose.BarCode in Python – learn how
    to set dimensions, change fill, and save PNG images in minutes.
  headline: How to generate barcode with Aspose.BarCode in Python
  type: TechArticle
- description: How to generate barcode using Aspose.BarCode in Python – learn how
    to set dimensions, change fill, and save PNG images in minutes.
  name: How to generate barcode with Aspose.BarCode in Python
  steps:
  - name: Why set `x_dimension.pixels`?
    text: Even though the default works, you often need to **how to set dimensions**
      to match printer DPI or UI constraints. The `x_dimension` property controls
      the width of a single bar in pixels; larger numbers yield a thicker barcode,
      while smaller numbers make it more compact.
  - name: Expected output
    text: 'Running the script prints something like:'
  - name: 5.1 Making the barcode larger for print
    text: 'If you’re printing on a 300 dpi label printer, a 4‑pixel bar might look
      tiny. Increase the `x_dimension` to, say, 8 pixels:'
  - name: 5.2 Making the barcode smaller for mobile screens
    text: Conversely, for a mobile app you might want a tighter barcode. Setting `x_dimension`
      to 2 pixels reduces the width without breaking readability (Aspose handles the
      scaling automatically).
  type: HowTo
tags:
- barcode
- Aspose
- Python
title: Como gerar código de barras com Aspose.BarCode em Python
url: /pt/python-java/general/how-to-generate-barcode-with-aspose-barcode-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como gerar código de barras com Aspose.BarCode em Python

Já se perguntou **como gerar código de barras** em um projeto Python sem lutar com bibliotecas de imagem de baixo nível? Você não está sozinho. Seja construindo um sistema de etiquetas de envio, uma plataforma de bilhetagem ou apenas precisando de um QR code rápido para uma demonstração, dominar a geração de códigos de barras pode economizar horas de tentativa‑e‑erro.

Neste tutorial vamos percorrer um exemplo completo, pronto‑para‑executar, que mostra **como gerar código de barras** usando a biblioteca Aspose.BarCode, como definir dimensões e como alterar o preenchimento. Ao final, você terá dois arquivos PNG — um com barras preenchidas e outro com barras vazias — diretamente na sua pasta de saída.

## Pré‑requisitos

Antes de mergulharmos, certifique‑se de que você tem:

* Python 3.8+ instalado (o código funciona no Windows, macOS e Linux)
* Uma licença ativa do Aspose.BarCode for Python via .NET (você pode começar com um teste gratuito)
* `pip install aspose-barcode` executado no seu ambiente virtual
* Uma pasta onde você possa gravar — nos exemplos a chamaremos de `YOUR_DIRECTORY`

Nenhum outro pacote de terceiros é necessário.

## Etapa 1: Instalar e importar Aspose.BarCode

Primeiro de tudo: precisamos da própria biblioteca. Execute isso uma vez no seu terminal:

```bash
pip install aspose-barcode
```

Agora podemos importar as classes que usaremos. Esta é a parte onde **como gerar código de barras** realmente começa, porque sem as importações corretas você nem consegue chamar o gerador.

```python
# Import the required Aspose.BarCode classes
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

> **Dica profissional:** Se você estiver usando um ambiente virtual, ative‑o antes de executar `pip install`. Isso mantém seu Python global organizado.

## Etapa 2: Criar um código de barras Planet – a versão padrão (preenchida)

O código de barras Planet é uma simbologia clássica 2‑of‑5 usada por serviços postais. Vamos começar com o caso mais simples: um código de barras preenchido. Esta etapa demonstra **como gerar código de barras** com as configurações padrão.

```python
# Step 2: Create a Planet barcode with filled bars (default)
filled_barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")
filled_barcode.parameters.barcode.x_dimension.pixels = 4   # default width per bar
filled_barcode.save("YOUR_DIRECTORY/PostalPlanetFilled.png", BarCodeImageFormat.Png)
```

### Por que definir `x_dimension.pixels`?

Mesmo que o padrão funcione, muitas vezes você precisa **definir dimensões** para combinar com a DPI da impressora ou restrições da UI. A propriedade `x_dimension` controla a largura de uma única barra em pixels; números maiores produzem um código de barras mais grosso, enquanto números menores o tornam mais compacto.

## Etapa 3: Criar um código de barras Planet com barras vazias (não preenchidas)

Agora vamos responder à pergunta **como alterar o preenchimento**. Ao alternar a flag `filled_bars` podemos mudar de uma barra preta sólida para uma barra vazia que ainda codifica os mesmos dados.

```python
# Step 3: Create a Planet barcode with empty (unfilled) bars
empty_barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")
empty_barcode.parameters.barcode.x_dimension.pixels = 4   # keep dimensions consistent
empty_barcode.parameters.barcode.filled_bars = False     # turn off fill
empty_barcode.save("YOUR_DIRECTORY/PostalPlanetEmpty.png", BarCodeImageFormat.Png)
```

Quando você abrir `PostalPlanetFilled.png` e `PostalPlanetEmpty.png` lado a lado, verá a diferença visual: a versão preenchida é preta sólida, enquanto a versão vazia mostra as barras como contornos. Isso é útil quando você precisa de um peso visual mais leve para sobreposições de UI.

## Etapa 4: Script completo, executável (a solução completa)

Abaixo está o programa inteiro que você pode copiar‑colar em um arquivo chamado `generate_planet_barcodes.py`. Ele inclui tudo, desde as importações até a gravação das imagens, para que você não precise procurar partes ausentes.

```python
#!/usr/bin/env python3
"""
Complete example: generate filled and empty Planet barcodes using Aspose.BarCode.
Demonstrates how to generate barcode, how to set dimensions, and how to change fill.
"""

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

def ensure_output_dir(path: str) -> None:
    """Create the output directory if it doesn't exist."""
    if not os.path.isdir(path):
        os.makedirs(path)
        print(f"Created output directory: {path}")

def generate_filled_barcode(output_dir: str, data: str = "123456", x_dim: int = 4) -> str:
    """Generate a filled Planet barcode and return the file path."""
    generator = BarcodeGenerator(EncodeTypes.Planet, data)
    generator.parameters.barcode.x_dimension.pixels = x_dim
    file_path = os.path.join(output_dir, "PostalPlanetFilled.png")
    generator.save(file_path, BarCodeImageFormat.Png)
    return file_path

def generate_empty_barcode(output_dir: str, data: str = "123456", x_dim: int = 4) -> str:
    """Generate an empty (unfilled) Planet barcode and return the file path."""
    generator = BarcodeGenerator(EncodeTypes.Planet, data)
    generator.parameters.barcode.x_dimension.pixels = x_dim
    generator.parameters.barcode.filled_bars = False
    file_path = os.path.join(output_dir, "PostalPlanetEmpty.png")
    generator.save(file_path, BarCodeImageFormat.Png)
    return file_path

if __name__ == "__main__":
    # Define where the PNG files will be stored
    output_folder = "YOUR_DIRECTORY"
    ensure_output_dir(output_folder)

    filled_path = generate_filled_barcode(output_folder)
    empty_path = generate_empty_barcode(output_folder)

    print(f"Filled barcode saved to: {filled_path}")
    print(f"Empty barcode saved to: {empty_path}")
```

### Saída esperada

Executar o script imprime algo como:

```
Created output directory: YOUR_DIRECTORY
Filled barcode saved to: YOUR_DIRECTORY/PostalPlanetFilled.png
Empty barcode saved to: YOUR_DIRECTORY/PostalPlanetEmpty.png
```

Abra os dois arquivos PNG com qualquer visualizador de imagens; você deverá ver um clássico código de barras Planet — um sólido, outro vazio. Ambos codificam a string `123456`.

## Etapa 5: Ajustando dimensões para diferentes casos de uso

Agora que você sabe **como definir dimensões**, vamos explorar alguns cenários comuns.

### 5.1 Tornar o código de barras maior para impressão

Se você estiver imprimindo em uma impressora de etiquetas de 300 dpi, uma barra de 4 pixels pode parecer minúscula. Aumente `x_dimension` para, por exemplo, 8 pixels:

```python
filled_barcode.parameters.barcode.x_dimension.pixels = 8
```

### 5.2 Tornar o código de barras menor para telas móveis

Por outro lado, para um aplicativo móvel você pode querer um código de barras mais compacto. Definir `x_dimension` para 2 pixels reduz a largura sem comprometer a legibilidade (Aspose lida com o redimensionamento automaticamente).

```python
empty_barcode.parameters.barcode.x_dimension.pixels = 2
```

Lembre‑se de que a altura do código de barras é ajustada automaticamente com base nas especificações da simbologia, portanto você só precisa se preocupar com a largura.

## Etapa 6: Opções avançadas de preenchimento e por que você pode precisar delas

Além do simples Boolean `filled_bars`, o Aspose.BarCode permite personalizar cores de barras, cores de fundo e até adicionar gradientes. Se você precisar **como alterar o preenchimento** além de “preenchido vs vazio”, pode fazer algo assim:

```python
filled_barcode.parameters.barcode.barcode_color = System.Drawing.Color.from_argb(255, 0, 0, 255)  # blue bars
filled_barcode.parameters.barcode.back_color = System.Drawing.Color.from_argb(255, 255, 255, 255)   # white background
```

*(Observação: o exemplo acima usa structs de cor .NET; em Python puro você usaria o enum apropriado do Aspose.)* Isso é útil para branding — imagine o logotipo da empresa sutilmente incorporado ao fundo de um código de barras.

## Armadilhas comuns e como evitá‑las

| Sintoma | Causa provável | Solução |
|---------|----------------|--------|
| O código de barras aparece borrado no PNG salvo | `x_dimension` muito baixa para a DPI alvo | Aumente `x_dimension` ou aumente a imagem após a gravação |
| O scanner se recusa a ler o código de barras vazio | `filled_bars = False` não suportado por alguns scanners legados | Use a versão padrão preenchida para máxima compatibilidade |
| `ImportError: cannot import name 'BarcodeGenerator'` | Aspose.BarCode não instalado ou runtime .NET incompatível | Reinstale com `pip install aspose-barcode` e garanta que o runtime .NET Core esteja presente |

## Recapitulação: O que cobrimos

* **Como gerar código de barras** com Aspose.BarCode em Python
* **Como definir dimensões** usando `x_dimension.pixels`
* **Como alterar o preenchimento** via a flag `filled_bars` (e uma visão sobre personalização de cores)
* Um script completo, pronto‑para‑copiar, que você pode adaptar para qualquer string de dados

## O que vem a seguir? (Próximos passos e tópicos relacionados)

Se este guia foi útil, considere explorar:

* **Gerar códigos QR** (`EncodeTypes.QR`) — perfeito para URLs e informações de contato.
* **Adicionar legendas de texto** abaixo do código de barras (`parameters.caption`) para valores legíveis por humanos.
* **Exportar para outros formatos** como SVG ou PDF (`BarCodeImageFormat.Svg`, `BarCodeImageFormat.Pdf`) — ideal para gráficos vetoriais.
* **Geração em lote** — percorrer um CSV de IDs de produto para criar um catálogo inteiro de códigos de barras de uma só vez.

Todos esses tópicos também se relacionam com nossas palavras‑chave secundárias: *generate barcode with aspose* e *how to set dimensions* para diferentes formatos de saída.

---

Sinta‑se à vontade para deixar um comentário se encontrar algum problema, ou compartilhar suas próprias variações. Boa criação de códigos de barras!


## O que você deve aprender a seguir?


Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)
- [How to create code128 barcode images in Java with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)
- [How to Colorize Barcode Images in Java with Aspose.BarCode](/barcode/english/java/image-manipulation/colorizing-barcode-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}