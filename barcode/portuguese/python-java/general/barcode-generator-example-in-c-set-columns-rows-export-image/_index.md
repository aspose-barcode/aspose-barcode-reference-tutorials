---
category: general
date: 2026-07-15
description: Exemplo de gerador de código de barras em C# mostrando como definir colunas,
  como definir linhas e exportar a imagem do código de barras rapidamente. Siga este
  guia passo a passo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to set columns
- how to set rows
- export barcode image
- create barcode image c#
language: pt
lastmod: 2026-07-15
og_description: Exemplo de gerador de código de barras em C# demonstra como definir
  colunas, como definir linhas e exportar a imagem do código de barras. Aprenda todo
  o fluxo de trabalho em minutos.
og_image_alt: Screenshot of a barcode generator example showing column and row settings
  in C#
og_title: Exemplo de Gerador de Código de Barras em C# – Colunas, Linhas e Exportação
  de Imagem
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Barcode generator example in C# showing how to set columns, how to
    set rows, and export barcode image quickly. Follow this step‑by‑step guide.
  headline: Barcode Generator Example in C# – Set Columns, Rows & Export Image
  type: TechArticle
- description: Barcode generator example in C# showing how to set columns, how to
    set rows, and export barcode image quickly. Follow this step‑by‑step guide.
  name: Barcode Generator Example in C# – Set Columns, Rows & Export Image
  steps:
  - name: '**Add colors** – Set `generator.Parameters.Barcode.ForegroundColor` to
      `Color.Blue`.'
    text: '**Add colors** – Set `generator.Parameters.Barcode.ForegroundColor` to
      `Color.Blue`.'
  - name: '**Encode different data** – Pass a variable string instead of the hard‑coded
      `"Databar Expanded Stacked long"`.'
    text: '**Encode different data** – Pass a variable string instead of the hard‑coded
      `"Databar Expanded Stacked long"`.'
  - name: '**Batch processing** – Loop over a CSV file of product codes, generating
      a PNG for each.'
    text: '**Batch processing** – Loop over a CSV file of product codes, generating
      a PNG for each.'
  - name: '**Integrate with a web API** – Expose an endpoint that returns the barcode
      as a base64‑encoded string.'
    text: '**Integrate with a web API** – Expose an endpoint that returns the barcode
      as a base64‑encoded string.'
  type: HowTo
tags:
- barcode
- C#
- image export
title: Exemplo de Gerador de Código de Barras em C# – Definir Colunas, Linhas e Exportar
  Imagem
url: /pt/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Exemplo de Gerador de Código de Barras em C# – Guia Completo

Já se perguntou como criar um **exemplo de gerador de código de barras** em C# que permite ajustar colunas, linhas e, em seguida, exportar o resultado como imagem? Você não está sozinho. Muitos desenvolvedores esbarram em um obstáculo quando precisam de uma maneira rápida de gerar códigos DataBar Expanded Stacked com opções de layout personalizadas. Neste tutorial vamos resolver esse problema passo a passo, mostrando **como definir colunas**, **como definir linhas** e, finalmente, **exportar arquivos de imagem de código de barras** — tudo com código limpo e pronto para produção.

Ao final deste guia você terá um programa completo e executável que cria uma imagem de código de barras, ajusta seu layout e salva dois arquivos PNG no disco. Sem bibliotecas misteriosas, sem configurações ocultas — apenas C# puro e um SDK de código de barras confiável.

---

## Pré‑requisitos

Antes de mergulharmos, certifique‑se de que você tem o seguinte:

- **.NET 6.0** (ou qualquer versão posterior do .NET). O código também compila com .NET Framework, mas .NET 6+ oferece as melhorias mais recentes de runtime.
- Uma **biblioteca de geração de código de barras** que suporte DataBar Expanded Stacked. Nos exemplos usaremos **Aspose.BarCode for .NET**, que tem versão de avaliação gratuita e oferece uma API direta.
- Um ambiente de desenvolvimento — Visual Studio 2022, Rider ou VS Code servem perfeitamente.
- Permissão de escrita em uma pasta onde os arquivos PNG serão salvos.

Se ainda não possui a biblioteca, obtenha‑a via NuGet:

```bash
dotnet add package Aspose.BarCode
```

Essa única linha traz tudo que você precisa, incluindo a classe `BarcodeGenerator` e o enum `BarCodeImageFormat` usado mais adiante.

---

## Etapa 1: Configurar a Estrutura do Projeto

Crie um novo aplicativo de console e adicione as diretivas `using` necessárias:

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generation classes
using Aspose.BarCode;               // For BarCodeImageFormat enum
```

Aqui está o **esqueleto completo** do arquivo `Program.cs`:

```csharp
namespace BarcodeDemo
{
    internal class Program
    {
        static void Main(string[] args)
        {
            // We'll fill this in in the next steps.
        }
    }
}
```

> **Dica profissional:** Mantenha o método `Main` organizado; delegaremos o trabalho pesado para métodos auxiliares mais tarde. Isso torna o código mais fácil de testar e reutilizar.

---

## Etapa 2: Criar o Exemplo de Gerador de Código de Barras

Agora vamos construir o **exemplo de gerador de código de barras** que cria um código DataBar Expanded Stacked. Este é o coração do tutorial.

```csharp
static BarcodeGenerator CreateGenerator()
{
    // Step 1: Instantiate the generator for DataBar Expanded Stacked.
    // The second argument is the text you want encoded.
    var generator = new BarcodeGenerator(
        EncodeTypes.DatabarExpandedStacked,
        "Databar Expanded Stacked long");

    // Optional: fine‑tune image size or resolution if needed.
    generator.Parameters.Image.Width = 300;
    generator.Parameters.Image.Height = 150;

    return generator;
}
```

Por que separar isso em seu próprio método? Ele isola a lógica do **exemplo de gerador de código de barras**, tornando‑a reutilizável caso você precise gerar vários códigos com dados diferentes.

---

## Etapa 3: Como Definir Colunas

O formato DataBar Expanded Stacked pode ser renderizado em um layout orientado a colunas. Por padrão o SDK escolhe um valor sensato, mas muitas vezes você precisa adequar‑se a um tamanho de etiqueta específico. Veja **como definir colunas** para quatro:

```csharp
static void SetColumns(BarcodeGenerator generator, int columns)
{
    // Step 2: Adjust the column count.
    generator.Parameters.Barcode.DataBar.Columns = columns;
}
```

> **Por que as colunas importam:** Cada coluna adiciona espaço vertical, o que pode ser crucial ao imprimir em etiquetas estreitas. Definir `4` fornece um código equilibrado e legível sem sacrificar a confiabilidade da leitura.

No fluxo principal chamaremos este método:

```csharp
var generator = CreateGenerator();
SetColumns(generator, 4);
```

---

## Etapa 4: Como Definir Linhas

Às vezes você precisa de um layout mais compacto, especialmente se estiver imprimindo em uma etiqueta curta e larga. É aí que entra **como definir linhas**. Trocar de um arranjo centrado em colunas para um centrado em linhas pode reduzir a pegada do código de barras.

```csharp
static void SetRows(BarcodeGenerator generator, int rows)
{
    // Step 4: Change the layout to use rows instead of columns.
    generator.Parameters.Barcode.DataBar.Rows = rows;
}
```

A chamada fica assim:

```csharp
SetRows(generator, 3);
```

> **Observação de caso extremo:** Você não pode definir colunas *e* linhas simultaneamente — o SDK prioriza linhas se você atribuir um valor diferente de zero a `Rows`. Portanto, limpe a outra propriedade ao mudar de layout:

```csharp
generator.Parameters.Barcode.DataBar.Columns = 0; // Disable columns when using rows
```

---

## Etapa 5: Exportar Imagem de Código de Barras

Com o layout configurado, a última peça é **exportar arquivos de imagem de código de barras**. O SDK suporta PNG, JPEG, BMP e mais. PNG é sem perdas e funciona bem para a maioria das impressoras de etiquetas.

```csharp
static void SaveBarcode(BarcodeGenerator generator, string filePath)
{
    // Step 5: Save the image using the PNG format.
    generator.Save(filePath, BarCodeImageFormat.Png);
}
```

Juntando tudo em `Main`:

```csharp
static void Main(string[] args)
{
    // 1️⃣ Create the generator (barcode generator example)
    var generator = CreateGenerator();

    // 2️⃣ Set columns and save the first image
    SetColumns(generator, 4);
    string colsPath = @"YOUR_DIRECTORY\DatabarCols4.png";
    SaveBarcode(generator, colsPath);
    Console.WriteLine($"Barcode with 4 columns saved to {colsPath}");

    // 3️⃣ Switch to rows and save the second image
    SetRows(generator, 3);
    // Clear columns to avoid conflict
    generator.Parameters.Barcode.DataBar.Columns = 0;
    string rowsPath = @"YOUR_DIRECTORY\DatabarRows3.png";
    SaveBarcode(generator, rowsPath);
    Console.WriteLine($"Barcode with 3 rows saved to {rowsPath}");
}
```

### Saída Esperada

Ao executar o programa, você deverá ver dois arquivos PNG em `YOUR_DIRECTORY`:

- **DatabarCols4.png** – um código renderizado com quatro colunas verticais.
- **DatabarRows3.png** – os mesmos dados, mas dispostos em três linhas horizontais.

Ambas as imagens terão 300 × 150 px (conforme definido em `CreateGenerator`) e estarão prontas para impressão ou incorporação em um PDF.

---

## Armadilhas Comuns & Dicas

| Problema | Por que acontece | Solução |
|----------|------------------|---------|
| **Erros de caminho de arquivo** | Usar um caminho relativo sem o diretório correto pode gerar `DirectoryNotFoundException`. | Use `Path.Combine(Environment.CurrentDirectory, "output", "file.png")` ou garanta que a pasta exista com `Directory.CreateDirectory`. |
| **Conflito Linhas vs. Colunas** | Definir ambas as propriedades faz o SDK ignorar colunas. | Defina explicitamente a propriedade oposta como `0` ao trocar de layout. |
| **Tipo de código de barras não suportado** | Nem todas as bibliotecas suportam DataBar Expanded Stacked. | Verifique se sua versão da biblioteca inclui `EncodeTypes.DatabarExpandedStacked`. |
| **Qualidade da imagem muito baixa** | DPI padrão pode ser insuficiente para impressoras de alta resolução. | Ajuste `generator.Parameters.Image.ResolutionX/Y` para `300` ou mais. |

---

## Extendendo o Exemplo de Gerador de Código de Barras

Agora que você tem um **exemplo de gerador de código de barras** sólido, pode se perguntar o que mais é possível fazer.

1. **Adicionar cores** – Defina `generator.Parameters.Barcode.ForegroundColor` para `Color.Blue`.
2. **Codificar dados diferentes** – Passe uma string variável em vez da literal `"Databar Expanded Stacked long"`.
3. **Processamento em lote** – Percorra um arquivo CSV de códigos de produto, gerando um PNG para cada um.
4. **Integrar com uma API web** – Exponha um endpoint que retorne o código de barras como string codificada em base64.

Cada uma dessas extensões segue o mesmo padrão: configure a instância `BarcodeGenerator` e, em seguida, chame `Save` ou `Export` conforme necessário.

---

## Conclusão

Percorremos um **exemplo completo de gerador de código de barras** em C# que demonstra **como definir colunas**, **como definir linhas** e **como exportar arquivos de imagem de código de barras**. O código é autocontido, funciona imediatamente com Aspose.BarCode e demonstra boas práticas de legibilidade e manutenção.

Sinta‑se à vontade para experimentar — troque a string de dados, ajuste as dimensões da imagem ou mude para outra simbologia de código de barras. Os conceitos aprendidos aqui — inicializar o gerador, configurar parâmetros de layout e exportar — se aplicam a praticamente qualquer tipo de código de barras suportado pelo SDK.

Tem perguntas sobre criar programas de imagem de código de barras em C#, ou precisa de ajuda com uma impressora de etiquetas específica? Deixe um comentário abaixo e feliz codificação!

---


## O Que Você Deve Aprender a Seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas em seus próprios projetos.

- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Create barcode image c# – Configure Codablock F Rows & Columns](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Create barcode image C# – GS1 DataMatrix Example](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}