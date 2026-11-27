---
category: general
date: 2026-11-27
description: como ler código de barras pdf417 em C# a partir de uma imagem usando
  Aspose.BarCode – guia passo a passo com exemplo de código completo e dicas de solução
  de problemas.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode from image c#
- C# barcode decoding
- BarCodeReader class
- DecodeType.MacroPdf417
- BarCodeResult properties
language: pt
lastmod: 2026-11-27
og_description: como ler código de barras PDF417 em C# rapidamente. Aprenda a decodificar
  códigos de barras PDF417 a partir de imagens com Aspose.BarCode, código completo
  e melhores práticas.
og_image_alt: Console output showing how to read PDF417 barcode in C#
og_title: Como ler código de barras PDF417 em C# – guia passo a passo
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: how to read pdf417 barcode in C# from an image using Aspose.BarCode
    – step‑by‑step guide with full code example and troubleshooting tips.
  headline: How to read PDF417 barcode in C# – complete programming guide
  type: TechArticle
- description: how to read pdf417 barcode in C# from an image using Aspose.BarCode
    – step‑by‑step guide with full code example and troubleshooting tips.
  name: How to read PDF417 barcode in C# – complete programming guide
  steps:
  - name: Create a new console project
    text: 'Open a terminal (or PowerShell) and run:'
  - name: Install the Aspose.BarCode NuGet package
    text: 'Aspose.BarCode provides the `BarCodeReader` class used in the example.
      Install it with:'
  - name: Add the code shown above
    text: Replace the content of `Program.cs` with the full snippet from the previous
      section. The code demonstrates **C# barcode decoding** and shows how to access
      **BarCodeResult properties** such as `CodeTypeName`, `CodeText`, and the macro‑specific
      `MacroPdf417FileID`.
  - name: Run the application
    text: '```bash dotnet run ```'
  - name: Handle multiple barcodes and error cases
    text: 'Real‑world images may hold more than one barcode or none at all. Wrap the
      reading logic in a `try`/`catch` block to surface parsing errors, and check
      `reader.HasBarcodes` before iterating:'
  - name: Optional – Decode other barcode types from the same image
    text: 'If you later need to **read barcode from image c#** for other symbologies,
      simply change the `DecodeType` argument:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Como ler código de barras PDF417 em C# – guia completo de programação
url: /pt/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como ler código de barras PDF417 em C# – guia completo de programação

Se você precisa **como ler código de barras pdf417** a partir de uma imagem, este guia mostra as etapas exatas. Usando Aspose.BarCode para .NET, você pode decodificar um código de barras PDF417 em uma única chamada de método, e o guia o conduz por cada linha de código necessária.

Ler um código de barras a partir de uma imagem é uma tarefa comum ao criar scanners de inventário, sistemas de validação de ingressos ou pipelines de processamento de documentos. Neste tutorial você aprenderá como configurar o ambiente, instalar o pacote necessário e escrever um programa C# robusto que lê um código de barras PDF417 e extrai seus campos de dados estendidos. Nenhum serviço externo é necessário; tudo roda localmente.

> **Pré‑requisitos**  
> • .NET 6.0 SDK ou posterior instalado  
> • Conhecimento básico de C# e aplicações de console  
> • Acesso a um arquivo de imagem que contenha um código de barras PDF417 (ou Macro PDF417)  

Também abordaremos **ler código de barras a partir de imagem c#** alternativas, explicaremos as propriedades mais úteis do objeto `BarCodeResult` e daremos dicas para lidar com múltiplos códigos de barras em uma única imagem.

---

## Como ler código de barras PDF417 a partir de uma imagem em C#

O primeiro passo importante é criar um `BarCodeReader` que aponte para o arquivo de imagem e indique à biblioteca qual tipo de código de barras procurar. Ao especificar `DecodeType.MacroPdf417` você limita a varredura às variantes PDF417, o que melhora a velocidade e a precisão.

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
            // Path to the image that contains the PDF417 barcode
            string imagePath = @"C:\Barcodes\Pdf417Sample.png";

            // Initialize the reader for Macro PDF417 barcodes
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Iterate through all detected barcodes
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // Macro PDF417 specific extended information
                    if (result.Extended?.Pdf417?.MacroPdf417FileID != null)
                    {
                        Console.WriteLine($"Macro PDF417 File ID : {result.Extended.Pdf417.MacroPdf417FileID}");
                    }

                    // Show confidence and symbology details
                    Console.WriteLine($"Code Confidence : {result.CodeTextConfidence}");
                    Console.WriteLine($"Is Mirror Image : {result.IsMirrored}");
                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

**Por que isso funciona** – O construtor `BarCodeReader` recebe o caminho da imagem e um `DecodeType`. `MacroPdf417` indica ao motor que procure pela família PDF417, incluindo a extensão macro que transporta metadados extras, como o ID do arquivo. O método `ReadBarCodes()` retorna um enumerável de objetos `BarCodeResult`, cada um representando um código de barras detectado.

### Etapa 1: Criar um novo projeto de console

Abra um terminal (ou PowerShell) e execute:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Criar um projeto novo isola a demonstração e garante que o arquivo `csproj` contenha apenas as dependências que você adicionará a seguir.

### Etapa 2: Instalar o pacote NuGet Aspose.BarCode

Aspose.BarCode fornece a classe `BarCodeReader` usada no exemplo. Instale-a com:

```bash
dotnet add package Aspose.BarCode --version 23.12
```

O pacote inclui suporte para todas as simbologias 1D e 2D, incluindo PDF417 e sua variante macro.

### Etapa 3: Adicionar o código mostrado acima

Substitua o conteúdo de `Program.cs` pelo trecho completo da seção anterior. O código demonstra **decodificação de código de barras C#** e mostra como acessar **propriedades do BarCodeResult** como `CodeTypeName`, `CodeText` e o `MacroPdf417FileID` específico da macro.

### Etapa 4: Executar a aplicação

```bash
dotnet run
```

Se a imagem contiver um código de barras PDF417 legível, o console exibirá algo semelhante a:

```
Code Type : PDF417
Code Text : https://example.com/invoice/12345
Macro PDF417 File ID : 7
Code Confidence : 98.7
Is Mirror Image : False
----------------------------------------
```

Se a imagem não contiver um código de barras PDF417, o loop simplesmente termina sem imprimir nada.

### Etapa 5: Manipular múltiplos códigos de barras e casos de erro

Imagens do mundo real podem conter mais de um código de barras ou nenhum. Envolva a lógica de leitura em um bloco `try`/`catch` para expor erros de análise e verifique `reader.HasBarcodes` antes de iterar:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    if (!reader.HasBarcodes)
    {
        Console.WriteLine("No PDF417 barcodes detected.");
        return;
    }

    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        // existing processing code...
    }
}
```

**Dica profissional:** Ajuste a propriedade `Resolution` no `BarCodeReader` (por exemplo, `reader.Resolution = 300;`) ao lidar com digitalizações de baixa resolução. Resolução maior melhora a detecção, mas pode aumentar o uso de CPU.

### Etapa 6: Opcional – Decodificar outros tipos de código de barras da mesma imagem

Se mais tarde precisar **ler código de barras a partir de imagem c#** para outras simbologias, basta mudar o argumento `DecodeType`:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupportedTypes))
{
    // This will detect QR, Code128, DataMatrix, etc.
}
```

A mesma classe `BarCodeResult` funciona para todos os tipos, permitindo reutilizar o loop de processamento sem modificações.

---

## Entendendo as classes principais

| Classe | Propósito | Membros mais úteis |
|--------|-----------|--------------------|
| `BarCodeReader` | Abre uma imagem e procura por códigos de barras | `ReadBarCodes()`, `HasBarcodes`, `Resolution` |
| `BarCodeResult` | Mantém informações sobre um único código de barras detectado | `CodeTypeName`, `CodeText`, `CodeTextConfidence`, `Extended` |
| `Extended.Pdf417` | Fornece dados específicos de macro para PDF417 | `MacroPdf417FileID`, `MacroPdf417SegmentCount`, `MacroPdf417SegmentIndex` |

Conhecer esses membros permite extrair não apenas o texto legível por humanos, mas também os metadados estruturados que o Macro PDF417 incorpora, frequentemente necessários para o processamento em lote de documentos de várias páginas.

---

## Armadilhas comuns e como evitá‑las

* **`DecodeType` incorreto** – Usar `DecodeType.Pdf417` em vez de `MacroPdf417` fará com que as extensões macro sejam ignoradas. Escolha o tipo exato que corresponde ao seu código de barras.  
* **Formato de imagem não suportado** – Aspose.BarCode lê PNG, JPEG, BMP, TIFF e GIF. Se você possuir uma imagem RAW, converta‑a primeiro.  
* **Baixo contraste da imagem** – Pré‑procese a imagem (aumente o contraste ou binarize) antes de enviá‑la ao `BarCodeReader`. A biblioteca também oferece `reader.ImageProcessingOptions`.  
* **Arquivos grandes** – Para digitalizações de altíssima resolução, defina `reader.MaxBarcodesPerPage` para limitar o consumo de memória.

---

## Conclusão

Agora você sabe **como ler código de barras pdf417** em C# usando Aspose.BarCode, desde a configuração do projeto até o tratamento de campos específicos da macro. O exemplo completo e executável demonstra **decodificação de código de barras C#**, mostra como acessar **propriedades do BarCodeResult** e oferece dicas práticas para uma leitura robusta.  

Em seguida, explore tópicos relacionados, como **ler código de barras a partir de imagem c#** para QR codes, integre a leitura de códigos de barras em APIs ASP.NET Core ou experimente o processamento em lote de múltiplas imagens. A mesma classe `BarCodeReader` funciona em todas as simbologias suportadas, permitindo estender esta solução a qualquer código de barras que sua aplicação encontrar.

Feliz codificação, e sinta‑se à vontade para adaptar o exemplo ao seu fluxo de trabalho!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Como ler código de barras macro PDF417 em C# com Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-read-macro-pdf417-barcode-in-c-with-aspose-barcode/)
- [Como ler código de barras PDF417 em C# – guia completo do leitor de códigos de barras](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-full-barcode-reader-guide/)
- [Como criar código de barras PDF417 com Aspose – Guia completo passo a passo](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}