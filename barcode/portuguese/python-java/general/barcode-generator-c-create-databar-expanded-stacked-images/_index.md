---
category: general
date: 2026-07-24
description: Tutorial de Gerador de Código de Barras em C# que mostra como gerar a
  imagem do código de barras, definir colunas, definir linhas e criar código de barras
  Databar em apenas algumas linhas de código.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- generate barcode image
- how to set columns
- how to set rows
- create databar barcode
language: pt
lastmod: 2026-07-24
og_description: O tutorial de Gerador de Código de Barras em C# orienta você na geração
  de imagens de códigos de barras, na configuração de colunas e linhas e na criação
  de um código de barras Databar com exemplos de código claros.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: Gerador de Código de Barras C# – Crie Códigos DataBar Empilhados Rapidamente
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Barcode Generator C# tutorial that shows how to generate barcode image,
    set columns, set rows, and create Databar barcode in just a few lines of code.
  headline: Barcode Generator C# – Create DataBar Expanded Stacked Images
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Gerador de Código de Barras C# – Criar Imagens DataBar Expandido Empilhado
url: /pt/python-java/general/barcode-generator-c-create-databar-expanded-stacked-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gerador de Código de Barras C# – Guia Completo para DataBar Expanded Stacked

Já se perguntou como usar **barcode generator c#** para gerar imagens nítidas e legíveis em segundos? Talvez você tenha ficado olhando para um projeto em branco, sem saber onde as colunas ou linhas devem ficar, ou como realmente *generate barcode image* arquivos sem dor de cabeça. Bem, você está no lugar certo. Neste tutorial vamos configurar um pequeno aplicativo de console, criar um código de barras DataBar Expanded Stacked, ajustar seu layout e salvar o resultado como PNGs — tudo com a biblioteca **barcode generator c#**.

Vamos cobrir tudo o que você precisa saber: instalar o pacote, configurar colunas e linhas (sim, vamos responder *how to set columns* e *how to set rows*), e finalmente como **create databar barcode** objetos que você pode inserir em faturas, tickets ou qualquer coisa que precise de um rótulo legível por máquina. Nenhuma documentação externa é necessária; basta copiar‑colar, executar, e você verá dois arquivos PNG aparecerem na sua pasta.

## O Que Você Precisa

- .NET 6.0 SDK ou posterior (o código funciona no .NET Core, .NET Framework e .NET 5+)
- Um novo projeto de console (`dotnet new console`) – você também pode usar o Visual Studio se preferir uma interface gráfica.
- O pacote NuGet Aspose.BarCode for .NET (a biblioteca que alimenta **barcode generator c#**). Instale-o com:

```bash
dotnet add package Aspose.BarCode
```

É isso. Depois que o pacote for restaurado, você está pronto para começar.

## Gerador de Código de Barras C# – Configurando o Projeto

Primeiro, vamos trazer os namespaces necessários para o escopo e criar um método auxiliar que manterá nossa rotina principal organizada.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Folder where PNG files will be saved
        string outputFolder = Environment.CurrentDirectory;

        // Build the first barcode with custom columns
        GenerateDatabarWithColumns(outputFolder, columns: 4);

        // Build the second barcode with custom rows
        GenerateDatabarWithRows(outputFolder, rows: 3);
    }

    // -----------------------------------------------------------------
    // Helper: creates a DataBar Expanded Stacked barcode and sets columns
    // -----------------------------------------------------------------
    static void GenerateDatabarWithColumns(string folder, int columns)
    {
        // Step 1: Create a DataBar Expanded Stacked barcode generator with the desired text
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // Step 2: Configure the barcode to use the supplied number of columns
        // This answers the “how to set columns” question.
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = columns;

        // Step 3: Save the barcode image as PNG – this is the “generate barcode image” part.
        string filePath = System.IO.Path.Combine(folder, $"DatabarCols{columns}.png");
        barcodeGenerator.Save(filePath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ Created barcode with {columns} columns: {filePath}");
    }

    // -----------------------------------------------------------------
    // Helper: creates a DataBar Expanded Stacked barcode and sets rows
    // -----------------------------------------------------------------
    static void GenerateDatabarWithRows(string folder, int rows)
    {
        // Step 4: Create another generator for the same barcode type and text
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // Step 5: Configure the barcode to use the supplied number of rows
        // This answers the “how to set rows” query.
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = rows;

        // Step 6: Save the second barcode image as PNG
        string filePath = System.IO.Path.Combine(folder, $"DatabarRows{rows}.png");
        barcodeGenerator.Save(filePath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ Created barcode with {rows} rows: {filePath}");
    }
}
```

### Por Que Esta Estrutura Funciona

- **Separação de responsabilidades** – cada auxiliar foca em uma única configuração (colunas vs. linhas). Isso torna o código mais fácil de ler e reutilizar.
- **Parâmetros explícitos** – passamos `columns` ou `rows` como argumentos, assim você pode chamar o mesmo método com qualquer valor sem editar o corpo.
- **Feedback imediato** – `Console.WriteLine` informa exatamente onde o arquivo foi salvo, o que é útil ao executar o programa a partir de um terminal.

## Como Definir Colunas para DataBar Expanded Stacked

A propriedade `DataBar.Columns` é o controle que determina quantas fatias verticais o código de barras terá. O padrão é `4`, mas você pode precisar de `2` ou `6` dependendo da quantidade de dados que codifica ou dos requisitos do scanner. Aqui está um trecho rápido que isola a lógica de definição de colunas:

```csharp
var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "Sample Text");
generator.Parameters.Barcode.DataBar.Columns = 5;   // ← change this number as needed
generator.Save("databar_columns5.png", BarCodeImageFormat.Png);
```

**Dica profissional:** Quando você aumenta as colunas, a largura total do código de barras cresce proporcionalmente. Se você pretende incorporar a imagem em um PDF ou página web, certifique‑se de que o contêiner pode acomodar a largura extra, caso contrário o scanner pode ler incorretamente.

## Como Definir Linhas para DataBar Expanded Stacked

As linhas funcionam da mesma forma, mas afetam a altura do código de barras. A contagem padrão de linhas é `3`. Se o seu rótulo tem espaço vertical limitado, você pode reduzi‑la para `2`. Por outro lado, mais linhas podem melhorar a legibilidade em impressoras de baixa resolução.

```csharp
var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "Sample Text");
generator.Parameters.Barcode.DataBar.Rows = 2;   // ← adjust rows here
generator.Save("databar_rows2.png", BarCodeImageFormat.Png);
```

**Atenção:** Definir linhas para um valor menor que o mínimo necessário para os dados codificados causará uma exceção em tempo de execução. A biblioteca lança `ArgumentException` com uma mensagem clara, então você saberá instantaneamente se a configuração é inválida.

## Gerar Imagem de Código de Barras – Salvando como PNG

Ambos os auxiliares acima terminam com uma chamada a `Save`. O enum `BarCodeImageFormat.Png` indica ao Aspose.BarCode que gere um arquivo PNG sem perdas, ideal para a maioria dos cenários de leitura porque preserva bordas nítidas. Se você preferir outro formato (JPEG para web, BMP para sistemas legados), basta trocar o valor do enum — nenhuma outra alteração de código é necessária.

```csharp
generator.Save("mybarcode.jpeg", BarCodeImageFormat.Jpeg);
```

Os PNGs gerados se parecem com isto (imagine a imagem; o texto alternativo abaixo a descreve):

> **Texto alternativo para as imagens geradas:** *Código de barras DataBar Expanded Stacked com 4 colunas (esquerda) e 3 linhas (direita), renderizado em preto de alto contraste sobre fundo transparente.*

## Criar Código de Barras DataBar – Exemplo Completo Funcional

Juntando tudo, aqui está uma versão compacta que você pode inserir diretamente em `Program.cs`. Ela demonstra tanto a configuração de colunas quanto de linhas, além de uma rápida verificação de integridade de que os arquivos existem após a gravação.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Demo
{
    static void Main()
    {
        string outDir = Directory.GetCurrentDirectory();

        // ---------- Create barcode with custom columns ----------
        var colGen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked,
                                          "Databar Expanded Stacked long");
        colGen.Parameters.Barcode.DataBar.Columns = 4;   // how to set columns
        string colPath = Path.Combine(outDir, "DatabarCols4.png");
        colGen.Save(colPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved column barcode → {colPath}");

        // ---------- Create barcode with custom rows ----------
        var rowGen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked,
                                          "Databar Expanded Stacked long");
        rowGen.Parameters.Barcode.DataBar.Rows = 3;      // how to set rows
        string rowPath = Path.Combine(outDir, "DatabarRows3.png");
        rowGen.Save(rowPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved row barcode → {rowPath}");

        // ---------- Verify files exist ----------
        Console.WriteLine(File.Exists(colPath)
            ? "✅ Column image generated successfully."
            : "❌ Column image missing.");
        Console.WriteLine(File.Exists(rowPath)
            ? "✅ Row image generated successfully."
            : "❌ Row image missing.");
    }
}
```

### Saída Esperada

Ao executar o programa (`dotnet run`), você deverá ver linhas no console semelhantes a:

```
Saved column barcode → C:\MyProject\DatabarCols4.png
Saved row barcode → C:\MyProject\DatabarRows3.png
✅ Column image generated successfully.
✅ Row image generated successfully.
```

Abra os dois arquivos PNG em qualquer visualizador de imagens; você notará que o arquivo da esquerda tem quatro módulos verticais (colunas) enquanto o da direita tem três módulos de altura (linhas). Ambos são perfeitamente legíveis por qualquer leitor padrão de DataBar.

## Armadilhas Comuns & Como Evitá‑las

| Sintoma | Causa Provável | Correção |
|---------|----------------|----------|
| `ArgumentException: Columns value is out of range` | Colunas definidas como 0 ou > 8 (a biblioteca limita a 8). | Use valores entre **1** e **8**. |
| O código de barras aparece borrado no PDF | PNG salvo com DPI padrão (96) e depois dimensionado. | Use `generator.Parameters.ImageResolution = 300;` antes de salvar. |
| O scanner falha na configuração apenas de linhas | Linhas alteradas mas colunas deixadas no padrão que não correspondem ao comprimento dos dados. | Ajuste tanto linhas **quanto** colunas juntas, ou deixe a biblioteca dimensionar automaticamente omitindo as configurações manuais. |

## Próximos Passos

Agora que você sabe como **generate barcode image**, **set columns**, **set rows**, e **create databar barcode** com **barcode generator c#**, você pode:

- Incorporar os PNGs em PDFs usando `Aspose.PDF` ou `iTextSharp`.
- Mudar para `EncodeTypes.DatabarLimited` se precisar de uma pegada menor.
- Experimentar cores (`generator.Parameters.Barcode.ForeColor = Color.Blue`).
- Adicionar códigos QR ou outras simbologias no mesmo projeto — Aspose.BarCode suporta mais de 150 tipos.

Se encontrar algum problema, deixe um comentário abaixo ou consulte a documentação oficial do Aspose.BarCode (a referência da API é exaustiva e inclui dezenas de exemplos de código ao vivo). Boa codificação, e que seus scanners nunca percam um ponto!

## O Que Você Deve Aprender a Seguir?

Os tutoriais a seguir cobrem tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Create barcode image c# – Configure Codablock F Rows & Columns](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}