---
category: general
date: 2026-07-24
description: Gere código de barras PDF417 em C# usando Aspose.BarCode. Aprenda a criar
  código de barras PDF417 em C# com modo compacto em minutos.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- create pdf417 barcode c#
- c# barcode generator pdf417
- how to generate pdf417 barcode
language: pt
lastmod: 2026-07-24
og_description: Gere código de barras PDF417 em C# rapidamente com Aspose.BarCode.
  Este tutorial mostra como criar código de barras PDF417 em C# no modo compacto,
  abordando configuração, código e verificação.
og_image_alt: Screenshot of generated compact PDF417 barcode saved as PNG using C#
  code
og_title: Gerar código de barras PDF417 em C# – Guia rápido
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Generate PDF417 barcode in C# using Aspose.BarCode. Learn how to create
    PDF417 barcode C# with compact mode in minutes.
  headline: Generate PDF417 Barcode in C# – Create PDF417 Barcode C#
  type: TechArticle
- description: Generate PDF417 barcode in C# using Aspose.BarCode. Learn how to create
    PDF417 barcode C# with compact mode in minutes.
  name: Generate PDF417 Barcode in C# – Create PDF417 Barcode C#
  steps:
  - name: '**Data definition** – PDF417 can store up to ~1850 characters, but we keep
      it short for the demo. Unicode support means those accented characters won’t
      break anything.'
    text: '**Data definition** – PDF417 can store up to ~1850 characters, but we keep
      it short for the demo. Unicode support means those accented characters won’t
      break anything.'
  - name: '**Generator construction** – The `EncodeTypes.Pdf417` enum value tells
      Aspose which symbology to use; swapping it for `EncodeTypes.QR` would give you
      a QR code instead.'
    text: '**Generator construction** – The `EncodeTypes.Pdf417` enum value tells
      Aspose which symbology to use; swapping it for `EncodeTypes.QR` would give you
      a QR code instead.'
  - name: '**X‑dimension** – This controls the width of each module (the tiny squares
      that make up the barcode). A value of `2` pixels yields a crisp image that’s
      still readable when printed at 300 dpi.'
    text: '**X‑dimension** – This controls the width of each module (the tiny squares
      that make up the barcode). A value of `2` pixels yields a crisp image that’s
      still readable when printed at 300 dpi.'
  - name: '**PDF417 options** – `Columns` influences the barcode’s aspect ratio; fewer
      columns make the image taller, which can be useful for receipts. `Truncate`
      (also called *Compact mode*) removes the start/stop pattern padding, reducing
      file size without sacrificing data integrity.'
    text: '**PDF417 options** – `Columns` influences the barcode’s aspect ratio; fewer
      columns make the image taller, which can be useful for receipts. `Truncate`
      (also called *Compact mode*) removes the start/stop pattern padding, reducing
      file size without sacrificing data integrity.'
  - name: '**Output path** – Using `Environment.CurrentDirectory` ensures the image
      lands next to the executable, making it easy to locate during development.'
    text: '**Output path** – Using `Environment.CurrentDirectory` ensures the image
      lands next to the executable, making it easy to locate during development.'
  - name: '**Saving** – `BarCodeImageFormat.Png` gives lossless quality, perfect for
      further processing or embedding in PDFs.'
    text: '**Saving** – `BarCodeImageFormat.Png` gives lossless quality, perfect for
      further processing or embedding in PDFs.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Gerar código de barras PDF417 em C# – Criar código de barras PDF417 C#
url: /pt/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-create-pdf417-barcode-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gerar Código de Barras PDF417 em C# – Guia Completo de Programação

Já se perguntou como **gerar código de barras PDF417** em uma aplicação C# sem ficar vasculhando inúmeros tópicos de fórum? Você não está sozinho. Seja construindo um sistema de bilhetagem, um crachá de identidade seguro ou apenas precisando de uma maneira rápida de incorporar dados em um formato imprimível, dominar o formato PDF417 pode economizar horas de tentativa‑e‑erro.

Neste guia vamos percorrer um **exemplo completo, pronto‑para‑executar** que mostra exatamente como **criar código de barras PDF417 C#** usando a popular biblioteca Aspose.BarCode. Cobriremos tudo, desde a instalação do pacote NuGet até o ajuste do modo compacto, para que você possa copiar‑colar o código e ver os resultados instantaneamente.

## O que você vai aprender

- Como configurar a biblioteca Aspose.BarCode em um projeto .NET.  
- As instruções C# exatas necessárias para **gerar código de barras PDF417** com texto personalizado, tamanho de módulo e contagem de colunas.  
- Por que alternar a opção *Compact* (Truncate) é importante para dados densos.  
- Como salvar o código de barras como PNG e verificar a saída.  

Nenhuma experiência prévia com códigos de barras é necessária; apenas um entendimento básico de C# e Visual Studio (ou qualquer IDE de sua preferência). Ao final, você terá um método reutilizável que pode ser inserido em qualquer projeto que precise de uma imagem PDF417.

## Pré‑requisitos

| Requisito | Por que é importante |
|-----------|----------------------|
| .NET 6.0 ou posterior (ou .NET Framework 4.7+) | Aspose.BarCode suporta ambos; runtimes mais recentes oferecem melhor desempenho. |
| Visual Studio 2022 (ou VS Code com extensões C#) | Fornece IntelliSense e depuração fácil. |
| Conexão com a Internet (para a primeira restauração do NuGet) | A biblioteca é obtida do NuGet.org. |
| Conhecimento básico de C# | Necessário para entender estruturas de classes e chamadas de método. |

Se você já possui esses itens, ótimo—vamos começar.

## Instalar o Pacote NuGet Aspose.BarCode

Abra a pasta do seu projeto em um terminal e execute:

```bash
dotnet add package Aspose.BarCode
```

Ou, dentro do Visual Studio, clique com o botão direito em **Dependencies → Manage NuGet Packages**, procure por *Aspose.BarCode* e clique em **Install**. Essa única linha traz todos os tipos que usaremos, incluindo `BarcodeGenerator`, `EncodeTypes` e `BarCodeImageFormat`.

> **Dica profissional:** Após a instalação, limpe e reconstrua a solução para garantir que o assembly esteja referenciado corretamente.

## Gerar Código de Barras PDF417 – Configuração e Dependências

Primeiro de tudo: precisamos de um bloco `using` que traga os namespaces relevantes para o escopo.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Esses namespaces nos dão acesso à classe geradora e à enumeração dos tipos de código de barras. Nada sofisticado—apenas três linhas, e já podemos começar a criar o código de barras.

## Criar Código de Barras PDF417 C# – Implementação Passo a Passo

Abaixo está um **programa de console autônomo** que cria um código de barras PDF417 compacto a partir da string `"Åspóse.Barcóde©"` e o salva como `CompactPdf417.png`. Sinta-se à vontade para substituir o texto por qualquer coisa que precisar; o gerador lida com caracteres Unicode nativamente.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Define the data you want to encode.
            string data = "Åspóse.Barcóde©";

            // 2️⃣ Initialise the generator for PDF417.
            //    EncodeTypes.Pdf417 tells Aspose we want a PDF417 barcode.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // 3️⃣ Adjust the module (X‑dimension) size.
            //    Smaller values give a tighter image; 2 pixels works well for most screens.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Configure PDF417‑specific options.
            //    • Columns = 3 → fewer columns, taller barcode.
            //    • Truncate = true → enables Compact mode, which removes unnecessary padding.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Choose the output folder – adjust as needed.
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "CompactPdf417.png");

            // 6️⃣ Save the image as PNG.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ PDF417 barcode saved to: {outputPath}");
        }
    }
}
```

### Por que cada passo importa

1. **Definição dos dados** – PDF417 pode armazenar até ~1850 caracteres, mas mantemos curto para a demonstração. O suporte a Unicode garante que os caracteres acentuados não quebrem nada.  
2. **Construção do gerador** – O valor de enum `EncodeTypes.Pdf417` indica ao Aspose qual simbologia usar; trocá‑lo por `EncodeTypes.QR` geraria um QR code em vez disso.  
3. **X‑dimension** – Controla a largura de cada módulo (os quadradinhos que compõem o código de barras). Um valor de `2` pixels produz uma imagem nítida que ainda é legível quando impressa a 300 dpi.  
4. **Opções PDF417** – `Columns` influencia a proporção do código de barras; menos colunas tornam a imagem mais alta, o que pode ser útil para recibos. `Truncate` (também chamado *Compact mode*) remove o preenchimento do padrão de início/fim, reduzindo o tamanho do arquivo sem sacrificar a integridade dos dados.  
5. **Caminho de saída** – Usar `Environment.CurrentDirectory` garante que a imagem seja salva ao lado do executável, facilitando a localização durante o desenvolvimento.  
6. **Salvamento** – `BarCodeImageFormat.Png` oferece qualidade sem perdas, perfeito para processamento adicional ou incorporação em PDFs.

Execute o programa (`dotnet run` ou pressione **F5** no Visual Studio). Após alguns segundos você verá uma mensagem no console confirmando a localização do arquivo, e o PNG aparecerá na pasta do seu projeto.

![Generate PDF417 barcode example](generated-pdf417.png)

*Texto alternativo da imagem: exemplo de geração de código de barras pdf417 – imagem PNG de um código de barras PDF417 compacto criado com C#.*

## Configurar Modo Compacto – opções do gerador de código de barras pdf417 c#

Se precisar de um código de barras maior (talvez para leitura à distância), ajuste as propriedades `Columns` e `Rows`. Aqui está um trecho rápido que demonstra configurações alternativas:

```csharp
// Increase columns for a wider, shorter barcode.
generator.Parameters.Barcode.Pdf417.Columns = 6;

// Disable Compact mode if the scanning hardware struggles with it.
generator.Parameters.Barcode.Pdf417.Truncate = false;

// Optionally set error correction level (0–8). Higher values increase redundancy.
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;
```

> **Pergunta comum:** *Desativar Truncate quebra scanners existentes?*  
> Normalmente não. A maioria dos scanners modernos entende tanto o PDF417 em tamanho completo quanto o compacto. Contudo, se você estiver mirando hardware legado, deixe `Truncate` definido como `false`.

## Salvar e Verificar – como gerar saída de código de barras pdf417

Depois de salvar, você pode abrir o PNG com qualquer visualizador de imagens. Para confirmar que o código de barras codifica os dados pretendidos, use o `BarCodeReader` da Aspose:



## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [java barcode library – Add barcode to PDF using Aspose](/barcode/english/java/barcode-basics/adding-barcode-to-pdf-document/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}