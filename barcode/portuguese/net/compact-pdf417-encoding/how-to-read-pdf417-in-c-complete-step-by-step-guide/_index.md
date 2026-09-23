---
category: general
date: 2026-07-15
description: Como ler código de barras PDF417 em C# e ler vários códigos de barras
  de uma imagem. Aprenda a ler imagens de códigos de barras em C# com código detalhado
  e dicas.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- read barcode image c#
- Aspose.BarCode PDF417
- C# barcode decoding
language: pt
lastmod: 2026-07-15
og_description: Como ler código de barras PDF417 em C# rapidamente. Este guia mostra
  como ler vários códigos de barras de uma única imagem e decodificar cada propriedade.
og_image_alt: Screenshot of C# console output displaying PDF417 barcode details
og_title: Como ler PDF417 em C# – Exemplo completo de código e explicação
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: How to read PDF417 barcode in C# and read multiple barcodes from an
    image. Learn to read barcode image C# with detailed code and tips.
  headline: How to Read PDF417 in C# – Complete Step‑by‑Step Guide
  type: TechArticle
- description: How to read PDF417 barcode in C# and read multiple barcodes from an
    image. Learn to read barcode image C# with detailed code and tips.
  name: How to Read PDF417 in C# – Complete Step‑by‑Step Guide
  steps:
  - name: Why This Code Works
    text: '* **`BarCodeReader`** is the core class that streams the image, detects
      barcodes, and returns a collection of `BarCodeResult` objects. * Passing **`DecodeType.MacroPdf417`**
      tells the library to treat Macro‑PDF417 specially; it still returns plain PDF417
      symbols, which satisfies the **read multiple '
  - name: What if the image has both Macro‑PDF417 and regular PDF417 symbols?
    text: The same `BarCodeReader` call will return both. You can differentiate them
      by checking `result.CodeType` (`MacroPdf417` vs `Pdf417`). The extended properties
      will be `null` for a plain PDF417, so the `if (macro != null)` guard prevents
      a `NullReferenceException`.
  - name: My barcode is rotated or skewed—will the reader still work?
    text: Aspose.BarCode includes built‑in rotation and distortion compensation. As
      long as the barcode is at least 30 % of the image width, the decoder will usually
      succeed. For extreme cases you can enable `reader.Options.AllowInvertedBarcodes
      = true;` before calling `ReadBarCodes()`.
  - name: How do I handle large batches of images?
    text: Wrap the reading logic in a `foreach (var file in Directory.GetFiles(folder,
      "*.png"))` loop. The `using` pattern ensures each image’s native resources are
      freed before the next iteration, keeping memory usage low.
  type: HowTo
tags:
- C#
- barcode
- PDF417
- Aspose
title: Como ler PDF417 em C# – Guia completo passo a passo
url: /pt/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Ler PDF417 em C# – Guia Completo Passo a Passo

Já se perguntou **como ler PDF417** a partir de uma imagem usando C#? Você não está sozinho. A maioria dos desenvolvedores bate em um muro quando precisam extrair os campos estendidos Macro‑PDF417 de um documento escaneado. A boa notícia? Com apenas algumas linhas de código você pode decodificar um PDF417, ler vários códigos de barras na mesma imagem e capturar todas as propriedades ocultas que a especificação oferece.

Neste tutorial vamos percorrer um exemplo real que mostra **como ler PDF417**, como **ler múltiplos códigos de barras** de um único arquivo, e por que o código **read barcode image C#** tem a aparência que tem. Ao final, você terá um aplicativo console pronto para executar que imprime todas as informações que você possa precisar — ID do arquivo, ID do segmento, checksum, timestamps, o que for.

## Pré‑requisitos

Antes de mergulharmos, certifique‑se de que você tem:

* .NET 6.0 SDK ou superior (o código funciona também com .NET Core e .NET Framework).  
* Visual Studio 2022 (ou qualquer editor de sua preferência).  
* O pacote NuGet **Aspose.BarCode for .NET** – esta é a biblioteca que realmente analisa PDF417.  
* Uma imagem de exemplo que contenha um código de barras Macro‑PDF417 (por exemplo `ExtPDF417Meta.png`).  

Nenhuma configuração extra é necessária; a biblioteca já inclui todos os decodificadores que você precisa.

## Etapa 1: Instalar Aspose.BarCode

Abra a pasta do seu projeto em um terminal e execute:

```bash
dotnet add package Aspose.BarCode
```

Esse comando obtém a versão estável mais recente (em julho 2026 é a 23.12). Se preferir o Package Manager Console dentro do Visual Studio, use:

```powershell
Install-Package Aspose.BarCode
```

> **Dica profissional:** fixe a versão (`23.12.0`) no seu `.csproj` para evitar alterações inesperadas mais tarde.

## Etapa 2: Criar a Estrutura de um Aplicativo Console

Crie um novo projeto console caso ainda não tenha um:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Substitua o `Program.cs` gerado automaticamente pelo código abaixo. Explicaremos cada bloco nas próximas seções.

## Etapa 3: Escrever o Código Completo “Como Ler PDF417”

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -----------------------------------------------------------------
            // 1️⃣  Set the path to the image that contains one or more PDF417 codes
            // -----------------------------------------------------------------
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            // -----------------------------------------------------------------
            // 2️⃣  Initialise the BarCodeReader for MacroPdf417 decoding
            // -----------------------------------------------------------------
            // The DecodeType flag tells Aspose to look specifically for Macro‑PDF417,
            // but it will also pick up plain PDF417 symbols that happen to be in the
            // same image – perfect for the “read multiple barcodes” scenario.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // -----------------------------------------------------------------
                // 3️⃣  Iterate over every barcode found in the image
                // -----------------------------------------------------------------
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // -------------------------------------------------------------
                    // 4️⃣  Basic barcode information – works for any barcode type
                    // -------------------------------------------------------------
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // -------------------------------------------------------------
                    // 5️⃣  Macro‑PDF417 extended properties (the real reason you’re here)
                    // -------------------------------------------------------------
                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40)); // visual separator
                }
            }

            // -----------------------------------------------------------------
            // 6️⃣  Keep the console window open when running from VS
            // -----------------------------------------------------------------
            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

### Por Que Este Código Funciona

* **`BarCodeReader`** é a classe central que processa a imagem, detecta códigos de barras e devolve uma coleção de objetos `BarCodeResult`.  
* Passar **`DecodeType.MacroPdf417`** indica à biblioteca que deve tratar Macro‑PDF417 de forma especial; ela ainda devolve símbolos PDF417 simples, atendendo ao requisito de **read multiple barcodes**.  
* O objeto **`Extended.Pdf417.MacroPdf417`** contém todos os campos opcionais definidos pela norma ISO/IEC 15438 – é aqui que você obtém `FileID`, `SegmentID`, `Checksum`, etc.  
* O bloco `using` garante que os recursos nativos sejam liberados, evitando vazamentos de memória em serviços de longa execução.

## Etapa 4: Executar o Aplicativo e Verificar a Saída

No terminal:

```bash
dotnet run
```

Você deverá ver algo como:

```
Code Type : MacroPdf417
Code Text : 1234567890...
File ID          : 12
Segment ID       : 1
Segments Count   : 3
File Name        : invoice2024.pdf
Checksum         : 9A3F
File Size        : 245760
Time Stamp       : 2024-11-02T14:23:00Z
Addressee        : Acme Corp
Sender           : Logistics Dept
Terminator       : 1
----------------------------------------
Done. Press any key to exit...
```

Se a imagem contiver mais de um código de barras, o laço imprimirá uma linha separadora (`----------------------------------------`) e continuará com o próximo resultado — exatamente como o **read multiple barcodes** se comporta na prática.

## Perguntas Frequentes & Casos de Borda

### E se a imagem tiver símbolos Macro‑PDF417 e PDF417 normais?

A mesma chamada `BarCodeReader` retornará ambos. Você pode diferenciá‑los verificando `result.CodeType` (`MacroPdf417` vs `Pdf417`). As propriedades estendidas serão `null` para um PDF417 simples, portanto a verificação `if (macro != null)` impede um `NullReferenceException`.

### Meu código de barras está rotacionado ou inclinado — o leitor ainda funciona?

Aspose.BarCode inclui compensação de rotação e distorção embutida. Desde que o código de barras ocupe pelo menos 30 % da largura da imagem, o decodificador geralmente tem sucesso. Para casos extremos, você pode habilitar `reader.Options.AllowInvertedBarcodes = true;` antes de chamar `ReadBarCodes()`.

### Como lidar com grandes lotes de imagens?

Envolva a lógica de leitura em um laço `foreach (var file in Directory.GetFiles(folder, "*.png"))`. O padrão `using` garante que os recursos nativos de cada imagem sejam liberados antes da próxima iteração, mantendo o uso de memória baixo.

## Listagem Completa do Código (Pronta para Copiar e Colar)

A seguir está o programa inteiro em um único bloco para cópia rápida. Sem dependências ocultas — apenas o pacote NuGet Aspose.BarCode.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

## Recapitulação – O Que Cobremos

* **Como ler PDF417** usando Aspose.BarCode em C#.  
* Os passos exatos para **read multiple barcodes** a partir de uma única imagem.  
* Como **read barcode image C#** e extrair cada campo Macro‑PDF417.  
* Dicas para rotação, processamento em lote e tratamento de dados estendidos ausentes.

## Próximos Passos & Tópicos Relacionados

* **Encode PDF417** – gere seus próprios códigos de barras Macro‑PDF417 com `BarCodeBuilder`.  
* **Read other 2‑D symbologies** – QR, DataMatrix, Aztec – usando a mesma classe `BarCodeReader`.  
* **Integrate with ASP.NET Core** – exponha um endpoint web que aceita uma imagem enviada e devolve JSON com os campos decodificados.  

Sinta‑se à vontade para experimentar: altere o caminho da imagem, coloque um PDF417 simples na mesma pasta ou ajuste as flags `DecodeType` para ver como a biblioteca se comporta. Quanto mais você brincar, mais confortável ficará com cenários de **read barcode image C#**.

Tem uma imagem complicada que se recusa a ser decodificada? Deixe um comentário abaixo ou abra uma issue no repositório GitHub do projeto de exemplo. Boa codificação!

## O Que Você Deve Aprender a Seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas em seus próprios projetos.

- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Read DataMatrix barcode C# – Generate DataMatrix Mode (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}