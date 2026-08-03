---
category: general
date: 2026-08-03
description: Tutorial de geração de código de barras em C# mostrando como criar código
  de barras Planet com Aspose.BarCode, definir a dimensão X e salvar como imagens
  PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- create planet barcode
language: pt
lastmod: 2026-08-03
og_description: O tutorial de gerador de código de barras em C# orienta você na criação
  de um código de barras Planet, ajuste da dimensão X e salvamento como PNG usando
  Aspose.BarCode.
og_image_alt: Screenshot of generated Planet and RM4SCC barcodes in PNG format
og_title: Gerador de código de barras C# – crie o código de barras Planet passo a
  passo
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Barcode generator C# tutorial showing how to create Planet barcode
    with Aspose.BarCode, set X‑dimension, and save as PNG images.
  headline: Barcode generator C# – create Planet barcode and RM4SCC example
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Gerador de código de barras C# – criar código de barras Planet e exemplo RM4SCC
url: /pt/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gerador de código de barras C# – exemplo de criação de código Planet e RM4SCC

Se você precisa de um **barcode generator C#** que possa gerar símbolos postais específicos, este guia mostra exatamente como **create Planet barcode** imagens com Aspose.BarCode. Você verá como configurar a dimensão X, gerar um código de barras RM4SCC correspondente e salvar ambos como arquivos PNG — tudo em poucos passos concisos.

O tutorial cobre tudo o que você precisa para executar o código no .NET 6 ou posterior, explica por que cada configuração importa e aponta armadilhas comuns, como largura de módulo incorreta ou permissões de diretório ausentes. Ao final, você terá duas imagens de código de barras prontas para impressão que atendem aos padrões Planet e RM4SCC.

## Prerequisites

Antes de começar, certifique‑se de que você tem:

* .NET 6 SDK (ou qualquer versão do .NET suportada pelo Aspose.BarCode)
* Visual Studio 2022 ou qualquer IDE C# de sua preferência
* Uma referência NuGet ao **Aspose.BarCode** (`Install-Package Aspose.BarCode`)
* Permissão de escrita na pasta onde você pretende armazenar os arquivos PNG

Nenhum serviço externo adicional é necessário; a biblioteca lida com toda a codificação localmente.

## Step 1: Initialise the barcode generator C# object

A primeira tarefa é criar uma instância de `BarcodeGenerator`. O construtor recebe a simbologia do código de barras (`EncodeTypes.Planet`) e os dados a serem codificados.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a Planet barcode generator with the data to encode
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

*Why this step?*  
`BarcodeGenerator` é o ponto de entrada para cada código de barras que você gera. Selecionar `EncodeTypes.Planet` indica à biblioteca que deve seguir a especificação ISO/IEC 24723 usada por muitos serviços postais.

## Step 2: Set the X‑dimension (module width) for the Planet barcode

A dimensão X define a largura de um único módulo do código de barras (a menor barra ou espaço). Um valor de **4 pixels** funciona bem para a maioria das impressoras de etiquetas.

```csharp
// Step 2: Define the X‑dimension (module width) in pixels
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Why this matters*  
Se o módulo for muito estreito, o código de barras pode ficar ilegível; se for muito largo, o tamanho da etiqueta cresce desnecessariamente. Ajustar `Pixels` permite afinar o código de barras para a resolução específica da sua impressora.

## Step 3: Save the Planet barcode as a PNG image

Aspose.BarCode calcula automaticamente a altura do código de barras com base na simbologia selecionada, portanto você só precisa especificar o caminho do arquivo e o formato.

```csharp
// Step 3: Save the Planet barcode as a PNG image (height is calculated automatically)
planetGenerator.Save("YOUR_DIRECTORY/PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);
```

*Tip*  
Substitua `YOUR_DIRECTORY` por um caminho absoluto ou relativo que exista na sua máquina. Se a pasta não existir, o método `Save` lançará uma `DirectoryNotFoundException`.

**Expected output** – um arquivo PNG que se parece com a ilustração abaixo (a imagem real não é exibida aqui, mas você verá um clássico código Planet com carga numérica `123456`).

## Step 4: Initialise a second generator for the RM4SCC barcode

Muitos sistemas postais exigem símbolos Planet e RM4SCC no mesmo envelope. Crie uma nova instância de `BarcodeGenerator` para a simbologia RM4SCC.

```csharp
// Step 4: Create an RM4SCC barcode generator with the same data
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
```

*Why a separate instance?*  
Cada simbologia tem seu próprio conjunto de parâmetros. Reutilizar o mesmo gerador poderia transferir inadvertidamente configurações (como a dimensão X) que não são ideais para o segundo código de barras.

## Step 5: Configure the X‑dimension for the RM4SCC barcode

RM4SCC também respeita a configuração da dimensão X, então aplicamos a mesma largura em pixels para consistência visual.

```csharp
// Step 5: Set the X‑dimension for the RM4SCC barcode
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Pro tip*  
Se precisar de um código de barras mais alto (por exemplo, para etiquetas maiores), você pode também definir `Height.Pixels`. Deixar esse parâmetro sem definição permite que a biblioteca calcule a altura ideal automaticamente.

## Step 6: Save the RM4SCC barcode as a PNG image

Por fim, persista o código de barras RM4SCC no disco.

```csharp
// Step 6: Save the RM4SCC barcode as a PNG image (height is calculated automatically)
rm4sccGenerator.Save("YOUR_DIRECTORY/PostalRM4SCCBarHeightNone.png", BarCodeImageFormat.Png);
```

Agora você tem dois arquivos PNG — `PostalPlanetBarHeightNone.png` e `PostalRM4SCCBarHeightNone.png` — que podem ser incorporados em etiquetas de correio, impressos em envelopes ou enviados a um serviço de impressão terceirizado.

## Optional: Adjusting height or using other image formats

Se seu fluxo de trabalho exigir uma altura de código de barras específica ou um formato de imagem diferente (por exemplo, JPEG ou BMP), você pode modificar os parâmetros antes de chamar `Save`:

```csharp
// Example: set a fixed height of 100 pixels and save as JPEG
planetGenerator.Parameters.Barcode.Height.Pixels = 100;
planetGenerator.Save("PostalPlanet.jpg", BarCodeImageFormat.Jpeg);
```

**Edge case** – Ao definir uma altura personalizada, certifique‑se de que o valor respeita a altura mínima exigida pela norma ISO; caso contrário, o código de barras pode falhar na validação.

## Common pitfalls and how to avoid them

| Pitfall | Why it happens | Fix |
|---------|----------------|-----|
| `DirectoryNotFoundException` | A pasta de destino não existe ou está escrita incorretamente. | Crie a pasta primeiro ou use `Path.Combine` com `Environment.CurrentDirectory`. |
| Barcode unreadable on low‑resolution printers | X‑dimension muito pequena para o DPI da impressora. | Aumente `XDimension.Pixels` para 5 – 6 em impressoras de 203 dpi, ou teste com uma etiqueta de amostra. |
| Wrong symbology used | Passando `EncodeTypes.Code128` em vez de `EncodeTypes.Planet`. | Verifique novamente se o valor do enum `EncodeTypes` corresponde ao padrão postal requerido. |
| Null reference on `Parameters` | Usando uma versão mais antiga do Aspose.BarCode onde a API difere. | Atualize para o pacote NuGet mais recente (v23.12 ou superior). |

## Full runnable example

Abaixo está o programa completo que você pode copiar, colar e executar. Ele inclui instruções `using`, tratamento de erros e comentários que explicam cada linha.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define the output directory (change as needed)
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // -------- Planet barcode ----------
        var planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        string planetPath = Path.Combine(outputDir, "PostalPlanetBarHeightNone.png");
        planetGenerator.Save(planetPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Planet barcode saved to: {planetPath}");

        // -------- RM4SCC barcode ----------
        var rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        string rm4sccPath = Path.Combine(outputDir, "PostalRM4SCCBarHeightNone.png");
        rm4sccGenerator.Save(rm4sccPath, BarCodeImageFormat.Png);
        Console.WriteLine($"RM4SCC barcode saved to: {rm4sccPath}");
    }
}
```

Executar o programa cria uma pasta `Barcodes` ao lado do executável e coloca os dois arquivos PNG dentro. Abra-os com qualquer visualizador de imagens para verificar o resultado.

## Conclusion

Você agora possui uma solução **barcode generator C#** que pode **create Planet barcode** imagens, ajustar a dimensão X para impressão ideal e gerar um código de barras RM4SCC correspondente — tudo com poucas linhas de código. A abordagem funciona com .NET 6+, requer apenas o pacote NuGet Aspose.BarCode e pode ser estendida a outras simbologias como Code128, QR ou DataMatrix trocando o valor de `EncodeTypes`.

### What’s next?

* Experimente diferentes valores de `XDimension.Pixels` para combinar com o DPI da sua impressora.  
* Gere códigos de barras em outros formatos (PDF, SVG) alterando o enum `BarCodeImageFormat`.  
* Combine os dois arquivos PNG em uma única etiqueta usando uma biblioteca gráfica como **SkiaSharp**.  
* Explore a API completa do Aspose.BarCode para recursos avançados como validação de checksum ou fontes personalizadas.

Sinta‑se à vontade para adaptar o código para processamento em lote ou integrá‑lo a um serviço web ASP.NET Core que devolva imagens de códigos de barras sob demanda. Boa codificação!

## What Should You Learn Next?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas em seus próprios projetos.

- [Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [How to Save PNG using DataMatrix C40 with Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/)
- [barcode generator tutorial c# – Customize Code 16K Barcode Aspect Ratios with Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}