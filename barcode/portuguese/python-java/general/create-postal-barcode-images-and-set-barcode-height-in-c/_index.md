---
category: general
date: 2026-09-07
description: Crie imagens de códigos de barras postais em C# e aprenda como alterar
  a altura do código de barras com um exemplo conciso de gerador de códigos de barras
  – tutorial C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode images
- barcode generator example c#
- change barcode height
language: pt
lastmod: 2026-09-07
og_description: Crie imagens de códigos de barras postais em C# e descubra a maneira
  mais fácil de alterar a altura do código de barras usando um exemplo claro de gerador
  de códigos de barras em C#.
og_image_alt: Screenshot showing created postal barcode images with custom height
og_title: Criar imagens de código de barras postal – definir altura do código de barras
  em C#
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Create postal barcode images in C# and learn how to change barcode
    height with a concise barcode generator example C# tutorial.
  headline: Create postal barcode images and set barcode height in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Criar imagens de código de barras postal e definir a altura do código de barras
  em C#
url: /pt/python-java/general/create-postal-barcode-images-and-set-barcode-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar imagens de código de barras postal e definir a altura do código de barras em C#

Se você precisar **criar imagens de código de barras postal** para aplicações de envio, este guia mostra uma solução completa, pronta‑para‑executar. Você verá um **exemplo de gerador de código de barras C#** que produz códigos de barras Planet e RM4SCC e aprenderá como **alterar a altura do código de barras** sem sair do código.

O tutorial cobre tudo o que você precisa para começar a gerar códigos de barras postais imediatamente: pacotes NuGet necessários, preparação de pastas, geração com altura padrão, personalização de altura fixa e armadilhas comuns a evitar.

## Pré-requisitos

- .NET 6.0 SDK ou posterior instalado  
- Visual Studio 2022 (ou qualquer IDE C#)  
- O pacote NuGet **Aspose.BarCode** (`Install-Package Aspose.BarCode`)  

Esses componentes dão acesso à classe `BarcodeGenerator` usada ao longo dos exemplos.

## Etapa 1: Preparar a pasta de saída

O gerador grava arquivos PNG no disco, portanto a pasta deve existir e ser gravável.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Define where the barcode images will be saved
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

// Ensure the directory exists
Directory.CreateDirectory(outputFolder);
Console.WriteLine($"Images will be saved to: {outputFolder}");
```

*Por que isso importa*: Tentar salvar em um caminho inexistente lança uma `DirectoryNotFoundException`. `Directory.CreateDirectory` é seguro porque não faz nada se a pasta já existir.

## Etapa 2: Gerar códigos de barras Planet e RM4SCC com altura padrão

Quando você omite a propriedade `BarHeight`, a biblioteca escolhe automaticamente uma altura ideal (modo automático). Isso é útil para protótipos rápidos.

```csharp
// Planet barcode – auto height
var planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456")
{
    // Set module width (X dimension) to 4 pixels for readability
    Parameters = { Barcode = { XDimension = { Pixels = 4 } } }
};
planetAuto.Save(Path.Combine(outputFolder, "PostalPlanetBarHeightAuto.png"),
                BarCodeImageFormat.Png);

// RM4SCC barcode – auto height
var rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
{
    Parameters = { Barcode = { XDimension = { Pixels = 4 } } }
};
rm4sccAuto.Save(Path.Combine(outputFolder, "PostalRM4SCCBarHeightAuto.png"),
                BarCodeImageFormat.Png);
```

**Resultado**: Dois arquivos PNG aparecem em `Barcodes/` com a altura de barra escolhida pela biblioteca.

## Etapa 3: Definir uma altura de barra explícita (100 pixels)

Às vezes, as especificações de envio exigem uma altura de barra fixa. Você pode controlá‑la via a propriedade `BarHeight.Pixels`.

```csharp
// Planet barcode – fixed 100‑pixel height
var planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456")
{
    Parameters = {
        Barcode = {
            XDimension = { Pixels = 4 },   // module width
            BarHeight = { Pixels = 100 }   // explicit height
        }
    }
};
planetFixed.Save(Path.Combine(outputFolder, "PostalPlanetBarHeight100.png"),
                 BarCodeImageFormat.Png);

// RM4SCC barcode – fixed 100‑pixel height
var rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
{
    Parameters = {
        Barcode = {
            XDimension = { Pixels = 4 },
            BarHeight = { Pixels = 100 }
        }
    }
};
rm4sccFixed.Save(Path.Combine(outputFolder, "PostalRM4SCCBarHeight100.png"),
                 BarCodeImageFormat.Png);
```

**Por que você pode precisar disso**: Os serviços postais frequentemente definem uma altura mínima de barra para confiabilidade de leitura. Definir uma altura fixa garante conformidade em todas as imagens geradas.

## Etapa 4: Verificar as imagens geradas

Você pode abrir os arquivos PNG com qualquer visualizador de imagens. A diferença visual está no comprimento da barra:

- **Arquivos de altura automática**: a altura da barra se adapta ao comprimento dos dados.
- **Arquivos de altura fixa**: as barras têm exatamente 100 pixels de altura, independentemente do conteúdo.

Se precisar confirmar programaticamente a altura, você pode carregar a imagem com `System.Drawing` e inspecionar `Bitmap.Height`.

```csharp
using System.Drawing;

void PrintBarHeight(string filePath)
{
    using var bmp = new Bitmap(filePath);
    Console.WriteLine($"{Path.GetFileName(filePath)} – Height: {bmp.Height}px");
}

PrintBarHeight(Path.Combine(outputFolder, "PostalPlanetBarHeightAuto.png"));
PrintBarHeight(Path.Combine(outputFolder, "PostalPlanetBarHeight100.png"));
```

## Dica profissional: Ajustar DPI para impressões de alta resolução

Quando o código de barras será impresso em uma impressora de etiquetas, você pode desejar uma configuração de DPI mais alta. A propriedade `Resolution` permite controlá‑la sem alterar as dimensões em pixels.

```csharp
planetFixed.Parameters.Resolution = 300; // 300 dpi for crisp prints
planetFixed.Save(Path.Combine(outputFolder, "Planet_300dpi.png"),
                 BarCodeImageFormat.Png);
```

## Armadilhas comuns e como evitá‑las

| Problema | Causa | Correção |
|----------|-------|----------|
| **Imagem não criada** | Pasta de saída ausente ou sem permissão de gravação | Chamar `Directory.CreateDirectory` e executar o aplicativo com privilégios suficientes |
| **Código de barras ilegível** | Dimensão X muito pequena (ex.: 1 pixel) | Use pelo menos 2 pixels; 4 pixels funciona bem para a maioria dos scanners |
| **Tipo de código de barras incorreto** | Valor `EncodeTypes` errado | Verifique a especificação postal (Planet vs. RM4SCC) e use o enum correspondente |

## Código-fonte completo (pronto para copiar)

```csharp
using System;
using System.IO;
using System.Drawing;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class PostalBarcodeDemo
{
    static void Main()
    {
        // -------------------------------------------------
        // Step 1 – Prepare output folder
        // -------------------------------------------------
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);
        Console.WriteLine($"Saving images to: {outputFolder}");

        // -------------------------------------------------
        // Step 2 – Auto‑height barcodes
        // -------------------------------------------------
        var planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456")
        {
            Parameters = { Barcode = { XDimension = { Pixels = 4 } } }
        };
        planetAuto.Save(Path.Combine(outputFolder, "PostalPlanetBarHeightAuto.png"),
                        BarCodeImageFormat.Png);

        var rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
        {
            Parameters = { Barcode = { XDimension = { Pixels = 4 } } }
        };
        rm4sccAuto.Save(Path.Combine(outputFolder, "PostalRM4SCCBarHeightAuto.png"),
                        BarCodeImageFormat.Png);

        // -------------------------------------------------
        // Step 3 – Fixed 100‑pixel height barcodes
        // -------------------------------------------------
        var planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456")
        {
            Parameters = {
                Barcode = {
                    XDimension = { Pixels = 4 },
                    BarHeight = { Pixels = 100 }
                }
            }
        };
        planetFixed.Save(Path.Combine(outputFolder, "PostalPlanetBarHeight100.png"),
                         BarCodeImageFormat.Png);

        var rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
        {
            Parameters = {
                Barcode = {
                    XDimension = { Pixels = 4 },
                    BarHeight = { Pixels = 100 }
                }
            }
        };
        rm4sccFixed.Save(Path.Combine(outputFolder, "PostalRM4SCCBarHeight100.png"),
                         BarCodeImageFormat.Png);

        // -------------------------------------------------
        // Step 4 – Verify heights (optional)
        // -------------------------------------------------
        PrintBarHeight(Path.Combine(outputFolder, "PostalPlanetBarHeightAuto.png"));
        PrintBarHeight(Path.Combine(outputFolder, "PostalPlanetBarHeight100.png"));
    }

    static void PrintBarHeight(string filePath)
    {
        using var bmp = new Bitmap(filePath);
        Console.WriteLine($"{Path.GetFileName(filePath)} – Height: {bmp.Height}px");
    }
}
```

Executar o programa cria quatro arquivos PNG:

- `PostalPlanetBarHeightAuto.png`
- `PostalRM4SCCBarHeightAuto.png`
- `PostalPlanetBarHeight100.png`
- `PostalRM4SCCBarHeight100.png`

Cada

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Criar Código de Barras Postal em C# – Exemplo Completo do Gerador](/barcode/english/python-java/general/create-postal-barcode-in-c-full-generator-example/)
- [.net barcode generator – alterar altura do código de barras](/barcode/english/python-java/general/net-barcode-generator-change-barcode-height/)
- [Criar Código de Barras com Altura Personalizada – Códigos de Barras Unidimensionais](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}