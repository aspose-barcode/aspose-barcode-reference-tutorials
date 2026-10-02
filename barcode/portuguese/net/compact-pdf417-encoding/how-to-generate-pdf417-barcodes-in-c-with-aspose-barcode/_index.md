---
category: general
date: 2026-09-10
description: Como gerar códigos de barras PDF417 em C# usando Aspose.BarCode. Siga
  um guia passo a passo para criar Macro PDF417, ajustar parâmetros e exportar como
  PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417
- macro pdf417 barcode
- aspose.barcode for .net
- c# barcode generator
- pdf417 barcode parameters
- barcode image export
language: pt
lastmod: 2026-09-10
og_description: Como gerar códigos de barras PDF417 em C# com Aspose.BarCode. Aprenda
  todo o fluxo de trabalho, desde a configuração até salvar uma imagem PNG Macro PDF417.
og_image_alt: Screenshot of a generated Macro PDF417 barcode saved as a PNG file
og_title: Como gerar códigos de barras PDF417 em C# – guia completo do Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: How to generate PDF417 barcodes in C# using Aspose.BarCode. Follow
    a step‑by‑step guide to create Macro PDF417, adjust parameters, and export as
    PNG.
  headline: How to generate PDF417 barcodes in C# with Aspose.BarCode
  type: TechArticle
- description: How to generate PDF417 barcodes in C# using Aspose.BarCode. Follow
    a step‑by‑step guide to create Macro PDF417, adjust parameters, and export as
    PNG.
  name: How to generate PDF417 barcodes in C# with Aspose.BarCode
  steps:
  - name: '**Create a Macro PDF417 generator** – `EncodeTypes.MacroPdf417` tells Aspose.BarCode
      to use the macro version of PDF417, which supports splitting a large payload
      across multiple symbols.'
    text: '**Create a Macro PDF417 generator** – `EncodeTypes.MacroPdf417` tells Aspose.BarCode
      to use the macro version of PDF417, which supports splitting a large payload
      across multiple symbols.'
  - name: '**Adjust basic appearance** – `XDimension` controls the module (dot) width;
      `Columns` defines how many columns each symbol will contain, influencing both
      size and readability.'
    text: '**Adjust basic appearance** – `XDimension` controls the module (dot) width;
      `Columns` defines how many columns each symbol will contain, influencing both
      size and readability.'
  - name: '**Set macro‑specific fields** – These properties (`MacroPdf417FileID`,
      `MacroPdf417SegmentID`, etc.) are required by the PDF417 macro specification
      to re‑assemble the original data on the scanner side.'
    text: '**Set macro‑specific fields** – These properties (`MacroPdf417FileID`,
      `MacroPdf417SegmentID`, etc.) are required by the PDF417 macro specification
      to re‑assemble the original data on the scanner side.'
  - name: '**Export the image** – `BarCodeImageFormat.Png` provides a lossless image
      that works well for web, print, and mobile scenarios.'
    text: '**Export the image** – `BarCodeImageFormat.Png` provides a lossless image
      that works well for web, print, and mobile scenarios.'
  - name: '**Visual verification** – Open `MacroPdf417.png` in any image viewer. You
      should see a stacked set of vertical bars with a small text caption (the encoded
      data).'
    text: '**Visual verification** – Open `MacroPdf417.png` in any image viewer. You
      should see a stacked set of vertical bars with a small text caption (the encoded
      data).'
  - name: '**Scanner test** – Use a mobile barcode scanner app that supports PDF417.
      Scan the image; the app should return the original “Sample text” plus macro
      metadata (file ID, segment ID, etc.).'
    text: '**Scanner test** – Use a mobile barcode scanner app that supports PDF417.
      Scan the image; the app should return the original “Sample text” plus macro
      metadata (file ID, segment ID, etc.).'
  - name: '**Error handling** – If the scanner reports “checksum error,” double‑check
      `MacroPdf417Checksum` and ensure the `MacroPdf417Terminator` is set correctly
      on the last segment.'
    text: '**Error handling** – If the scanner reports “checksum error,” double‑check
      `MacroPdf417Checksum` and ensure the `MacroPdf417Terminator` is set correctly
      on the last segment.'
  - name: '**Performance** – Generating many segments in a loop can be CPU‑intensive.
      Re‑use a single `BarcodeGenerator` instance and only update the macro fields
      between saves to improve throughput.'
    text: '**Performance** – Generating many segments in a loop can be CPU‑intensive.
      Re‑use a single `BarcodeGenerator` instance and only update the macro fields
      between saves to improve throughput.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- aspose
title: Como gerar códigos de barras PDF417 em C# com Aspose.BarCode
url: /pt/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como gerar códigos de barras PDF417 em C# com Aspose.BarCode

Se você precisa **como gerar pdf417** em um projeto .NET, este tutorial mostra o fluxo de trabalho completo. Você verá como criar um código de barras Macro PDF417, ajustar suas configurações e exportar o resultado como uma imagem PNG — tudo com Aspose.BarCode para .NET.

Gerar códigos de barras PDF417 é comum em logística, bilhetagem e fluxos de trabalho de documentos seguros. Ao final deste guia você terá um gerador de código de barras C# pronto para uso que pode ser inserido em qualquer aplicação.

## O que você precisará

- **Visual Studio 2022** (ou qualquer IDE C#)  
- **.NET 6.0** ou posterior  
- **Aspose.BarCode for .NET** pacote NuGet (`Install-Package Aspose.BarCode`)  
- Familiaridade básica com a sintaxe C#  

> **Dica profissional:** Use a versão mais recente do Aspose.BarCode para obter os recursos mais novos do Macro PDF417 e correções de bugs.

---

## Como gerar códigos de barras PDF417 em C#

Abaixo está um exemplo totalmente executável que cria um código de barras **Macro PDF417**, configura seus campos específicos de macro e salva a imagem.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // STEP 1 – create a Macro PDF417 generator with the desired text
        using (BarcodeGenerator generator =
               new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
        {
            // STEP 2 – adjust basic barcode appearance
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
            generator.Parameters.Barcode.Pdf417.Columns = 5;     // number of columns

            // STEP 3 – configure Macro PDF417 specific fields
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp =
                new DateTime(2023, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // STEP 4 – save the generated barcode as a PNG image
            generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
        }

        Console.WriteLine("Macro PDF417 barcode generated: MacroPdf417.png");
    }
}
```

### Por que cada passo importa

1. **Create a Macro PDF417 generator** – `EncodeTypes.MacroPdf417` tells Aspose.BarCode to use the macro version of PDF417, which supports splitting a large payload across multiple symbols.  
2. **Adjust basic appearance** – `XDimension` controls the module (dot) width; `Columns` defines how many columns each symbol will contain, influencing both size and readability.  
3. **Set macro‑specific fields** – These properties (`MacroPdf417FileID`, `MacroPdf417SegmentID`, etc.) are required by the PDF417 macro specification to re‑assemble the original data on the scanner side.  
4. **Export the image** – `BarCodeImageFormat.Png` provides a lossless image that works well for web, print, and mobile scenarios.

---

## Configurando Aspose.BarCode para .NET (gerador de código de barras C#)

Antes de executar o código acima, você deve adicionar a biblioteca Aspose.BarCode ao seu projeto:

```bash
dotnet add package Aspose.BarCode
```

*O pacote NuGet inclui todas as dependências, portanto nenhum DLL adicional é necessário.*  
Se você direcionar o .NET Framework, o mesmo comando `Install-Package Aspose.BarCode` funciona a partir do Console do Gerenciador de Pacotes.

### Armadilhas comuns

- **Missing license** – By default Aspose runs in evaluation mode, which adds a watermark to the barcode. Register a license file (`License license = new License(); license.SetLicense("Aspose.BarCode.lic");`) to remove it.  
- **Incorrect `EncodeTypes`** – Using `EncodeTypes.Pdf417` instead of `EncodeTypes.MacroPdf417` will ignore all macro fields, breaking multi‑segment reconstruction.

---

## Configurando parâmetros do código de barras Macro PDF417

Os campos de macro permitem dividir um documento grande em vários símbolos PDF417. Aqui está uma referência rápida:

| Propriedade | Propósito | Faixa típica |
|-------------|-----------|--------------|
| `MacroPdf417FileID` | Identificador único para o arquivo completo | 0‑2³¹‑1 |
| `MacroPdf417SegmentID` | Índice do segmento atual (começa em 0) | 0‑254 |
| `MacroPdf417SegmentsCount` | Número total de segmentos no arquivo | 1‑255 |
| `MacroPdf417FileName` | Nome legível por humanos (opcional) | 0‑255 characters |
| `MacroPdf417Checksum` | Checksum CCITT‑16 para detecção de erros | 0‑65535 |
| `MacroPdf417FileSize` | Tamanho original do arquivo em bytes | 0‑2³¹‑1 |
| `MacroPdf417TimeStamp` | Timestamp de criação (opcional) | `DateTime` value |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Metadados opcionais para roteamento | Any string |
| `MacroPdf417Terminator` | Indica o segmento final (`Set` ou `Unset`) | `Pdf417MacroTerminator` enum |

Ajuste esses valores para corresponder aos dados que você está codificando. Por exemplo, se você dividir um arquivo de 2 MB em 20 segmentos, defina `MacroPdf417FileSize` como `2_000_000` e `MacroPdf417SegmentsCount` como `20`.

---

## Exportando o código de barras como imagem PNG (exportação de imagem de código de barras)

Salvar o código de barras como PNG é o formato de exportação mais comum porque preserva bordas nítidas e suporta transparência. Aspose.BarCode também suporta JPEG, BMP, GIF e TIFF — escolha o que se adapta ao seu processo posterior.

```csharp
generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
```

**Dicas para saída de alta qualidade**

- Increase `XDimension.Pixels` for larger modules when printing on high‑resolution media.  
- Use `BarCodeImageFormat.Tiff` with CCITT Group 4 compression for fax‑compatible PDFs.  
- Set `generator.Parameters.ImageOptions.Resolution` if you need a specific DPI (e.g., 300 dpi for print).

---

## Testando e solucionando problemas do seu código de barras PDF417

1. **Visual verification** – Open `MacroPdf417.png` in any image viewer. You should see a stacked set of vertical bars with a small text caption (the encoded data).  
2. **Scanner test** – Use a mobile barcode scanner app that supports PDF417. Scan the image; the app should return the original “Sample text” plus macro metadata (file ID, segment ID, etc.).  
3. **Error handling** – If the scanner reports “checksum error,” double‑check `MacroPdf417Checksum` and ensure the `MacroPdf417Terminator` is set correctly on the last segment.  
4. **Performance** – Generating many segments in a loop can be CPU‑intensive. Re‑use a single `BarcodeGenerator` instance and only update the macro fields between saves to improve throughput.

---

## Conclusão

Você agora sabe **como gerar PDF417** códigos de barras em C# usando Aspose.BarCode, desde a instalação da biblioteca até a configuração dos campos Macro PDF417 e a exportação de uma imagem PNG limpa. A solução completa demonstra:

- Configurando um **gerador de código de barras C#** com o tipo Macro PDF417  
- Personalizando **parâmetros do código de barras PDF417** para dados multi‑segmento  
- Realizando **exportação de imagem de código de barras** para uso posterior  

A partir daqui você pode explorar tópicos avançados como incorporar o código de barras em documentos PDF, gerar companheiros QR‑code ou automatizar o processamento em lote de arquivos grandes.

**Próximos passos**

- Experimente valores diferentes de `BarCodeImageFormat` (por exemplo, `Tiff` para impressões de alta resolução).  
- Combine Macro PDF417 com outras simbologias no mesmo documento usando `generator.Parameters.Barcode.Symbology`.  
- Revise a [documentação do Aspose.BarCode](https://docs.aspose.com/barcode/net/) para opções de personalização mais avançadas, como nível de correção de erros e modos de codificação.

Happy coding!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Gerar código de barras com texto – Guia completo Macro PDF417](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)
- [Ajustar tamanho do código de barras – Guia C# para gerar códigos de barras PDF417](/barcode/english/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [Como gerar código de barras PDF417 – Guia completo de programação](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}