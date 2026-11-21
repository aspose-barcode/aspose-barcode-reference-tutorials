---
category: general
date: 2026-11-20
description: Aprenda como gerar código de barras PDF417 em C# usando BarcodeGenerator.
  Este guia passo a passo cobre a dimensão X, as configurações de colunas e a exportação
  PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- PDF417 barcode in C#
- BarcodeGenerator EncodeTypes
- set XDimension pixels
- configure PDF417 columns
- save barcode as PNG
language: pt
lastmod: 2026-11-20
og_description: Gere código de barras PDF417 em C# rapidamente. Siga este guia para
  definir dimensões, colunas e exportar o código de barras como imagem PNG.
og_image_alt: Screenshot of C# code that generates a PDF417 barcode and saves it as
  a PNG file
og_title: Gerar código de barras PDF417 em C# – guia completo passo a passo
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to generate PDF417 barcode in C# using BarcodeGenerator.
    This step‑by‑step guide covers X‑Dimension, column settings, and PNG export.
  headline: How to generate PDF417 barcode in C# with BarcodeGenerator
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using BarcodeGenerator.
    This step‑by‑step guide covers X‑Dimension, column settings, and PNG export.
  name: How to generate PDF417 barcode in C# with BarcodeGenerator
  steps:
  - name: '**Initialize the generator** – The `BarcodeGenerator` ties the chosen symbology
      (`EncodeTypes.Pdf417`) to the data you want to encode. Without this object you
      cannot access any further configuration.'
    text: '**Initialize the generator** – The `BarcodeGenerator` ties the chosen symbology
      (`EncodeTypes.Pdf417`) to the data you want to encode. Without this object you
      cannot access any further configuration.'
  - name: '**Set X‑Dimension** – PDF417 is built from tiny rectangular modules. Changing
      `XDimension.Pixels` lets you control the barcode’s visual density, which is
      crucial for readability on low‑resolution displays or printers.'
    text: '**Set X‑Dimension** – PDF417 is built from tiny rectangular modules. Changing
      `XDimension.Pixels` lets you control the barcode’s visual density, which is
      crucial for readability on low‑resolution displays or printers.'
  - name: '**Configure columns** – PDF417 can arrange its codewords in a variable
      number of columns. Fewer columns produce a taller barcode, while more columns
      flatten it. Adjust this to fit the space where the image will be placed.'
    text: '**Configure columns** – PDF417 can arrange its codewords in a variable
      number of columns. Fewer columns produce a taller barcode, while more columns
      flatten it. Adjust this to fit the space where the image will be placed.'
  - name: '**Save as PNG** – PNG is a loss‑less format, preserving the sharp edges
      required for accurate scanning. You could also choose JPEG or BMP, but PNG is
      the safest default.'
    text: '**Save as PNG** – PNG is a loss‑less format, preserving the sharp edges
      required for accurate scanning. You could also choose JPEG or BMP, but PNG is
      the safest default.'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose.BarCode
title: Como gerar código de barras PDF417 em C# com BarcodeGenerator
url: /pt/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como gerar código de barras PDF417 em C# com BarcodeGenerator

Se você precisa **gerar código de barras PDF417** em uma aplicação .NET, este guia mostra exatamente como fazer isso. Você verá um exemplo completo e executável que define o X‑Dimension, escolhe o número de colunas e salva o resultado como uma imagem PNG.

Gerar um código de barras PDF417 é comum quando você precisa codificar muitos dados — como a carteira de motorista, o cartão de embarque ou um registro de inventário — em uma imagem compacta e legível por máquina. Neste tutorial usamos a classe **BarcodeGenerator** da biblioteca Aspose.BarCode, mas os conceitos se aplicam a qualquer biblioteca que suporte PDF417.

Ao final deste artigo você será capaz de:

* Inicializar um `BarcodeGenerator` para codificação PDF417.  
* Ajustar o tamanho do módulo com **set XDimension pixels**.  
* Controlar o layout usando **configure PDF417 columns**.  
* **Salvar código de barras como PNG** para uso em páginas web, aplicativos móveis ou material impresso.  

> **Pré-requisitos**  
> * .NET 6.0 ou superior (o código também funciona com .NET Framework 4.7+).  
> * Uma referência ao pacote NuGet **Aspose.BarCode** (`Install-Package Aspose.BarCode`).  
> * Familiaridade básica com C# e Visual Studio (ou qualquer IDE de sua preferência).

---

## Como gerar código de barras PDF417 em C#

O núcleo da solução é um processo curto de quatro etapas. Cada etapa está encapsulada em um método dedicado para que você possa reutilizar a lógica em projetos maiores.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialize the generator with the desired text
            var generator = CreateGenerator("Åspóse.Barcóde©");

            // 2️⃣ Adjust the X‑Dimension (module size)
            SetXDimension(generator, 2);

            // 3️⃣ Define how many columns the barcode should have
            SetPdf417Columns(generator, 3);

            // 4️⃣ Save the barcode as a PNG file
            SaveAsPng(generator, @"YOUR_DIRECTORY\Pdf417Basic.png");

            Console.WriteLine("PDF417 barcode generated successfully.");
        }

        // ---------------------------------------------------------
        // Step 1: Create a BarcodeGenerator for PDF417
        // ---------------------------------------------------------
        private static BarcodeGenerator CreateGenerator(string text)
        {
            // EncodeTypes.Pdf417 tells the library to use the PDF417 symbology.
            return new BarcodeGenerator(EncodeTypes.Pdf417, text);
        }

        // ---------------------------------------------------------
        // Step 2: Set the X‑Dimension (size of a single module)
        // ---------------------------------------------------------
        private static void SetXDimension(BarcodeGenerator generator, int pixels)
        {
            // XDimension controls the width of the smallest black/white bar.
            // A value of 2 pixels works well for most screen resolutions.
            generator.Parameters.Barcode.XDimension.Pixels = pixels;
        }

        // ---------------------------------------------------------
        // Step 3: Configure the number of columns in the PDF417 barcode
        // ---------------------------------------------------------
        private static void SetPdf417Columns(BarcodeGenerator generator, int columns)
        {
            // Columns affect the barcode’s aspect ratio.
            // Small numbers (e.g., 3) produce a tall barcode; larger numbers make it wider.
            generator.Parameters.Barcode.Pdf417.Columns = columns;
        }

        // ---------------------------------------------------------
        // Step 4: Export the barcode as a PNG image
        // ---------------------------------------------------------
        private static void SaveAsPng(BarcodeGenerator generator, string outputPath)
        {
            // BarCodeImageFormat.Png ensures lossless quality.
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }
    }
}
```

### Por que essas quatro etapas são importantes

1. **Initialize the generator** – O `BarcodeGenerator` vincula a simbologia escolhida (`EncodeTypes.Pdf417`) aos dados que você deseja codificar. Sem esse objeto você não pode acessar nenhuma configuração adicional.  
2. **Set X‑Dimension** – O PDF417 é construído a partir de pequenos módulos retangulares. Alterar `XDimension.Pixels` permite controlar a densidade visual do código de barras, o que é crucial para a legibilidade em telas ou impressoras de baixa resolução.  
3. **Configure columns** – O PDF417 pode organizar seus codewords em um número variável de colunas. Menos colunas produzem um código de barras mais alto, enquanto mais colunas o deixam mais achatado. Ajuste isso para caber no espaço onde a imagem será colocada.  
4. **Save as PNG** – PNG é um formato sem perdas, preservando as bordas nítidas necessárias para a leitura precisa. Você também pode escolher JPEG ou BMP, mas PNG é a opção padrão mais segura.  

---

## Configurar dimensões do código de barras (X‑Dimension)

A etapa **set XDimension pixels** influencia diretamente como os scanners interpretam o código de barras. Se o módulo for muito pequeno, câmeras de baixa qualidade podem perder barras individuais; se for muito grande, o código de barras pode ficar desnecessariamente grande.

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 2; // 2‑pixel modules
```

**Melhor prática:** Teste a imagem gerada no tamanho de impressão pretendido. Para impressão de alta densidade (300 dpi ou mais), um valor de `1` ou `2` funciona bem. Para exibição em tela a 96 dpi, `2`–`3` oferece uma visualização clara.

---

## Definir colunas PDF417

A etapa **configure PDF417 columns** permite que você decida a forma do código de barras.

```csharp
generator.Parameters.Barcode.Pdf417.Columns = 3; // three columns → tall barcode
```

### Quando mudar a contagem de colunas

| Colunas | Forma resultante | Caso de uso típico |
|---------|------------------|--------------------|
| 1–3     | Alta, estreita   | Etiquetas com largura limitada |
| 4–9     | Equilibrada      | Leitura de uso geral |
| 10+     | Larga, curta     | Sinalização grande ou gráficos web |

Se a carga de dados exceder a capacidade padrão, a biblioteca adiciona automaticamente linhas extras, mas você ainda pode influenciar a proporção ajustando a contagem de colunas.

---

## Exportar código de barras para PNG

Salvar o código de barras como uma imagem PNG é simples:

```csharp
generator.Save(@"C:\Barcodes\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**Por que PNG?**  
* A compressão sem perdas mantém as bordas nítidas necessárias para leitores de código de barras.  
* PNG suporta transparência, o que pode ser útil se você sobrepor o código de barras a um fundo colorido posteriormente.

Se você precisar de um formato diferente, substitua `BarCodeImageFormat.Png` por `Jpeg`, `Bmp` ou `Svg` — a API lida com a conversão automaticamente.

---

## Armadilhas comuns e solução de problemas

| Problema | Causa provável | Correção |
|----------|----------------|----------|
| Código de barras aparece borrado | X‑Dimension muito pequeno para a resolução de saída | Aumente `XDimension.Pixels` para 3 ou 4. |
| Scanner não consegue ler o código | Caracteres Unicode não suportados pela fonte escolhida | Garanta que a fonte da biblioteca suporte os caracteres, ou substitua-os por equivalentes ASCII. |
| Arquivo de saída não criado | Caminho inválido ou permissões de gravação ausentes | Use um caminho absoluto e verifique o acesso de gravação da pasta. |
| Muitas linhas, código de barras fica alto | Contagem de colunas muito baixa para o tamanho dos dados | Aumente `Pdf417.Columns` para um número maior (ex.: 6). |

---

## Recapitulação do exemplo completo

Abaixo está o **programa completo** que você pode copiar e colar em um novo projeto de console. Nenhum código adicional é necessário além das instruções `using` e do pacote Aspose.BarCode.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
            Console.WriteLine("PDF417 barcode generated and saved as PNG.");
        }
    }
}
```

**Saída esperada:** Um arquivo chamado `Pdf417Basic.png` contendo um código de barras PDF417 claro que codifica a string `Åspóse.Barcóde©`. Ao abrir, a imagem deve mostrar uma série de barras retangulares empilhadas com uma densidade maior no lado esquerdo (devido ao layout de três colunas).

---

## Conclusão

Agora você sabe como **gerar código de barras PDF417** em C# usando a classe `BarcodeGenerator`. O tutorial abordou a inicialização do gerador, **set XDimension pixels**, **configure PDF417 columns**, e **save barcode as PNG** — as etapas essenciais para qualquer fluxo de trabalho de código de barras pronto para produção.

A partir daqui você pode:

* Experimentar com diferentes `EncodeTypes` (ex.: QR, Code128).  
* Adicionar níveis de correção de erro via `generator.Parameters.Barcode.Pdf417.ErrorLevel`.  
* Renderizar o código de barras diretamente para um `MemoryStream` para APIs web.  

Sinta-se à vontade para adaptar o código ao seu próprio projeto e compartilhar seus resultados nos comentários ou no Stack Overflow usando a tag `#pdf417`. Feliz codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Gerar código de barras PDF417 como PNG em C# – guia passo a passo](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-as-png-in-c-step-by-step-guide/)
- [Como gerar código de barras PDF417 em C# – guia passo a passo](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [Como gerar código de barras PDF417 em C# com dimensões personalizadas](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}