---
category: general
date: 2026-07-15
description: Crie rapidamente uma imagem de código de barras planetário com C#. Aprenda
  como gerar código de barras postal e como salvar a imagem do código de barras como
  PNG usando Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode image
- how to generate postal barcode
- how to save barcode image
language: pt
lastmod: 2026-07-15
og_description: Crie imagem de código de barras Planet em C#. Este guia explica como
  gerar código de barras postal e como salvar a imagem do código de barras com exemplos
  de código claros.
og_image_alt: Screenshot showing a generated Planet barcode image saved as PNG
og_title: Criar Imagem de Código de Barras Planet em C# – Guia Rápido de Códigos de
  Barras Postais
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Create planet barcode image quickly with C#. Learn how to generate
    postal barcode and how to save barcode image as PNG using Aspose.BarCode.
  headline: Create Planet Barcode Image in C# – How to Generate Postal Barcode
  type: TechArticle
- description: Create planet barcode image quickly with C#. Learn how to generate
    postal barcode and how to save barcode image as PNG using Aspose.BarCode.
  name: Create Planet Barcode Image in C# – How to Generate Postal Barcode
  steps:
  - name: Why This Structure Works
    text: '- **Separate generators**: We instantiate two `BarcodeGenerator` objects
      because the `FilledBars` property is immutable once an image is rendered. Keeping
      them independent avoids side‑effects. - **X‑dimension choice**: A value of 4
      pixels balances readability and file size. If you need a higher‑reso'
  - name: Changing the Data Payload
    text: 'The `EncodeTypes.Planet` symbology expects numeric data up to 16 digits.
      To encode a different tracking number, just replace `"123456"` with your actual
      string:'
  - name: Adjusting Image Format
    text: If you need a JPEG for web delivery, swap `BarCodeImageFormat.Png` with
      `BarCodeImageFormat.Jpeg`. Remember JPEG introduces compression artifacts—avoid
      it for high‑precision scanning.
  - name: Handling Errors Gracefully
    text: 'When dealing with user‑supplied data, wrap the generation in a try‑catch
      block:'
  type: HowTo
- questions:
  - answer: Yes. Aspose.BarCode supports .NET Framework 4.5 and higher. Just change
      the target framework in your `.csproj` file.
    question: Does this work with .NET Framework 4.5?
  - answer: Replace `EncodeTypes.Planet` with any other enum value (e.g., `EncodeTypes.Code128`).
      The rest of the code stays the same.
    question: What if I need a different barcode symbology?
  - answer: 'Absolutely. Use `generator.Parameters.Barcode.BarColor = Color.Blue;`
      before saving. ## Conclusion You now know **how to create planet barcode image**
      in C#, **how to generate postal barcode** with the Aspose.BarCode library, and
      **how to save barcode image** as PNG files. The full example covered i'
    question: Can I change the bar color?
  type: FAQPage
tags:
- barcode
- C#
- Aspose.BarCode
title: Criar imagem de código de barras Planet em C# – Como gerar código de barras
  postal
url: /pt/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Imagem de Código de Barras Planet em C# – Como Gerar Código de Barras Postal

Já precisou **criar imagem de código de barras planet** em um projeto .NET mas não sabia por onde começar? Você não está sozinho. Neste guia vamos percorrer **como gerar código de barras postal** usando Aspose.BarCode e, em seguida, mostrar **como salvar a imagem do código de barras** no disco como um arquivo PNG.  

Imagine que você está construindo um sistema de correspondência que imprime etiquetas postais em tempo real—ter um gerador de código de barras confiável economiza horas de trabalho manual. Ao final deste tutorial você terá um aplicativo console pronto‑para‑executar que gera dois arquivos PNG: um com as barras preenchidas e outro apenas com os contornos.

## Pré‑requisitos

Antes de mergulharmos no código, certifique‑se de que você tem:

- .NET 6 SDK (ou qualquer versão recente do .NET) instalado.
- Visual Studio 2022 ou VS Code com extensões C#.
- O pacote NuGet **Aspose.BarCode for .NET**. Você pode adicioná‑lo via CLI:

```bash
dotnet add package Aspose.BarCode
```

Nenhuma outra dependência externa é necessária.

## Etapa 1: Configurar a Estrutura do Projeto

Primeiro, crie um novo projeto console e inclua a biblioteca de código de barras.

```bash
dotnet new console -n PlanetBarcodeDemo
cd PlanetBarcodeDemo
dotnet add package Aspose.BarCode
```

A pasta agora contém um arquivo `Program.cs` onde colocaremos toda a nossa lógica.

## Etapa 2: Escrever o Código Completo – Criar Imagem de Código de Barras Planet

Abaixo está o programa completo e autocontido. Copie‑e cole em `Program.cs` (sobrescrevendo o stub que o `dotnet new` gerou).

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Namespace and class are optional in a top‑level program (C# 9+), but we keep them for clarity.
namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -----------------------------------------------------------------
            // 1️⃣  Create a Planet barcode generator with the desired data.
            // -----------------------------------------------------------------
            // The "Planet" symbology is used by many postal services for
            // tracking and sorting. Here we encode a simple numeric string.
            var generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // ---------------------------------------------------------------
            // 2️⃣  Set the X‑dimension (width of a single bar) to 4 pixels.
            // ---------------------------------------------------------------
            // XDimension controls the visual density of the barcode.
            // 4 px is a common default that works well on most printers.
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            // ---------------------------------------------------------------
            // 3️⃣  Save the barcode using the default *filled‑bars* appearance.
            // ---------------------------------------------------------------
            // BarCodeImageFormat.Png ensures a lossless image, perfect for
            // later processing or printing.
            string filledPath = "PlanetFilledBars.png";
            generator.Save(filledPath, BarCodeImageFormat.Png);
            Console.WriteLine($"✔️ Filled bars saved to {filledPath}");

            // -----------------------------------------------------------------
            // 4️⃣  Create another generator for the same data to show empty bars.
            // -----------------------------------------------------------------
            var emptyBarsGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            emptyBarsGenerator.Parameters.Barcode.XDimension.Pixels = 4;

            // ---------------------------------------------------------------
            // 5️⃣  Disable filled bars so only the outlines are drawn.
            // ---------------------------------------------------------------
            emptyBarsGenerator.Parameters.Barcode.FilledBars = false;

            // ---------------------------------------------------------------
            // 6️⃣  Save the barcode with empty bars.
            // ---------------------------------------------------------------
            string emptyPath = "PlanetEmptyBars.png";
            emptyBarsGenerator.Save(emptyPath, BarCodeImageFormat.Png);
            Console.WriteLine($"✔️ Empty bars saved to {emptyPath}");

            // -----------------------------------------------------------------
            // 7️⃣  Quick verification – open the files if you’re on Windows.
            // -----------------------------------------------------------------
            // This is optional but handy when you run the demo locally.
            if (OperatingSystem.IsWindows())
            {
                System.Diagnostics.Process.Start(new System.Diagnostics.ProcessStartInfo
                {
                    FileName = filledPath,
                    UseShellExecute = true
                });
                System.Diagnostics.Process.Start(new System.Diagnostics.ProcessStartInfo
                {
                    FileName = emptyPath,
                    UseShellExecute = true
                });
            }
        }
    }
}
```

### Por Que Essa Estrutura Funciona

- **Geradores separados**: Instanciamos dois objetos `BarcodeGenerator` porque a propriedade `FilledBars` é imutável após a imagem ser renderizada. Mantê‑los independentes evita efeitos colaterais.
- **Escolha da dimensão X**: Um valor de 4 pixels equilibra legibilidade e tamanho do arquivo. Se precisar de impressão em alta resolução, aumente para 6 ou 8.
- **Salvando como PNG**: PNG preserva as bordas nítidas do código de barras, o que é crítico para scanners ópticos usados pelos serviços postais.

## Etapa 3: Executar a Demo e Verificar a Saída

Compile e execute o programa:

```bash
dotnet run
```

Você deverá ver mensagens no console confirmando que os dois arquivos foram salvos. Na pasta do projeto, você encontrará agora:

- `PlanetFilledBars.png` – um código de barras preenchido solidamente.
- `PlanetEmptyBars.png` – apenas os contornos das barras.

Abaixo está uma representação visual de como a versão preenchida se parece (a imagem é apenas ilustrativa; sua saída real pode variar ligeiramente conforme as configurações de DPI).

![create planet barcode image example](https://example.com/planet-filled.png)

*Texto alternativo: exemplo de criação de imagem de código de barras planet mostrando um PNG de um código de barras Planet com barras preenchidas.*

## Etapa 4: Ajustando o Código de Barras – Variações Comuns

### Alterando a Carga de Dados

A simbologia `EncodeTypes.Planet` aceita dados numéricos de até 16 dígitos. Para codificar um número de rastreamento diferente, basta substituir `"123456"` pela sua string real:

```csharp
var generator = new BarcodeGenerator(EncodeTypes.Planet, "9876543210123456");
```

### Ajustando o Formato da Imagem

Se precisar de JPEG para entrega web, troque `BarCodeImageFormat.Png` por `BarCodeImageFormat.Jpeg`. Lembre‑se de que JPEG introduz artefatos de compressão—evite‑o para digitalização de alta precisão.

### Tratamento de Erros de Forma Elegante

Ao lidar com dados fornecidos pelo usuário, envolva a geração em um bloco try‑catch:

```csharp
try
{
    generator.Save(path, BarCodeImageFormat.Png);
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Failed to save barcode: {ex.Message}");
}
```

Isso garante que sua aplicação não trave em caso de entrada inválida.

## Etapa 5: Integrando em uma Aplicação Maior

Em um sistema de correspondência real, você provavelmente gerará o código de barras sob demanda e o incorporará em um PDF ou modelo de etiqueta. Aqui está um trecho rápido mostrando como obter o código de barras como um `byte[]` para processamento posterior:

```csharp
using System.IO;

// Generate the image in memory
using (MemoryStream ms = new MemoryStream())
{
    generator.Save(ms, BarCodeImageFormat.Png);
    byte[] barcodeBytes = ms.ToArray();

    // Pass barcodeBytes to a PDF library, send over a network, etc.
}
```

Agora você pode alimentar o array de bytes ao iTextSharp, QuestPDF ou qualquer outro gerador de documentos sem tocar no sistema de arquivos.

## Perguntas Frequentes (FAQ)

**Q: Isso funciona com .NET Framework 4.5?**  
A: Sim. Aspose.BarCode suporta .NET Framework 4.5 e superiores. Basta mudar o framework alvo no seu arquivo `.csproj`.

**Q: E se eu precisar de uma simbologia de código de barras diferente?**  
A: Substitua `EncodeTypes.Planet` por qualquer outro valor de enum (por exemplo, `EncodeTypes.Code128`). O restante do código permanece o mesmo.

**Q: Posso mudar a cor das barras?**  
A: Claro. Use `generator.Parameters.Barcode.BarColor = Color.Blue;` antes de salvar.

## Conclusão

Agora você sabe **como criar imagem de código de barras planet** em C#, **como gerar código de barras postal** com a biblioteca Aspose.BarCode e **como salvar a imagem do código de barras** como arquivos PNG. O exemplo completo abordou inicialização, ajuste da dimensão X, alternância de barras preenchidas e salvamento em disco—além de algumas dicas úteis para integração no mundo real.

Pronto para o próximo passo? Experimente incorporar o PNG gerado em uma etiqueta PDF, teste cores diferentes ou troque para um formato de imagem de maior resolução. O céu é o limite quando você combina geração de códigos de barras com as ferramentas modernas do .NET.

Se encontrou algum problema ou tem ideias para extensões, deixe um comentário abaixo. Boa codificação!

## O Que Você Deve Aprender a Seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [How to Save PNG using DataMatrix C40 with Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/)
- [How to create barcode quiet zone for Code 16K using Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Generate barcode image – Code 93 with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}