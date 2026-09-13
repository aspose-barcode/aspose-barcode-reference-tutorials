---
category: general
date: 2026-09-13
description: Crie código de barras Databar empilhado em C# rapidamente usando Aspose.Barcode
  – aprenda a definir colunas, linhas e salvar imagens.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- Databar Expanded Stacked
- barcode columns
- barcode rows
- Aspose.Barcode for .NET
- C# barcode generator
language: pt
lastmod: 2026-09-13
og_description: Crie código de barras databar empilhado em C# usando Aspose.Barcode.
  Este guia mostra como configurar colunas, linhas e exportar imagens PNG.
og_image_alt: Screenshot of a generated Databar stacked barcode saved as PNG
og_title: Crie um Código de Barras Databar Empilhado em C# – Guia Completo Passo a
  Passo
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Create databar stacked barcode in C# quickly using Aspose.Barcode –
    learn to set columns, rows, and save images.
  headline: How to create databar stacked barcode in C# with Aspose.Barcode
  type: TechArticle
- description: Create databar stacked barcode in C# quickly using Aspose.Barcode –
    learn to set columns, rows, and save images.
  name: How to create databar stacked barcode in C# with Aspose.Barcode
  steps:
  - name: 'Create a new Console App project:'
    text: 'Create a new Console App project:'
  - name: 'Add the Aspose.Barcode package:'
    text: 'Add the Aspose.Barcode package:'
  - name: 'Open **Program.cs** and add the required `using` statements:'
    text: 'Open **Program.cs** and add the required `using` statements:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- Databar
title: Como criar um código de barras Databar empilhado em C# com Aspose.Barcode
url: /pt/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar databar stacked barcode em C# com Aspose.Barcode

Se você precisa **criar databar stacked barcode** em uma aplicação .NET, este guia fornece uma solução completa e pronta‑para‑executar. Você verá exatamente como configurar o número de colunas, ajustar linhas e salvar o resultado como um arquivo PNG — tudo com a biblioteca Aspose.Barcode for .NET.

Gerar um código de barras **Databar Expanded Stacked** não é um mistério depois que você entende o fluxo de trabalho de três etapas: instanciar o gerador, definir as dimensões desejadas e gravar a imagem no disco. As seções a seguir orientam você em cada parte, explicam por que as configurações são importantes e mostram o resultado final que pode ser verificado instantaneamente.

## Pré-requisitos

- **Visual Studio 2022** (ou qualquer IDE C#) com .NET 6+ instalado.
- **Aspose.Barcode for .NET** pacote NuGet (`Install-Package Aspose.Barcode`).
- Permissão de gravação em uma pasta onde os arquivos PNG serão salvos.

Nenhuma dependência adicional é necessária.

## Etapa 1: Configurar o projeto e adicionar Aspose.Barcode

1. Crie um novo projeto Console App:

   ```bash
   dotnet new console -n DatabarStackedDemo
   cd DatabarStackedDemo
   ```

2. Adicione o pacote Aspose.Barcode:

   ```bash
   dotnet add package Aspose.Barcode
   ```

3. Abra **Program.cs** e adicione as declarações `using` necessárias:

   ```csharp
   using Aspose.BarCode;
   using Aspose.BarCode.Generation;
   using System;
   ```

Essas etapas garantem que as classes **C# barcode generator** estejam disponíveis em seu código.

## Etapa 2: Criar um gerador para um Databar stacked barcode

O primeiro objeto que você precisa é um `BarcodeGenerator` configurado para a simbologia **Databar Expanded Stacked**. Este objeto é o ponto de entrada para todas as operações relacionadas a códigos de barras.

```csharp
// Step 2: Initialize a generator for Databar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, // Symbology
    "Databar Expanded Stacked long");   // Human‑readable text (optional)
```

**Por que isso importa:**  
`EncodeTypes.DatabarExpandedStacked` indica ao Aspose.Barcode para usar a versão empilhada da família DataBar, que é ideal para espaços de altura limitada, como recibos. O segundo argumento fornece os dados codificados no código de barras; você pode substituí-lo por qualquer string numérica ou alfanumérica que esteja em conformidade com o padrão DataBar.

## Etapa 3: Configurar colunas do código de barras e salvar a imagem

Um DataBar empilhado pode ser exibido usando um número configurável de **colunas**. O padrão é três, mas você pode precisar de quatro colunas para strings de dados mais longas. Ajuste a propriedade `Columns` antes de salvar.

```csharp
// Step 3: Set the barcode to use 4 columns (default rows) and save the image
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Choose an output folder that exists on your machine
string outputPathCols = @"YOUR_DIRECTORY\DatabarCols4.png";
barcodeGenerator.Save(outputPathCols, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 4 columns saved to {outputPathCols}");
```

**Explicação:**  
- `Parameters.Barcode.DataBar.Columns` influencia diretamente a segmentação horizontal do código de barras. Mais colunas criam uma imagem mais larga, mas mantêm a mesma altura.
- `Save` grava o código de barras em um arquivo PNG. Outros formatos (JPEG, BMP, SVG) também são suportados ao passar um valor diferente para `BarCodeImageFormat`.

## Etapa 4: Criar outro gerador e configurar linhas do código de barras

Às vezes, o ambiente de leitura requer um código de barras mais alto, o que você consegue aumentando o número de **linhas**. O trecho a seguir cria uma segunda instância do gerador, define três linhas e salva o resultado.

```csharp
// Step 4: Create a new generator for the same data but with 3 rows
BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the barcode to use 3 rows (default columns)
barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

// Save the image with rows configured
string outputPathRows = @"YOUR_DIRECTORY\DatabarRows3.png";
barcodeGeneratorRows.Save(outputPathRows, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 3 rows saved to {outputPathRows}");
```

**Por que uma instância separada?**  
Alterar `Rows` no mesmo `BarcodeGenerator` após a chamada de `Save` também funcionaria, mas criar uma nova instância mantém cada configuração isolada e torna o código mais fácil de ler — especialmente quando você expandir o tutorial para cobrir mais variações (por exemplo, diferentes strings de dados ou níveis de correção de erro).

## Etapa 5: Verificar os códigos de barras gerados

Abra os dois arquivos PNG que você acabou de criar. Você deverá ver:

- **DatabarCols4.png** – um código de barras mais largo, composto por quatro colunas verticais.
- **DatabarRows3.png** – um código de barras mais alto, composto por três linhas horizontais.

Ambas as imagens codificam o mesmo texto (`"Databar Expanded Stacked long"`), mas suas estruturas visuais diferem. Escaneie-as com qualquer scanner DataBar padrão ou um aplicativo móvel que suporte DataBar para confirmar que decodificam corretamente.

## Armadilhas comuns e dicas profissionais

| Problema | Por que acontece | Como evitar |
|----------|------------------|--------------|
| **Caminho de pasta incorreto** | `Save` lança `DirectoryNotFoundException` se o diretório não existir. | Use `Directory.CreateDirectory(Path.GetDirectoryName(outputPath))` antes de chamar `Save`. |
| **Muitas colunas/linhas** | As especificações do DataBar limitam colunas a 4 e linhas a 3. | Mantenha-se dentro da faixa permitida; caso contrário, Aspose.Barcode lançará `ArgumentOutOfRangeException`. |
| **Código de barras ilegível** | Baixa resolução da imagem pode deixar o código de barras borrado. | Aumente o DPI via `barcodeGenerator.Parameters.ImageResolution` se precisar de maior qualidade (ex.: 300 dpi). |
| **Formato de dados incorreto** | DataBar aceita apenas strings numéricas de até 13 dígitos em certos modos. | Valide sua string de entrada antes de passá‑la ao gerador. |

## Expandindo o exemplo

Agora que você pode **criar databar stacked barcode** com colunas e linhas personalizadas, talvez queira explorar:

- **Alterar cores de primeiro plano/fundo** (`barcodeGenerator.Parameters.Barcode.Color = Color.Blue;`).
- **Adicionar zona silenciosa** (`barcodeGenerator.Parameters.Barcode.Qz = 2;`).
- **Exportar para SVG** para renderização independente de resolução (`BarCodeImageFormat.Svg`).

Todas essas opções estão documentadas na [referência da API Aspose.Barcode for .NET](https://docs.aspose.com/barcode/net/).

## Código-fonte completo

Abaixo está o programa completo e executável que incorpora cada passo descrito acima. Copie‑o para o seu `Program.cs`, substitua `YOUR_DIRECTORY` por um caminho real e execute `dotnet run`.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;
using System.IO;

class Program
{
    static void Main()
    {
        // Ensure the output directory exists
        string outputDir = @"YOUR_DIRECTORY";
        Directory.CreateDirectory(outputDir);

        // -------------------------------------------------
        // Step 1: Generator for 4‑column stacked barcode
        // -------------------------------------------------
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 4 columns (default rows = 2)
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        string colsPath = Path.Combine(outputDir, "DatabarCols4.png");
        barcodeGenerator.Save(colsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved 4‑column barcode to {colsPath}");

        // -------------------------------------------------
        // Step 2: Generator for 3‑row stacked barcode
        // -------------------------------------------------
        BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 3 rows (default columns = 2)
        barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

        string rowsPath = Path.Combine(outputDir, "DatabarRows3.png");
        barcodeGeneratorRows.Save(rowsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved 3‑row barcode to {rowsPath}");
    }
}
```

Executar o programa gera dois arquivos PNG que demonstram como **colunas de código de barras** e **linhas de código de barras** afetam o layout visual de um símbolo **Databar Expanded Stacked**.

## Conclusão

Agora você sabe como **criar databar stacked barcode** em C# usando Aspose.Barcode for .NET. Ajustando as propriedades `Columns` e `Rows`, você pode gerar códigos de barras que se adequam a uma ampla variedade de restrições de espaço, mantendo a integridade dos dados. O exemplo cobre tudo, desde a configuração do projeto até a solução de problemas, proporcionando uma base sólida para cenários de códigos de barras mais avançados.

**Próximos passos:**  
- Experimente diferentes strings de dados e veja como os limites de colunas/linhas impactam a legibilidade.  
- Combine este código com uma API web para gerar códigos de barras sob demanda.  
- Explore outras simbologias (ex.: QR, Code128) usando o mesmo padrão `BarcodeGenerator`.

Feliz codificação, e que seus scans sejam sempre bem‑sucedidos!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Gerador de Código de Barras C# – Criar Imagens DataBar Expanded Stacked](/barcode/english/python-java/general/barcode-generator-c-create-databar-expanded-stacked-images/)
- [Guia de databar expanded stacked barcode – como gerar e dimensionar em C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Gerar código de barras Aspose.BarCode Databar usando API .NET – Configuração de Linha e Coluna](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}