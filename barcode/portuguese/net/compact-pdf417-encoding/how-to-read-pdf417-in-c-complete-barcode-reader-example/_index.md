---
category: general
date: 2026-07-21
description: Como ler o código de barras PDF417 em C# usando um exemplo conciso de
  leitor de códigos de barras. Aprenda rapidamente a ler o código de barras a partir
  de uma imagem com código passo a passo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read barcode from image
- c# barcode reader example
language: pt
lastmod: 2026-07-21
og_description: Como ler código de barras PDF417 em C# com um exemplo prático. Descubra
  como ler o código de barras a partir de uma imagem e integrar o exemplo de leitor
  de código de barras em C# instantaneamente.
og_image_alt: Screenshot of a C# console app printing PDF417 barcode details
og_title: Como Ler PDF417 em C# – Guia Completo do Leitor de Código de Barras
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: How to read PDF417 barcode in C# using a concise barcode reader example.
    Quickly learn how to read barcode from image with step‑by‑step code.
  headline: How to Read PDF417 in C# – Complete Barcode Reader Example
  type: TechArticle
- description: How to read PDF417 barcode in C# using a concise barcode reader example.
    Quickly learn how to read barcode from image with step‑by‑step code.
  name: How to Read PDF417 in C# – Complete Barcode Reader Example
  steps:
  - name: Why This Works
    text: '- **`DecodeType.MacroPdf417`** tells the reader to expect the extended
      Macro PDF417 format, which carries extra metadata (file ID, segment count, timestamps,
      etc.). - The **`Extended.Pdf417`** object is only populated for Macro PDF417
      barcodes, so accessing those properties is safe after the `ReadBa'
  - name: Multiple Barcodes in One Image
    text: Sometimes a single scan contains more than one PDF417 segment (think of
      a multi‑page document encoded across several symbols). The `foreach` loop already
      enumerates *all* detected barcodes, so you don’t need extra logic—just collect
      the segments and reassemble them later if required.
  - name: Missing Extended Data
    text: 'Not every PDF417 carries macro information. In that scenario `result.Extended.Pdf417`
      will be instantiated but its fields will be default values (zero, empty string,
      or `false`). You can guard against it like this:'
  - name: Performance Tips
    text: '- **Batch processing:** If you have a folder of images, wrap the `BarCodeReader`
      creation inside a loop that reuses the same instance with `barcodeReader.SetImage(imagePath)`.
      This reduces allocation overhead. - **Parallelism:** For large workloads, consider
      `Parallel.ForEach` on the file list, but '
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Como ler PDF417 em C# – Exemplo completo de leitor de código de barras
url: /pt/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Ler PDF417 em C# – Exemplo Completo de Leitor de Código de Barras

Já se perguntou **como ler PDF417** em um projeto .NET sem precisar vasculhar documentação interminável? Você não está sozinho. Seja escaneando carteiras de motorista, cartões de embarque ou etiquetas de inventário personalizadas, extrair esses dados de forma confiável é uma necessidade real.

Neste guia vamos percorrer um **exemplo de leitor de código de barras c#** que extrai todos os metadados Macro PDF417 de um único arquivo de imagem. Ao final, você terá um aplicativo console pronto‑para‑executar que **lê código de barras a partir de imagem** e imprime todos os campos estendidos que você possa precisar.

## O Que Você Precisa

- .NET 6.0 SDK ou superior (você também pode direcionar .NET Framework 4.7+ – o código funciona da mesma forma)
- Visual Studio 2022, VS Code ou qualquer editor C# de sua preferência
- O pacote NuGet **Aspose.BarCode for .NET** (a classe `BarCodeReader` vem desta biblioteca)
- Um arquivo de imagem que contenha um código de barras Macro PDF417 (para a demonstração usaremos `ExtPDF417Meta.png`)

> **Dica de especialista:** Se você não tem um exemplo de PDF417 à mão, a Aspose disponibiliza algumas imagens de teste em seu repositório no GitHub – basta baixar uma e colocá‑la na pasta do seu projeto.

## Etapa 1: Instalar a Biblioteca de Código de Barras

Abra um terminal na pasta do seu projeto e execute:

```bash
dotnet add package Aspose.BarCode
```

O pacote adiciona o `BarCodeReader`, o `DecodeType` e a propriedade `Extended` que usaremos mais adiante. Nenhuma configuração extra é necessária; a biblioteca funciona prontamente para a maioria dos formatos de imagem (PNG, JPEG, BMP, etc.).

## Etapa 2: Criar um Aplicativo Console Minimalista

Crie um novo projeto console caso ainda não tenha feito:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Substitua o `Program.cs` gerado pelo código abaixo. Observe como cada seção está comentada para que você possa seguir a lógica mesmo sendo novo no processamento de códigos de barras.

```csharp
using System;
using Aspose.BarCode;               // Core barcode classes
using Aspose.BarCode.BarCodeRecognition; // DecodeType enum

class Program
{
    static void Main()
    {
        // 👉 1️⃣  Point the reader at the image that holds the Macro PDF417 barcode.
        //    Replace the path with your own image location if needed.
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // The BarCodeReader is disposable – using a using‑statement guarantees resources are freed.
        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // 👉 2️⃣  Iterate over every barcode that the reader finds.
            //    Macro PDF417 can embed multiple segments, so we handle them all.
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
            {
                // Basic barcode info – always handy for logging.
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // 👉 3️⃣  Pull out the extended Macro PDF417 fields.
                //    These properties live under result.Extended.Pdf417.
                var macro = result.Extended.Pdf417;

                Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40)); // visual separator
            }
        }

        // Keep the console window open when debugging.
        Console.WriteLine("Done. Press any key to exit...");
        Console.ReadKey();
    }
}
```

### Por Que Isso Funciona

- **`DecodeType.MacroPdf417`** indica ao leitor que ele deve esperar o formato Macro PDF417 estendido, que carrega metadados adicionais (ID do arquivo, contagem de segmentos, timestamps, etc.).
- O objeto **`Extended.Pdf417`** só é preenchido para códigos de barras Macro PDF417, portanto acessar essas propriedades é seguro após a chamada `ReadBarCodes()`.
- Usar um bloco **`using`** garante que os manipuladores de arquivo sejam liberados, evitando problemas de bloqueio de arquivos no Windows.

## Etapa 3: Executar a Aplicação

Compile e execute:

```bash
dotnet run
```

Se a imagem contiver um código de barras Macro PDF417 válido, você deverá ver uma saída semelhante a:

```
CodeType: MacroPdf417
CodeText: 1234567890
Pdf417MacroFileID: 1
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: SampleDocument.pdf
Pdf417MacroChecksum: 0xABCD
Pdf417MacroFileSize: 102400
Pdf417MacroTimeStamp: 2024-03-15T10:23:45Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
Done. Press any key to exit...
```

Se nada for impresso, verifique se o caminho da imagem está correto e se o código de barras é realmente uma variante Macro PDF417. Um PDF417 regular (sem a extensão macro) ainda será decodificado, mas as propriedades `Extended` ficarão vazias.

## Tratamento de Casos Limites

### Vários Códigos de Barras em Uma Imagem

Às vezes, uma única digitalização contém mais de um segmento PDF417 (pense em um documento de várias páginas codificado em vários símbolos). O laço `foreach` já enumera *todos* os códigos de barras detectados, portanto você não precisa de lógica extra – basta coletar os segmentos e remontá‑los posteriormente, se necessário.

### Dados Estendidos Ausentes

Nem todo PDF417 transporta informações macro. Nesse caso, `result.Extended.Pdf417` será instanciado, mas seus campos terão valores padrão (zero, string vazia ou `false`). Você pode proteger seu código assim:

```csharp
if (macro.MacroPdf417FileID != 0)
{
    // Process macro data
}
else
{
    Console.WriteLine("No macro information present in this barcode.");
}
```

### Dicas de Performance

- **Processamento em lote:** Se você tem uma pasta de imagens, envolva a criação do `BarCodeReader` dentro de um loop que reutiliza a mesma instância com `barcodeReader.SetImage(imagePath)`. Isso reduz a sobrecarga de alocação.
- **Paralelismo:** Para cargas de trabalho grandes, considere `Parallel.ForEach` na lista de arquivos, mas lembre‑se de que o leitor Aspose é thread‑safe apenas quando cada thread usa sua própria instância de `BarCodeReader`.

## Listagem Completa do Código (Pronta para Copiar‑Colar)

A seguir está o programa inteiro novamente, pronto para ser colocado em `Program.cs`. Não são necessários arquivos extras além da imagem.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
            {
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                var macro = result.Extended.Pdf417;

                Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }

        Console.WriteLine("Done. Press any key to exit...");
        Console.ReadKey();
    }
}
```

## Recapitulando: Como Ler PDF417 em C# Rapidamente

- Instale **Aspose.BarCode** via NuGet.  
- Aponte um `BarCodeReader` para sua imagem com `DecodeType.MacroPdf417`.  
- Percorra `ReadBarCodes()` e extraia tanto os campos básicos quanto os estendidos.  
- Trate a ausência de dados macro de forma elegante e considere ajustes de performance para leituras em massa.

## Próximos Passos & Tópicos Relacionados

- **Read barcode from image** usando outros formatos (QR, DataMatrix) – basta trocar o enum `DecodeType`.  
- **Encode PDF417** com `BarCodeGenerator` se precisar criar códigos de barras programaticamente.  
- Explore **níveis de correção de erro** e como eles afetam a confiabilidade da leitura.  
- Integre essa lógica em uma API ASP.NET Core para expor a leitura de códigos de barras como um serviço web.

Sinta‑se à vontade para experimentar: altere a imagem, brinque com a flag `DecodeType` ou grave os dados macro em um banco de dados. O padrão central permanece o mesmo, e agora você tem um sólido **exemplo de leitor de código de barras c#** em sua caixa de ferramentas.

Bom código, e que seus scans estejam sempre limpos!


## O Que Você Deve Aprender a Seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui código completo e explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas em seus próprios projetos.

- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to create barcode quiet zone for Code 16K using Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}