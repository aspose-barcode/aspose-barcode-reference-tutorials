---
category: general
date: 2026-09-28
description: Leia código de barras PDF417 c# rapidamente com Aspose.BarCode. Decodifique
  vários códigos de barras a partir de uma imagem, extraia campos Macro‑PDF417 e trate
  rotação ou processamento em lote.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read pdf417 barcode c#
- read multiple barcodes
- pdf417 c# decoding
- Aspose.BarCode PDF417
- barcode image c#
lastmod: 2026-09-28
og_description: Leia código de barras PDF417 c# rapidamente com Aspose.BarCode. Este
  guia mostra como decodificar vários códigos de barras de uma única imagem, extrair
  todas as propriedades Macro‑PDF417 e lidar com imagens rotacionadas ou em lote.
og_image_alt: Screenshot of C# console output displaying PDF417 barcode details
og_title: Leia código de barras PDF417 c# – exemplo completo de código e guia
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Read PDF417 barcode c# and read multiple barcodes from an image. Learn
    to read barcode image C# with detailed code and tips.
  headline: Read PDF417 barcode c# – complete step‑by‑step guide
  type: TechArticle
- description: Read PDF417 barcode c# and read multiple barcodes from an image. Learn
    to read barcode image C# with detailed code and tips.
  name: Read PDF417 barcode c# – complete step‑by‑step guide
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
title: Como ler código de barras PDF417 c# – guia completo passo a passo
url: /pt/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como ler código de barras PDF417 c# – guia completo passo a passo

Já se perguntou **como ler PDF417** de uma imagem usando C#? Você não é o único. A maioria dos desenvolvedores encontra dificuldades quando precisam extrair os campos estendidos Macro‑PDF417 de um documento escaneado. A boa notícia? Com apenas algumas linhas de código você pode **read PDF417 barcode c#**, decodificar vários códigos de barras na mesma imagem e obter todas as propriedades ocultas que a especificação oferece.

## Respostas rápidas
- **O Aspose.BarCode pode decodificar Macro‑PDF417?** Sim – basta habilitar `DecodeType.MacroPdf417` e a biblioteca retorna todos os campos estendidos.  
- **Quantos códigos de barras podem ser lidos de uma única imagem?** Ilimitado; a API retorna uma coleção de objetos `BarCodeResult`.  
- **Preciso de uma licença para produção?** É necessária uma licença comercial para uso em produção; uma avaliação gratuita funciona para testes.  
- **Códigos de barras rotacionados serão detectados?** A compensação de rotação integrada funciona para códigos que cobrem pelo menos 30 % da largura da imagem.  
- **O processamento em lote é suportado?** Absolutamente – envolva o leitor em um loop `foreach` e descarte cada instância com `using`.

## O que é read PDF417 barcode c#?
`read pdf417 barcode c#` refere-se ao processo de usar uma biblioteca .NET para decodificar símbolos PDF417 (incluindo Macro‑PDF417) a partir de arquivos de imagem diretamente em código C#. O Aspose.BarCode SDK fornece uma API de chamada única que lida com o carregamento de imagens, detecção de códigos de barras e extração de todos os campos definidos pela ISO.

## Por que usar Aspose.BarCode para decodificação de PDF417?
Aspose.BarCode suporta **mais de 30 simbologias de códigos de barras** e pode processar imagens de até **5000 × 5000 px** em menos de **0.1 s** em hardware de servidor típico. Também oferece rotação, distorção e tratamento de códigos de barras invertidos prontos para uso, eliminando a necessidade de pré‑processamento de imagem personalizado. Além disso, a biblioteca inclui suporte integrado para leitura de campos estendidos Macro‑PDF417, tornando-a uma solução completa para cenários de digitalização complexos.

## Pré-requisitos

Antes de começarmos, certifique‑se de que você tem:

* .NET 6.0 SDK ou posterior (o código funciona também com .NET Core e .NET Framework).  
* Visual Studio 2022 (ou qualquer editor de sua preferência).  
* O pacote NuGet **Aspose.BarCode for .NET** – esta é a biblioteca que realmente analisa PDF417.  
* Uma imagem de exemplo que contém um código de barras Macro‑PDF417 (por exemplo `ExtPDF417Meta.png`).  

Nenhuma configuração extra é necessária; a biblioteca já inclui todos os decodificadores que você precisa.

## Como ler PDF417 barcode c#?

Carregue a imagem com `BarCodeReader`, especifique `DecodeType.MacroPdf417` e itere a coleção `BarCodeResult` retornada – essa é a solução completa em menos de dez linhas de código. O leitor extrai automaticamente tanto os símbolos PDF417 simples quanto os dados estendidos Macro‑PDF417, assim você obtém identificadores de arquivo, números de segmento, timestamps e checksums sem parsing extra.

### Etapa 1: instalar Aspose.BarCode

Abra a pasta do seu projeto em um terminal e execute:

```bash
dotnet add package Aspose.BarCode
```

Esse comando obtém a versão estável mais recente (em julho 2026 é 23.12). Se preferir o Package Manager Console dentro do Visual Studio, use:

```powershell
Install-Package Aspose.BarCode
```

> **Dica profissional:** fixe a versão (`23.12.0`) no seu `.csproj` para evitar alterações inesperadas mais tarde.

### Etapa 2: criar um esqueleto de aplicativo console

Crie um novo projeto console se ainda não tiver um:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Substitua o `Program.cs` gerado automaticamente pelo código abaixo. Explicaremos cada bloco nas próximas seções.

### Etapa 3: escrever o código completo “como ler PDF417”

`BarCodeReader` é a classe principal que processa a imagem, detecta códigos de barras e retorna uma coleção de objetos `BarCodeResult`.

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

* `BarCodeReader` — a classe principal responsável por ler e decodificar códigos de barras de imagens.  
* `DecodeType.MacroPdf417` — um sinalizador que indica ao SDK para tratar Macro‑PDF417 de forma especial, ainda retornando símbolos PDF417 simples.  
* `Extended.Pdf417.MacroPdf417` — o objeto que contém todos os campos opcionais definidos pela ISO/IEC 15438, como `FileID`, `SegmentID` e `Checksum`.

O bloco `using` garante que os recursos nativos sejam liberados, evitando vazamentos de memória em serviços de longa duração.

### Etapa 4: executar o aplicativo e verificar a saída

No terminal:

```bash
dotnet run
```

Você deve ver algo como:

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

Se a imagem contiver mais de um código de barras, o loop imprime uma linha separadora (`----------------------------------------`) e continua com o próximo resultado — exatamente como **read multiple barcodes** aparece na prática.

## Perguntas comuns & casos extremos

### E se a imagem tiver símbolos Macro‑PDF417 e PDF417 regulares?

A mesma chamada `BarCodeReader` retornará ambos. Você pode diferenciá‑los verificando `result.CodeType` (`MacroPdf417` vs `Pdf417`). As propriedades estendidas serão `null` para um PDF417 simples, portanto a verificação `if (macro != null)` evita um `NullReferenceException`.

### Meu código de barras está rotacionado ou inclinado — o leitor ainda funcionará?

Aspose.BarCode inclui compensação integrada de rotação e distorção. Desde que o código de barras ocupe pelo menos 30 % da largura da imagem, o decodificador geralmente terá sucesso. Para casos extremos, você pode habilitar `reader.Options.AllowInvertedBarcodes = true;` antes de chamar `ReadBarCodes()`.

### Como lidar com grandes lotes de imagens?

Envolva a lógica de leitura em um loop `foreach (var file in Directory.GetFiles(folder, "*.png"))`. O padrão `using` garante que os recursos nativos de cada imagem sejam liberados antes da próxima iteração, mantendo o uso de memória baixo.

## Listagem completa do código fonte (pronta para copiar e colar)

Abaixo está o programa inteiro em um bloco para cópia rápida. Sem dependências ocultas — apenas o pacote NuGet Aspose.BarCode.

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

## Recapitulação – o que cobrimos

* **How to read PDF417 barcode c#** using Aspose.BarCode.  
* The exact steps to **read multiple barcodes** from a single image.  
* How to **read barcode image c#** and extract every Macro‑PDF417 field.  
* Dicas para rotação, processamento em lote e tratamento de dados estendidos ausentes.

## Próximos passos & tópicos relacionados

* **Encode PDF417** – gere seus próprios códigos de barras Macro‑PDF417 com `BarCodeBuilder`.  
* **Read other 2‑D symbologies** – QR, DataMatrix, Aztec – usando a mesma classe `BarCodeReader`.  
* **Integrate with ASP.NET Core** – exponha um endpoint web que aceita uma imagem enviada e retorna JSON com os campos decodificados.  

### Links úteis adicionais
- [Como ler códigos de barras DataMatrix com Aspose.BarCode para .NET](/barcode/english/net/datamatrix-barcode-reading/)  
- [Como criar código de barras – Compact PDF417 com Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)  
- [Ler código de barras DataMatrix C# – Gerar modo DataMatrix (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

Sinta‑se à vontade para experimentar: altere o caminho da imagem, coloque um PDF417 simples na mesma pasta ou ajuste as flags `DecodeType` para ver como a biblioteca se comporta. Quanto mais você brincar, mais confortável ficará com cenários de **read barcode image c#**.

Tem uma imagem complicada que se recusa a ser decodificada? Deixe um comentário abaixo ou abra uma issue no repositório GitHub do projeto de exemplo. Feliz codificação!

## Perguntas frequentes

**Q: Posso usar isso em uma aplicação comercial?**  
A: Sim, você pode usar Aspose.BarCode em projetos comerciais desde que possua uma licença válida; uma avaliação gratuita está disponível para testes.

**Q: O leitor suporta imagens protegidas por senha?**  
A: O SDK funciona com qualquer formato de imagem padrão; proteção por senha não se aplica a imagens raster, apenas a PDFs, que são tratados por um componente separado Aspose.PDF.

**Q: Quais versões do .NET são suportadas?**  
A: .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ e .NET 6+ são totalmente suportados pela versão atual do Aspose.BarCode.

**Q: Como posso melhorar o desempenho para lotes de imagens muito grandes?**  
A: Habilite `reader.Options.Quality = QualityMode.HighPerformance` e processe as imagens em paralelo usando `Parallel.ForEach`, mantendo cada `BarCodeReader` dentro de um bloco `using`.

**Q: Existe uma maneira de obter apenas os campos Macro‑PDF417 sem iterar todos os resultados?**  
A: Sim – após chamar `ReadBarCodes()`, filtre a coleção com `result => result.CodeType == DecodeType.MacroPdf417` e então acesse a propriedade `Extended.Pdf417.MacroPdf417`.

**Última atualização:** 2026-09-28  
**Testado com:** Aspose.BarCode 23.12 for .NET  
**Autor:** Aspose

## Tutoriais Relacionados

- [Como gerar imagem de código de barras Pdf417 em C com Aspose](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)  
- [Criar código de barras Pdf417 com Aspose Barcode – Guia passo a passo](/barcode/net/compact-pdf417-encoding/create-pdf417-barcode-with-aspose-barcode-step-by-step-guide/)  
- [Ler múltiplos códigos de barras C – Guia completo com Pdf417](/barcode/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}