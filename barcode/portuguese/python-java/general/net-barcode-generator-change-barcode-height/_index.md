---
category: general
date: 2026-07-18
description: Aprenda a gerar imagens de código de barras com um gerador de códigos
  de barras .net e altere facilmente a altura do código de barras para símbolos GS1‑Databar
  Omni‑Directional.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- .net barcode generator
- how to generate barcode
- change barcode height
- GS1‑Databar Omni‑Directional
- barcode image export
language: pt
lastmod: 2026-07-18
og_description: O gerador de códigos de barras .net permite criar imagens de códigos
  de barras rapidamente. Este guia mostra como gerar códigos de barras, ajustar a
  altura das barras e salvar arquivos PNG.
og_image_alt: Screenshot of a .net barcode generator output showing different bar
  heights
og_title: Alterar a altura do código de barras com o gerador de código de barras .NET
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  headline: .net barcode generator – change barcode height
  type: TechArticle
- description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  name: .net barcode generator – change barcode height
  steps:
  - name: Why each line matters
    text: '| Line | Reason | |------|--------| | `BarcodeGenerator generator = new
      BarcodeGenerator(...);` | Instantiates the **.net barcode generator** with the
      desired symbology and data payload. The `EncodeTypes.DatabarOmniDirectional`
      enum tells the library to use the GS1‑Databar Omni‑Directional format. |'
  - name: Adjusting the X‑dimension for larger prints
    text: '```csharp generator.Parameters.Barcode.XDimension.Pixels = 4; // Double
      the narrow bar width ``` Increasing the X‑dimension makes the whole barcode
      larger without altering the encoded data. This is handy when you print on large
      labels.'
  - name: Switching output formats
    text: '```csharp generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
      ``` SVG scales infinitely, which is perfect for web‑based scanners that need
      crisp vectors.'
  - name: Adding human‑readable text
    text: '```csharp generator.Parameters.Barcode.CodeTextVisible = true; generator.Parameters.Barcode.CodeTextAlignment
      = CodeLocation.Below; ``` Enabling `CodeTextVisible` appends the raw data under
      the barcode, useful for verification during testing.'
  type: HowTo
tags:
- barcode
- .net
- image export
title: Gerador de código de barras .NET – alterar altura do código de barras
url: /pt/python-java/general/net-barcode-generator-change-barcode-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .net barcode generator – alterar altura do código de barras

Já se perguntou **como gerar código de barras** sem lidar com dezenas de ferramentas de terceiros? No mundo .NET há uma maneira surpreendentemente simples de fazer isso, e a peça chave é o **.net barcode generator**. Com apenas algumas linhas de C# você pode criar um símbolo GS1‑Databar Omni‑Directional, ajustar a altura das barras e salvar o resultado em um arquivo PNG.

Se você está construindo um sistema de inventário, uma impressora de etiquetas de envio ou qualquer aplicativo que precise de um código escaneável, este tutorial levará você do zero a um código de barras funcional em minutos. Vamos percorrer o código completo, explicar por que cada configuração importa e mostrar como **alterar a altura do código de barras** sem violar a especificação.

## O que você precisará

- .NET 6.0 ou superior (a API funciona da mesma forma no .NET Framework 4.7+)
- Uma referência à biblioteca de códigos de barras (por exemplo, Aspose.BarCode for .NET – as mesmas classes são usadas por muitos kits comerciais)
- Um ambiente de desenvolvimento (Visual Studio, Rider ou VS Code com a extensão C#)
- Uma pasta onde você tem permissão de escrita – o tutorial salvará arquivos PNG lá

É isso. Nenhum pacote NuGet extra além da própria biblioteca de códigos de barras.

## Usando o .net barcode generator para alterar a altura do código de barras

Abaixo está um **programa de console completo e executável**. Cole-o em um novo projeto C#, ajuste a pasta de saída e pressione F5.

```csharp
using System;
using Aspose.BarCode.Generation;   // Namespace for the barcode generator
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a barcode generator for a GS1‑Databar Omni‑Directional symbol.
            // The string "(01)12345678901231" follows the GS1 Application Identifier syntax.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Define common visual parameters.
            // X‑dimension controls the width of the narrowest bar; 2 pixels works well for screen display.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set the initial bar height to 30 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 4️⃣ Save the first image – a compact barcode.
            string outFolder = @"YOUR_DIRECTORY"; // ← replace with a real path
            generator.Save($"{outFolder}/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 5️⃣ Increase the bar height to 60 pixels for a larger, more readable code.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 6️⃣ Save the second image – a taller barcode.
            generator.Save($"{outFolder}/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two barcode images have been generated successfully.");
        }
    }
}
```

### Por que cada linha importa

| Line | Reason |
|------|--------|
| `BarcodeGenerator generator = new BarcodeGenerator(...);` | Instancia o **.net barcode generator** com a simbologia desejada e o payload de dados. O enum `EncodeTypes.DatabarOmniDirectional` indica à biblioteca para usar o formato GS1‑Databar Omni‑Directional. |
| `XDimension.Pixels = 2;` | A X‑dimension é a largura da barra mais fina. Definir para *2 pixels* fornece uma imagem nítida na maioria dos monitores, mantendo o tamanho do arquivo baixo. |
| `BarHeight.Pixels = 30;` | Esta é a etapa de **alterar a altura do código de barras** que determina quão alta cada barra será. Uma altura de 30 pixels é um bom padrão para etiquetas pequenas. |
| `generator.Save(...);` | Persiste o código de barras em um arquivo PNG. PNG é sem perdas, o que significa que os scanners veem o padrão exato que você gerou. |
| `BarHeight.Pixels = 60;` | Aqui **alteramos a altura do código de barras** novamente—desta vez para 60 pixels. A biblioteca re‑renderiza automaticamente o símbolo com a nova dimensão quando você chama `Save` pela segunda vez. |
| `Console.WriteLine(...);` | Fornece um feedback rápido de que o processo terminou sem lançar exceção. |

> **Dica profissional:** Se você precisar de saída de alta resolução para impressão, troque `BarCodeImageFormat.Png` por `BarCodeImageFormat.Tiff` e aumente a propriedade `Resolution` (por exemplo, `generator.Parameters.ImageResolution = 300;`). A altura das barras ainda será respeitada, apenas renderizada em DPI mais fino.

## Como gerar imagens de código de barras com diferentes configurações

O trecho acima cobre o básico, mas cenários do mundo real frequentemente exigem ajustes adicionais:

### Ajustando a X‑dimension para impressões maiores
```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4; // Double the narrow bar width
```
Aumentar a X‑dimension torna todo o código de barras maior sem alterar os dados codificados. Isso é útil quando você imprime em etiquetas grandes.

### Alterando formatos de saída
```csharp
generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
```
SVG escala infinitamente, o que é perfeito para scanners baseados na web que precisam de vetores nítidos.

### Adicionando texto legível por humanos
```csharp
generator.Parameters.Barcode.CodeTextVisible = true;
generator.Parameters.Barcode.CodeTextAlignment = CodeLocation.Below;
```
Habilitar `CodeTextVisible` adiciona os dados brutos sob o código de barras, útil para verificação durante testes.

## Armadilhas comuns ao **alterar a altura do código de barras**

1. **Altura muito pequena** – Alguns scanners exigem uma altura mínima de barra (geralmente 10 mm em unidades físicas). Se você definir `BarHeight.Pixels` muito baixo, a imagem gerada pode ser ilegível em um scanner real. Sempre teste com o hardware alvo.
2. **X‑dimension e altura incompatíveis** – Uma altura de barra enorme combinada com uma X‑dimension diminuta pode parecer esticada e causar erros de decodificação. Procure uma proporção equilibrada (aproximadamente 3:1 a 5:1) a menos que a especificação indique o contrário.
3. **Esquecer de redefinir parâmetros** – O gerador mantém o estado entre salvamentos. Se você alterar `BarHeight` para uma imagem e depois reutilizar a mesma instância para outro código de barras, a altura anterior permanecerá. Redefina a propriedade ou instancie um novo `BarcodeGenerator` para cada código de barras distinto.

## Exemplo completo de ponta a ponta (incluindo instalação via NuGet)

Se você está começando do zero, siga estas etapas para colocar o projeto em funcionamento:

```bash
dotnet new console -n BarcodeHeightDemo
cd BarcodeHeightDemo
dotnet add package Aspose.BarCode
```

Substitua o `Program.cs` gerado automaticamente pelo bloco de código mostrado anteriormente, **lembre-se de substituir `YOUR_DIRECTORY`** por algo como `Path.Combine(Environment.CurrentDirectory, "output")`. Em seguida:

```bash
dotnet run
```

Você deverá ver dois arquivos PNG na pasta `output`:

- `DatabarBarHeight30Pixels.png` – um código de barras compacto com 30 pixels de altura.
- `DatabarBarHeight60Pixels.png` – uma versão mais alta com 60 pixels.

Ambas as imagens terão aparência similar, mas a segunda terá barras visivelmente mais longas, facilitando a leitura por scanners de baixa resolução.

![Barcode height example](/images/barcode-height.png){alt=".net barcode generator output mostrando diferentes alturas de barra"}

## Recapitulação & próximos passos

Abordamos como **gerar códigos de barras** usando um **.net barcode generator**, ajustamos a propriedade **alterar a altura do código de barras** e salvamos os resultados em formato PNG. Os principais pontos são:

- Instanciar o gerador com o `EncodeTypes` correto.
- Controlar o tamanho visual via `XDimension` e `BarHeight`.
- Chamar `Save` após cada alteração para persistir uma nova imagem.
- Ajustar resolução, formato,

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá-lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como gerar código de barras Aztec com proporção personalizada usando Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Como criar texto de código estendido para dotcode com Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Como gerar códigos de barras DataMatrix (ECC 200) com Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}