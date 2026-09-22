---
category: general
date: 2026-08-09
description: Crie um código de barras databar de 4 colunas em C# rapidamente com Aspose.BarCode.
  Aprenda como configurar colunas, linhas e salvar imagens PNG neste guia conciso.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create 4‑column databar barcode
- databar expanded stacked
- barcode generator c#
- set barcode rows
- barcode image format
language: pt
lastmod: 2026-08-09
og_description: Crie um código de barras databar de 4 colunas em C# usando Aspose.BarCode,
  personalize as linhas e exporte imagens PNG para seu aplicativo.
og_image_alt: Screenshot of a 4‑column DataBar Expanded Stacked barcode generated
  in C#
og_title: Crie código de barras databar de 4 colunas em C# – tutorial rápido
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create 4‑column databar barcode in C# quickly with Aspose.BarCode.
    Learn how to configure columns, rows, and save PNG images in this concise guide.
  headline: Create 4‑column databar barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Create 4‑column databar barcode in C# quickly with Aspose.BarCode.
    Learn how to configure columns, rows, and save PNG images in this concise guide.
  name: Create 4‑column databar barcode in C# – step‑by‑step guide
  steps:
  - name: Configure DataBar Expanded Stacked columns
    text: If you need a different column count, simply change the integer assigned
      to `Columns`. The property accepts values from 1 to 4 for the expanded stacked
      variant.
  - name: Save the barcode image
    text: The `BarCodeImageFormat` enumeration provides several options (`Png`, `Jpeg`,
      `Bmp`, `Gif`, `Tiff`). PNG is loss‑less and works well for most web and desktop
      scenarios.
  - name: Set barcode rows dynamically
    text: 'You can compute the row count at runtime based on input data:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- DataBar
title: Criar código de barras databar de 4 colunas em C# – guia passo a passo
url: /pt/python-java/general/create-4-column-databar-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar código de barras databar de 4 colunas em C# – guia passo a passo

Se você precisa **criar um código de barras databar de 4 colunas** em C#, este tutorial mostra exatamente como fazer. Vamos percorrer a geração de um código de barras DataBar Expanded Stacked, configurando quatro colunas e salvando o resultado como uma imagem PNG.

Neste guia você aprenderá como:

* Inicializar o `BarcodeGenerator` para um símbolo **DataBar Expanded Stacked**.  
* Definir a contagem de colunas para 4 (o requisito principal).  
* Ajustar a contagem de linhas quando precisar de um layout empilhado com três linhas.  
* Exportar o código de barras como PNG usando o **formato de imagem de código de barras** apropriado.

Você só precisa da biblioteca Aspose.BarCode for .NET (versão 23.10 ou posterior) e de um ambiente de desenvolvimento .NET 6+ como o Visual Studio 2022. Nenhuma dependência adicional é necessária.

---

## Como criar código de barras databar de 4 colunas

O primeiro passo é criar uma instância de `BarcodeGenerator` que tenha como alvo a simbologia **DataBar Expanded Stacked**. Esta classe encapsula todas as opções de renderização, facilitando a troca entre layouts baseados em colunas e em linhas.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise a generator for DataBar Expanded Stacked
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");
        
        // 2️⃣ Set the barcode to use a 4‑column layout
        generator.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Save the image as PNG
        generator.Save("DatabarCols4.png", BarCodeImageFormat.Png);
    }
}
```

**Por que isso funciona:**  
`EncodeTypes.DatabarExpandedStacked` indica ao Aspose.BarCode que produza a versão empilhada da família DataBar. A propriedade `DataBar.Columns` controla quantos módulos verticais o código de barras ocupa. Definir isso para 4 corresponde ao requisito de **criar um código de barras databar de 4 colunas**. Por fim, `Save` grava a representação visual no disco usando o **formato de imagem de código de barras** `Png`.

### Configurar colunas do DataBar Expanded Stacked

Se você precisar de uma contagem de colunas diferente, basta alterar o número inteiro atribuído a `Columns`. A propriedade aceita valores de 1 a 4 para a variante expanded stacked.

```csharp
// Example: switch to a 2‑column layout
generator.Parameters.Barcode.DataBar.Columns = 2;
```

*Dica profissional:* Sempre teste o código de barras gerado com um scanner que suporte a família DataBar, pois a aparência visual sozinha não garante a legibilidade.

### Salvar a imagem do código de barras

A enumeração `BarCodeImageFormat` oferece várias opções (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`). PNG é sem perdas e funciona bem na maioria dos cenários web e desktop.

```csharp
generator.Save("DatabarCols4.png", BarCodeImageFormat.Png);
```

Se você precisar de um formato diferente, substitua `Png` pelo valor de enum desejado. O arquivo salvo pode ser incorporado diretamente em HTML, PDFs ou impresso em etiquetas.

## Criar um código de barras com linhas personalizadas

Às vezes, um layout empilhado é necessário com um número específico de linhas em vez de colunas. A mesma classe `BarcodeGenerator` expõe uma propriedade `Rows` para esse propósito.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class RowExample
{
    static void Main()
    {
        // 1️⃣ Initialise a generator for the same symbology
        BarcodeGenerator rowGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Configure the barcode to use a 3‑row layout
        rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 3️⃣ Save the image as PNG
        rowGenerator.Save("DatabarRows3.png", BarCodeImageFormat.Png);
    }
}
```

**Por que as linhas são importantes:**  
Quando o código de barras empilhado é mais alto que largo, a propriedade `Rows` determina em quantas fatias horizontais o símbolo será dividido. Definir `Rows = 3` cria um código de barras empilhado de três linhas, útil para larguras estreitas de etiqueta.

### Definir linhas do código de barras dinamicamente

Você pode calcular a contagem de linhas em tempo de execução com base nos dados de entrada:

```csharp
int desiredRows = GetRowsFromUser(); // your custom logic
rowGenerator.Parameters.Barcode.DataBar.Rows = desiredRows;
```

Essa flexibilidade permite que você **defina linhas do código de barras** sem recompilar a aplicação.

## Exemplo completo de ponta a ponta

A seguir, um programa único que gera tanto um código de barras de 4 colunas quanto um de 3 linhas, demonstrando como as duas configurações coexistem.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class FullExample
{
    static void Main()
    {
        // ---------- 4‑column barcode ----------
        BarcodeGenerator colGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");
        colGen.Parameters.Barcode.DataBar.Columns = 4; // create 4‑column databar barcode
        colGen.Save("DatabarCols4.png", BarCodeImageFormat.Png);

        // ---------- 3‑row barcode ----------
        BarcodeGenerator rowGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");
        rowGen.Parameters.Barcode.DataBar.Rows = 3; // set barcode rows to 3
        rowGen.Save("DatabarRows3.png", BarCodeImageFormat.Png);

        // Output confirmation
        System.Console.WriteLine("Barcodes generated:");
        System.Console.WriteLine(" - DatabarCols4.png (4 columns)");
        System.Console.WriteLine(" - DatabarRows3.png (3 rows)");
    }
}
```

**Saída esperada:**  
Dois arquivos PNG aparecem no diretório de trabalho da aplicação:

* `DatabarCols4.png` – um código de barras DataBar Expanded Stacked com quatro colunas verticais.  
* `DatabarRows3.png` – a mesma simbologia organizada em três linhas horizontais.

Ambas as imagens podem ser abertas em qualquer visualizador de imagens ou incorporadas em um controle de UI.

---

## Perguntas comuns e casos de borda

| Pergunta | Resposta |
|----------|----------|
| *Posso usar uma simbologia de código de barras diferente?* | Sim. Substitua `EncodeTypes.DatabarExpandedStacked` por outro valor de `EncodeTypes` (por exemplo, `EncodeTypes.QR`), mas as propriedades `Columns` e `Rows` são específicas das famílias DataBar. |
| *E se a string de dados exceder o comprimento máximo?* | A simbologia DataBar Expanded Stacked suporta até 61 caracteres numéricos. Exceder esse limite lança uma `ArgumentException`. Valide a entrada antes de atribuí‑la ao gerador. |
| *Preciso descartar o `BarcodeGenerator`?* | `BarcodeGenerator` implementa `IDisposable`. Em um serviço de longa duração, envolva‑o em um bloco `using` ou chame `Dispose()` manualmente para liberar recursos nativos. |
| *Posso gerar SVG em vez de PNG?* | Absolutamente. Use `BarCodeImageFormat.Svg` no método `Save`. |
| *A biblioteca é compatível com .NET Core?* | Aspose.BarCode for .NET suporta .NET Core 3.1, .NET 5, .NET 6 e posteriores. Nenhuma alteração de código é necessária. |

## Conclusão

Agora você sabe como **criar um código de barras databar de 4 colunas** em C# usando Aspose.BarCode, como ajustar o layout com linhas e como exportar o resultado em um conveniente **formato de imagem de código de barras**. O exemplo completo mostra tanto configurações baseadas em colunas quanto em linhas, proporcionando uma base sólida para qualquer cenário de impressão de etiquetas ou digitalização móvel.

**Próximos passos**

* Experimente diferentes cargas de dados e verifique a compatibilidade com scanners.  
* Explore opções adicionais de estilo, como cores de primeiro plano/fundo (`generator.Parameters.Barcode.Color`).  
* Combine o código de barras com outros gráficos usando a API `Graphics` para designs de etiquetas personalizados.  

Sinta‑se à vontade para adaptar o código para projetos ASP.NET Core, Windows Forms ou Xamarin — Aspose.BarCode funciona em todas as plataformas .NET. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Criar imagem de código de barras DotCode – linhas e colunas (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Criar imagem de código de barras c# – Configurar linhas e colunas do Codablock F](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Como criar texto de código estendido dotcode com Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}