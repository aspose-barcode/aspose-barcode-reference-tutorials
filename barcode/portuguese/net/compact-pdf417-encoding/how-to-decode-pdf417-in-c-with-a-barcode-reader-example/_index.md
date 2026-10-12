---
category: general
date: 2026-09-19
description: Como decodificar PDF417 em C# – aprenda a ler códigos de barras a partir
  de imagens usando um exemplo conciso de leitor de códigos de barras que extrai os
  dados completos do Macro PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read barcodes from image
- decode pdf417 barcode
- c# barcode reader example
language: pt
lastmod: 2026-09-19
og_description: Como decodificar PDF417 em C# com um exemplo de leitor de código de
  barras passo a passo. Extraia todos os campos Macro PDF417 de uma imagem em segundos.
og_image_alt: Screenshot showing how to decode PDF417 in C# using a barcode reader
og_title: Como decodificar PDF417 em C# – guia completo de leitor de código de barras
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to decode PDF417 in C# – learn to read barcodes from image using
    a concise barcode reader example that extracts full Macro PDF417 data.
  headline: How to decode PDF417 in C# with a barcode reader example
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: Como decodificar PDF417 em C# com um exemplo de leitor de código de barras
url: /pt/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como decodificar PDF417 em C# com um exemplo de leitor de código de barras

Se você precisa decodificar PDF417 em C#, este guia mostra exatamente como decodificar PDF417 a partir de um arquivo de imagem. Você aprenderá a ler códigos de barras de imagens, acessar os campos estendidos Macro PDF417 e integrar a solução em qualquer projeto .NET.

A decodificação de códigos de barras PDF417 é comum em logística, bilhetagem e verificação de identidade. Este tutorial cobre tudo o que é necessário para uma implementação pronta para produção, incluindo bibliotecas pré‑requisitos, código‑fonte completo e dicas para lidar com casos de borda.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

- .NET 6.0 ou superior instalado  
- Visual Studio 2022 (ou qualquer IDE que suporte C#)  
- O pacote NuGet **Aspose.BarCode for .NET** (versão 23.11 ou mais recente)  

Você pode adicionar o pacote com o seguinte comando:

```bash
dotnet add package Aspose.BarCode
```

A classe `BarCodeReader` desta biblioteca suporta o tipo de decodificação `MacroPdf417` necessário para a extração completa do PDF417.

## Etapa 1: Como decodificar PDF417 em C# – inicializar o leitor

A primeira etapa cria uma instância de `BarCodeReader` que aponta para uma imagem Macro PDF417. O sinalizador `DecodeType.MacroPdf417` indica à biblioteca que ela deve analisar os campos Macro estendidos.

```csharp
using System;
using Aspose.BarCode;               // Core barcode classes
using Aspose.BarCode.BarCodeRecognition; // Reader and result types

// Path to the Macro PDF417 image
string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

// Initialise the reader for Macro PDF417 decoding
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Continue with step 2...
```

**Por que isso importa:** Inicializar com `MacroPdf417` habilita a propriedade `Extended.Pdf417` em cada `BarCodeResult`, dando acesso a metadados de nível de arquivo, como IDs de segmento e timestamps.

## Etapa 2: Ler códigos de barras da imagem

Uma imagem PDF417 pode conter vários segmentos macro. O método `ReadBarCodes()` devolve um enumerável com todos os códigos de barras detectados, permitindo que você itere sobre eles com segurança.

```csharp
    // Step 2: Read every barcode present in the image
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        // Continue with step 3...
```

**Dica:** Se você espera apenas um único código de barras, pode interromper o loop após a primeira iteração, mas percorrer todos os resultados garante que você capture cada segmento em documentos de várias páginas.

## Etapa 3: Decodificar código de barras PDF417 – extrair dados básicos e estendidos

Dentro do loop, exiba tanto as informações genéricas do código de barras quanto os campos específicos do Macro. O objeto `Extended.Pdf417` contém cada pedaço de metadado definido pelo padrão PDF417.

```csharp
        // Basic barcode information
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");

        // Macro PDF417 extended data
        Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
        Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
        Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
        Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
        Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
        Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
        Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
        Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
    }
}
```

**Explicação dos campos principais**

| Campo | Significado |
|-------|-------------|
| `MacroPdf417FileID` | Identificador que agrupa todos os segmentos pertencentes ao mesmo arquivo lógico |
| `MacroPdf417SegmentID` | Índice do segmento atual (começa em 0) |
| `MacroPdf417SegmentsCount` | Número total de segmentos esperados para o arquivo |
| `MacroPdf417FileName` | Nome de arquivo opcional embutido no macro |
| `MacroPdf417Checksum` | Checksum CRC‑16 para integridade dos dados |
| `MacroPdf417FileSize` | Tamanho original do arquivo em bytes |
| `MacroPdf417TimeStamp` | Timestamp de quando o macro foi gerado |
| `MacroPdf417Addressee` | Destinatário pretendido dos dados do macro |
| `MacroPdf417Sender` | Originador dos dados do macro |
| `MacroPdf417Terminator` | Flag booleano que indica o segmento final |

Ter acesso a esses campos permite reconstruir o documento original, verificar a integridade ou rotear os dados com base nas informações de remetente/destinatário.

## Etapa 4: Exemplo completo de leitor de código de barras em C# – juntando tudo

Abaixo está o programa completo e executável. Substitua `YOUR_DIRECTORY` pela pasta que contém seu arquivo `MacroPdf417.png`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417Decoder
{
    class Program
    {
        static void Main()
        {
            // Path to the image containing a Macro PDF417 barcode
            string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            // Initialise the reader for Macro PDF417 decoding
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Iterate through all detected barcodes
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // Basic information
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // Extended Macro PDF417 data
                    Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding complete.");
        }
    }
}
```

**Saída esperada no console (exemplo)**

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 452312
Pdf417MacroTimeStamp: 2024-03-15T14:27:00Z
Pdf417MacroAddressee: LogisticsDept
Pdf417MacroSender: Warehouse01
MacroPdf417Terminator: False
----------------------------------------
Decoding complete.
```

Os valores exatos variarão de acordo com o conteúdo do seu código de barras Macro PDF417.

## Lidando com casos de borda comuns

| Situação | Abordagem recomendada |
|----------|-----------------------|
| **Nenhum código de barras detectado** | Verifique o caminho da imagem, assegure‑se de que o arquivo não está corrompido e confirme que o código de barras está visível (contraste adequado). |
| **Segmentos macro parciais** | Use `MacroPdf417SegmentsCount` para detectar partes ausentes. Você pode solicitar os segmentos restantes ao sistema de origem e executar novamente o decodificador. |
| **Imagens grandes causando pressão de memória** | Carregue a imagem em um `System.Drawing.Bitmap` com resolução reduzida antes de passá‑la ao `BarCodeReader`. |
| **PDF417 não‑Macro** | Altere `DecodeType.MacroPdf417` para `DecodeType.Pdf417` se você precisar apenas do texto simples do código de barras. |

## Dicas avançadas

- **Processamento em lote:** Envolva a lógica do leitor em um método que aceita uma lista de caminhos de arquivos. Reutilize uma única instância de `BarCodeReader` por thread para reduzir a sobrecarga de alocação.  
- **Desempenho:** Para cenários de alta taxa de transferência, habilite a propriedade `ReaderOptions` `ReadQuality` para equilibrar velocidade e precisão.  
- **Segurança:** Valide `CodeText` antes de usá‑lo em operações de sistema de arquivos para prevenir ataques de traversal de caminho.

## Conclusão

Neste tutorial você aprendeu como decodificar PDF417 em C# lendo códigos de barras de imagens, extraindo todos os campos Macro PDF417 e construindo um exemplo completo de leitor de código de barras em C#. A solução funciona com a versão mais recente da biblioteca Aspose.BarCode, trata macros de múltiplos segmentos e oferece orientações práticas para projetos do mundo real.

Em seguida, explore tópicos relacionados como **leitura de QR codes**, **processamento em lote de códigos de barras** e **geração de códigos de barras PDF417** para ampliar seu conjunto de ferramentas de automação de documentos. Sinta‑se à vontade para experimentar diferentes fontes de imagem, integrar o código em serviços ASP.NET ou estendê‑lo para armazenar os metadados extraídos em um banco de dados. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [How to Read PDF417 in C# – Complete Barcode Reader Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Read barcode from image – C# barcode reader example](/barcode/english/net/one-dimensional-barcode-types/read-barcode-from-image-c-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}