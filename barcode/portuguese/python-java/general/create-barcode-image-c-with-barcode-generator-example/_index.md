---
category: general
date: 2026-09-10
description: Crie rapidamente uma imagem de código de barras em C# usando um exemplo
  de gerador de código de barras em C# que mostra como definir dimensões e salvar
  arquivos PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image c#
- barcode generator example c#
language: pt
lastmod: 2026-09-10
og_description: Crie imagem de código de barras em C# com um exemplo conciso de gerador
  de códigos de barras em C#. Aprenda a configurar tamanho, altura e exportar arquivos
  PNG em minutos.
og_image_alt: Screenshot of a barcode image created with C# code
og_title: Criar imagem de código de barras C# – exemplo de gerador passo a passo
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Create barcode image C# quickly using a barcode generator example C#
    that shows how to set dimensions and save PNG files.
  headline: Create barcode image C# with barcode generator example
  type: TechArticle
tags:
- barcode
- C#
- image generation
title: Criar imagem de código de barras em C# com exemplo de gerador de código de
  barras
url: /pt/python-java/general/create-barcode-image-c-with-barcode-generator-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar imagem de código de barras C# com exemplo de gerador de código de barras

Se você precisa **criar imagem de código de barras C#** para rotulagem de produtos, rastreamento de inventário ou leitura móvel, este guia mostra uma solução completa. Você verá um **exemplo de gerador de código de barras C#** que configura a largura do módulo, a altura das barras e salva arquivos PNG em apenas algumas linhas de código.

O tutorial cobre tudo, desde a instalação da biblioteca necessária até a execução de um programa de console pronto‑para‑compilar. Ao final, você terá dois arquivos PNG de código de barras — um com altura de barra de 30 pixels e outro com altura de barra de 60 pixels — prontos para uso em qualquer aplicação .NET.

## Pré-requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 SDK ou posterior instalado  
* Um ambiente de desenvolvimento como Visual Studio 2022 ou VS Code  
* O pacote NuGet **Aspose.BarCode** (o código usa `BarcodeGenerator` desta biblioteca)  

Você pode adicionar o pacote com o seguinte comando CLI:

```bash
dotnet add package Aspose.BarCode
```

## Etapa 1: Configurar o projeto de console

Crie um novo projeto de console e faça referência à biblioteca de código de barras.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

O comando cria um arquivo `Program.cs` onde você colocará o código do **exemplo de gerador de código de barras C#**.

## Etapa 2: Escrever o programa completo de geração de código de barras

Substitua o conteúdo de `Program.cs` pelo exemplo completo e executável abaixo. O programa demonstra como **criar imagem de código de barras C#** com dimensões personalizadas e como salvar o resultado como arquivos PNG.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a DataBar Omnidirectional barcode generator with the desired data.
            // The string "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Set the X‑dimension (module width) to 2 pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Configure a 30‑pixel bar height and save the first image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            SaveBarcode(generator, "DatabarBarHeight30Pixels.png");

            // 4️⃣ Change the bar height to 60 pixels and save the second image.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            SaveBarcode(generator, "DatabarBarHeight60Pixels.png");

            Console.WriteLine("Barcode images have been saved to the output folder.");
        }

        /// <summary>
        /// Saves the current barcode image as a PNG file.
        /// </summary>
        /// <param name="generator">The configured BarcodeGenerator instance.</param>
        /// <param name="fileName">The file name for the PNG image.</param>
        private static void SaveBarcode(BarcodeGenerator generator, string fileName)
        {
            // Ensure the output directory exists.
            string outputPath = System.IO.Path.Combine(
                AppDomain.CurrentDomain.BaseDirectory, "output");
            System.IO.Directory.CreateDirectory(outputPath);

            // Combine the directory and file name.
            string fullPath = System.IO.Path.Combine(outputPath, fileName);

            // Save the barcode as a PNG image.
            generator.Save(fullPath, BarCodeImageFormat.Png);
        }
    }
}
```

### Por que cada linha importa

* **EncodeTypes.DatabarOmniDirectional** – seleciona a simbologia DataBar Omnidirectional, que codifica dados numéricos e é amplamente usada no varejo.  
* **XDimension.Pixels = 2** – define a largura do módulo; um valor menor gera um código de barras mais compacto.  
* **BarHeight.Pixels** – controla a altura visual das barras. Ajustar esse valor permite criar códigos de barras que se adequam a diferentes tamanhos de etiqueta.  
* **Save method** – grava o código de barras em um arquivo PNG, um formato que preserva bordas nítidas e funciona com a maioria das bibliotecas de imagem.

## Etapa 3: Compilar e executar o programa

Execute o seguinte comando a partir da pasta do projeto:

```bash
dotnet run
```

Quando o programa terminar, você verá dois arquivos PNG na subpasta `output`:

* `DatabarBarHeight30Pixels.png` – altura de barra de 30 pixels  
* `DatabarBarHeight60Pixels.png` – altura de barra de 60 pixels  

Ambas as imagens contêm os mesmos dados codificados, mas diferem na altura visual, ilustrando como o **exemplo de gerador de código de barras C#** pode ser adaptado para diferentes requisitos de etiqueta.

## Etapa 4: Verificar os códigos de barras gerados

Abra os arquivos PNG com qualquer visualizador de imagens. Você deverá ver um código DataBar claro e de alto contraste. Para confirmar que os códigos de barras são legíveis, você pode usar um aplicativo de scanner móvel (por exemplo, apps baseados em ZXing) ou uma biblioteca de desktop como **Aspose.BarCode** em modo de decodificação:

```csharp
var reader = new BarCodeReader(fullPath, DecodeType.DatabarOmniDirectional);
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    Console.WriteLine($"Decoded value: {result.CodeText}");
}
```

Se a saída corresponder a `(01)12345678901231`, a geração foi bem‑sucedida.

## Variações comuns e casos de borda

| Situação | Ajuste | Trecho de código |
|-----------|------------|--------------|
| **Simbolismo diferente** (por exemplo, QR, Code128) | Alterar o valor de `EncodeTypes` | `new BarcodeGenerator(EncodeTypes.QR, "Hello World")` |
| **Formato de imagem personalizado** (JPEG, BMP) | Usar um enum `BarCodeImageFormat` diferente | `generator.Save(path, BarCodeImageFormat.Jpeg)` |
| **Dados dinâmicos** (entrada do usuário) | Substituir a string fixa por uma variável | `string data = Console.ReadLine(); var generator = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, data);` |
| **Comprimento de dados inválido** | Capturar `ArgumentException` lançada pelo gerador | ```csharp try { ... } catch (ArgumentException ex) { Console.WriteLine(ex.Message); }``` |

Dica profissional: sempre valide o comprimento da entrada para a simbologia selecionada; o Aspose.BarCode lança uma exceção se os dados não atenderem à especificação.

## Lista de verificação de solução de problemas

* **Diretório não encontrado** – O helper `SaveBarcode` cria a pasta `output` automaticamente, mas verifique se a aplicação tem permissões de gravação.  
* **Tamanho de imagem inesperado** – Verifique se `XDimension.Pixels` e `BarHeight.Pixels` estão definidos antes de chamar `Save`. Alterar esses valores após a gravação não afeta arquivos já escritos.  
* **Código de barras ilegível** – Certifique‑se de que a string codificada segue o formato GS1 ao usar simbologias DataBar. Parênteses ausentes ou identificadores de aplicação incorretos causam falhas na decodificação.

## Conclusão

Agora você sabe como **criar imagem de código de barras C#** usando um **exemplo prático de gerador de código de barras C#**. O programa completo define a largura do módulo, ajusta a altura das barras e salva arquivos PNG com código mínimo. A partir daqui, você pode explorar recursos adicionais, como personalização de cores, exportação de PDF multipágina ou geração em tempo real em APIs web ASP.NET Core.

**Próximos passos**

* Experimente outras simbologias (`EncodeTypes.Code128`, `EncodeTypes.QR`) para ampliar suas opções de leitura.  
* Integre o gerador a um serviço web que retorne imagens de código de barras sob demanda.  
* Combine o código de barras com metadados do produto em uma fatura PDF usando Aspose.PDF.

Feliz codificação e aproveite a flexibilidade que o C# oferece para a criação de imagens de código de barras!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Exemplo de Gerador de Código de Barras em C# – Definir Colunas, Linhas e Exportar Imagem](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Criar imagem de código de barras C# – Exemplo GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Exemplo de Gerador de Código de Barras – Construir Imagem DataBar em C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}