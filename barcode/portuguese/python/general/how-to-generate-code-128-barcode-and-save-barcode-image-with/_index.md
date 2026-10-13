---
category: general
date: 2026-09-23
description: Aprenda a gerar código de barras Code 128 e salvar a imagem do código
  de barras usando Aspose.BarCode em Python – guia passo a passo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate code 128 barcode
- save barcode image
- Aspose.BarCode Python
- extended codetext builder
- barcode PNG export
language: pt
lastmod: 2026-09-23
og_description: Gere código de barras Code 128 e salve a imagem do código de barras
  com Aspose.BarCode em Python. Siga este exemplo completo para criar, personalizar
  e exportar o código de barras como um arquivo PNG.
og_image_alt: Python-generated Code 128 barcode saved as PNG image
og_title: Gerar código de barras Code 128 e salvar imagem do código de barras – Guia
  Python
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to generate Code 128 barcode and save barcode image using
    Aspose.BarCode in Python – step‑by‑step guide.
  headline: How to generate Code 128 barcode and save barcode image with Aspose.BarCode
  type: TechArticle
tags:
- barcode
- Code 128
- Python
- Aspose
title: Como gerar código de barras Code 128 e salvar a imagem do código de barras
  com Aspose.BarCode
url: /pt/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como gerar código de barras Code 128 e salvar a imagem do código de barras com Aspose.BarCode

Se você precisa **gerar código de barras Code 128** e **salvar a imagem do código de barras** em um projeto Python, este tutorial mostra os passos exatos. Usando o `ExtCodetextBuilder` do Aspose.BarCode, você pode incorporar texto simples e segmentos Unicode em uma única carga útil, e então renderizar o resultado como um arquivo PNG.

Você verá um script completo e executável, uma explicação de cada linha e dicas para armadilhas comuns, como lidar com a codificação ECI ou escolher a pasta de saída correta. Nenhuma documentação externa é necessária — basta copiar, colar e executar.

## Pré-requisitos

* Python 3.8+ instalado.
* O pacote `aspose.barcode` (instale com `pip install aspose-barcode`).
* Permissão de escrita no diretório onde o PNG será salvo.

O código funciona com qualquer simbologia suportada pelo Aspose.BarCode, mas o exemplo foca em **Code 128** porque codifica eficientemente dados alfanuméricos e suporta conjuntos de caracteres estendidos.

## Etapa 1: Importar as classes necessárias

```python
import barcode                     # Core Aspose.BarCode namespace
from barcode import BarCodeWriter, BarCodeEncodeMode, BarCodeImageFormat
from barcode import ExtCodetextBuilder, BuildVersionInfo
```

*Por que esta etapa?* Importar as classes fornece acesso ao construtor para codetext estendido, ao escritor que cria a imagem e ao auxiliar de versão que pode ser útil para depurar atualizações da biblioteca.

## Etapa 2: Construir o codetext estendido

```python
# Create a builder for extended codetext
builder = ExtCodetextBuilder()

# Add plain text (no ECI) – this part is simple ASCII
builder.add_plain_codetext("ABC123")

# Add a Unicode segment with ECI 0x03 (UTF‑8). The word “Пример” means “Example” in Russian.
builder.add_eci_codetext(0x03, "Пример")

# Retrieve the full extended codetext string
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

O `ExtCodetextBuilder` permite misturar dados ASCII simples e Unicode em uma única carga útil de código de barras. O byte ECI (Extended Channel Interpretation) `0x03` informa ao scanner que os bytes subsequentes estão codificados em UTF‑8, o que é essencial para idiomas como Russo, Chinês ou Árabe.

## Etapa 3: Configurar o escritor de código de barras para Code 128

```python
writer = BarCodeWriter()
writer.encode_type = BarCodeEncodeMode.CODE_128   # Choose Code 128 symbology
writer.code_text = extended_codetext
```

Definir `encode_type` como `CODE_128` instrui o escritor a renderizar um **código de barras Code 128**. A propriedade `code_text` recebe a string estendida construída na etapa anterior.

## Etapa 4: Salvar a imagem do código de barras como PNG

```python
output_path = "YOUR_DIRECTORY/extended_codetext.png"
writer.save(output_path, BarCodeImageFormat.PNG)
print(f"Barcode image saved to {output_path}")
```

O método `save` grava o código de barras em um arquivo. Usar `BarCodeImageFormat.PNG` garante compressão sem perdas e ampla compatibilidade com aplicações web e móveis.

## Etapa 5 (opcional): Verificar a versão da biblioteca Aspose.BarCode

```python
version_info = BuildVersionInfo()
print("Assembly version :", version_info.ASSEMBLY_VERSION)
print("Product version   :", f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR}")
print("Release date      :", version_info.RELEASE_DATE)
```

Conhecer a versão exata da biblioteca ajuda quando você precisa relatar bugs ou comparar o comportamento entre versões.

## Saída esperada

Executar o script produz uma saída no console semelhante a:

```
Extended codetext: ABC123[ECI=03]Пример
Assembly version : 23.12.0.0
Product version   : 23.12
Release date      : 2023-12-01
Barcode image saved to YOUR_DIRECTORY/extended_codetext.png
```

O PNG gerado (`extended_codetext.png`) se parece com isto:

![Código de barras Code 128 gerado em Python salvo como imagem PNG](images/code128_extended.png)

*A imagem mostra um código de barras Code 128 que codifica tanto a string ASCII `ABC123` quanto a palavra russa “Пример”.*

## Perguntas comuns e tratamento de casos extremos

| Pergunta | Resposta |
|----------|----------|
| **Posso usar uma simbologia diferente?** | Sim. Substitua `BarCodeEncodeMode.CODE_128` por qualquer outro modo suportado, como `QR`, `EAN_13` ou `PDF_417`. |
| **E se meu texto Unicode contiver emojis?** | Emojis também são caracteres UTF‑8, então a mesma chamada `add_eci_codetext` funciona. Certifique‑se de que o scanner de destino suporta o ECI que você usa. |
| **Como mudar o tamanho da imagem?** | Defina `writer.x_dimension` e `writer.bar_height` antes de chamar `save`. |
| **Qual pasta devo usar para `output_path`?** | Qualquer pasta que o processo Python possa gravar. Use `os.makedirs` com `exist_ok=True` para criá‑la automaticamente. |

## Dicas profissionais

* **Evite codificar caminhos de forma fixa.** Use `os.path.join` e `Path` do módulo `pathlib` para compatibilidade entre plataformas.
* **Valide o código de barras.** Após salvar, você pode ler a imagem novamente com `barcode.BarCodeReader` para confirmar que o texto codificado corresponde a `extended_codetext`.
* **Dica de desempenho.** Se você gerar muitos códigos de barras em um loop, reutilize uma única instância de `BarCodeWriter` e apenas atualize `code_text` a cada iteração.

## Conclusão

Agora você sabe como **gerar código de barras Code 128** com dados ASCII e Unicode misturados e **salvar a imagem do código de barras** como PNG usando Aspose.BarCode em Python. O script completo cobre a construção do codetext estendido, a configuração do escritor, a exportação da imagem e a verificação das versões da biblioteca.

A partir daqui você pode explorar:

* Adicionar cores de primeiro plano/fundo (`writer.back_color`, `writer.fore_color`).
* Incorporar o código de barras em PDFs com `Aspose.PDF`.
* Usar a classe `BarCodeReader` para decodificar a imagem salva e verificar o conteúdo automaticamente.

Feliz codificação, e sinta‑se à vontade para experimentar outras simbologias e formatos de imagem!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Gerar código de barras Code128 com Aspose.Barcode Python – Guia completo](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [Como gerar código de barras em Python – guia completo passo a passo](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [Como gerar imagem de QR Code em Python com Aspose.Barcode – Guia completo](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}