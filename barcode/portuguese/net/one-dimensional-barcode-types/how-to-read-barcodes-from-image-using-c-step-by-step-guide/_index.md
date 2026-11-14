---
category: general
date: 2026-11-14
description: Aprenda a ler códigos de barras a partir de imagens em C# com um tutorial
  completo de leitor de códigos de barras em C#. Inclui configuração, código completo
  e tratamento de campos Macro PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcodes from image
- barcode reader tutorial c#
language: pt
lastmod: 2026-11-14
og_description: Leia códigos de barras a partir de uma imagem em C# com este tutorial
  de leitor de códigos de barras em C#. Obtenha um exemplo completo em funcionamento
  e aprenda a extrair dados Macro PDF417.
og_image_alt: C# code screenshot that reads barcodes from image using BarCodeReader
og_title: Ler códigos de barras de imagem em C# – tutorial completo
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to read barcodes from image in C# with a complete barcode
    reader tutorial c#. Includes setup, full code, and handling Macro PDF417 fields.
  headline: How to read barcodes from image using C# – step‑by‑step guide
  type: TechArticle
- description: Learn how to read barcodes from image in C# with a complete barcode
    reader tutorial c#. Includes setup, full code, and handling Macro PDF417 fields.
  name: How to read barcodes from image using C# – step‑by‑step guide
  steps:
  - name: Prerequisites
    text: '- .NET 8 SDK (or .NET 6+ if you prefer) installed. - Basic familiarity
      with C# console applications. - An image file that contains a Macro PDF417 barcode
      (e.g., `MacroPdf417.png`).'
  - name: Explanation of each step
    text: '| Step | Why it matters | |------|----------------| | **1️⃣ Define image
      path** | The reader works with a file path or stream. Using a relative path
      makes the example easy to copy‑paste. | | **2️⃣ Create BarCodeReader** | Passing
      `DecodeType.MacroPdf417` restricts the scan to that symbology, which i'
  - name: Reading other symbologies
    text: 'If you need to **read barcodes from image** that are not Macro PDF417,
      replace `DecodeType.MacroPdf417` with a comma‑separated list, e.g.:'
  - name: Handling large images
    text: 'Large PNG or JPEG files can increase memory usage. To keep the process
      lightweight, you can downscale the image before passing it to `BarCodeReader`:'
  - name: Working with streams instead of file paths
    text: 'When the image comes from a database or a web request, pass a `Stream`:'
  type: HowTo
tags:
- C#
- barcode
- image processing
title: Como ler códigos de barras a partir de uma imagem usando C# – guia passo a
  passo
url: /pt/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como ler códigos de barras a partir de imagem usando C# – guia passo a passo

Se você precisa **ler códigos de barras a partir de imagem** em uma aplicação .NET, este guia mostra exatamente como fazer. Ao final do tutorial você terá um programa completo e executável que extrai tanto os dados básicos do código de barras quanto os campos específicos do Macro PDF417.

Neste **tutorial de leitor de código de barras c#** cobriremos a configuração do projeto, o pacote NuGet necessário e um exemplo de código completo que funciona com o mais recente .NET 8 SDK. Nenhum serviço externo é necessário — tudo roda localmente.

## O que você vai aprender

- Como adicionar a biblioteca Aspose.BarCode (ou similar) a um projeto C#.  
- Como criar um `BarCodeReader` que aponta para um arquivo de imagem específico.  
- Como iterar por todos os códigos de barras detectados e exibir seu tipo, texto e metadados do Macro PDF417.  
- Dicas para lidar com imagens contendo múltiplos códigos de barras ou diferentes tipos de decodificação.

### Pré‑requisitos

- .NET 8 SDK (ou .NET 6+ se preferir) instalado.  
- Familiaridade básica com aplicações console em C#.  
- Um arquivo de imagem que contenha um código de barras Macro PDF417 (por exemplo, `MacroPdf417.png`).  

---

## Etapa 1: Configurar um novo projeto console

Abra um terminal e execute:

```bash
dotnet new console -n BarcodeReaderDemo
cd BarcodeReaderDemo
```

Isso cria um aplicativo console mínimo chamado **BarcodeReaderDemo**. O arquivo de projeto (`BarcodeReaderDemo.csproj`) será usado na próxima etapa.

## Etapa 2: Instalar a biblioteca de leitura de códigos de barras

Para este tutorial usamos a biblioteca **Aspose.BarCode for .NET**, pois ela oferece suporte ao Macro PDF417 nativamente. Instale-a via NuGet:

```bash
dotnet add package Aspose.BarCode --version 23.12
```

> **Por que esta biblioteca?** Ela fornece uma única classe `BarCodeReader`, suporta dezenas de simbologias e expõe a propriedade `Extended` que contém os campos do Macro PDF417.

## Etapa 3: Escrever o código do leitor de códigos de barras (tutorial de leitor de código de barras c#)

Substitua o conteúdo de `Program.cs` pelo exemplo completo a seguir. Ele demonstra **como ler códigos de barras a partir de imagem** e imprime tanto informações genéricas quanto específicas do Macro PDF417.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Recognition;

namespace BarcodeReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -------------------------------------------------------------
            // 1️⃣  Define the path to the image that contains the barcode.
            // -------------------------------------------------------------
            string imagePath = "YOUR_DIRECTORY/MacroPdf417.png";

            // -------------------------------------------------------------
            // 2️⃣  Create a BarCodeReader for the Macro PDF417 symbology.
            // -------------------------------------------------------------
            // DecodeType.MacroPdf417 tells the reader to look for the
            // Macro PDF417 variant and to populate the Extended.Pdf417
            // fields when they are present.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // ---------------------------------------------------------
                // 3️⃣  Iterate through every barcode found in the image.
                // ---------------------------------------------------------
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // -----------------------------------------------------
                    // 4️⃣  Output generic barcode information.
                    // -----------------------------------------------------
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // -----------------------------------------------------
                    // 5️⃣  Output Macro PDF417 specific fields (if any).
                    // -----------------------------------------------------
                    // The Extended property is only populated for
                    // symbologies that expose extra data, such as Macro PDF417.
                    Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");

                    // -----------------------------------------------------
                    // 6️⃣  (Optional) Add more macro fields here as needed.
                    // -----------------------------------------------------
                    Console.WriteLine(new string('-', 40));
                }
            }

            // -------------------------------------------------------------
            // 7️⃣  Keep the console window open when debugging.
            // -------------------------------------------------------------
            Console.WriteLine("Finished reading barcodes. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Explicação de cada passo

| Etapa | Por que é importante |
|------|----------------------|
| **1️⃣ Definir caminho da imagem** | O leitor funciona com um caminho de arquivo ou stream. Usar um caminho relativo facilita a cópia‑e‑colagem do exemplo. |
| **2️⃣ Criar BarCodeReader** | Passar `DecodeType.MacroPdf417` restringe a varredura a essa simbologia, o que melhora a velocidade e garante que os campos `Extended` sejam preenchidos. |
| **3️⃣ Iterar resultados** | Uma imagem pode conter múltiplos códigos de barras; o laço `foreach` garante que todos sejam capturados. |
| **4️⃣ Saída genérica** | `CodeTypeName` e `CodeText` são as informações mais comuns que os desenvolvedores precisam. |
| **5️⃣ Campos Macro PDF417** | O Macro PDF417 incorpora dados adicionais (ID do arquivo, ID do segmento, contagem de segmentos). Acessar `result.Extended.Pdf417` fornece esses valores sem parsing extra. |
| **6️⃣ Campos extras opcionais** | A biblioteca expõe outros campos macro (por exemplo, `MacroPdf417FileName`). Você pode estender a saída conforme sua necessidade. |
| **7️⃣ Manter console aberto** | Útil ao executar a partir do Visual Studio ou `dotnet run` para ver a saída antes da janela fechar. |

## Etapa 4: Executar o programa e verificar a saída

Coloque seu arquivo `MacroPdf417.png` na pasta referenciada por `imagePath`. Em seguida execute:

```bash
dotnet run
```

A saída típica no console é semelhante a:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12
Pdf417MacroSegmentID: 3
Pdf417MacroSegmentsCount: 5
----------------------------------------
Finished reading barcodes. Press any key to exit.
```

Se a imagem contiver múltiplos símbolos Macro PDF417, o programa listará cada conjunto de valores sequencialmente.

## Variações comuns e casos de borda

### Lendo outras simbologias

Se precisar **ler códigos de barras a partir de imagem** que não sejam Macro PDF417, substitua `DecodeType.MacroPdf417` por uma lista separada por vírgulas, por exemplo:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
    DecodeType.QR | DecodeType.Code128 | DecodeType.DataMatrix))
```

A propriedade `Extended` será `null` para simbologias que não fornecem dados extras, portanto verifique sempre se é `null` antes de acessá‑la.

### Manipulando imagens grandes

Arquivos PNG ou JPEG grandes podem aumentar o uso de memória. Para manter o processo leve, você pode reduzir a escala da imagem antes de passá‑la ao `BarCodeReader`:

```csharp
using (System.Drawing.Bitmap bmp = new System.Drawing.Bitmap(imagePath))
{
    var resized = new System.Drawing.Bitmap(bmp, new System.Drawing.Size(bmp.Width / 2, bmp.Height / 2));
    using (BarCodeReader reader = new BarCodeReader(resized, DecodeType.MacroPdf417))
    {
        // read as before...
    }
}
```

### Trabalhando com streams em vez de caminhos de arquivo

Quando a imagem vem de um banco de dados ou de uma requisição web, passe um `Stream`:

```csharp
using (FileStream fs = File.OpenRead(imagePath))
using (BarCodeReader reader = new BarCodeReader(fs, DecodeType.MacroPdf417))
{
    // read as before...
}
```

## Dicas profissionais para uma experiência tranquila com o leitor de códigos de barras

- **Dica profissional:** Sempre defina o `DecodeType` para o conjunto mais restrito de simbologias que você espera. Isso reduz falsos positivos e acelera o processamento.  
- **Cuidado com:** Imagens com baixo contraste ou compressão excessiva podem causar leituras perdidas. Pré‑procese a imagem (ajuste brilho/contraste) se notar baixa taxa de detecção.  
- **Dica:** A classe `BarCodeReader` implementa `IDisposable`; usar um bloco `using` garante que os recursos nativos sejam liberados prontamente.  

---

## Conclusão

Agora você sabe como **ler códigos de barras a partir de imagem** em C# e extrair tanto informações padrão quanto específicas do Macro PDF417. Este **tutorial de leitor de código de barras c#** oferece uma solução completa e autônoma que pode ser inserida em qualquer projeto .NET.

A partir daqui você pode:

- Explorar outros tipos de decodificação (QR, DataMatrix, Code128).  
- Integrar o leitor em uma API ASP.NET Core para processar uploads em tempo real.  
- Armazenar os campos macro extraídos em um banco de dados para agregação posterior.

Boa codificação, e sinta‑se à vontade para experimentar diferentes fontes de imagem e formatos de código de barras!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas em seus próprios projetos.

- [How to decode PDF417 barcodes in C# and read barcode image C#](/barcode/english/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-and-read-barcode-image-c/)
- [How to read barcode from image c# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-read-barcode-from-image-c-using-aspose-barcode/)
- [Read barcode from image C# – complete guide with Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}