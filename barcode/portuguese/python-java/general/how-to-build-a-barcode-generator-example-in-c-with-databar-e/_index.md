---
category: general
date: 2026-09-19
description: Exemplo de gerador de código de barras em C# mostrando como gerar código
  de barras em C# usando Aspose.BarCode para layouts de colunas e linhas.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- generate barcode c#
language: pt
lastmod: 2026-09-19
og_description: O exemplo de gerador de código de barras demonstra como gerar códigos
  de barras em C# com layouts de coluna e linha usando o Aspose.BarCode.
og_image_alt: C# barcode generator example output showing a DataBar Expanded Stacked
  barcode with 4 columns
og_title: exemplo de gerador de código de barras – crie códigos de barras DataBar
  Expanded Stacked em C#
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: barcode generator example in C# showing how to generate barcode C#
    using Aspose.BarCode for column and row layouts
  headline: How to build a barcode generator example in C# with DataBar Expanded Stacked
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Como criar um exemplo de gerador de código de barras em C# com DataBar Expanded
  Stacked
url: /pt/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-databar-e/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# exemplo de gerador de código de barras – criar códigos DataBar Expanded Stacked em C#

Se você precisa de um **exemplo de gerador de código de barras** que funcione em um projeto .NET, este guia mostra exatamente como gerar barcode C# usando a biblioteca Aspose.BarCode. Você verá como configurar um código DataBar Expanded Stacked tanto para um layout baseado em colunas quanto para um layout baseado em linhas, e receberá código pronto‑para‑executar que produz imagens PNG.

O tutorial cobre tudo, desde a instalação do pacote NuGet até a gravação das imagens finais, para que você possa copiar o código para sua própria solução sem pesquisas adicionais.

## O que você aprenderá

* Como instalar e referenciar Aspose.BarCode em um projeto C#.  
* Como criar um **exemplo de gerador de código de barras** que codifica uma string de dados longa.  
* Como definir um layout de 4 colunas e um layout de 3 linhas no mesmo tipo de código de barras.  
* Como salvar as imagens geradas como arquivos PNG.  

Ao final deste artigo você terá dois arquivos PNG prontos‑para‑uso: `ExpandedStackedCols4.png` (quatro colunas) e `ExpandedStackedRows3.png` (três linhas).

## Pré-requisitos

* .NET 6.0 SDK ou posterior (o código também funciona com .NET Framework 4.7.2).  
* Visual Studio 2022, VS Code ou qualquer IDE C# de sua preferência.  
* Acesso à internet para baixar o pacote NuGet **Aspose.BarCode**.  

Nenhum serviço externo adicional é necessário.

## Etapa 1: Instalar o pacote NuGet Aspose.BarCode

Abra um terminal na pasta do seu projeto e execute:

```bash
dotnet add package Aspose.BarCode
```

O comando adiciona a versão estável mais recente do Aspose.BarCode ao seu arquivo de projeto. Após a restauração do pacote, você pode referenciar seus namespaces nos arquivos de código C#.

## Etapa 2: Adicionar as diretivas `using` necessárias

Crie um novo aplicativo de console C# (ou adicione o código a um projeto existente) e inclua as seguintes instruções `using` no topo do arquivo:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Essas diretivas dão acesso à classe `BarcodeGenerator` e à enumeração `EncodeTypes` usadas no **exemplo de gerador de código de barras**.

## Etapa 3: Criar um exemplo de gerador de código de barras com layout de 4 colunas

A primeira parte do exemplo constrói um código DataBar Expanded Stacked que usa um arranjo de quatro colunas. O código abaixo segue exatamente os passos mostrados no snippet original, mas adiciona comentários que explicam por que cada linha é necessária.

```csharp
// Step 3.1: Initialise the generator with the desired barcode type and data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,   // DataBar Expanded Stacked type
    "Long data string");                  // The data you want to encode

// Step 3.2: Configure the barcode to use a 4‑column layout
generator.Parameters.Barcode.DataBar.Columns = 4;

// Step 3.3: Save the image as a PNG file
generator.Save("ExpandedStackedCols4.png", BarCodeImageFormat.Png);
```

**Por que isso funciona**

* `EncodeTypes.DatabarExpandedStacked` indica ao Aspose.BarCode que gere um símbolo DataBar Expanded Stacked, adequado para aplicações de varejo.  
* Definir `DataBar.Columns` como `4` força o gerador a dividir o símbolo em quatro seções verticais, melhorando a legibilidade em rótulos estreitos.  
* `Save` grava o código de barras no disco; o argumento `BarCodeImageFormat.Png` garante qualidade de imagem sem perdas.

Executar este bloco cria `ExpandedStackedCols4.png` no diretório de trabalho da aplicação. O arquivo contém um código de barras de alta resolução que pode ser escaneado por qualquer leitor padrão de DataBar.

## Etapa 4: Re‑inicializar o gerador para um layout diferente

Para demonstrar um layout baseado em linhas, você precisa de uma nova instância de `BarcodeGenerator`. Re‑inicializar garante que a configuração de coluna anterior não afete a nova configuração.

```csharp
// Step 4.1: Create a new generator with the same data string
generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Long data string");
```

## Etapa 5: Configurar o código de barras para usar um layout de 3 linhas

A API DataBar também suporta um arranjo em linhas. Definir a propriedade `Rows` determina quantas fatias horizontais o símbolo terá.

```csharp
// Step 5.1: Apply a 3‑row layout
generator.Parameters.Barcode.DataBar.Rows = 3;

// Step 5.2: Save the row‑oriented barcode
generator.Save("ExpandedStackedRows3.png", BarCodeImageFormat.Png);
```

**Por que você pode preferir linhas em vez de colunas**

Linhas são úteis quando a altura do rótulo é limitada, mas a largura é abundante. Um layout de três linhas comprime o código de barras verticalmente enquanto preserva a quantidade necessária de dados.

## Arquivo de código completo

Abaixo está um `Program.cs` completo e autocontido que você pode compilar e executar diretamente. Ele inclui tanto os exemplos de coluna quanto de linha, produzindo dois arquivos PNG com uma única execução.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeGeneratorExample
{
    class Program
    {
        static void Main(string[] args)
        {
            // Data to encode – replace with your own value if needed
            const string data = "Long data string";

            // ---------- Column layout (4 columns) ----------
            var columnGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                data);

            // Set 4‑column layout
            columnGenerator.Parameters.Barcode.DataBar.Columns = 4;

            // Save the column image
            columnGenerator.Save("ExpandedStackedCols4.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved ExpandedStackedCols4.png (4‑column layout)");

            // ---------- Row layout (3 rows) ----------
            var rowGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                data);

            // Set 3‑row layout
            rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

            // Save the row image
            rowGenerator.Save("ExpandedStackedRows3.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved ExpandedStackedRows3.png (3‑row layout)");
        }
    }
}
```

### Saída esperada

Após executar o programa, você verá duas mensagens no console confirmando a criação dos arquivos:

```
Saved ExpandedStackedCols4.png (4‑column layout)
Saved ExpandedStackedRows3.png (3‑row layout)
```

Ambos os arquivos PNG exibirão um código DataBar Expanded Stacked que codifica a string `"Long data string"`. Escanear qualquer uma das imagens com um leitor padrão de código de barras retornará os dados originais.

## Perguntas frequentes e casos de borda

| Pergunta | Resposta |
|----------|----------|
| **Posso mudar o formato da imagem?** | Sim. Substitua `BarCodeImageFormat.Png` por `Jpeg`, `Bmp` ou `Tiff` conforme suas necessidades. |
| **E se a string de dados for mais curta?** | O formato DataBar ajusta automaticamente o tamanho do símbolo; não é necessário modificar as configurações de layout. |
| **Como definir o tamanho do código de barras (largura/altura)?** | Use `generator.Parameters.Image.Width` e `generator.Parameters.Image.Height` antes de chamar `Save`. |
| **É possível adicionar uma legenda legível por humanos?** | Defina `generator.Parameters.Barcode.CodeText` e habilite `generator.Parameters.Barcode.CodeLocation = CodeLocation.Above`. |
| **Quais versões do .NET são suportadas?** | Aspose.BarCode suporta .NET Standard 2.0, .NET 5/6 e .NET Framework 4.6.1+. |

Abordar essas variações torna o **exemplo de gerador de código de barras** robusto o suficiente para uso em produção.

## Dicas profissionais

* **Reutilize o objeto generator apenas quando o layout permanecer o mesmo.** Criar uma nova instância para cada layout, como mostrado nas Etapas 4‑5, evita que propriedades indesejadas sejam herdadas.  
* **Valide o código de barras gerado** com `generator.Validate()` se precisar garantir conformidade com os padrões ISO/GS1.  
* **Processamento em lote:** Envolva a lógica de coluna e linha dentro de um loop que itere sobre uma lista de configurações de layout. Isso reduz a duplicação de código quando precisar de muitas variações.

## Conclusão

Este **exemplo de gerador de código de barras** demonstra como **gerar barcode C#** que produz tanto um código DataBar Expanded Stacked de 4 colunas quanto um de 3 linhas. Agora você tem um programa completo e executável, entende as propriedades principais (`Columns`, `Rows`) e possui dicas práticas para expandir a solução.

Em seguida, explore tópicos relacionados como **personalizar cores de código de barras**, **incorporar códigos de barras em documentos PDF** ou **gerar códigos QR com Aspose.BarCode**. Cada um desses assuntos se baseia nos mesmos princípios da API abordados aqui.

Sinta‑se à vontade para experimentar diferentes strings de dados, formatos de imagem e combinações de layout. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas em seus próprios projetos.

- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Generate Aspose.BarCode Databar barcode using .NET API – Row & Column Configuration](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}