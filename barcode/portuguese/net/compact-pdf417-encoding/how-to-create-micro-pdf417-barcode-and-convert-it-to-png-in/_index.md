---
category: general
date: 2026-10-12
description: Aprenda a criar código de barras micro PDF417 e converter o código de
  barras para PNG usando C#. Guia passo a passo com código completo e dicas.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro PDF417 barcode
- convert barcode to PNG
- micro PDF417 C# example
- GS1 micro PDF417 generation
- barcode image settings
language: pt
lastmod: 2026-10-12
og_description: Crie um código de barras micro PDF417 e converta-o para PNG com C#.
  Siga este guia completo para gerar as versões padrão e GS1.
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: Crie código de barras micro PDF417 e converta para PNG – tutorial C#
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn to create micro PDF417 barcode and convert barcode to PNG using
    C#. Step‑by‑step guide with full code and tips.
  headline: How to create micro PDF417 barcode and convert it to PNG in C#
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Como criar código de barras micro PDF417 e convertê-lo para PNG em C#
url: /pt/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-convert-it-to-png-in/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar micro PDF417 barcode e convertê-lo para PNG em C#

Se você precisa **criar micro PDF417 barcode** em uma aplicação .NET, este tutorial mostra exatamente como fazer. Você verá um exemplo completo e executável que gera tanto um barcode Micro PDF417 padrão quanto uma versão compatível com GS1, e então **converte o barcode para PNG** para uso posterior, como impressão ou exibição na web.

Gerar um barcode é mais do que chamar um único método — escolher o tamanho correto do módulo, a contagem de colunas e o formato de codificação determina a confiabilidade da leitura. Ao final deste guia, você entenderá por que cada configuração importa e como ajustá‑las para seus próprios projetos.

## Pré-requisitos

| Requisito | Motivo |
|-----------|--------|
| .NET 6.0 SDK or later | Fornece o runtime para o aplicativo console em C# |
| Visual Studio 2022 (or any C# IDE) | Facilita a edição e depuração |
| **Aspose.BarCode for .NET** NuGet package | Fornece as classes `BarcodeGenerator`, `EncodeTypes` e `BarCodeImageFormat` |
| Write permission to the output folder | Necessário para chamadas `Save` que criam arquivos PNG |

Você pode adicionar o pacote Aspose.BarCode via CLI:

```bash
dotnet add package Aspose.BarCode
```

## Etapa 1: Configurar um projeto console mínimo

Crie um novo projeto console e faça referência à biblioteca de barcode. O `Program.cs` a seguir contém todo o código necessário; nenhum arquivo externo é requerido.

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generation classes
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace MicroPdf417Demo
{
    internal class Program
    {
        static void Main()
        {
            // Define the folder where PNG files will be saved
            string outputFolder = Environment.CurrentDirectory;

            // ------------------------------------------------------------
            // 1️⃣ Create a Micro PDF417 barcode generator with plain data
            // ------------------------------------------------------------
            BarcodeGenerator microGen = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,          // Micro PDF417 symbology
                "Micro data");                    // Simple alphanumeric payload

            // ------------------------------------------------------------
            // 2️⃣ Adjust the X dimension (module size) and set column count
            // ------------------------------------------------------------
            // XDimension controls the physical size of each barcode module.
            // A value of 2 pixels gives a compact yet readable barcode.
            microGen.Parameters.Barcode.XDimension.Pixels = 2;

            // For Micro PDF417 you can limit the number of columns.
            // Four columns keep the barcode small enough for labels.
            microGen.Parameters.Barcode.Pdf417.Columns = 4;

            // ------------------------------------------------------------
            // 3️⃣ Convert barcode to PNG and save the image
            // ------------------------------------------------------------
            string microPath = System.IO.Path.Combine(outputFolder, "MicroPdf417.png");
            microGen.Save(microPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Standard Micro PDF417 saved to: {microPath}");

            // ------------------------------------------------------------
            // 4️⃣ Create a GS1 Micro PDF417 barcode with AI‑encoded data
            // ------------------------------------------------------------
            // GS1 syntax requires Application Identifiers (AIs) wrapped in parentheses.
            // Example: (01) – GTIN, (21) – serial number.
            BarcodeGenerator gs1MicroGen = new BarcodeGenerator(
                EncodeTypes.Gs1MicroPdf417,
                "(01)12345678901231(21)ABC123");

            // ------------------------------------------------------------
            // 5️⃣ Set the X dimension for the GS1 barcode (same as step 2)
            // ------------------------------------------------------------
            gs1MicroGen.Parameters.Barcode.XDimension.Pixels = 2;

            // ------------------------------------------------------------
            // 6️⃣ Convert barcode to PNG and save the GS1 image
            // ------------------------------------------------------------
            string gs1Path = System.IO.Path.Combine(outputFolder, "GS1MicroPdf417.png");
            gs1MicroGen.Save(gs1Path, BarCodeImageFormat.Png);
            Console.WriteLine($"GS1 Micro PDF417 saved to: {gs1Path}");

            // End of demo
            Console.WriteLine("Barcode generation complete.");
        }
    }
}
```

### Por que cada linha importa

* **`EncodeTypes.MicroPdf417` vs `EncodeTypes.Gs1MicroPdf417`** – O primeiro cria um barcode Micro PDF417 simples, enquanto o segundo segue os padrões GS1, incorporando Identificadores de Aplicação (AIs). Escolha com base em se seu sistema downstream espera dados GS1.  
* **`XDimension.Pixels = 2`** – Controla a largura do módulo. Valores menores criam uma imagem mais densa, mas podem ficar ilegíveis em scanners de baixa resolução. Dois pixels é um padrão seguro para a maioria das impressoras de etiquetas.  
* **`Pdf417.Columns = 4`** – O Micro PDF417 permite limitar as colunas, reduzindo a largura total. Quatro colunas mantêm o barcode compacto sem sacrificar a capacidade de dados para cargas curtas.  
* **`BarCodeImageFormat.Png`** – PNG preserva qualidade sem perdas, essencial para a clareza do barcode. Por isso **convertimos o barcode para PNG** em vez de JPEG.

## Etapa 2: Executar o programa e verificar a saída

1. Compile o projeto: `dotnet build`.  
2. Execute: `dotnet run`.

Você deverá ver mensagens no console semelhantes a:

```
Standard Micro PDF417 saved to: C:\Path\To\Project\MicroPdf417.png
GS1 Micro PDF417 saved to: C:\Path\To\Project\GS1MicroPdf417.png
Barcode generation complete.
```

Abra os arquivos PNG gerados com qualquer visualizador de imagens. Ambas as imagens exibem um barcode nítido e de alto contraste, pronto para leitura.

### Resultado visual esperado

| Tipo de barcode | Aparência |
|-----------------|-----------|
| **Micro PDF417** | Pequeno padrão retangular com 4 colunas, legível pela maioria dos scanners de barcode 2‑D. |
| **GS1 Micro PDF417** | Mesmo tamanho, mas codifica AIs GS1; um scanner que entende GS1 retornará o GTIN e o número de série. |

Se um scanner não conseguir ler a imagem, tente aumentar `XDimension.Pixels` para **3** ou **4**, ou reduzir a contagem de colunas para o Micro PDF417 padrão.

## Armadilhas comuns e como evitá‑las

| Problema | Causa | Correção |
|----------|-------|----------|
| Barcode borrado após impressão | Configurações de impressora com baixa DPI | Exporte o PNG em 300 dpi ou superior, ou deixe o driver da impressora lidar com o dimensionamento. |
| Scanner retorna “dados inválidos” | Formato de AI GS1 ausente ou malformado | Garanta que cada AI esteja entre parênteses e siga a especificação GS1 (ex.: `(01)` para GTIN‑14). |
| Arquivo de imagem não criado | Pasta de saída sem permissão de escrita | Execute o programa com privilégios elevados ou escolha uma pasta como `Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments)`. |
| Barcode muito grande para a etiqueta | Contagem padrão de colunas muito alta | Reduza `Pdf417.Columns` (ex.: para **3**) ou aumente `XDimension` para diminuir o tamanho geral. |

## Expandindo o exemplo

* **Formatos de imagem diferentes** – Substitua `BarCodeImageFormat.Png` por `Jpeg` ou `Bmp` se seu fluxo de trabalho exigir. PNG continua sendo a melhor escolha para qualidade sem perdas.  
* **Dados dinâmicos** – Passe a entrada do usuário ou valores de banco de dados ao construtor `BarcodeGenerator` para criar barcodes em tempo real.  
* **Geração em lote** – Envolva a lógica de criação em um loop que lê linhas de um arquivo CSV e salva cada barcode com um nome de arquivo único.  

## Conclusão

Agora você sabe como **criar micro PDF417 barcode** em C# e **converter barcode para PNG** tanto para cenários padrão quanto compatíveis com GS1. O código completo e executável demonstra as configurações essenciais — dimensão X, contagem de colunas e tipo de codificação — para que você possa adaptar a solução a qualquer projeto .NET que precise de barcodes 2‑D compactos e de alta qualidade.

*Próximos passos*: explore outras simbologias suportadas pelo Aspose.BarCode (ex.: QR, DataMatrix), experimente diferentes valores de `XDimension` para impressão em alta resolução, ou integre os PNGs gerados em uma API web que fornece barcodes sob demanda.

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como criar micro pdf417 barcode em C# e salvá‑lo como PNG](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-and-save-it-as-png/)
- [Criar barcode PNG em C# – guia completo para GS1 Micro PDF417](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [Gerar Micro PDF417 Barcode em C# – Guia Completo](/barcode/english/net/compact-pdf417-encoding/generate-micro-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}