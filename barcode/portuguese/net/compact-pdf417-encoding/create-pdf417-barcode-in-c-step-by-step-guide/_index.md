---
category: general
date: 2026-10-04
description: Crie código de barras PDF417 em C# rapidamente. Aprenda como gerar código
  de barras PDF417 e como salvar a imagem do código de barras como PNG com Aspose.Barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode c#
- barcode for mobile scanning
- aspose barcode png generation
lastmod: 2026-10-04
og_description: Crie código de barras PDF417 em C# com Aspose.Barcode. Este tutorial
  mostra como gerar um código de barras PDF417 compacto, configurar sua aparência
  e salvá-lo como imagem PNG para digitalização móvel ou impressão de etiquetas.
og_image_alt: 'Developer guide: Create PDF417 barcode in C# and save as PNG using
  Aspose.Barcode'
og_title: Criar código de barras PDF417 em C# – guia passo a passo completo
schemas:
- author: Aspose
  dateModified: '2026-10-04'
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
- Aspose.Barcode
title: Criar código de barras PDF417 em C# – guia passo a passo
url: /pt/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar código de barras PDF417 em C# – guia passo a passo

Se você precisar **criar PDF417 barcode** em uma aplicação .NET, este guia mostra exatamente como gerar um PDF417 barcode e como salvar a imagem do código de barras como um arquivo PNG. Você obterá uma imagem compacta que funciona muito bem para digitalização móvel, sistemas de bilhetagem ou impressoras de etiquetas.

## Respostas rápidas
- **Qual biblioteca lida com a geração de PDF417?** Aspose.Barcode for .NET.  
- **Qual formato o exemplo salva?** PNG, usando `BarCodeImageFormat.Png`.  
- **Quantas linhas de código são necessárias?** Cerca de 10 linhas após a configuração do projeto.  
- **Posso personalizar tamanho e truncamento?** Sim – propriedades `Columns`, `Rows` e `Truncate`.  
- **O código é compatível com .NET‑6?** Sim, e também funciona com .NET Framework 4.7+.

## O que você precisa para criar um código de barras PDF417 em C#?
Para começar, você precisa de um SDK .NET recente, uma IDE como o Visual Studio 2022 e o pacote NuGet **Aspose.Barcode for .NET**. Essas ferramentas permitem que o exemplo compile e execute sem configuração extra.

- .NET 6.0 SDK ou posterior (também funciona com .NET Framework 4.7+)
- Visual Studio 2022 ou qualquer editor compatível com C#
- Acesso à Internet para baixar o pacote NuGet Aspose.Barcode

## Como configurar um projeto .NET para geração de código de barras PDF417?
Crie um novo projeto de console, adicione o pacote Aspose.Barcode e abra o `Program.cs` gerado. Isso prepara um ambiente limpo onde você pode instanciar o gerador de código de barras e escrever o arquivo de saída.

```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

## Como gerar um código de barras PDF417 com Aspose.Barcode?
`BarcodeGenerator` é a classe Aspose.Barcode que cria imagens de código de barras a partir dos dados e simbologia fornecidos. Você especifica a simbologia PDF417, fornece o texto a ser codificado e, opcionalmente, ajusta configurações de tamanho ou correção de erros.

```bash
   dotnet add package Aspose.Barcode
   ```

### Por que isso importa
* **EncodeTypes.Pdf417** informa à biblioteca para usar o padrão PDF417, que suporta grandes cargas de dados e correção de erros.
* Fornecer caracteres Unicode demonstra que o gerador lida com entrada não‑ASCII sem configuração extra.

## Como configurar a aparência de um código de barras PDF417?
Você pode controlar o tamanho do módulo, a contagem de colunas e se o código de barras usa o modo compacto (truncado). Essas configurações afetam diretamente a legibilidade em telas pequenas e o tamanho total do arquivo PNG.

```csharp
   using System;
   using Aspose.Barcode.Generation;
   using Aspose.Barcode;
   ```

### Dica prática
Se você precisar de um código de barras mais alto para espaço horizontal limitado, aumente `Columns`. Definir `Truncate` como `true` reduz a altura total removendo as zonas silenciosas, o que é ideal para telas móveis.

## Como salvar a imagem do código de barras como PNG?
`Save` é um método de `BarcodeGenerator` que grava a imagem gerada em um arquivo. Passe um caminho de arquivo e `BarCodeImageFormat.Png` para criar uma imagem PNG em um único passo.

```csharp
// Step 1: Initialise the generator with PDF417 symbology and sample text.
// The text includes Unicode characters to demonstrate full‑range support.
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

### Resultado esperado
Executar o programa cria `CompactPdf417.png` na pasta do projeto. Abrir o arquivo mostra um código de barras PDF417 compacto que codifica a string *Åspóse.Barcóde©*. A imagem pode ser incorporada em HTML, relatórios PDF ou impressa em etiquetas.

## Como verificar o arquivo de código de barras gerado?
Após o programa terminar, você pode verificar se o arquivo existe com um comando rápido. Essa verificação simples confirma que as etapas de geração e salvamento foram concluídas sem erros.

```csharp
// Step 2: Set the module (X) dimension – each barcode element will be 2 pixels wide.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Configure PDF417‑specific options.
generator.Parameters.Barcode.Pdf417.Columns = 3;      // Number of columns (affects height)
generator.Parameters.Barcode.Pdf417.Truncate = true; // Enable compact mode
```

Se o arquivo aparecer, o processo de **criar PDF417 barcode** foi bem-sucedido.

## Quais são as variações comuns e casos extremos ao gerar códigos de barras PDF417?
Cenários diferentes podem exigir ajustes nas configurações do gerador. Abaixo está uma tabela de referência rápida que mostra como lidar com variações típicas.

| Situação | Ajuste |
|-----------|------------|
| **String de dados mais longa** | Aumente `Columns` ou defina `Rows` para acomodar mais codewords. |
| **Formato de imagem diferente** | Substitua `BarCodeImageFormat.Png` por `Jpeg`, `Bmp` ou `Gif`. |
| **Resolução mais alta** | Defina `generator.Parameters.ImageResolution` antes de `Save`. |
| **Cor de fundo** | Use `generator.Parameters.Barcode.ImageBackgroundColor = Color.White;`. |
| **Tratamento de exceções** | Envolva `generator.Save` em um bloco `try/catch` para capturar erros de I/O. |

Essas variações permitem que você ajuste o código de barras para dispositivos específicos ou requisitos de marca.

## Qual é o próximo passo após criar o código de barras?
Agora que você pode gerar e salvar um código de barras PDF417, pode explorar recursos relacionados, como gerar códigos QR, incorporar códigos de barras em documentos PDF ou personalizar cores para alinhamento de marca. Todos esses utilizam a mesma API `BarcodeGenerator`, então você pode estender o exemplo com esforço mínimo.

## Guias relacionados
- [Como criar código de barras – PDF417 compacto com Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Como gerar códigos de barras DataMatrix (ECC 200) com Aspose.BarCode para .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Como gerar código de barras Aztec com proporção personalizada usando Aspose.BarCode para .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

## Perguntas frequentes

**Q: Posso usar este código em uma aplicação web?**  
A: Sim. A mesma classe `BarcodeGenerator` funciona em projetos ASP.NET, MVC ou Blazor; apenas certifique-se de que o servidor tenha permissão de gravação na pasta de saída.

**Q: O Aspose.Barcode suporta outras simbologias 2‑D?**  
A: Absolutamente. Mais de 30 tipos de códigos de barras 2‑D são suportados, incluindo QR, DataMatrix e Aztec.

**Q: Quão grande um código de barras posso criar?**  
A: PDF417 pode codificar até 1.850 caracteres em um único símbolo; você também pode dividir os dados em várias linhas ajustando `Rows` e `Columns`.

**Q: É necessária uma licença para uso em produção?**  
A: Sim. Um teste gratuito está disponível para avaliação, mas uma licença comercial é necessária para implantação.

**Q: Quais versões do .NET são compatíveis?**  
A: Aspose.Barcode suporta .NET Framework 4.5+, .NET Core 3.1+, e .NET 5/6/7.

---

**Última atualização:** 2026-10-04  
**Testado com:** Aspose.Barcode 24.11 for .NET  
**Autor:** Aspose  

```csharp
// Step 4: Save the generated barcode as a PNG image.
string outputPath = @"./CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```
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
```bash
dotnet run && ls -l CompactPdf417.png
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}