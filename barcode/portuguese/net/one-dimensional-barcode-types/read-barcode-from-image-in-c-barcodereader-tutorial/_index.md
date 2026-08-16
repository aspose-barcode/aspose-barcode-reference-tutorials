---
category: general
date: 2026-08-15
description: Leia código de barras a partir de imagem em C# usando BarCodeReader.
  Aprenda como ler vários códigos de barras em C#, ler código de barras PDF417 e veja
  um exemplo completo de BarCodeReader em C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image
- read multiple barcodes c#
- how to read pdf417 barcode
- c# barcodereader example
language: pt
lastmod: 2026-08-15
og_description: Leia códigos de barras a partir de imagem em C# com um guia passo
  a passo. Descubra como ler múltiplos códigos de barras em C#, decodificar símbolos
  PDF417 e executar um exemplo completo do BarCodeReader em C#.
og_image_alt: Screenshot of C# code that reads barcode from image using BarCodeReader
og_title: Ler código de barras de imagem em C# – tutorial BarCodeReader
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Read barcode from image in C# using BarCodeReader. Learn how to read
    multiple barcodes C#, read PDF417 barcode, and see a full C# BarCodeReader example.
  headline: Read barcode from image in C# – BarCodeReader tutorial
  type: TechArticle
tags:
- barcode
- C#
- .NET
- image processing
title: Ler código de barras de imagem em C# – tutorial BarCodeReader
url: /pt/net/one-dimensional-barcode-types/read-barcode-from-image-in-c-barcodereader-tutorial/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ler código de barras a partir de imagem em C# – tutorial BarCodeReader

Se você precisa **ler código de barras a partir de imagem** em uma aplicação .NET, este guia mostra exatamente como fazer isso com a classe `BarCodeReader`. Você também verá como **ler vários códigos de barras C#**, decodificar um símbolo PDF417 e obter um **exemplo completo de C# BarCodeReader** que pode ser copiado para o seu projeto.

O tutorial cobre cada passo — desde a adição do pacote NuGet necessário até a impressão dos campos estendidos do PDF417 — para que você termine com um programa de console executável. Nenhuma documentação externa é necessária; todo o código e explicações estão incluídos.

## O que você precisará

Antes de começar, certifique‑se de que tem:

* .NET 6.0 SDK ou posterior (o código funciona com .NET Core e .NET Framework)
* Visual Studio 2022 ou qualquer editor compatível com C#
* O pacote NuGet `Aspose.BarCode` (ou a biblioteca equivalente que fornece `BarCodeReader`)
* Um arquivo de imagem que contenha um código de barras Macro PDF417 (por exemplo, `ExtPDF417Meta.png`)

Ter esses pré‑requisitos garante que o exemplo compile sem configuração adicional.

## Ler código de barras a partir de imagem com BarCodeReader

O primeiro passo é criar uma instância de `BarCodeReader` que aponte para o arquivo de imagem e indique à biblioteca qual tipo de código de barras procurar.

```csharp
using System;
using Aspose.BarCode;               // Namespace for BarCodeReader
using Aspose.BarCode.BarCodeRecognition; // DecodeType enum

class Program
{
    static void Main()
    {
        // Path to the image that holds the Macro PDF417 barcode
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417 barcodes only
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Read all barcodes present in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Basic barcode information
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");

                // Extended Macro PDF417 fields (available only for this type)
                Console.WriteLine($"File ID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Segment ID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"File Name        : {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Checksum         : {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"File Size        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Time Stamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee        : {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Sender           : {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"Terminator Flag  : {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**Por que isso funciona:**  
`BarCodeReader` abre a imagem, escaneia o `DecodeType` especificado e devolve uma coleção de objetos `BarCodeResult`. Cada resultado contém os dados genéricos do código de barras (`CodeTypeName`, `CodeText`) e, para Macro PDF417, um objeto `Extended.Pdf417` que expõe todos os campos adicionais definidos pelo padrão.

## Ler vários códigos de barras C# em uma única imagem

Às vezes, uma imagem contém mais de um código de barras (por exemplo, um QR code ao lado de um PDF417). Para lidar com esse cenário, basta omitir o `DecodeType` explícito ou passar `DecodeType.AllSupported` e percorrer os resultados.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Found {result.CodeTypeName}: {result.CodeText}");
    }
}
```

**Por que você precisa disso:**  
Especificar `AllSupported` indica ao motor que ele deve tentar todos os formatos de código de barras que conhece, o que garante que você capture cada símbolo na imagem. Essa é a abordagem recomendada quando não é possível prever os tipos de código de barras com antecedência.

## Como ler código de barras PDF417 usando C#

Se você se interessa apenas pelo formato clássico PDF417 (não‑macro), altere o `DecodeType` para `Pdf417`. O restante do código permanece idêntico, exceto que os campos estendidos não estarão disponíveis.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"PDF417 text: {result.CodeText}");
    }
}
```

**Por que isso importa:**  
O PDF417 clássico não expõe as propriedades específicas de macro, portanto o bloco `Extended.Pdf417` é desnecessário. Usar o `DecodeType` preciso também acelera a varredura, pois a biblioteca ignora algoritmos não suportados.

## Exemplo completo de C# BarCodeReader que você pode copiar

Abaixo está o programa completo que combina os três cenários em uma única aplicação de console fácil de executar. Substitua `YOUR_DIRECTORY/ExtPDF417Meta.png` pelo caminho real da sua imagem.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 1️⃣ Read Macro PDF417 and show extended fields
        Console.WriteLine("=== Macro PDF417 ===");
        ReadMacroPdf417(imagePath);

        // 2️⃣ Read any barcode type present (multiple barcodes)
        Console.WriteLine("\n=== All supported barcodes ===");
        ReadAllBarcodes(imagePath);

        // 3️⃣ Read classic PDF417 only
        Console.WriteLine("\n=== Classic PDF417 ===");
        ReadClassicPdf417(imagePath);
    }

    static void ReadMacroPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.MacroPdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");
                Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
                // ... other extended fields omitted for brevity
                Console.WriteLine(new string('-', 30));
            }
        }
    }

    static void ReadAllBarcodes(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.AllSupported))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"{result.CodeTypeName}: {result.CodeText}");
            }
        }
    }

    static void ReadClassicPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.Pdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"PDF417 text: {result.CodeText}");
            }
        }
    }
}
```

### Saída esperada

Quando a imagem de exemplo contém um código de barras Macro PDF417, o console imprime algo semelhante a:

```
=== Macro PDF417 ===
Code Type : MacroPdf417
Code Text : 1234567890
File ID   : 5
Segment ID       : 2
Segments Count   : 3
File Name        : report.pdf
Checksum         : 0x1A2B
File Size        : 84212
Time Stamp       : 2024-03-15T10:22:31Z
Addressee        : John Doe
Sender           : Acme Corp
Terminator Flag  : True
------------------------------

=== All supported barcodes ===
MacroPdf417: 1234567890
QrCode: https://example.com

=== Classic PDF417 ===
PDF417 text: 0987654321
```

Se a imagem contiver apenas um PDF417 regular, a seção “Macro PDF417” ficará vazia, e a seção “Classic PDF417” exibirá o texto decodificado.

## Conclusão

Agora você sabe como **ler código de barras a partir de imagem** em C# usando `BarCodeReader`, como **ler vários códigos de barras C#** em um único arquivo, e os passos exatos para **ler código de barras PDF417** — tanto nas variantes macro quanto clássica. O **exemplo completo de C# BarCodeReader** está pronto para ser colado em qualquer projeto .NET, e você pode estendê‑lo para lidar com outros formatos ou integrá‑lo a um pipeline maior de processamento de imagens.

**Próximos passos**

* Explore padrões de tratamento de erros, como `try / catch`, ao redor do bloco do leitor.  
* Experimente o objeto `ReaderParameters` para ajustar a velocidade e a precisão da detecção.  
* Combine a leitura de códigos de barras com bibliotecas de pré‑processamento de imagens (

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código totalmente funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Como ler códigos de barras DataMatrix com Aspose.BarCode para .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Ler código de barras DataMatrix C# – Gerar modo DataMatrix (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Ler código de barras a partir de imagem – Dominando a extração de região de código de barras em Java com Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}