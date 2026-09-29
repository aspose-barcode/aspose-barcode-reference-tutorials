---
category: general
date: 2026-08-19
description: Gere código de barras PDF417 em C# rapidamente. Aprenda como gerar código
  de barras PDF417 em C# usando Aspose.BarCode com modo compacto e configurações personalizadas.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode c#
- Aspose.BarCode PDF417
- compact PDF417 barcode
- barcode X‑dimension
language: pt
lastmod: 2026-08-19
og_description: Gere código de barras PDF417 em C# com Aspose.BarCode. Este tutorial
  mostra como gerar código de barras PDF417 em C# no modo compacto, definir a dimensão
  X e salvar como PNG.
og_image_alt: Screenshot of a compact PDF417 barcode saved as PNG
og_title: Gerar código de barras PDF417 em C# – guia passo a passo
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    barcode C# using Aspose.BarCode with compact mode and custom settings.
  headline: Generate PDF417 barcode in C# – complete guide with compact layout
  type: TechArticle
- description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    barcode C# using Aspose.BarCode with compact mode and custom settings.
  name: Generate PDF417 barcode in C# – complete guide with compact layout
  steps:
  - name: Why each line matters
    text: '* **`EncodeTypes.Pdf417`** – selects the PDF417 symbology, which supports
      up to ~1.1 KB of data. * **`XDimension.Pixels = 2`** – sets the basic bar width.
      Smaller values make the barcode thinner; larger values improve readability on
      low‑resolution devices. * **`Pdf417.Columns = 3`** – limits the num'
  - name: 4️⃣ Generate a high‑density PDF417 for printing
    text: 'If you need a barcode that fits on a small label, increase the column count
      and lower the X‑dimension:'
  - name: 5️⃣ Change the output format to SVG for vector scaling
    text: '```csharp generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
      ```'
  - name: 6️⃣ Encode binary data (e.g., a byte array)
    text: 'If you need to embed binary payloads, convert them to a Base64 string first:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Gerar código de barras PDF417 em C# – guia completo com layout compacto
url: /pt/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide-with-compact-lay/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gerar código de barras PDF417 em C# – guia completo

Se você precisa **gerar código de barras PDF417** em uma aplicação .NET, este tutorial mostra exatamente como fazer isso. Você verá um exemplo conciso, pronto para produção, que cria um código de barras PDF417 compacto, personaliza a dimensão X e salva o resultado como uma imagem PNG.

Gerar um código de barras PDF417 é comum quando você tem que codificar grandes quantidades de dados — como informações de tickets, manifestos de envio ou documentos de identidade — em um formato legível por máquina. Usar Aspose.BarCode torna o processo simples, e o código funciona com .NET 6+ ou .NET Framework 4.7.2 e posteriores.

Neste guia você vai:

* Instalar o pacote NuGet Aspose.BarCode.
* Escrever um programa C# autônomo que **gere código de barras PDF417** com um pequeno número de colunas e modo compacto (truncado).
* Ajustar a largura da barra (dimensão X) para renderização mais nítida.
* Salvar o código de barras como um arquivo PNG.
* Explorar variações, casos de borda e dicas de boas práticas.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

* Visual Studio 2022 (ou qualquer IDE C#) com .NET 6 SDK instalado.
* Acesso à internet para baixar o pacote NuGet **Aspose.BarCode**.
* Permissão de gravação em uma pasta onde o arquivo PNG será salvo.

Nenhuma biblioteca adicional é necessária; Aspose.BarCode lida com a codificação de imagens internamente.

## Etapa 1: Adicionar o pacote Aspose.BarCode

Abra seu projeto no Visual Studio, clique com o botão direito na solução e selecione **Manage NuGet Packages**. Procure por `Aspose.BarCode` e instale a versão estável mais recente.

```bash
dotnet add package Aspose.BarCode
```

> **Dica profissional:** Mantenha o pacote atualizado. Novas versões costumam incluir melhorias de desempenho e suporte às runtimes .NET mais recentes.

## Etapa 2: Criar um aplicativo console minimalista

Crie um novo projeto console C# se ainda não tiver um:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

Substitua o conteúdo de `Program.cs` pelo exemplo completo abaixo. Este programa demonstra **como gerar código de barras PDF417 C#** do início ao fim.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -----------------------------------------------------------------
            // 1️⃣  Define the data you want to encode.
            // -----------------------------------------------------------------
            // The string can contain Unicode characters; Aspose.BarCode handles
            // encoding automatically. Here we use characters with diacritics to
            // prove Unicode support.
            string data = "Åspóse.Barcóde©";

            // -----------------------------------------------------------------
            // 2️⃣  Initialise the BarcodeGenerator for PDF417.
            // -----------------------------------------------------------------
            // EncodeTypes.Pdf417 tells the library which symbology to use.
            // The constructor also accepts the data to encode.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // -----------------------------------------------------------------
            // 3️⃣  Configure visual parameters.
            // -----------------------------------------------------------------
            // • XDimension controls the bar width in pixels. A value of 2 gives
            //   a clear, readable barcode on most screens.
            // • Columns define how many data columns the barcode will use.
            //   Fewer columns produce a more compact image but increase the
            //   number of rows.
            // • Truncate enables “compact mode”, which removes the trailing
            //   stop pattern and reduces the overall size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true; // compact mode

            // -----------------------------------------------------------------
            // 4️⃣  Choose the output format and save the image.
            // -----------------------------------------------------------------
            // BarCodeImageFormat.Png yields a lossless PNG file that works
            // well for web, print, and further image processing.
            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to: {outputPath}");
        }
    }
}
```

### Por que cada linha importa

* **`EncodeTypes.Pdf417`** – seleciona a simbologia PDF417, que suporta até ~1,1 KB de dados.
* **`XDimension.Pixels = 2`** – define a largura básica da barra. Valores menores deixam o código de barras mais fino; valores maiores melhoram a legibilidade em dispositivos de baixa resolução.
* **`Pdf417.Columns = 3`** – limita o número de colunas, forçando o gerador a usar mais linhas, o que resulta em um código de barras mais alto, porém mais estreito.
* **`Pdf417.Truncate = true`** – ativa o modo compacto, removendo o padrão de parada e reduzindo a imagem sem perder a integridade dos dados.
* **`Save(..., BarCodeImageFormat.Png)`** – grava um arquivo PNG. Você também pode escolher `Jpeg`, `Bmp` ou `Svg` conforme as necessidades posteriores.

Execute o programa:

```bash
dotnet run
```

Você deverá ver a saída no console confirmando o local do arquivo, e a pasta conterá `CompactPdf417.png`. Abrir o PNG mostrará um código de barras PDF417 compacto e nítido que codifica a string Unicode.

## Etapa 3: Verificar o código de barras (opcional, mas recomendado)

Para garantir que o código de barras seja legível, você pode usar qualquer aplicativo scanner PDF417 padrão em um smartphone ou uma biblioteca decodificadora de desktop. O texto codificado deve corresponder exatamente à string original `data`, incluindo os caracteres especiais.

Se você encontrar problemas de decodificação:

* Aumente o `XDimension` para 3 ou 4 pixels.
* Reduza o número de colunas (por exemplo, defina `Columns = 2`).
* Desative `Truncate` (`Truncate = false`) para adicionar o padrão de parada.

Esses ajustes trocam tamanho por legibilidade, o que é útil para impressoras ou scanners de baixa resolução.

## Etapa 4: Explorar variações comuns

### 4️⃣ Gerar um PDF417 de alta densidade para impressão

Se precisar de um código de barras que caiba em uma etiqueta pequena, aumente a contagem de colunas e diminua a dimensão X:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 1;
generator.Parameters.Barcode.Pdf417.Columns = 6;
generator.Parameters.Barcode.Pdf417.Truncate = false; // keep full pattern
```

### 5️⃣ Alterar o formato de saída para SVG para dimensionamento vetorial

```csharp
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

A saída SVG escala sem perda de qualidade, perfeita para páginas web responsivas.

### 6️⃣ Codificar dados binários (ex.: um array de bytes)

Se precisar incorporar payloads binários, converta‑os primeiro para uma string Base64:

```csharp
byte[] payload = new byte[] { 0x01, 0xFF, 0xA5 };
string base64 = Convert.ToBase64String(payload);
generator = new BarcodeGenerator(EncodeTypes.Pdf417, base64);
```

O código de barras agora transporta a informação binária, e o decodificador deve reverter a etapa Base64.

## Perguntas frequentes

| Pergunta | Resposta |
|----------|----------|
| **Posso gerar PDF417 sem Aspose?** | Sim, outras bibliotecas como ZXing.Net ou Dynamsoft existem, mas Aspose.BarCode oferece controle de layout mais rico (colunas, truncamento) e melhor tratamento de Unicode. |
| **Qual é o comprimento máximo de dados?** | PDF417 pode codificar até 1.108 bytes (≈ 1 KB) de dados binários. Se ultrapassar isso, considere dividir os dados em vários códigos de barras. |
| **O modo compacto está em conformidade com os padrões?** | PDF417 truncado faz parte da especificação ISO/IEC 15438 e é amplamente suportado, mas verifique se o scanner alvo o suporta explicitamente. |
| **Como altero a cor de fundo?** | Defina `generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;` e `generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Black;` antes de salvar. |

## Conclusão

Agora você sabe **como gerar código de barras PDF417 C#** usando Aspose.BarCode, como ajustar finamente a dimensão X, habilitar o modo compacto e exportar o resultado como uma imagem PNG. O exemplo completo e executável pode ser copiado para qualquer projeto .NET, e as variações mostradas permitem adaptar o código de barras para impressão, web ou cenários de payload binário.

Próximos passos que você pode explorar:

* Integrar a geração de código de barras em uma API ASP.NET Core que retorne a imagem sob demanda.
* Combinar PDF417 com códigos QR na mesma etiqueta para leitura de formato duplo.
* Usar a classe `Reader` do Aspose.BarCode para decodificar a imagem gerada e verificar os dados programaticamente.

Boa codificação e aproveite a flexibilidade que as soluções de **gerar código de barras PDF417** trazem para suas aplicações!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Generate Barcode Image with Supplemental Space Customization using Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}