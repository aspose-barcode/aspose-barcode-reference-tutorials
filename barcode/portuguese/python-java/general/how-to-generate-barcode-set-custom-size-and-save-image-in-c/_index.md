---
category: general
date: 2026-09-13
description: Aprenda a gerar códigos de barras em C#, personalizar o tamanho do código
  de barras e salvar a imagem do código de barras como PNG usando Aspose.BarCode.
  Guia completo passo a passo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- custom barcode size
- save barcode image
- Aspose.BarCode C#
- barcode image format
language: pt
lastmod: 2026-09-13
og_description: Como gerar código de barras em C# com tamanho personalizado e salvar
  a imagem do código de barras como PNG. Siga este guia completo para Aspose.BarCode.
og_image_alt: Screenshot of a DataBar stacked omnidirectional barcode generated in
  C#
og_title: Como gerar código de barras, definir tamanho personalizado e salvar a imagem
  em C#
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to generate barcode in C#, customize barcode size, and save
    barcode image as PNG using Aspose.BarCode. Complete step‑by‑step guide.
  headline: How to generate barcode set custom size and save image in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Como gerar um conjunto de códigos de barras de tamanho personalizado e salvar
  a imagem em C#
url: /pt/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como gerar códigos de barras com tamanho personalizado e salvar a imagem em C#

Se você precisa **gerar códigos de barras** em uma aplicação .NET, este tutorial mostra uma solução completa. Você verá como ajustar o **tamanho personalizado do código de barras** e **salvar a imagem do código de barras** com apenas algumas linhas de código C#.

Gerar códigos de barras é uma necessidade comum para sistemas de inventário, etiquetas de envio e aplicações de ponto de venda. Ao final deste guia você terá um programa executável que cria dois códigos de barras DataBar‑Stacked‑Omnidirectional, cada um com uma proporção diferente, e os grava em arquivos PNG no disco.

**Pré-requisitos**

- .NET 6.0 ou posterior (o código também funciona com .NET Framework 4.7+)
- Visual Studio 2022 ou qualquer IDE C#
- Aspose.BarCode for .NET (versão de avaliação gratuita ou pacote NuGet licenciado)

---

## Como gerar código de barras com Aspose.BarCode

A biblioteca Aspose.BarCode abstrai os detalhes de baixo nível dos padrões de códigos de barras, permitindo que você se concentre nos dados que deseja codificar e na aparência visual que precisa.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar stacked omnidirectional barcode generator
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GS1‑128 format example

        // 2️⃣ Set a basic module width – this influences the overall **custom barcode size**
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First aspect ratio (15) → save the image
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 15.");

        // 4️⃣ Change aspect ratio to 30 → **save barcode image** again
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 30.");
    }
}
```

### Por que cada linha importa

| Etapa | Explicação |
|------|-------------|
| **1️⃣ Criar um gerador** | O enum `EncodeTypes.DatabarStackedOmniDirectional` informa ao Aspose qual simbologia de código de barras usar. A string `"(01)12345678901231"` segue o formato de dados GS1‑128, onde `(01)` é o Identificador de Aplicação para um GTIN. |
| **2️⃣ Definir X‑dimension** | `XDimension.Pixels` define a largura de um único módulo do código de barras (a barra mais fina). Alterar esse valor é a principal forma de obter um **tamanho personalizado do código de barras** sem modificar os dados codificados. |
| **3️⃣ Definir proporção e salvar** | `DataBar.AspectRatio` controla a proporção altura‑largura dos símbolos DataBar. Uma proporção de 15 produz um código de barras relativamente curto e largo, enquanto 30 o torna mais alto. `Save` grava a representação visual em um arquivo PNG, atendendo ao requisito de **salvar a imagem do código de barras**. |
| **4️⃣ Alterar proporção e salvar novamente** | Reutilizar a mesma instância do gerador permite produzir várias imagens com diferentes características visuais mantendo os dados constantes. |

---

## Ajustando tamanho personalizado do código de barras além da X‑dimension

Embora `XDimension.Pixels` defina a largura do módulo, você também pode ajustar finamente as dimensões gerais do código de barras combinando duas propriedades:

1. **`BarHeight`** – altura explícita em pixels.  
2. **`BarWidth`** – largura explícita em pixels (substitui X‑dimension).

```csharp
// Example: make a larger, more readable barcode
generator.Parameters.Barcode.XDimension.Pixels = 4;      // wider modules
generator.Parameters.Barcode.BarHeight.Pixels = 120;    // taller bars
generator.Parameters.Barcode.DataBar.AspectRatio = 20; // balanced ratio
generator.Save("LargeCustomSize.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved large custom size barcode.");
```

> **Dica profissional:** Ao imprimir códigos de barras, sempre teste a imagem gerada no tamanho final de impressão. Uma largura de módulo de 2 px funciona para exibição na tela, mas etiquetas impressas geralmente precisam de pelo menos 4 px para permanecer escaneáveis.

---

## Escolhendo o formato de imagem correto para salvar o código de barras

Aspose.BarCode suporta PNG, JPEG, BMP, GIF e TIFF. PNG é sem perdas e preserva bordas nítidas, tornando‑se a escolha mais segura para a maioria das aplicações. Se precisar de um arquivo menor para uso na web, JPEG com qualidade 90 funciona bem, mas esteja ciente de que artefatos de compressão podem afetar a confiabilidade da leitura.

```csharp
generator.Save("DatabarAspectRatio15.jpg", BarCodeImageFormat.Jpeg, 90);
Console.WriteLine("Saved JPEG version with quality 90.");
```

---

## Exemplo completo e executável

Abaixo está um aplicativo de console autônomo que você pode copiar, colar e executar. Ele demonstra **como gerar código de barras**, modificar o **tamanho personalizado do código de barras** e **salvar a imagem do código de barras** em dois formatos diferentes.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with the desired symbology and data
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // ---- Custom size configuration ----
            generator.Parameters.Barcode.XDimension.Pixels = 2;      // module width
            generator.Parameters.Barcode.BarHeight.Pixels = 80;    // optional explicit height
            generator.Parameters.Barcode.DataBar.AspectRatio = 15; // first aspect ratio

            // Save first image as PNG
            string pngPath1 = "DatabarAspectRatio15.png";
            generator.Save(pngPath1, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath1}");

            // Change aspect ratio for a taller barcode
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string pngPath2 = "DatabarAspectRatio30.png";
            generator.Save(pngPath2, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath2}");

            // ---- Larger custom size example ----
            generator.Parameters.Barcode.XDimension.Pixels = 4;
            generator.Parameters.Barcode.BarHeight.Pixels = 120;
            generator.Parameters.Barcode.DataBar.AspectRatio = 20;
            string largePath = "LargeCustomSize.png";
            generator.Save(largePath, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {largePath}");

            // ---- Save as JPEG for web use ----
            string jpegPath = "DatabarAspectRatio15.jpg";
            generator.Save(jpegPath, BarCodeImageFormat.Jpeg, 90);
            Console.WriteLine($"Saved {jpegPath}");
        }
    }
}
```

**Saída esperada no console**

```
Saved DatabarAspectRatio15.png
Saved DatabarAspectRatio30.png
Saved LargeCustomSize.png
Saved DatabarAspectRatio15.jpg
```

Os quatro arquivos de imagem aparecerão no programa


## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como gerar códigos de barras DataMatrix usando Aspose.BarCode para .NET – Guia passo a passo](/barcode/english/net/datamatrix-barcode-configuration/)
- [Como gerar código de barras PDF417 com Aspose – Guia completo](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Como gerar código de barras Aztec com proporção personalizada usando Aspose.BarCode para .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}