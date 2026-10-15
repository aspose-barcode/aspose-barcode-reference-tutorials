---
category: general
date: 2026-10-04
description: Aprenda a decodificar PDF417 e ler vários códigos de barras em C# usando
  Aspose.BarCode. Este guia mostra como detectar o modo compacto e lidar com muitos
  códigos de barras em uma única imagem.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- c# barcode library
- read multiple barcodes
- pdf417 compact mode
- aspose barcode licensing
lastmod: 2026-10-04
og_description: Aprenda a decodificar PDF417 e ler vários códigos de barras em C#.
  Este guia passo a passo cobre a detecção do modo compacto, o tratamento de múltiplos
  códigos de barras e as melhores práticas.
og_image_alt: Screenshot of C# console output showing compact mode status for PDF417
  barcodes
og_title: Como decodificar PDF417 e ler vários códigos de barras em C#
schemas:
- author: Aspose
  dateModified: '2026-10-04'
  description: Learn how to decode PDF417 and read multiple barcodes in C# using Aspose.BarCode.
    Includes compact mode detection and multi‑barcode handling.
  headline: How to decode PDF417 and read multiple barcodes in C#
  type: TechArticle
- description: Learn how to decode PDF417 and read multiple barcodes in C# using Aspose.BarCode.
    Includes compact mode detection and multi‑barcode handling.
  name: How to decode PDF417 and read multiple barcodes in C#
  steps:
  - name: Why this code works
    text: '- **`BarCodeReader`** is the workhorse from the **BarCodeReader C#** API.
      It opens the image, applies pre‑processing, and searches for symbols of the
      type you specify. - **`ReadBarCodes()`** returns an array, not just a single
      result. That’s the key to **reading multiple barcodes C#**—the method aut'
  - name: 1️⃣ No barcodes detected
    text: 'If `ReadBarCodes()` returns an empty array, the most common culprits are:'
  - name: 2️⃣ Extremely large images
    text: 'Processing a 10 MP photo can be memory‑hungry. You can limit the scan area:'
  - name: 3️⃣ Thread‑safety
    text: '`BarCodeReader` implements `IDisposable` and is **not** thread‑safe. Spin
      up separate instances per thread if you need parallel processing.'
  - name: 4️⃣ Licensing
    text: 'Aspose.BarCode works in trial mode out of the box, but you’ll see a watermark
      on the output image. For production, set the license early:'
  - name: 5️⃣ Logging
    text: When you integrate this into a larger service, replace `Console.WriteLine`
      with a structured logger (Serilog, NLog). That way you can capture `CodeText`,
      `CodeType`, and `IsTruncated` as fields for downstream analytics.
  type: HowTo
tags:
- C#
- BarCode
- PDF417
- Aspose
- Barcode Decoding
title: Como decodificar PDF417 e ler vários códigos de barras em C#
url: /pt/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como decodificar PDF417 e ler vários códigos de barras em C#

## Respostas rápidas
- **O Aspose.BarCode pode ler mais de um código de barras de uma vez?** Sim, `ReadBarCodes()` retorna todos os símbolos detectados em uma única chamada.  
- **O que é o modo compacto para PDF417?** É uma codificação de tamanho reduzido que omite linhas de preenchimento opcionais para economizar espaço.  
- **Preciso de uma licença para produção?** A versão de avaliação funciona imediatamente, mas uma licença paga remove marcas d'água e desbloqueia o desempenho total.  
- **Quais versões do .NET são suportadas?** .NET 6+, .NET 5, .NET Core 3.1 e .NET Framework 4.6+.  
- **A biblioteca é thread‑safe?** Não, crie uma instância separada de `BarCodeReader` por thread.

## O que significa decodificar PDF417?
A expressão “how to decode PDF417” refere‑se à extração dos dados codificados em um código de barras PDF417 usando software. Aspose.BarCode fornece uma API pronta que lida automaticamente com correção de erros, detecção de símbolos e interpretação do modo compacto, permitindo que desenvolvedores obtenham o texto original sem lidar com processamento de imagem de baixo nível.

## Por que usar Aspose.BarCode para esta tarefa?
Aspose.BarCode suporta **mais de 50 simbologias de código de barras**, processa **imagens com centenas de páginas** sem carregar o arquivo inteiro na memória, e pode decodificar PDF417 tanto em modo completo quanto compacto com **100 % de precisão** em conjuntos de teste padrão (conforme verificado no conjunto de benchmarks de 2026). Também oferece documentação extensa e atualizações regulares, garantindo compatibilidade com as versões mais recentes do .NET.

## O que você precisará
Para seguir este tutorial você só precisa de um SDK .NET recente, do pacote NuGet Aspose.BarCode e de uma imagem contendo símbolos PDF417. O código funciona no Windows, Linux e macOS, e não requer bibliotecas nativas adicionais, tornando a configuração simples para qualquer desenvolvedor .NET.

- **SDK .NET 6.0** ou mais recente (o código também funciona com .NET Framework 4.6+ , mas .NET 6 é o ponto ideal).  
- **Aspose.BarCode para .NET** pacote NuGet (`Install-Package Aspose.BarCode`).  
- Uma imagem de exemplo que contém códigos de barras **PDF417** — de preferência uma que misture símbolos compactos e de tamanho completo. O tutorial usa `CompactPdf417.png`, mas qualquer PNG/JPEG serve.  
- Seu IDE favorito (Visual Studio, Rider ou VS Code).  

É isso — sem DLLs extras, sem dependências nativas. Aspose.BarCode é código puro gerenciado, então você pode incluí‑lo em qualquer projeto .NET.

![Read multiple barcodes C# console output](image.png "Read multiple barcodes C# console output")
[Read multiple barcodes C# console output](image.png "Read multiple barcodes C# console output")

*Texto alternativo da imagem: Read multiple barcodes C# – captura de tela do console exibindo o status do modo compacto para códigos de barras PDF417.*

## Como ler vários códigos de barras em C#?
Carregue a imagem com `BarCodeReader`, chame `ReadBarCodes()` e itere sobre a coleção retornada. O método descobre automaticamente cada código de barras, independentemente da posição ou orientação, e retorna um array `BarCodeResult[]` que você pode processar em um simples loop `foreach`. Essa abordagem elimina a necessidade de múltiplas varreduras ou seleção manual de regiões.

## Definição de BarCodeReader
A classe `BarCodeReader` é o componente central do Aspose.BarCode que escaneia uma imagem e extrai os dados de código de barras para todas as simbologias suportadas.

## Definição de ReadBarCodes()
`ReadBarCodes()` é um método da `BarCodeReader` que retorna um array de objetos `BarCodeResult`, cada um representando um código de barras detectado na imagem fonte.

## Etapa 1 – instalar e referenciar a biblioteca BarCodeReader C#
Primeiro de tudo, você precisa da classe **BarCodeReader C#** que alimenta a decodificação. Abra seu terminal (ou o Console do Gerenciador de Pacotes) e execute:

```powershell
dotnet add package Aspose.BarCode
```

Ou, se estiver dentro do gerenciador NuGet do Visual Studio, basta procurar por *Aspose.BarCode* e clicar em **Install**. Isso traz a versão estável mais recente (em julho 2026 é 23.9), que suporta PDF417, QR, DataMatrix e dezenas de outras simbologias.

Por que isso importa: a biblioteca abstrai o trabalho pesado de processamento de imagem, correção de erros e reconhecimento de símbolos. Você poderia escrever seu próprio scanner, mas gastaria semanas lidando com casos de borda. Aspose oferece uma **biblioteca de código de barras C#** testada em batalha, que foi atualizada para runtimes .NET modernos.

## Etapa 2 – configurar um projeto console mínimo
Crie um novo aplicativo console para que possamos focar na lógica de código de barras sem ruído de UI:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

Substitua o `Program.cs` gerado pelo exemplo completo abaixo. Sinta‑se à vontade para manter o namespace padrão ou renomeá‑lo — nada especial é necessário.

## Etapa 3 – escrever a implementação completa “read multiple barcodes C#”
Abaixo está um exemplo de código **completo e executável**. Ele cobre todas as quatro etapas do snippet original, adiciona tratamento de erros e imprime diagnósticos úteis.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // ---------------------------------------------------------
            // 1️⃣  Initialize the BarCodeReader for the target image.
            // ---------------------------------------------------------
            // Replace the path with your own image location.
            const string imagePath = "YOUR_DIRECTORY/CompactPdf417.png";

            // The DecodeType.Pdf417 tells the reader to look for PDF417 symbols.
            // You could pass DecodeType.AllSupported to scan every possible barcode.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
            {
                // ---------------------------------------------------------
                // 2️⃣  Iterate over every barcode found in the picture.
                // ---------------------------------------------------------
                BarCodeResult[] results = reader.ReadBarCodes();

                if (results.Length == 0)
                {
                    Console.WriteLine("No barcodes detected – double‑check the image path and content.");
                    return;
                }

                // ---------------------------------------------------------
                // 3️⃣  Process each result: check compact mode and output data.
                // ---------------------------------------------------------
                foreach (BarCodeResult result in results)
                {
                    // The Extended property gives us PDF417‑specific info.
                    bool isCompact = result.Extended?.Pdf417?.IsTruncated ?? false;

                    // Display the raw text and the compact‑mode flag.
                    Console.WriteLine($"Code Text   : {result.CodeText}");
                    Console.WriteLine($"Compact mode: {isCompact}");
                    Console.WriteLine(new string('-', 30));
                }
            }

            // ---------------------------------------------------------
            // 4️⃣  Keep the console window open when debugging.
            // ---------------------------------------------------------
            Console.WriteLine("Done. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

## Por que este código funciona
O `BarCodeReader` é a peça central da API **BarCodeReader C#**. Ele abre a imagem, aplica pré‑processamento e procura símbolos do tipo que você especifica. `ReadBarCodes()` retorna um array, não apenas um único resultado. Esse é o ponto chave para **reading multiple barcodes C#** — o método coleta automaticamente todas as correspondências encontradas. A flag `result.Extended.Pdf417.IsTruncated` indica se o PDF417 está em modo *compacto* (também chamado de truncado). Essa flag só existe para PDF417, então usamos o operador condicional nulo (`?.`) para evitar exceções se outro tipo de simbologia aparecer. O loop `foreach` imprime tanto o texto decodificado quanto o status compacto, oferecendo uma verificação rápida.

## Etapa 4 – lidar com diferentes tipos de código de barras (opcional)
Se sua imagem puder conter mais que PDF417, basta mudar o segundo argumento do `BarCodeReader` para `DecodeType.AllSupported`. O loop permanece o mesmo, mas você precisará proteger contra `result.Extended` ser nulo para símbolos que não sejam PDF417:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Symbology : {result.CodeTypeName}");
        Console.WriteLine($"Code Text : {result.CodeText}");

        // PDF417‑specific check only when applicable.
        if (result.CodeType == DecodeType.Pdf417)
        {
            bool isCompact = result.Extended?.Pdf417?.IsTruncated ?? false;
            Console.WriteLine($"Compact mode: {isCompact}");
        }

        Console.WriteLine(new string('=', 30));
    }
}
```

## Etapa 5 – casos de borda e dicas de boas práticas
### 1️⃣ Nenhum código de barras detectado  
Se `ReadBarCodes()` retornar um array vazio, os culpados mais comuns são:

- Caminho de arquivo incorreto ou permissões de leitura ausentes.  
- Qualidade da imagem muito baixa (desfoque, baixo contraste). Considere pré‑processamento com `reader.ImagePreprocessingOptions` (ex.: `reader.ImagePreprocessingOptions.Denoise = true;`).  

### 2️⃣ Imagens extremamente grandes  
Processar uma foto de 10 MP pode consumir muita memória. Você pode limitar a área de varredura:

```csharp
reader.SetRegionOfInterest(0, 0, 2000, 2000); // left, top, width, height
```

### 3️⃣ Segurança de thread  
`BarCodeReader` implementa `IDisposable` e **não** é thread‑safe. Crie instâncias separadas por thread se precisar de processamento paralelo.

### 4️⃣ Licenciamento  
Aspose.BarCode funciona em modo de avaliação imediatamente, mas você verá uma marca d'água na imagem de saída. Para produção, defina a licença logo no início:

```csharp
License license = new License();
license.SetLicense("Aspose.BarCode.lic");
```

### 5️⃣ Registro de logs  
Quando você integrar isso a um serviço maior, substitua `Console.WriteLine` por um logger estruturado (Serilog, NLog). Assim você pode capturar `CodeText`, `CodeType` e `IsTruncated` como campos para análises posteriores.

## Perguntas frequentes
**P: Posso decodificar PDF417 que usa modo compacto?**  
R: Sim. A propriedade `IsTruncated` no resultado estendido do PDF417 indica instantaneamente se o código de barras está compacto.

**P: E se a imagem contiver códigos QR e PDF417?**  
R: Use `DecodeType.AllSupported` ao construir o `BarCodeReader`. O leitor retornará resultados para cada simbologia detectada no mesmo array.

**P: Preciso descartar o leitor manualmente?**  
R: Absolutamente. Envolva o `BarCodeReader` em um bloco `using` ou chame `Dispose()` para liberar recursos nativos rapidamente.

**P: Qual o tamanho máximo de arquivo que o Aspose.BarCode pode processar?**  
R: A biblioteca pode processar imagens de até **200 MP** (aproximadamente 20 000 × 20 000 pixels) sem carregar todo o bitmap na memória, graças ao seu motor de varredura em blocos.

**P: É necessária uma licença separada para cada implantação?**  
R: Um único arquivo de licença pode ser usado em vários servidores, contanto que o número total de instâncias simultâneas não exceda a quantidade de assentos adquirida.

## Artigos relacionados
- [Como gerar códigos de barras PDF417 – Codificação Compact PDF417](/barcode/english/net/compact-pdf417-encoding/)
- [Como criar código de barras – PDF417 Compacto com Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Como ler códigos DataMatrix com Aspose.BarCode para .NET](/barcode/english/net/datamatrix-barcode-reading/)

**Última atualização:** 2026-10-04  
**Testado com:** Aspose.BarCode 23.9 para .NET  
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}