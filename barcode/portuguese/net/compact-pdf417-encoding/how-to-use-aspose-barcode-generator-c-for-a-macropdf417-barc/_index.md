---
category: general
date: 2026-10-05
description: O Aspose Barcode Generator C# permite adicionar dados macro e gerar códigos
  de barras PDF417 sem esforço. Aprenda passo a passo como adicionar metadados macro
  e criar uma imagem PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode generator c#
- how to add macro
- how to generate pdf417
language: pt
lastmod: 2026-10-05
og_description: O Aspose Barcode Generator C# mostra como adicionar metadados macro
  e gerar um código de barras PDF417 em poucas linhas de código.
og_image_alt: Screenshot of a MacroPdf417 barcode created with Aspose Barcode Generator
  C#
og_title: Gerador de Código de Barras Aspose C# – adicionar macro e gerar código de
  barras PDF417
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Aspose Barcode Generator C# lets you add macro data and generate PDF417
    barcodes effortlessly. Learn step‑by‑step how to add macro metadata and create
    a PDF417 image.
  headline: How to use Aspose Barcode Generator C# for a MacroPdf417 barcode
  type: TechArticle
tags:
- barcode
- csharp
- aspose
title: Como usar o Aspose Barcode Generator C# para um código de barras MacroPdf417
url: /pt/net/compact-pdf417-encoding/how-to-use-aspose-barcode-generator-c-for-a-macropdf417-barc/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como usar o Aspose Barcode Generator C# para um código de barras MacroPdf417

Se você precisa criar um código de barras MacroPdf417 em C#, **Aspose Barcode Generator C#** oferece uma API concisa que trata tanto da imagem do código de barras quanto dos metadados de macro necessários. Este tutorial mostra exatamente como adicionar informações de macro e gerar uma imagem de código de barras PDF417 em apenas alguns passos.

Você aprenderá a configurar parâmetros visuais, incorporar campos de macro como ID do arquivo e timestamp, e salvar o resultado como PNG. Nenhuma ferramenta externa é necessária — apenas a biblioteca Aspose.BarCode e um ambiente de desenvolvimento .NET.

## Pré-requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 ou superior instalado  
* Visual Studio 2022 (ou qualquer IDE para C#)  
* Uma cópia licenciada ou de avaliação do **Aspose.BarCode for .NET**  

O código funciona em Windows, Linux e macOS porque a biblioteca é independente de plataforma.

## Etapa 1: Instalar o pacote NuGet Aspose.BarCode

Abra seu projeto no Visual Studio e execute o seguinte comando no **Package Manager Console**:

```powershell
Install-Package Aspose.BarCode
```

Isso adiciona o assembly `Aspose.BarCode` e suas dependências ao seu projeto.

## Etapa 2: Criar a instância do gerador de código de barras

A primeira linha cria um objeto `BarcodeGenerator` para a simbologia **MacroPdf417** e fornece o texto que você deseja codificar.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

// Step 2: Initialise the generator with MacroPdf417 and the payload text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // subsequent configuration goes here
}
```

*Por que isso importa*: O valor `EncodeTypes.MacroPdf417` indica à biblioteca que campos relacionados a macro serão esperados, os quais você configurará na próxima etapa.

## Etapa 3: Definir a aparência visual

Você pode controlar o tamanho de cada módulo (o menor quadrado preto ou branco) e o número de colunas na matriz PDF417. Ajustar `XDimension` influencia a resolução geral da imagem.

```csharp
    // Step 3: Visual settings
    generator.Parameters.Barcode.XDimension.Pixels = 2;          // width of a single module
    generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol
```

Aumentar `Columns` reduz a altura do código de barras, enquanto um `XDimension` maior torna a imagem mais nítida em telas de alta DPI.

## Etapa 4: Adicionar metadados de macro (como adicionar macro)

MacroPdf417 requer vários campos adicionais que descrevem o arquivo de origem e sua segmentação. As propriedades a seguir mapeiam diretamente para as especificações de macro do PDF417:

```csharp
    // Step 4: Macro fields – how to add macro data
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;               // unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;                  // current segment number
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;              // total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";             // optional file name
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                // CCITT‑16 placeholder
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;              // size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2019, 11, 1);                                                   // creation timestamp
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";            // recipient identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";               // sender identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;                                                   // marks the last segment
```

*Por que esses campos*:  
* `MacroPdf417FileID` une todos os segmentos, garantindo que um scanner possa remontar o documento original.  
* `MacroPdf417SegmentID` e `MacroPdf417SegmentsCount` informam ao decodificador a ordem e o número total de partes.  
* `MacroPdf417FileSize` e `MacroPdf417Checksum` fornecem verificações de integridade, úteis para transferências de dados volumosas.

## Etapa 5: Salvar a imagem do código de barras (como gerar pdf417)

Por fim, grave o código de barras no disco. O método `Save` aceita um caminho de arquivo e um formato de imagem. PNG preserva as bordas nítidas do código de barras sem artefatos de compressão.

```csharp
    // Step 5: Save the generated barcode – how to generate pdf417 image
    generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

Quando o programa for executado, você encontrará **ExtPDF417Meta.png** na pasta de saída. Abrir a imagem exibirá um código de barras MacroPdf417 limpo, pronto para impressão ou incorporação em um PDF.

### Saída esperada

| Nome do arquivo     | Formato | Dimensões (aprox.) |
|---------------------|---------|--------------------|
| ExtPDF417Meta.png  | PNG     | 300 × 150 px (varia com `XDimension`) |

Escanear a imagem com um leitor compatível com PDF417 (por exemplo, ZXing, Aspose.BarCode for .NET) devolve o texto original **“Åspóse.Barcóde©”** juntamente com todos os campos de macro.

## Problemas comuns e como evitá‑los

| Problema | Por que acontece | Correção |
|----------|------------------|----------|
| **EncodeTypes incorreto** | Usar `EncodeTypes.Pdf417` em vez de `EncodeTypes.MacroPdf417` desabilita os campos de macro. | Sempre instancie o gerador com `EncodeTypes.MacroPdf417`. |
| **Campos de macro ausentes** | Alguns scanners ignoram o código de barras se os campos de macro exigidos forem omitidos. | Preencha ao menos `FileID`, `SegmentID`, `SegmentsCount` e `Terminator`. |
| **XDimension muito pequeno** | Um valor abaixo de 1 pixel pode gerar um código de barras ilegível em telas de baixa resolução. | Mantenha `XDimension` ≥ 2 pixels para a maioria dos cenários de tela e impressão. |
| **Erros no caminho do arquivo** | Fornecer um caminho relativo que não existe gera exceção. | Use `Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png")` ou um caminho absoluto. |

## Código‑fonte completo

Abaixo está o exemplo completo e executável que você pode copiar para um novo projeto de console.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with MacroPdf417 and the payload text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Visual appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns

                // Macro fields – how to add macro
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save the barcode – how to generate pdf417
                generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("MacroPdf417 barcode generated successfully.");
        }
    }
}
```

Execute o programa (`dotnet run`). Após a execução, o console exibirá uma mensagem de sucesso e o arquivo PNG aparecerá na pasta de saída do projeto.

## Próximos passos

* **Codificar dados maiores** – Aumente `Columns` ou ajuste `Rows` (via `Pdf417.Rows`) para acomodar mais caracteres.  
* **Incorporar em PDF** – Use Aspose.PDF para colocar o PNG gerado em um documento.  
* **Verificação de leitura** – Utilize `Aspose.BarCode.Reader` para decodificar o código de barras e confirmar programaticamente os campos de macro.  

Explorar esses tópicos aprofunda sua compreensão de **como gerar códigos de barras PDF417** com informações de macro enriquecidas e o prepara para casos de uso reais, como processamento em lote de documentos ou troca segura de dados.

---

*Feliz codificação! Se este guia foi útil, considere compartilhá‑lo com colegas ou dar uma estrela ao repositório Aspose.BarCode no GitHub.*

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas em seus próprios projetos.

- [Como criar código de barras macro PDF417 em C# usando Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Como gerar código de barras PDF417 em C# com Barcode Generator](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcode-generator/)
- [Exemplo Aspose barcode: gerar Macro PDF417 em C#](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}