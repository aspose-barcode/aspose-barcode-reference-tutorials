---
category: general
date: 2026-08-03
description: Crie código de barras PDF417 em C# rapidamente. Aprenda como gerar código
  de barras PDF417 e como salvar a imagem do código de barras como PNG com Aspose.Barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417 barcode
- how to save barcode image
language: pt
lastmod: 2026-08-03
og_description: Crie código de barras PDF417 em C# com Aspose.Barcode. Siga este guia
  para gerar o código de barras PDF417 e aprender como salvar a imagem do código de
  barras de forma eficiente.
og_image_alt: Screenshot of a generated compact PDF417 barcode saved as PNG
og_title: Criar código de barras PDF417 em C# – tutorial completo de codificação
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
    and how to save barcode image as PNG with Aspose.Barcode.
  headline: Create PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Create PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
    and how to save barcode image as PNG with Aspose.Barcode.
  name: Create PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: Why this matters
    text: '* **EncodeTypes.Pdf417** tells the library to use the PDF417 standard,
      which supports large data payloads and error correction. * Providing Unicode
      characters proves the generator handles non‑ASCII input without extra configuration.'
  - name: Practical tip
    text: If you need a taller barcode for limited horizontal space, increase `Columns`.
      Setting `Truncate` to `true` reduces the overall height by removing quiet zones,
      which is ideal for mobile screens.
  - name: Expected result
    text: Running the program creates `CompactPdf417.png` in the project folder. Opening
      the file shows a compact PDF417 barcode that encodes the string *Åspóse.Barcóde©*.
      The image can be embedded in HTML, PDF reports, or printed on labels.
  - name: Verifying the output
    text: 'After the program finishes, you can verify the file exists with a quick
      command:'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
title: Criar código de barras PDF417 em C# – guia passo a passo
url: /pt/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar código de barras PDF417 em C# – guia passo a passo

Se você precisa **criar código de barras PDF417** em uma aplicação .NET, este guia mostra exatamente como gerar o código de barras PDF417 e como salvar a imagem do código de barras. Você obterá um arquivo PNG que pode ser usado em relatórios, tickets ou aplicativos de escaneamento móvel.

O tutorial cobre tudo, desde a configuração do projeto até o arquivo PNG final. Nenhuma documentação externa é necessária; basta seguir os passos e executar o código.

## O que você precisará

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 SDK ou posterior (o código também funciona com .NET Framework 4.7+)
* Visual Studio 2022 ou qualquer IDE que suporte C#
* Acesso à internet para instalar o pacote NuGet **Aspose.Barcode for .NET**

Esses pré‑requisitos garantem que o código compile sem configuração adicional.

## Criar código de barras PDF417 – configuração do projeto

1. Abra um prompt de comando e crie um novo projeto de console:

   ```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

2. Adicione a biblioteca Aspose.Barcode:

   ```bash
   dotnet add package Aspose.Barcode
   ```

3. Abra o arquivo `Program.cs` gerado. As instruções `using` no topo dão acesso às classes de código de barras:

   ```csharp
   using System;
   using Aspose.Barcode.Generation;
   using Aspose.Barcode;
   ```

O projeto agora está pronto para **criar código de barras PDF417**.

## Como gerar código de barras PDF417 com Aspose.Barcode

O núcleo da criação do código de barras está na classe `BarcodeGenerator`. Você especifica a simbologia (`EncodeTypes.Pdf417`) e os dados que deseja codificar.

```csharp
// Step 1: Initialise the generator with PDF417 symbology and sample text.
// The text includes Unicode characters to demonstrate full‑range support.
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

### Por que isso importa

* **EncodeTypes.Pdf417** indica à biblioteca para usar o padrão PDF417, que suporta grandes cargas de dados e correção de erros.
* Fornecer caracteres Unicode demonstra que o gerador lida com entrada não‑ASCII sem configuração extra.

## Como configurar a aparência do código de barras

Você pode controlar o tamanho de cada módulo, o número de colunas e se o código de barras usa o modo compacto (truncado). Essas configurações afetam tanto a legibilidade quanto o tamanho do arquivo.

```csharp
// Step 2: Set the module (X) dimension – each barcode element will be 2 pixels wide.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Configure PDF417‑specific options.
generator.Parameters.Barcode.Pdf417.Columns = 3;      // Number of columns (affects height)
generator.Parameters.Barcode.Pdf417.Truncate = true; // Enable compact mode
```

### Dica prática

Se precisar de um código de barras mais alto para espaço horizontal limitado, aumente `Columns`. Definir `Truncate` como `true` reduz a altura total removendo as zonas silenciosas, o que é ideal para telas móveis.

## Como salvar a imagem do código de barras como PNG

Após configurar o gerador, chame `Save` com um caminho de arquivo e o formato de imagem desejado. O método grava a imagem diretamente no disco.

```csharp
// Step 4: Save the generated barcode as a PNG image.
string outputPath = @"./CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

### Resultado esperado

Executar o programa cria `CompactPdf417.png` na pasta do projeto. Abrir o arquivo mostra um código de barras PDF417 compacto que codifica a string *Åspóse.Barcóde©*. A imagem pode ser incorporada em HTML, relatórios PDF ou impressa em etiquetas.

## Código-fonte completo

Abaixo está o programa completo e executável. Copie‑o para `Program.cs` e execute `dotnet run`.

```csharp
using System;
using Aspose.Barcode.Generation;
using Aspose.Barcode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with PDF417 symbology and sample text.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Åspóse.Barcóde©");

            // Set the module width to 2 pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Configure PDF417‑specific options.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Define the output file path.
            string outputPath = @"./CompactPdf417.png";

            // Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Verificando a saída

Depois que o programa terminar, você pode verificar se o arquivo existe com um comando rápido:

```bash
dotnet run && ls -l CompactPdf417.png
```

Se o arquivo aparecer, o processo de **criar código de barras PDF417** foi bem‑sucedido.

## Variações comuns e casos extremos

| Situação | Ajuste |
|-----------|------------|
| **String de dados mais longa** | Aumente `Columns` ou defina `Rows` para acomodar mais codewords. |
| **Formato de imagem diferente** | Substitua `BarCodeImageFormat.Png` por `Jpeg`, `Bmp` ou `Gif`. |
| **Resolução mais alta** | Defina `generator.Parameters.ImageResolution` antes de `Save`. |
| **Cor de fundo** | Use `generator.Parameters.Barcode.ImageBackgroundColor = Color.White;` |
| **Tratamento de exceções** | Envolva `generator.Save` em um bloco `try/catch` para capturar erros de I/O. |

Essas variações permitem adaptar o código de barras a dispositivos específicos ou requisitos de branding.

## Conclusão

Agora você sabe como **criar código de barras PDF417** em C# usando Aspose.Barcode, configurar sua aparência e **salvar a imagem do código de barras** como um arquivo PNG. O exemplo completo demonstra cada passo necessário, desde a configuração do projeto até a verificação, para que você possa integrar a geração de códigos de barras em qualquer solução .NET.

Em seguida, considere explorar tópicos relacionados, como **como gerar códigos QR**, **incorporar códigos de barras em documentos PDF** ou **personalizar cores de códigos de barras**. Cada um desses se baseia na mesma API do gerador, permitindo que você amplie as capacidades de escaneamento da sua aplicação com esforço mínimo. Feliz codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como criar código de barras – PDF417 compacto com Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Como gerar códigos de barras DataMatrix (ECC 200) com Aspose.BarCode para .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Como gerar código de barras Aztec com proporção personalizada usando Aspose.BarCode para .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}