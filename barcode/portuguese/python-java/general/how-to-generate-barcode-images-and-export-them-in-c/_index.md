---
category: general
date: 2026-10-21
description: Aprenda a gerar imagens de código de barras em C# e a exportar arquivos
  de código de barras como PNG usando o Aspose.BarCode para resultados rápidos e confiáveis.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to export barcode
language: pt
lastmod: 2026-10-21
og_description: Como gerar imagens de código de barras em C# e como exportar arquivos
  de código de barras como PNG. Siga este tutorial completo para criar códigos de
  barras Planet e RM4SCC com Aspose.BarCode.
og_image_alt: Screenshot showing how to generate barcode images with C# code
og_title: Como gerar imagens de código de barras e exportá‑las em C# – guia passo
  a passo
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Learn how to generate barcode images in C# and how to export barcode
    files as PNG using Aspose.BarCode for fast, reliable results.
  headline: How to generate barcode images and export them in C#
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: Como gerar imagens de código de barras e exportá‑las em C#
url: /pt/python-java/general/how-to-generate-barcode-images-and-export-them-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como gerar imagens de código de barras e exportá‑las em C#

Se você precisa **gerar códigos de barras** em uma aplicação .NET, este guia mostra os passos exatos para criar códigos de barras Planet e RM4SCC e então **exportar códigos de barras** como arquivos PNG. Você receberá um exemplo de código pronto‑para‑executar, uma descrição de cada configuração e dicas para armadilhas comuns.

O tutorial cobre:

* Adicionar o pacote NuGet Aspose.BarCode
* Configurar a largura do módulo e a altura opcional das barras
* Salvar os códigos de barras gerados em disco
* Verificar os arquivos de saída

> **Pré‑requisito** – SDK .NET 6+ , Visual Studio 2022 (ou qualquer IDE) e conexão à internet para baixar o pacote Aspose.BarCode.

## O que você vai conseguir

Ao final deste artigo você será capaz de:

* Gerar um código de barras **Planet** com altura automática das barras.
* Gerar um código de barras **RM4SCC** com altura automática das barras.
* Substituir a altura padrão e produzir um código de barras com 100 pixels de altura.
* Exportar cada código de barras para um arquivo PNG em uma pasta de sua escolha.

## Etapa 1: Instalar Aspose.BarCode

Abra um terminal na pasta do seu projeto e execute:

```bash
dotnet add package Aspose.BarCode
```

O pacote fornece a classe `BarcodeGenerator` e a enumeração `EncodeTypes` usadas no código a seguir.

## Etapa 2: Configurar a pasta de saída

Crie uma pasta onde os arquivos PNG serão armazenados. A pasta pode ser absoluta ou relativa à raiz do projeto.

```csharp
// Define the folder where barcode images will be saved
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

// Ensure the directory exists
Directory.CreateDirectory(outputFolder);
```

> **Dica:** Usar `Path.Combine` evita separadores de caminho codificados e funciona no Windows, macOS e Linux.

## Etapa 3: Gerar códigos de barras com altura automática das barras

Quando você não especifica uma altura de barra, Aspose.BarCode escolhe um tamanho que se ajusta aos dados codificados. O código a seguir cria dois códigos de barras — Planet e RM4SCC — usando uma largura de módulo de 4 pixels.

```csharp
using Aspose.BarCode.Generation;

// Planet barcode, automatic height
var planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetAuto.Parameters.Barcode.XDimension.Pixels = 4; // Set module width
planetAuto.Save(Path.Combine(outputFolder, "PlanetAutoHeight.png"),
                BarCodeImageFormat.Png);

// RM4SCC barcode, automatic height
var rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4; // Set module width
rm4sccAuto.Save(Path.Combine(outputFolder, "RM4SCCAutoHeight.png"),
                BarCodeImageFormat.Png);
```

**Por que isso funciona:**  
* `EncodeTypes.Planet` e `EncodeTypes.RM4SCC` informam ao gerador qual simbologia usar.  
* `XDimension.Pixels` define a largura de um único módulo do código de barras; um valor de 4 px gera uma imagem nítida e legível.  
* Como `BarHeight` não está definido, a biblioteca calcula a altura ideal automaticamente.

## Etapa 4: Gerar códigos de barras com altura fixa de 100 pixels

Se o seu design requer uma altura de barra específica, você pode sobrescrever o cálculo automático:

```csharp
// Planet barcode, fixed 100‑pixel height
var planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetFixed.Parameters.Barcode.XDimension.Pixels = 4;      // Module width
planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;   // Fixed height
planetFixed.Save(Path.Combine(outputFolder, "PlanetHeight100.png"),
                 BarCodeImageFormat.Png);

// RM4SCC barcode, fixed 100‑pixel height
var rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;      // Module width
rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;   // Fixed height
rm4sccFixed.Save(Path.Combine(outputFolder, "RM4SCCHeight100.png"),
                 BarCodeImageFormat.Png);
```

**Por que você pode precisar de uma altura fixa:**  
Especificações de design para etiquetas de envio frequentemente determinam dimensões exatas das barras para garantir compatibilidade com leitores de código de barras. Definir `BarHeight.Pixels` garante uniformidade em todas as imagens geradas.

## Etapa 5: Verificar os arquivos exportados

Depois que o programa for executado, a pasta `Barcodes` conterá quatro arquivos PNG:

* `PlanetAutoHeight.png`
* `RM4SCCAutoHeight.png`
* `PlanetHeight100.png`
* `RM4SCCHeight100.png`

Abra qualquer um deles com um visualizador de imagens ou incorpore‑os em um PDF para confirmar que foram renderizados corretamente. Se um scanner não conseguir ler o código de barras, aumente o valor de `XDimension.Pixels` ou verifique novamente o comprimento da string de entrada.

```bash
# Example verification command (Linux/macOS)
file Barcodes/*.png
```

Você deverá ver uma saída semelhante a:

```
Barcodes/PlanetAutoHeight.png: PNG image data, 180 x 100, 8-bit/color RGBA, non-interlaced
```

## Perguntas frequentes e casos especiais

| Pergunta | Resposta |
|----------|----------|
| **Posso exportar para formatos diferentes de PNG?** | Sim. Substitua `BarCodeImageFormat.Png` por `Jpeg`, `Bmp`, `Gif` ou `Tiff`. |
| **E se meus dados contiverem caracteres não permitidos pela simbologia?** | O gerador lança `ArgumentException`. Valide a entrada ou troque para uma simbologia que suporte esse conjunto de caracteres. |
| **Como altero as cores de primeiro plano/fundo?** | Defina `Parameters.Barcode.ForeColor` e `Parameters.Barcode.BackColor` antes de chamar `Save`. |
| **Existe uma forma de gerar códigos de barras na memória ao invés de salvar em disco?** | Chame `GenerateBarCodeImage()` para obter um objeto `System.Drawing.Image`, então manipule ou faça streaming conforme necessário. |

## Dica de especialista: processamento em lote

Quando precisar criar muitos códigos de barras (por exemplo, para uma lista de correspondência), envolva a lógica de geração em um loop `foreach`:

```csharp
var values = new[] { "001122", "334455", "667788" };
int index = 0;

foreach (var value in values)
{
    var generator = new BarcodeGenerator(EncodeTypes.Planet, value);
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Save(Path.Combine(outputFolder, $"Planet_{index++}.png"),
                   BarCodeImageFormat.Png);
}
```

Esse padrão escala para milhares de códigos de barras mantendo o código conciso.

## Conclusão

Agora você sabe **como gerar imagens de código de barras** em C# e **como exportar arquivos de código de barras** como PNG usando Aspose.BarCode. O exemplo completo demonstra tanto a geração automática quanto a de altura fixa para as simbologias Planet e RM4SCC, oferecendo uma base sólida para qualquer projeto relacionado a códigos de barras.

**Próximos passos**

* Explore outras simbologias como Code128, QR ou DataMatrix.  
* Experimente a personalização de cores (`ForeColor`, `BackColor`).  
* Integre os PNGs gerados em faturas PDF ou etiquetas de envio usando uma biblioteca PDF.  

Feliz codificação, e que seus códigos de barras sejam lidos sem problemas!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)
- [Create GS1 Barcode Images in C# – How to Generate Barcode C# Quickly](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [how to generate barcode image with Aspose.BarCode in C#](/barcode/english/python-java/general/how-to-generate-barcode-image-with-aspose-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}