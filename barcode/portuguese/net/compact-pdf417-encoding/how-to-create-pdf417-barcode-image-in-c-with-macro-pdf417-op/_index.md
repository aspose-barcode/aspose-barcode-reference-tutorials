---
category: general
date: 2026-09-13
description: Aprenda a criar imagem de código de barras PDF417 em C# usando BarcodeGenerator
  e opções Macro PDF417. Código passo a passo, dicas e exemplo completo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode image
- macro PDF417 options
- BarcodeGenerator class
- C# barcode generation
- barcode image format
language: pt
lastmod: 2026-09-13
og_description: Crie a imagem de código de barras PDF417 em C# com BarcodeGenerator.
  Siga este tutorial detalhado para configurar as opções Macro PDF417 e salvar um
  código de barras PNG.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: Criar imagem de código de barras PDF417 em C# – guia completo
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to create PDF417 barcode image in C# using BarcodeGenerator
    and Macro PDF417 options. Step‑by‑step code, tips, and full example.
  headline: How to create PDF417 barcode image in C# with Macro PDF417 options
  type: TechArticle
- description: Learn how to create PDF417 barcode image in C# using BarcodeGenerator
    and Macro PDF417 options. Step‑by‑step code, tips, and full example.
  name: How to create PDF417 barcode image in C# with Macro PDF417 options
  steps:
  - name: '**Create the generator** – instantiate `BarcodeGenerator` with `EncodeTypes.MacroPdf417`
      and the data you want to encode.'
    text: '**Create the generator** – instantiate `BarcodeGenerator` with `EncodeTypes.MacroPdf417`
      and the data you want to encode.'
  - name: '**Define the module size** – set `XDimension.Pixels` to control the physical
      width of each barcode element.'
    text: '**Define the module size** – set `XDimension.Pixels` to control the physical
      width of each barcode element.'
  - name: '**Configure Macro PDF417 options** – specify columns, file identifiers,
      segment numbers, and optional checksum.'
    text: '**Configure Macro PDF417 options** – specify columns, file identifiers,
      segment numbers, and optional checksum.'
  - name: '**Save the barcode** – write the generated image to disk using a supported
      **barcode image format** such as PNG.'
    text: '**Save the barcode** – write the generated image to disk using a supported
      **barcode image format** such as PNG.'
  - name: Create a new .NET 6 (or later) console project.
    text: Create a new .NET 6 (or later) console project.
  - name: Add the Aspose.BarCode NuGet package (`dotnet add package Aspose.BarCode`).
    text: Add the Aspose.BarCode NuGet package (`dotnet add package Aspose.BarCode`).
  - name: Replace the generated `Program.cs` with the code above.
    text: Replace the generated `Program.cs` with the code above.
  - name: Adjust `outputPath` to a folder you have write access to.
    text: Adjust `outputPath` to a folder you have write access to.
  - name: Build and run – the console will confirm the image location.
    text: Build and run – the console will confirm the image location.
  type: HowTo
tags:
- PDF417
- C#
- Barcode
title: Como criar imagem de código de barras PDF417 em C# com opções Macro PDF417
url: /pt/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar imagem de código de barras PDF417 em C# com opções Macro PDF417

Se você precisa **criar imagem de código de barras PDF417** em C#, este guia mostra exatamente como fazer isso usando a **classe BarcodeGenerator**. Seja construindo um sistema de rastreamento de documentos ou codificando arquivos grandes, as instruções passo a passo abaixo cobrem tudo, desde a configuração das opções Macro PDF417 até a gravação do PNG final.

Gerar um código de barras é simples depois que você entende os parâmetros principais. Neste tutorial você aprenderá a:

* Inicializar um `BarcodeGenerator` para **Macro PDF417**.  
* Ajustar o tamanho do módulo do código de barras (`XDimension`).  
* Configurar definições específicas de segmento, como ID do arquivo, ID do segmento e checksum.  
* Salvar o resultado como um **formato de imagem de código de barras** (PNG) que pode ser exibido em qualquer UI.

O único pré‑requisito é um ambiente de desenvolvimento .NET (Visual Studio 2022 ou posterior) e o pacote NuGet Aspose.BarCode for .NET, que fornece a API `BarcodeGenerator` usada nos exemplos.

---

## Visão geral de como criar imagem de código de barras PDF417 em C#

Criar uma imagem de código de barras PDF417 consiste em quatro etapas lógicas:

1. **Criar o gerador** – instanciar `BarcodeGenerator` com `EncodeTypes.MacroPdf417` e os dados que você deseja codificar.  
2. **Definir o tamanho do módulo** – definir `XDimension.Pixels` para controlar a largura física de cada elemento do código de barras.  
3. **Configurar opções Macro PDF417** – especificar colunas, identificadores de arquivo, números de segmento e checksum opcional.  
4. **Salvar o código de barras** – gravar a imagem gerada no disco usando um **formato de imagem de código de barras** suportado, como PNG.

Cada etapa é explicada em detalhe abaixo, com código C# completo e executável.

---

## Etapa 1: Inicializar o BarcodeGenerator para Macro PDF417

A primeira linha cria um objeto `BarcodeGenerator` que sabe que deve produzir um código de barras **Macro PDF417**. O construtor recebe dois argumentos: o tipo de codificação e a string de dados bruta.

```csharp
using Aspose.BarCode.Generation;   // NuGet: Aspose.BarCode
using System.Drawing.Imaging;      // For ImageFormat if you prefer System.Drawing

// Step 1 – create a barcode generator for Macro PDF417
using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample data"))
{
    // Subsequent configuration goes here
}
```

**Por que isso importa:**  
`EncodeTypes.MacroPdf417` indica à biblioteca que o código de barras deve ser tratado como um contêiner de múltiplos segmentos, essencial quando você precisa dividir um arquivo grande em vários símbolos. A instância `BarcodeGenerator` é descartável, portanto o bloco `using` garante que todos os recursos não gerenciados sejam liberados após a imagem ser salva.

---

## Etapa 2: Definir o tamanho do módulo do código de barras (XDimension)

`XDimension` controla a largura em pixels de um único módulo do código de barras (a menor barra preta ou branca). Um valor de **2 pixels** gera uma imagem compacta, porém legível.

```csharp
    // Step 2 – define the size of each barcode module (pixel width)
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Dica prática:**  
Se a sua impressora alvo tem DPI baixo, aumente a contagem de pixels (por exemplo, `3` ou `4`) para evitar borrões. Por outro lado, para exibição em tela você pode mantê‑la baixa para reduzir o tamanho do arquivo.

---

## Etapa 3: Configurar opções específicas do Macro PDF417

Macro PDF417 adiciona metadados que permitem a um scanner reconstruir o arquivo original a partir de múltiplos segmentos de código de barras. As opções mais comuns são:

| Propriedade | Significado |
|-------------|-------------|
| `Columns` | Número de colunas em cada símbolo (afeta a largura). |
| `MacroPdf417FileID` | Identificador único para todo o arquivo. |
| `MacroPdf417SegmentID` | Índice do segmento atual (começa em 1). |
| `MacroPdf417SegmentsCount` | Total de segmentos que compõem o arquivo. |
| `MacroPdf417FileName` | Nome original do arquivo (opcional, para exibição). |
| `MacroPdf417Checksum` | Checksum opcional de 16 bits para verificação de integridade. |

```csharp
    // Step 3 – configure Macro PDF417 specific options
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns in the symbol
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "report.pdf"; // Original file name
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;    // Optional checksum
```

**Por que essas configurações são importantes:**  
- **Columns** afeta a legibilidade e as dimensões gerais da imagem.  
- **FileID** deve ser o mesmo em todos os segmentos para que o decodificador saiba que eles pertencem ao mesmo conjunto.  
- **SegmentID** e **SegmentsCount** permitem que o scanner ordene as partes corretamente.  
- **FileName** e **Checksum** são opcionais, mas melhoram a experiência do usuário e a integridade dos dados.

**Caso extremo:** Se você gerar mais de 999 segmentos, o campo `SegmentID` estoura; divida os dados em vários arquivos em vez disso.

---

## Etapa 4: Salvar o código de barras gerado como imagem PNG

A etapa final grava o código de barras no disco. `BarCodeImageFormat.Png` produz uma imagem sem perdas que funciona em plataformas web, desktop e mobile.

```csharp
    // Step 4 – save the generated barcode as a PNG image
    barcodeGenerator.Save("YOUR_DIRECTORY/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

**Formatos alternativos:**  
Você pode substituir `BarCodeImageFormat.Png` por `Jpeg`, `Bmp` ou `Gif` se o seu sistema downstream exigir um formato específico. Lembre‑se de que JPEG introduz artefatos de compressão que podem reduzir a confiabilidade da leitura.

**Saída esperada:**  
O arquivo `MacroPdf417.png` conterá um código de barras PDF417 de múltiplos segmentos, de alto contraste. Ao abri‑lo, ele deve se assemelhar à ilustração abaixo.

![Create PDF417 barcode image example](image.png){: .align-center alt="Create PDF417 barcode image example generated by C# code"}

---

## Código‑fonte completo – pronto para copiar e executar

A seguir está o programa completo, autocontido. Ele inclui as diretivas `using` necessárias, o método `Main` e comentários que explicam cada linha não óbvia.

```csharp
using System;
using Aspose.BarCode.Generation;   // Install-Package Aspose.BarCode
// No other external dependencies are required.

namespace Pdf417BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Data to encode – can be any UTF‑8 string up to 1,800 characters.
            const string dataToEncode = "Sample data";

            // Output directory – change this to a valid path on your machine.
            const string outputPath = @"C:\Barcodes\MacroPdf417.png";

            // Create a BarcodeGenerator for Macro PDF417.
            using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, dataToEncode))
            {
                // 1️⃣ Define module size (pixel width of each bar).
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // 2️⃣ Configure Macro PDF417 options.
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "report.pdf";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;

                // 3️⃣ Save the barcode as a PNG image.
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
            }

            Console.WriteLine($"PDF417 barcode image created at: {outputPath}");
        }
    }
}
```

**Executando o programa:**  

1. Crie um novo projeto console .NET 6 (ou posterior).  
2. Adicione o pacote NuGet Aspose.BarCode (`dotnet add package Aspose.BarCode`).  
3. Substitua o `Program.cs` gerado pelo código acima.  
4. Ajuste `outputPath` para uma pasta onde você tenha permissão de gravação.  
5. Compile e execute – o console confirmará a localização da imagem.

---

## Perguntas comuns e solução de problemas

| Pergunta | Resposta |
|----------|----------|
| *E se o código de barras ficar muito largo para a minha etiqueta?* | Reduza `Columns` ou aumente `XDimension.Pixels` para equilibrar largura e legibilidade. |
| *Preciso definir um checksum?* | O checksum é opcional |

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas em seus próprios projetos.

- [Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [Create PDF417 Barcode Metadata in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [Generate barcode with text – Full PDF417 Macro Guide](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}