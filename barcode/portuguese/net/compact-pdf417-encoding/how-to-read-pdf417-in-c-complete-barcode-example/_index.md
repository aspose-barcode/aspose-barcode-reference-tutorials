---
category: general
date: 2026-07-27
description: Como ler código de barras PDF417 em C# rapidamente. Aprenda a ler múltiplos
  códigos de barras, decodificar imagens e obter metadados Macro PDF417 em um exemplo
  completo de código de barras em C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- c# barcode example
- read barcode image c#
language: pt
lastmod: 2026-07-27
og_description: Como ler códigos de barras PDF417 em C# com este guia passo a passo.
  Decodifique imagens, manipule múltiplos códigos de barras e extraia metadados Macro
  PDF417 em um exemplo pronto para executar.
og_image_alt: Screenshot showing how to read PDF417 barcode using C# code
og_title: Como ler PDF417 em C# – Exemplo completo de código de barras
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  headline: How to Read PDF417 in C# – Complete Barcode Example
  type: TechArticle
- description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  name: How to Read PDF417 in C# – Complete Barcode Example
  steps:
  - name: Loads a barcode image from disk.
    text: Loads a barcode image from disk.
  - name: Decodes **PDF417** (including Macro PDF417) barcodes.
    text: Decodes **PDF417** (including Macro PDF417) barcodes.
  - name: Prints basic information such as code type and text.
    text: Prints basic information such as code type and text.
  - name: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
    text: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image-processing
- Aspose
title: Como ler PDF417 em C# – Exemplo completo de código de barras
url: /pt/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Ler PDF417 em C# – Exemplo Completo de Código de Barras

Já se perguntou **como ler o código de barras PDF417** em uma aplicação C# sem perder a cabeça? Você não está sozinho. Seja construindo um scanner logístico, um validador de ingressos ou apenas precisando extrair dados de um ID codificado em PDF417, o processo pode parecer um pouco misterioso no início.  

Neste tutorial vamos percorrer um **c# barcode example** que lê uma imagem PDF417, lida com **read multiple barcodes** se houver mais de um, e extrai todos os úteis metadados Macro PDF417 que você pode precisar.

## O Que Você Vai Construir

Ao final deste guia você terá um pequeno programa de console que:

1. Carrega uma imagem de código de barras do disco.  
2. Decodifica códigos de barras **PDF417** (incluindo Macro PDF417).  
3. Imprime informações básicas como tipo de código e texto.  
4. Exibe o conjunto completo de campos Macro PDF417 (file ID, segment ID, checksum, etc.).  

Sem serviços externos, apenas um único pacote NuGet e algumas linhas de C#.

## Pré-requisitos – O Que Você Precisa Antes de Começar

- **.NET 6.0** ou superior (o código também funciona no .NET Framework 4.6+).  
- Uma versão recente da biblioteca **Aspose.BarCode for .NET** – instale via NuGet (`Install-Package Aspose.BarCode`).  
- Um arquivo de imagem que contenha um código de barras PDF417 (o demo usa `ExtPDF417Meta.png`).  
- Um entendimento básico de aplicativos console em C# (se você já escreveu “Hello World”, está pronto).

> **Dica profissional:** Se você não tem uma amostra de PDF417 à mão, gere uma no site de demonstração da Aspose ou use um aplicativo de smartphone que crie tags PDF417.

## Etapa 1: Configurar o Projeto e Instalar a Biblioteca

Primeiro, crie um novo projeto console:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
dotnet add package Aspose.BarCode
```

Isso traz as dependências do **c# barcode example** que precisamos. Abra `Program.cs` e substitua o código padrão pelo esqueleto abaixo:

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
            // We'll fill this in in the next steps.
        }
    }
}
```

## Etapa 2: Inicializar o Leitor de Código de Barras para PDF417

O coração da solução é a classe `BarCodeReader`. Informamos a ela qual arquivo escanear e qual tipo de código de barras nos interessa — neste caso `DecodeType.Pdf417` ou a variante macro `DecodeType.MacroPdf417`. Usar o tipo macro garante que capturemos os campos estendidos.

```csharp
// Step 2: Create the reader, targeting Macro PDF417 barcodes
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(
           imagePath, DecodeType.MacroPdf417))
{
    // The rest of the logic lives inside this block.
}
```

Por que usar `MacroPdf417` em vez de apenas `Pdf417`? Macro PDF417 transporta metadados extras (file ID, contagem de segmentos, timestamps, etc.) que muitas aplicações do mundo real dependem — pense em manifestos de envio divididos em várias páginas.

## Etapa 3: Ler Todos os Códigos de Barras Encontrados na Imagem

Uma única imagem pode conter **read multiple barcodes** — talvez um QR code ao lado de um PDF417. O método `ReadBarCodes()` devolve um `IEnumerable<BarCodeResult>` que podemos percorrer.

```csharp
// Step 3: Iterate through every barcode detected
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Inside we’ll output both generic and macro‑specific data.
}
```

Se a imagem contiver apenas um PDF417, o laço ainda será executado uma vez, mantendo o código flexível para cenários futuros onde você possa precisar **read multiple barcodes** da mesma varredura.

## Etapa 4: Exibir Informações Básicas do Código de Barras

Antes de mergulhar nos campos macro, é útil mostrar o tipo de código de barras e o texto decodificado. Isso ajuda a verificar se o leitor realmente reconheceu um PDF417 e não outra simbologia.

```csharp
Console.WriteLine($"CodeType : {result.CodeTypeName}");
Console.WriteLine($"CodeText : {result.CodeText}");
```

A propriedade `CodeTypeName` exibirá *MacroPdf417* (ou *Pdf417* se a flag macro não estiver definida), enquanto `CodeText` contém os dados brutos codificados no código de barras.

## Etapa 5: Extrair Metadados Macro PDF417

A propriedade `Extended` oferece um mergulho profundo na estrutura específica do PDF417. Cada campo que imprimimos abaixo mapeia diretamente para a especificação macro do PDF417.

```csharp
// Step 5: Macro PDF417 metadata – all optional, but very handy
Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
```

Cada linha extrai uma parte diferente da carga macro:

- **FileID** – um identificador único para todo o conjunto de documentos.  
- **SegmentID** – qual parte do arquivo multissegmento você está visualizando.  
- **SegmentsCount** – número total de segmentos esperados.  
- **FileName, Checksum, FileSize** – úteis para validar a integridade do arquivo transferido.  
- **TimeStamp, Addressee, Sender** – campos opcionais que muitos sistemas logísticos incorporam.  

Se algum desses campos estiver ausente no código de barras de origem, a biblioteca retornará `null` ou `0`, que você pode tratar conforme necessário.

## Etapa 6: Executar o Exemplo Completo

Juntando tudo, aqui está o programa completo, pronto para ser executado:

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
            // Path to the image containing a Macro PDF417 barcode
            string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Initialize the reader for Macro PDF417 (covers both standard and macro)
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Loop through every barcode detected – handles read multiple barcodes gracefully
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // Basic info
                    Console.WriteLine($"CodeType : {result.CodeTypeName}");
                    Console.WriteLine($"CodeText : {result.CodeText}");

                    // Macro PDF417 specific metadata
                    Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding complete. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Saída Esperada

Ao executar o programa com um `ExtPDF417Meta.png` válido, você deverá ver algo semelhante a:

```
CodeType : MacroPdf417
CodeText : https://example.com/track?order=12345
Pdf417MacroFileID          : 101
Pdf417MacroSegmentID       : 1
Pdf417MacroSegmentsCount   : 3
Pdf417MacroFileName        : order_manifest.pdf
Pdf417MacroChecksum        : 0x1A2B3C4D
Pdf417MacroFileSize        : 45296
Pdf417MacroTimeStamp       : 2024-03-15T10:27:00Z
Pdf417MacroAddressee       : LogisticsDept
Pdf417MacroSender          : WarehouseA
MacroPdf417Terminator      : true
----------------------------------------
Decoding complete. Press any key to exit.
```

Se a imagem contiver mais de um código de barras,

## O Que Você Deve Aprender a Seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como Gerar Códigos de Barras PDF417 – Codificação Compacta PDF417](/barcode/english/net/compact-pdf417-encoding/)
- [Como Criar Código de Barras – PDF417 Compacto com Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Como Ler Códigos DataMatrix com Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}