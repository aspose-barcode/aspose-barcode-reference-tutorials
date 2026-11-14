---
category: general
date: 2026-11-14
description: Criar código de barras micro PDF417 em C# com Aspose.BarCode – guia passo
  a passo cobrindo a configuração do gerador, dimensão X, colunas e exportação PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- micro pdf417 barcode generator
- set XDimension pixels
- define barcode columns
- save barcode as PNG
- Aspose.BarCode C# example
language: pt
lastmod: 2026-11-14
og_description: Crie código de barras micro PDF417 em C# usando Aspose.BarCode. Aprenda
  a configurar o gerador, definir XDimension, escolher colunas e exportar como PNG.
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: Crie código de barras micro PDF417 em C# – guia completo de programação
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Create micro PDF417 barcode in C# with Aspose.BarCode – step‑by‑step
    guide covering generator setup, X‑dimension, columns, and PNG export.
  headline: How to create micro PDF417 barcode in C#
  type: TechArticle
- description: Create micro PDF417 barcode in C# with Aspose.BarCode – step‑by‑step
    guide covering generator setup, X‑dimension, columns, and PNG export.
  name: How to create micro PDF417 barcode in C#
  steps:
  - name: Open the PNG in an image viewer.
    text: Open the PNG in an image viewer.
  - name: Use any smartphone barcode‑scanning app that supports PDF417 (most “QR‑code
      scanner” apps include it).
    text: Use any smartphone barcode‑scanning app that supports PDF417 (most “QR‑code
      scanner” apps include it).
  - name: Scan the image; the app should display the original text `"Åspóse.Barcóde©"`.
    text: Scan the image; the app should display the original text `"Åspóse.Barcóde©"`.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
- image generation
title: Como criar um código de barras micro PDF417 em C#
url: /pt/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar micro PDF417 barcode em C#  

Se você precisa **criar micro PDF417 barcode** rapidamente, este guia mostra uma solução completa, pronta‑para‑executar. Você verá como instanciar o gerador de código de barras, configurar a X‑dimension, escolher o número de colunas e, finalmente, salvar o resultado como uma imagem PNG — tudo usando a biblioteca Aspose.BarCode para .NET.

Gerar um micro PDF417 barcode não requer um pipeline de compilação complexo. Ao final deste tutorial você terá um único arquivo C# que produz uma imagem de código de barras de alta qualidade que pode ser incorporada em relatórios, etiquetas ou aplicativos móveis.

## Pré-requisitos  

* .NET 6.0 SDK ou posterior (o código também funciona com .NET Framework 4.7+).  
* Um ambiente de desenvolvimento como Visual Studio 2022, VS Code ou Rider.  
* Uma licença do Aspose.BarCode para .NET (ou uma chave de avaliação gratuita). Você pode obtê‑la no [Aspose website](https://purchase.aspose.com/barcode/net).  

> **Dica profissional:** Se você estiver usando a versão de avaliação, o PNG gerado conterá uma pequena marca d'água “Evaluation”. Uma versão licenciada a remove automaticamente.

## Etapa 1: Configurar o projeto  

Crie um novo projeto de console e adicione o pacote NuGet Aspose.BarCode.

```bash
dotnet new console -n MicroPdf417Demo
cd MicroPdf417Demo
dotnet add package Aspose.BarCode --version 24.9.0
```

O comando `dotnet add package` obtém as dependências do **exemplo Aspose.BarCode C#**, de modo que você não precise gerenciar os DLLs manualmente.

## Etapa 2: Escrever o código completo  

Substitua o `Program.cs` auto‑gerado pelo código a seguir. Ele demonstra como **criar micro pdf417 barcode** do início ao fim.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a MicroPDF417 barcode generator with the desired text.
            // The text can contain Unicode characters; here we use a sample string.
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Åspóse.Barcóde©");

            // 2️⃣ Set the X‑dimension (module width) in pixels.
            // This determines the width of the smallest element (a bar or a space).
            generator.Parameters.Barcode.XDimension.Pixels = 2; // secondary keyword: set XDimension pixels

            // 3️⃣ Define the number of columns (allowed values: 1‑4 for MicroPDF417).
            // More columns mean a wider barcode but fewer rows, which can improve readability.
            generator.Parameters.Barcode.Pdf417.Columns = 4; // secondary keyword: define barcode columns

            // 4️⃣ Choose the output format and save the barcode as a PNG image.
            // PNG preserves the sharp edges of the barcode, which is ideal for scanning.
            string outputPath = "MicroPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png); // secondary keyword: save barcode as PNG

            Console.WriteLine($"Micro PDF417 barcode saved to {outputPath}");
        }
    }
}
```

### Por que cada linha importa  

* **BarcodeGenerator constructor** – Instancia o **micro pdf417 barcode generator** com o texto que você deseja codificar.  
* **XDimension.Pixels** – Controla a largura do módulo; definir para `2` pixels gera um código de barras denso, de alta resolução, adequado para a maioria dos scanners.  
* **Pdf417.Columns** – MicroPDF417 suporta apenas 1‑4 colunas. Escolher `4` reduz a altura do código de barras, o que é útil quando há espaço vertical limitado.  
* **Save method** – Grava o código de barras em um arquivo PNG. PNG é sem perdas, garantindo que o scanner leia exatamente o padrão que você gerou.

## Etapa 3: Compilar e executar  

Compile e execute o programa:

```bash
dotnet run
```

Você deverá ver a saída no console:

```
Micro PDF417 barcode saved to MicroPdf417.png
```

Um arquivo chamado **MicroPdf417.png** aparece na pasta do projeto. Abra-o com qualquer visualizador de imagens; você verá um micro PDF417 barcode nítido que codifica a string `"Åspóse.Barcóde©"`.

![Exemplo de código de barras micro PDF417 gerado](MicroPdf417.png "Exemplo de código de barras micro PDF417 gerado"){.center-image width=400 alt="Imagem de exemplo de código de barras micro PDF417 gerado"}

*A imagem acima é o resultado do código mostrado na Etapa 2.*

## Etapa 4: Variações comuns e casos de borda  

| Situação | Como adaptar o código |
|-----------|----------------------|
| **Comprimento de dados diferente** | MicroPDF417 pode codificar até 1 200 caracteres. Basta alterar o segundo argumento de `BarcodeGenerator`. |
| **Resolução mais alta** | Aumente `XDimension.Pixels` para `3` ou `4`. Módulos maiores melhoram a legibilidade em scanners de baixa resolução, mas aumentam o tamanho da imagem. |
| **Cores personalizadas** | Após criar o gerador, defina `generator.Parameters.Barcode.BarcodeColor = Color.Blue;` e `generator.Parameters.Barcode.BackgroundColor = Color.White;`. |
| **Salvando em outros formatos** | Substitua `BarCodeImageFormat.Png` por `Jpeg`, `Bmp` ou `Gif` dependendo dos seus requisitos posteriores. |
| **Incorporando em um PDF** | Use `generator.Save("barcode.pdf", BarCodeImageFormat.Pdf);` e então mescle o PDF com outros documentos usando Aspose.PDF. |

> **Atenção:** Definir `XDimension.Pixels` abaixo de `1` lança uma `ArgumentOutOfRangeException`. Sempre mantenha‑o em `1` ou superior.

## Etapa 5: Verificar o código de barras  

Para garantir que o código de barras seja lido corretamente:

1. Abra o PNG em um visualizador de imagens.  
2. Use qualquer aplicativo de escaneamento de código de barras para smartphone que suporte PDF417 (a maioria dos aplicativos “scanner de QR‑code” inclui esse suporte).  
3. Escaneie a imagem; o aplicativo deve exibir o texto original `"Åspóse.Barcóde©"`.

Se a leitura falhar, verifique novamente as configurações de **X‑dimension** e **column** – uma largura de módulo muito pequena ou um número de colunas não suportado podem tornar o padrão ilegível.

## Conclusão  

Agora você sabe como **criar micro pdf417 barcode** em C# usando Aspose.BarCode. O tutorial abordou:

* Instanciar um **micro pdf417 barcode generator**.  
* **Definir XDimension pixels** para controlar a largura do módulo.  
* **Definir colunas do código de barras** para ajustar a forma.  
* **Salvar o código de barras como PNG** para saída de imagem sem perdas.  

A partir daqui você pode explorar recursos adicionais, como personalização de cores, incorporação do código de barras em PDFs ou geração de códigos de barras em tempo real em APIs web ASP.NET Core. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Criar código de barras PNG em C# – guia completo para GS1 Micro PDF417](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [Como criar código de barras macro PDF417 em C# usando Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Criar código de barras PDF417 em C# usando Aspose.BarCode – guia passo a passo](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}