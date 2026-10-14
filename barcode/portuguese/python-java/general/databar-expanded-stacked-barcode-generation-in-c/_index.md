---
category: general
date: 2026-09-29
description: Aprenda a criar um código de barras Databar Expanded Stacked e gerar
  a imagem do código de barras em C#. Este guia passo a passo mostra como definir
  linhas e colunas usando o BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- how to create barcode
- how to set rows
- barcode generator c#
- generate barcode image
language: pt
lastmod: 2026-09-29
og_description: Geração de código de barras Databar Expanded Stacked em C# explicada.
  Siga o tutorial para criar imagens de códigos de barras, definir linhas e salvar
  arquivos PNG com o BarcodeGenerator.
og_image_alt: Screenshot of a Databar Expanded Stacked barcode saved as a PNG file
og_title: Geração de código de barras Databar Expanded Stacked em C# – guia completo
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Learn how to create a Databar Expanded Stacked barcode and generate
    barcode image in C#. This step‑by‑step guide shows how to set rows and columns
    using BarcodeGenerator.
  headline: Databar Expanded Stacked barcode generation in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Geração de código de barras Databar Expanded Stacked em C#
url: /pt/python-java/general/databar-expanded-stacked-barcode-generation-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Geração de código de barras Databar Expanded Stacked em C#

Se você precisa gerar um **Databar Expanded Stacked** em C#, este guia mostra exatamente **como criar códigos de barras** com linhas e colunas personalizadas. Você verá **como definir linhas**, como definir colunas e como **gerar arquivos de imagem de código de barras** usando a classe Aspose.BarCode `BarcodeGenerator`.

Neste tutorial você irá:

* Instalar o pacote NuGet necessário.  
* Inicializar um `BarcodeGenerator` para a simbologia Databar Expanded Stacked.  
* Configurar o número de colunas e linhas.  
* Salvar os arquivos PNG resultantes.  
* Entender armadilhas comuns, como licenças ausentes ou caminhos de imagem incorretos.

Os únicos pré‑requisitos são um .NET SDK recente (≥ .NET 6) e uma IDE como o Visual Studio 2022. Nenhum serviço externo é necessário.

## Instalar e configurar a biblioteca BarcodeGenerator C# library

Antes de escrever qualquer código, adicione o pacote Aspose.BarCode ao seu projeto:

```bash
dotnet add package Aspose.BarCode
```

Se você estiver usando o Visual Studio, também pode instalá‑lo via **NuGet Package Manager** (pesquise por *Aspose.BarCode*). Após a restauração do pacote, você pode começar a codificar.

> **Dica profissional:** A versão de avaliação gratuita adiciona uma pequena marca d'água aos códigos de barras gerados. Para uso em produção, obtenha um arquivo de licença e chame `License license = new License(); license.SetLicense("Aspose.BarCode.lic");` antes de criar quaisquer objetos de código de barras.

## Gerar uma imagem de código de barras Databar Expanded Stacked

Crie um novo aplicativo de console (ou integre o código em qualquer projeto C#) e adicione as seguintes instruções `using`:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Agora escreva o programa completo. O código segue exatamente os passos do exemplo original e adiciona comentários explicativos.

```csharp
// Program.cs
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // --------------------------------------------------------------------
        // Step 1: Create a barcode generator for Databar Expanded Stacked
        // --------------------------------------------------------------------
        // The EncodeTypes enum tells the generator which symbology to use.
        var databarGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // --------------------------------------------------------------------
        // Step 2: Set the number of columns (the default is 1)
        // --------------------------------------------------------------------
        // Columns control the horizontal density of the barcode.
        databarGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // --------------------------------------------------------------------
        // Step 3: Save the barcode image that uses 4 columns
        // --------------------------------------------------------------------
        // BarCodeImageFormat.Png creates a lossless PNG file.
        databarGenerator.Save("DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // --------------------------------------------------------------------
        // Step 4: Re‑initialize the generator for the same barcode type
        // --------------------------------------------------------------------
        // Re‑creating the object ensures that row settings start from defaults.
        databarGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // --------------------------------------------------------------------
        // Step 5: Set the number of rows (the default is 1)
        // --------------------------------------------------------------------
        // Rows affect the vertical stacking of the barcode modules.
        databarGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // --------------------------------------------------------------------
        // Step 6: Save the barcode image that uses 3 rows
        // --------------------------------------------------------------------
        databarGenerator.Save("DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

### Por que cada passo importa

* **Passo 1** cria um `BarcodeGenerator` vinculado à simbologia *Databar Expanded Stacked*, que é necessária para a leitura no varejo compatível com GS1.  
* **Passo 2** demonstra **como definir linhas** indiretamente ao primeiro ajustar colunas — isso mostra que as configurações de coluna e linha são independentes.  
* **Passo 3** persiste a imagem, permitindo que você verifique o impacto visual da contagem de colunas.  
* **Passo 4** reinicializa o gerador para que a configuração de linhas não herde o valor de coluna definido anteriormente, uma fonte comum de confusão.  
* **Passo 5** mostra explicitamente **como definir linhas**, que é o foco principal da palavra‑chave secundária.  
* **Passo 6** salva a segunda imagem, proporcionando uma comparação lado a lado da densidade baseada em colunas versus linhas.

Executar o programa produz dois arquivos PNG no diretório de saída:

```
DatabarCols4.png   // 4 columns, default row count (1)
DatabarRows3.png   // 3 rows, default column count (1)
```

Abra qualquer um dos arquivos com um visualizador de imagens para confirmar que o código de barras foi renderizado corretamente.

## Variações comuns e casos de borda

| Cenário | O que mudar | Motivo |
|----------|----------------|--------|
| **Carga de dados diferente** | Substitua o segundo argumento de `BarcodeGenerator` pela sua própria string (por exemplo, `"123456789012"`). | O código de barras codifica o texto fornecido; certifique‑se de que ele esteja em conformidade com as regras GS1 para Databar. |
| **Outros formatos de imagem** | Use `BarCodeImageFormat.Jpeg` ou `BarCodeImageFormat.Bmp`. | Escolha um formato que corresponda ao seu pipeline de processamento downstream. |
| **Resolução mais alta** | Chame `databarGenerator.Save("file.png", BarCodeImageFormat.Png, 300);` onde o último argumento é DPI. | Melhora a legibilidade ao imprimir rótulos grandes. |
| **Manipulação de licença** | Adicione o trecho de código `License` antes de qualquer criação de gerador. | Remove a marca d'água de avaliação e desbloqueia a funcionalidade completa. |

## Dicas para geração confiável de códigos de barras

* **Valide a string de entrada** – Databar Expanded Stacked espera dados numéricos de até 70 caracteres. Fornecer caracteres não numéricos pode causar uma exceção.  
* **Verifique os caminhos de arquivo** – Use `Path.Combine(Environment.CurrentDirectory, "output.png")` para evitar diretórios codificados que podem não existir na máquina de destino.  
* **Libere objetos** – `BarcodeGenerator` implementa `IDisposable`. Envolva‑o em um bloco `using` se você gerar muitos códigos de barras em um loop para liberar recursos nativos prontamente.

```csharp
using (var generator = new BarcodeGenerator(...))
{
    // configure and save
}
```

## Conclusão

Agora você sabe **como criar um código de barras Databar Expanded Stacked** e **como definir linhas** (e colunas) usando a API **barcode generator C#**, e pode **gerar arquivos de imagem de código de barras** em formato PNG. Seguindo o exemplo completo acima, você pode integrar códigos de barras Databar em sistemas de inventário, aplicações ponto‑de‑venda ou qualquer solução .NET que necessite de códigos de barras GS1 de alta densidade.

**Próximos passos**

* Experimente outras simbologias como `EncodeTypes.DatabarExpanded` ou `EncodeTypes.QR`.  
* Explore a classe `BarcodeReader` para verificar se suas imagens geradas são legíveis.  
* Combine a geração de códigos de barras com a criação de PDF (por exemplo, usando `Aspose.PDF`) para produzir etiquetas imprimíveis.

Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Como definir colunas para um código de barras Databar Expanded Stacked – guia completo em C#](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [Como alterar o tamanho do código de barras em C# com DataBar Stacked](/barcode/english/python-java/general/how-to-change-barcode-size-in-c-with-databar-stacked/)
- [Databar expanded stacked: gerar imagem de código de barras em C#](/barcode/english/python-java/general/databar-expanded-stacked-generate-barcode-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}