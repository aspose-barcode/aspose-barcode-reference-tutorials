---
category: general
date: 2026-10-24
description: Aprenda a criar código de barras GS1 em ASP.NET usando Aspose.BarCode.
  Guia passo a passo para gerar código de barras a partir de uma string e renderizar
  PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to create GS1 barcode
- generate barcode from string
- barcode generator asp.net
- create barcode with aspose
language: pt
lastmod: 2026-10-24
og_description: Como criar código de barras GS1 em ASP.NET usando Aspose.BarCode.
  Siga este tutorial para gerar código de barras a partir de uma string, configurar
  as configurações visuais e salvar arquivos PNG.
og_image_alt: Screenshot of a generated GS1 Micro PDF417 barcode saved as PNG
og_title: Como criar código de barras GS1 em ASP.NET – guia completo da Aspose
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to create GS1 barcode in ASP.NET using Aspose.BarCode. Step‑by‑step
    guide to generate barcode from string and render PNG.
  headline: How to create GS1 barcode in ASP.NET with Aspose.BarCode
  type: TechArticle
- description: Learn how to create GS1 barcode in ASP.NET using Aspose.BarCode. Step‑by‑step
    guide to generate barcode from string and render PNG.
  name: How to create GS1 barcode in ASP.NET with Aspose.BarCode
  steps:
  - name: 4.1 Prepare the GS1 data string
    text: 'GS1 data must be wrapped in parentheses with the AI code. For a product
      identifier (01) and a batch number (10) the string looks like:'
  - name: 4.2 Build the GS1 Micro PDF417 generator
    text: '```csharp public static byte[] GenerateGs1MicroPdf417(string gs1Data, string
      outputFolder) { // Step 4.2.1: Create a generator for Micro PDF417 using the
      GS1 data. BarcodeGenerator gs1Generator = new BarcodeGenerator(EncodeTypes.MicroPdf417,
      gs1Data);'
  - name: 4.3 Expose the generator through an ASP.NET endpoint
    text: '```csharp app.MapGet("/gs1barcode", (HttpContext context) => { string outputFolder
      = Path.Combine(Directory.GetCurrentDirectory(), "wwwroot", "barcodes"); Directory.CreateDirectory(outputFolder);
      // Ensure the folder exists'
  type: HowTo
tags:
- Aspose.BarCode
- GS1
- ASP.NET
- C#
title: Como criar código de barras GS1 em ASP.NET com Aspose.BarCode
url: /pt/net/gs1-barcode-encoding/how-to-create-gs1-barcode-in-asp-net-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar código de barras GS1 em ASP.NET com Aspose.BarCode

Se você precisa **como criar código de barras GS1** em uma aplicação ASP.NET, este guia mostra os passos exatos. Você verá como gerar um código de barras a partir de uma string, configurar a aparência visual e salvar o resultado como uma imagem PNG.

Criar códigos de barras GS1 não requer lógica de codificação personalizada. Ao usar Aspose.BarCode você obtém uma solução confiável e compatível com padrões que funciona em .NET 6+ e em frameworks anteriores. Este tutorial cobre tudo, desde a configuração do projeto até a verificação da saída, para que você possa copiar o código diretamente para o seu próprio projeto web.

## Pré-requisitos

Antes de começar, certifique‑se de que você tem:

* Visual Studio 2022 (ou qualquer IDE que suporte .NET)
* .NET 6 SDK (ou .NET Framework 4.7.2 ou superior)
* Conhecimento básico de ASP.NET Core ou ASP.NET Framework
* Uma licença Aspose.BarCode (a avaliação gratuita funciona para testes)

Nenhuma biblioteca de terceiros adicional é necessária porque o Aspose.BarCode lida com toda a codificação e renderização internamente.

## Etapa 1: Criar um novo projeto ASP.NET

Abra o Visual Studio e crie um **ASP.NET Core Web App** (escolha o modelo *Empty*). Para um projeto clássico Web Forms, o mesmo código funciona dentro de um arquivo code‑behind.

```csharp
// Program.cs (ASP.NET Core minimal API example)
using Microsoft.AspNetCore.Builder;
using Microsoft.Extensions.Hosting;

var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

app.MapGet("/", () => "GS1 barcode generator is ready.");
app.Run();
```

Executar o projeto deve exibir *GS1 barcode generator is ready.* no navegador. Isso confirma que o host web está operacional.

## Etapa 2: Instalar Aspose.BarCode via NuGet

Abra o **Package Manager Console** e execute:

```powershell
Install-Package Aspose.BarCode
```

O pacote adiciona o namespace `Aspose.BarCode.Generation`, que contém a classe `BarcodeGenerator` que você usará para **gerar código de barras a partir de string**. O comando NuGet também atualiza o arquivo do projeto com a referência necessária.

## Etapa 3: Gerar um código de barras simples a partir de uma string

Para ilustrar o uso básico, crie um método auxiliar que retorna um array de bytes PNG. Esse método pode ser chamado a partir de um controller, de uma página Razor ou de qualquer endpoint.

```csharp
using Aspose.BarCode.Generation;
using System.IO;

/// <summary>
/// Generates a barcode image from the supplied text.
/// </summary>
/// <param name="text">The data to encode.</param>
/// <param name="encodeType">The barcode symbology.</param>
/// <returns>PNG image bytes.</returns>
public static byte[] GenerateBarcode(string text, EncodeTypes encodeType)
{
    // Step 3.1: Initialize the generator with the desired symbology and data.
    BarcodeGenerator generator = new BarcodeGenerator(encodeType, text);

    // Step 3.2: Set a modest module width – 2 pixels gives a clear image.
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Step 3.3: Render the barcode to a memory stream in PNG format.
    using MemoryStream ms = new MemoryStream();
    generator.Save(ms, BarCodeImageFormat.Png);
    return ms.ToArray();
}
```

Agora você pode chamar `GenerateBarcode("HelloWorld", EncodeTypes.Code128)` de qualquer endpoint e escrever os bytes resultantes na resposta HTTP. Isso demonstra o padrão **gerador de código de barras asp.net** para strings arbitrárias.

## Etapa 4: Como criar código de barras GS1 – exemplo Micro PDF417

Os códigos de barras GS1 incorporam identificadores de aplicação (AIs) que transmitem informações do produto. O Aspose.BarCode suporta a variante compatível com GS1 do Micro PDF417, que é ideal para representação compacta de dados.

### 4.1 Preparar a string de dados GS1

Os dados GS1 devem ser envoltos em parênteses com o código AI. Para um identificador de produto (01) e um número de lote (10) a string fica assim:

```csharp
string gs1Data = "(01)12345678901234(10)ABCD";
```

Os parênteses fazem parte do padrão; o Aspose.BarCode os analisa automaticamente.

### 4.2 Construir o gerador GS1 Micro PDF417

```csharp
public static byte[] GenerateGs1MicroPdf417(string gs1Data, string outputFolder)
{
    // Step 4.2.1: Create a generator for Micro PDF417 using the GS1 data.
    BarcodeGenerator gs1Generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);

    // Step 4.2.2: Apply the same visual settings used for other barcodes.
    gs1Generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Step 4.2.3: Micro PDF417 allows 1‑4 columns; 4 gives a more square shape.
    gs1Generator.Parameters.Barcode.Pdf417.Columns = 4;

    // Step 4.2.4: Save the image to the specified folder.
    string filePath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
    gs1Generator.Save(filePath, BarCodeImageFormat.Png);

    // Return the file bytes for immediate HTTP response if needed.
    return File.ReadAllBytes(filePath);
}
```

### 4.3 Expor o gerador através de um endpoint ASP.NET

```csharp
app.MapGet("/gs1barcode", (HttpContext context) =>
{
    string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "wwwroot", "barcodes");
    Directory.CreateDirectory(outputFolder); // Ensure the folder exists

    byte[] pngBytes = GenerateGs1MicroPdf417("(01)12345678901234(10)ABCD", outputFolder);

    context.Response.ContentType = "image/png";
    return context.Response.Body.WriteAsync(pngBytes, 0, pngBytes.Length);
});
```

Ao acessar `https://localhost:5001/gs1barcode` agora o PNG gerado é transmitido. A imagem corresponde à especificação GS1, e o arquivo também é armazenado em disco para uso posterior.

## Etapa 5: Renderizando tipos adicionais de código de barras

O mesmo método **criar código de barras com aspose** funciona para outras simbologias. Abaixo está um exemplo rápido que cria um QR code a partir de uma URL:

```csharp
byte[] qrBytes = GenerateBarcode("https://example.com", EncodeTypes.QR);
File.WriteAllBytes(Path.Combine(outputFolder, "ExampleQR.png"), qrBytes);
```

Você pode substituir `EncodeTypes.QR` por `EncodeTypes.Code128`, `EncodeTypes.DataMatrix` ou qualquer outro tipo suportado. Os parâmetros visuais (`XDimension`, `Resolution`, `Color`) são configuráveis através do objeto `Parameters`.

## Etapa 6: Armadilhas comuns e dicas de boas práticas

| Problema | Por que acontece | Como evitar |
|----------|------------------|-------------|
| **Formatação de AI incorreta** | Parênteses ausentes ou comprimento de AI errado causam erros de codificação. | Sempre construa a string GS1 exatamente como o padrão especifica. Use um método auxiliar para concatenar AIs. |
| **Colunas em excesso** | O Micro PDF417 suporta apenas 1‑4 colunas; definir 5 gera uma exceção. | Valide o valor da coluna antes de atribuir: `if (columns < 1 || columns > 4) throw …` |
| **Resolução de imagem baixa** | Valores pequenos de `XDimension` podem tornar o código de barras ilegível em impressoras. | Para códigos de barras prontos para impressão, aumente `Resolution` (ex.: `generator.Parameters.Image.Resolution = 300`). |
| **Problemas de caminho de arquivo no Linux** | Barra invertida fixa quebra em hosts não Windows. | Use `Path.Combine` para construir caminhos de arquivo; ele lida com separadores específicos do SO. |
| **Licença não aplicada** | A avaliação gratuita adiciona marca d'água após 30 dias. | Aplique sua licença cedo: `new License().SetLicense("Aspose.BarCode.lic");` |

## Etapa 7: Verificar o código de barras gerado

Depois de executar o endpoint, abra o PNG em qualquer visualizador de imagens. Para confirmar que os dados GS1 foram codificados corretamente, você pode usar um scanner móvel gratuito que suporte GS1 Micro PDF417 (muitos aplicativos de scanner de códigos de barras listam essa simbologia). Escaneie a imagem; o aplicativo deve retornar:

```
(01)12345678901234
(10)ABCD
```

Se o scanner relatar um erro, verifique novamente a formatação das AIs e a contagem de colunas.

## Conclusão

Agora você sabe **como criar código de barras GS1** em um ambiente ASP.NET usando Aspose.BarCode. O tutorial abordou:

* Configurar um projeto ASP.NET e instalar o pacote NuGet Aspose.BarCode.  
* Usar **gerar código de barras a partir de string** para códigos de barras genéricos.  
* Implementar **criar código de barras com aspose** para produzir uma imagem Micro PDF417 compatível com GS1.  
* Salvar a imagem em disco e transmiti‑la via um endpoint HTTP.  

A partir daqui você pode explorar outras simbologias GS1 (por exemplo, GS1 DataMatrix) ou integrar o gerador em um fluxo de trabalho maior de processamento de pedidos. Experimente diferentes valores de `XDimension`, cores e níveis de correção de erro para combinar com sua identidade visual e ambiente de leitura.

Feliz codificação, e que suas aplicações falem a linguagem universal dos códigos de barras!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como criar código de barras code 128 com GS1 usando Aspose.BarCode](/barcode/english/net/gs1-barcode-encoding/gs1-code-128-example/)
- [Como criar zona silenciosa de código de barras para ITF-14 usando Aspose.BarCode para .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Como criar código de barras ITF-14 .NET – Tutoriais abrangentes Aspose.BarCode](/barcode/english/net/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}