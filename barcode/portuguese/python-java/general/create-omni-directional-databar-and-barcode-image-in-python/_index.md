---
category: general
date: 2026-08-12
description: Crie um databar omnidirecional com Python e aprenda como criar imagem
  de código de barras em Python usando Aspose.BarCode. Siga o guia passo a passo para
  uma solução completa.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni directional databar
- create barcode image python
language: pt
lastmod: 2026-08-12
og_description: Crie um databar omnidirecional com Python e gere uma imagem de código
  de barras em minutos. Este tutorial mostra um exemplo completo e executável.
og_image_alt: example of create omni directional databar barcode image in Python
og_title: Crie uma barra de dados omnidirecional – guia completo de Python
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create omni directional databar with Python and learn how to create
    barcode image python using Aspose.BarCode. Follow the step‑by‑step guide for a
    complete solution.
  headline: Create omni directional databar and barcode image in Python
  type: TechArticle
tags:
- barcode
- Python
- Aspose
- DataBar
title: Criar imagem de databar e código de barras omnidirecional em Python
url: /pt/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar databar omnidirecional e imagem de código de barras em Python

Se você precisa **criar databar omnidirecional** em um projeto Python, este guia mostra como fazer isso e também como **criar imagem de código de barras python** usando a biblioteca Aspose.BarCode. Você receberá um script pronto‑para‑executar que produz dois arquivos PNG com diferentes proporções.

Gerar um DataBar que segue a especificação omnidirecional é um requisito comum para aplicações de varejo e logística. O tutorial cobre instalação, configuração da dimensão X, ajuste da proporção e salvamento das imagens finais. Nenhum serviço externo é necessário; tudo roda localmente.

## O que você precisará

Antes de começar, certifique‑se de que você tem:

* Python 3.8 ou mais recente instalado na sua máquina.
* Acesso a um terminal ou prompt de comando.
* Permissão de escrita em uma pasta onde as imagens de código de barras serão salvas.

A única dependência de terceiros é **Aspose.BarCode for Python via .NET**, que suporta o tipo DataBar omnidirecional nativamente.

## Etapa 1: Instalar Aspose.BarCode para Python

Aspose.BarCode fornece a classe `BarcodeGenerator` usada no código de exemplo. Instale o pacote com `pip`:

```bash
pip install aspose-barcode
```

O pacote inclui as ligações necessárias ao runtime .NET, portanto você não precisa instalar o .NET SDK separadamente.

## Etapa 2: Importar a biblioteca e criar o gerador

A primeira linha do script cria um gerador para um DataBar omnidirecional empilhado. O valor GTIN‑14 `(01)12345678901231` é usado como dado de exemplo.

```python
# Step 2: Import classes and create the generator
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a stacked Omni‑directional DataBar with the required data
barcode_generator = BarcodeGenerator(
    EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
    "(01)12345678901231"
)
```

*Por que esta etapa importa*: A constante `EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL` indica à biblioteca que o valor deve ser codificado como um DataBar omnidirecional, formato exigido por muitos scanners de ponto de venda.

## Etapa 3: Definir a dimensão X (largura do módulo)

A dimensão X define a largura do menor módulo de barra. Um valor de `2` pixels produz um código de barras claro e legível sem tamanho de arquivo excessivo.

```python
# Step 3: Set the basic X‑dimension (width of the smallest module) in pixels
barcode_generator.parameters.barcode.x_dimension.pixels = 2
```

*Por que esta etapa importa*: Ajustar a dimensão X permite equilibrar legibilidade e dimensões da imagem. Uma dimensão X muito pequena pode gerar má qualidade em impressoras de baixa resolução.

## Etapa 4: Configurar a proporção e salvar a primeira imagem

A proporção influencia a altura total do DataBar em relação à sua largura. Uma proporção de `15` cria um estilo visual compacto.

```python
# Step 4: Configure an aspect ratio of 15 and save the first image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 15
barcode_generator.save("output/StackedAR15.png", BarCodeImageFormat.Png)
```

> **Dica profissional**: Use `pathlib.Path` para construir o caminho de saída, o que cria diretórios ausentes automaticamente.

```python
from pathlib import Path

output_dir = Path("output")
output_dir.mkdir(parents=True, exist_ok=True)
barcode_generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)
```

## Etapa 5: Alterar a proporção para um segundo estilo visual e salvar outra imagem

Mudar a proporção para `30` produz um código de barras mais alto, que pode ser exigido por hardware de scanner específico.

```python
# Step 5: Change the aspect ratio to 30 and save the second image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 30
barcode_generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)
```

*Por que esta etapa importa*: Diferentes varejistas e dispositivos de leitura têm restrições de tamanho distintas. Fornecer ambas as proporções em um único script permite gerar o estilo exato que você precisa sem duplicar código.

## Script completo – criar databar omnidirecional e imagem de código de barras python

Abaixo está o exemplo completo e executável que incorpora todas as etapas anteriores. Salve como `generate_databar.py` e execute com `python generate_databar.py`.

```python
#!/usr/bin/env python3
"""
Complete example that creates an omni directional databar
and demonstrates how to create barcode image python using Aspose.BarCode.
"""

# Import required classes
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
from pathlib import Path

def main():
    # Define output directory and ensure it exists
    output_dir = Path("output")
    output_dir.mkdir(parents=True, exist_ok=True)

    # Initialize the generator with Omni‑directional DataBar data
    generator = BarcodeGenerator(
        EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
        "(01)12345678901231"
    )

    # Set X‑dimension to 2 pixels for good readability
    generator.parameters.barcode.x_dimension.pixels = 2

    # First visual style – aspect ratio 15
    generator.parameters.barcode.data_bar.aspect_ratio = 15
    generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)

    # Second visual style – aspect ratio 30
    generator.parameters.barcode.data_bar.aspect_ratio = 30
    generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)

    print(f"Images saved to: {output_dir.resolve()}")

if __name__ == "__main__":
    main()
```

### Saída esperada

Executar o script cria os seguintes arquivos:

```
output/StackedAR15.png   # DataBar with aspect ratio 15
output/StackedAR30.png   # DataBar with aspect ratio 30
```

Ambas as imagens exibem um DataBar omnidirecional válido que pode ser lido por equipamentos de varejo padrão.

![exemplo de criação de databar omnidirecional e imagem de código de barras em Python](example_databar.png "criar databar omnidirecional e imagem de código de barras python")

*A imagem acima é um placeholder que ilustra os dois arquivos PNG salvos.*

## Tratamento de problemas comuns

| Problema | Motivo | Solução |
|----------|--------|---------|
| `ImportError: No module named aspose` | Aspose.BarCode não instalado ou instalado em outro ambiente. | Ative o ambiente virtual correto e execute `pip install aspose-barcode`. |
| `PermissionError` ao salvar | O script não tem permissão de escrita na pasta de destino. | Escolha um diretório que você possua ou execute o script com privilégios adequados. |
| Código de barras não lê | Dimensão X muito baixa ou proporção incompatível com o scanner. | Aumente `x_dimension.pixels` para 3 ou 4 e teste diferentes valores de `aspect_ratio` (ex.: 20, 25). |
| Runtime .NET ausente | Aspose.BarCode depende do runtime .NET no Windows/Linux. | Instale o runtime .NET mais recente a partir do site da Microsoft; a documentação do pacote fornece orientações específicas por plataforma. |

## Estendendo o exemplo

Você pode adaptar o script para gerar outras variantes de DataBar (ex.: `DATABAR_STACKED`, `DATABAR_EXPANDED`). Substitua a constante `EncodeTypes` conforme necessário:

```python
generator = BarcodeGenerator(EncodeTypes.DATABAR_EXPANDED, "(01)12345678901231")
```

Se precisar incorporar o código de barras em um PDF, Aspose.PDF para Python pode importar o arquivo PNG diretamente ou você pode usar o método `save` com `BarCodeImageFormat.Pdf`.

## Conclusão

Este tutorial mostrou como **criar databar omnidirecional** e como **criar imagem de código de barras python** usando Aspose.BarCode. Agora você tem um script completo e reproduzível que gera dois arquivos PNG com diferentes proporções, lida com armadilhas comuns e pode ser estendido para outros formatos de código de barras.

Em seguida, explore a geração de QR codes, a adição do código de barras a faturas PDF ou a automação de processamento em lote para grandes catálogos de produtos. Cada um desses tópicos se baseia no mesmo padrão `BarcodeGenerator` demonstrado aqui. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [How to create barcode image and render it in Java](/barcode/english/java/barcode-rendering-techniques/rendering-barcode-image-instance/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}