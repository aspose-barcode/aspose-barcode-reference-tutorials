---
category: general
date: 2026-10-02
description: Aprenda como definir colunas e linhas em um gerador de códigos de barras
  C# para criar códigos de barras DataBar. Guia passo a passo com código completo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to set columns
- how to set rows
- create databar barcode
language: pt
lastmod: 2026-10-02
og_description: Guia do gerador de códigos de barras em C# – aprenda como definir
  colunas e linhas para criar códigos de barras DataBar com exemplos de código completos.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with a C#
  barcode generator
og_title: 'Gerador de código de barras C#: definir colunas e linhas para códigos de
  barras DataBar'
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to set columns and rows in a C# barcode generator to create
    DataBar barcodes. Step‑by‑step guide with complete code.
  headline: How to use a C# barcode generator to create DataBar barcodes with custom
    columns and rows
  type: TechArticle
tags:
- barcode
- c#
- databar
title: Como usar um gerador de códigos de barras C# para criar códigos de barras DataBar
  com colunas e linhas personalizadas
url: /pt/python-java/general/how-to-use-a-c-barcode-generator-to-create-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como usar um gerador de código de barras C# para criar códigos de barras DataBar com colunas e linhas personalizadas

Se você precisa de um **c# barcode generator** que possa produzir códigos de barras DataBar com configurações precisas de colunas e linhas, este tutorial mostra exatamente como fazer. Você verá por que ajustar colunas e linhas é importante e receberá um exemplo completo, pronto‑para‑executar, que cria tanto um código de barras DataBar Expanded Stacked de 4 colunas quanto um de 3 linhas.

Nas seções a seguir, abordaremos:

* Os pré‑requisitos para usar a biblioteca Aspose.BarCode for .NET.
* Como definir colunas (`how to set columns`) e linhas (`how to set rows`) em um código de barras DataBar.
* Um programa completo em C# console que você pode copiar, compilar e executar.
* Arquivos de saída esperados e dicas para solução de problemas.

Ao final deste guia, você será capaz de **create databar barcode** imagens adaptadas aos requisitos do seu layout.

## Pré-requisitos

Antes de começar, certifique‑se de que você tem:

| Requisito | Motivo |
|-------------|--------|
| .NET 6.0 SDK or later | Fornece o runtime para o código C#. |
| Visual Studio 2022 (or any IDE that supports .NET) | Facilita a criação do projeto e a depuração. |
| Aspose.BarCode for .NET NuGet package | Fornece a classe `BarcodeGenerator` usada nos exemplos. |
| Write permission to a folder for the output PNG files | O gerador grava as imagens do código de barras no disco. |

Instale o pacote Aspose.BarCode com o seguinte comando:

```bash
dotnet add package Aspose.BarCode
```

## Etapa 1: Criar um código de barras DataBar Expanded Stacked básico

O primeiro passo é instanciar um **c# barcode generator** com o formato `EncodeTypes.DatabarExpandedStacked`. Esse formato é um código de barras DataBar bidimensional que pode codificar até 74 caracteres numéricos.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// ...

// Create a generator for a DataBar Expanded Stacked barcode
var generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

O construtor recebe dois argumentos:

* `EncodeTypes.DatabarExpandedStacked` – indica à biblioteca qual simbologia usar.
* `"Databar Expanded Stacked long"` – o texto que será codificado.

## Etapa 2: Como definir colunas

As colunas afetam a densidade horizontal do código de barras DataBar. Aumentar a contagem de colunas torna o código de barras mais largo, o que pode melhorar a confiabilidade da leitura em impressoras de baixa resolução.

```csharp
// Set the number of columns to 4
generator.Parameters.Barcode.DataBar.Columns = 4;
```

**Por que 4 colunas?**  
Quatro colunas oferecem um bom equilíbrio entre tamanho e legibilidade para a maioria das aplicações de varejo. Você pode experimentar valores de 1 a 8; a biblioteca ajustará automaticamente a largura do módulo.

## Etapa 3: Salvar o código de barras configurado com colunas

```csharp
// Save the image that uses the column setting
generator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
```

A imagem é salva como um arquivo PNG, que preserva as bordas nítidas necessárias para os scanners de código de barras.

## Etapa 4: Criar um gerador separado para configuração de linhas

A configuração de linhas funciona da mesma forma, mas influencia a densidade vertical. Para evitar misturar as configurações de colunas e linhas, criamos uma nova instância do gerador.

```csharp
var generatorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

## Etapa 5: Como definir linhas

```csharp
// Set the number of rows to 3
generatorRows.Parameters.Barcode.DataBar.Rows = 3;
```

**Quando usar mais linhas?**  
Adicionar linhas torna o código de barras mais alto, o que pode ser útil quando o espaço impresso é limitado horizontalmente, mas amplo verticalmente (por exemplo, em uma etiqueta de produto que é mais alta que larga).

## Etapa 6: Salvar o código de barras configurado com linhas

```csharp
// Save the image that uses the row setting
generatorRows.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
```

Ambos os arquivos PNG (`DatabarCols4.png` e `DatabarRows3.png`) aparecerão na pasta `C:\Barcodes`.

## Exemplo completo e executável

Abaixo está um aplicativo console autônomo que incorpora cada passo descrito acima. Copie o código para um novo projeto console .NET e execute‑o.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace DatabarDemo
{
    class Program
    {
        static void Main()
        {
            // Output directory – change to a folder that exists on your machine
            const string outputDir = @"C:\Barcodes";

            // -------------------------------------------------
            // 1️⃣ Create a barcode generator for column testing
            // -------------------------------------------------
            var colGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // Set the number of columns (how to set columns)
            colGenerator.Parameters.Barcode.DataBar.Columns = 4;

            // Save the column‑based barcode
            string colPath = System.IO.Path.Combine(outputDir, "DatabarCols4.png");
            colGenerator.Save(colPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Column barcode saved to: {colPath}");

            // -------------------------------------------------
            // 2️⃣ Create a barcode generator for row testing
            // -------------------------------------------------
            var rowGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // Set the number of rows (how to set rows)
            rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

            // Save the row‑based barcode
            string rowPath = System.IO.Path.Combine(outputDir, "DatabarRows3.png");
            rowGenerator.Save(rowPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Row barcode saved to: {rowPath}");

            // -------------------------------------------------
            // 3️⃣ Confirmation message
            // -------------------------------------------------
            Console.WriteLine("Both DataBar barcodes have been generated successfully.");
        }
    }
}
```

### O que o código faz

| Seção | Propósito |
|---------|---------|
| **Importações de namespace** | Importa `Aspose.BarCode` e `Aspose.BarCode.Generation`. |
| **Diretório de saída** | Centraliza o caminho para que você precise editar apenas uma linha se mover a pasta. |
| **Gerador de colunas** | Demonstrar **how to set columns** em um `c# barcode generator`. |
| **Gerador de linhas** | Demonstrar **how to set rows** em um `c# barcode generator`. |
| **Chamadas de salvamento** | Grava os arquivos PNG no disco, tornando‑os prontos para leitura ou inclusão em relatórios. |
| **Saída do console** | Fornece feedback imediato, útil durante o desenvolvimento. |

## Saída esperada

Depois de executar o programa, você deverá ver dois arquivos PNG:

* **DatabarCols4.png** – um código de barras mais largo refletindo quatro colunas.
* **DatabarRows3.png** – um código de barras mais alto refletindo três linhas.

Ambas as imagens contêm o texto *“Databar Expanded Stacked long”* codificado na simbologia DataBar Expanded Stacked. Você pode abri‑las em qualquer visualizador de imagens ou enviá‑las a um scanner de código de barras para verificar a legibilidade.

## Armadilhas comuns e como evitá‑las

| Problema | Motivo | Correção |
|-------|--------|-----|
| **Exceção de acesso ao arquivo** | A pasta de saída não existe ou você não tem permissão de gravação. | Crie a pasta manualmente ou execute o programa com privilégios elevados. |
| **Valores de coluna/linha incorretos** | A biblioteca aceita apenas valores de 1‑8 para colunas e 1‑4 para linhas. | Valide os valores antes de atribuir, por exemplo, `if (value < 1 || value > 8) throw new ArgumentOutOfRangeException();`. |
| **Código de barras não escaneia** | A imagem gerada é muito pequena para a resolução do scanner. | Aumente `ImageHeight` ou `ImageWidth` usando `generator.Parameters.Image.Height` / `...Width`. |
| **Truncamento de texto** | O texto codificado excede o comprimento máximo para a variante DataBar escolhida. | Use uma string mais curta ou troque para `EncodeTypes.DatabarExpanded` se precisar de mais capacidade. |

## Dicas profissionais

* **Cache o gerador** – Se precisar criar muitos códigos de barras com as mesmas configurações de coluna/linha, reutilize a mesma instância `BarcodeGenerator` e altere apenas a propriedade `CodeText`.
* **Processamento em lote** – Percorra uma coleção de identificadores de produto, defina `generator.CodeText` dentro do loop e chame `Save` com um nome de arquivo único a cada iteração.
* **Desempenho** – Para cenários de alto volume, desative o anti‑aliasing (`generator.Parameters.Image.AntiAlias = false`) para acelerar a geração de imagens sem afetar a qualidade da leitura.

## Próximos passos

Agora que você sabe **how to set columns** e **how to set rows** com um **c# barcode generator**, você pode querer explorar:

* **Adicionar texto legível por humanos** abaixo do código de barras (`generator.Parameters.Barcode.CodeTextLocation`).
* **Alterar cores** (`generator.Parameters.Image.ForegroundColor` e `BackgroundColor`).
* **Gerar outras variantes DataBar** como `DatabarLimited` ou `DatabarExpanded`.
* **Incorporar códigos de barras em relatórios PDF** usando Aspose.PDF.

Cada um desses tópicos se baseia na fundação abordada aqui e ajuda você a criar soluções de código de barras mais robustas e prontas para produção.

---

*Feliz codificação! Se você encontrar algum problema, sinta‑se à vontade para deixar um comentário ou consultar a documentação do Aspose.BarCode para detalhes mais aprofundados da API.*

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como definir colunas e linhas de código de barras com C# BarcodeGenerator](/barcode/english/python-java/general/how-to-set-barcode-columns-and-rows-with-c-barcodegenerator/)
- [Exemplo de Gerador de Código de Barras em C# – Definir Colunas, Linhas e Exportar Imagem](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Como usar um gerador de código de barras C# para criar códigos de barras DataBar](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}