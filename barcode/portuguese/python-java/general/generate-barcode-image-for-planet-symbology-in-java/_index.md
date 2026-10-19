---
category: general
date: 2026-10-18
description: Gere imagem de código de barras para a simbologia Planet usando Java.
  Aprenda a criar código de barras Planet com dimensões personalizadas e barras vazias.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode image
- create planet barcode
- custom barcode dimensions
language: pt
lastmod: 2026-10-18
og_description: Gere imagem de código de barras para a simbologia Planet em Java.
  Este tutorial mostra como criar um código de barras Planet com dimensões personalizadas
  e barras de contorno.
og_image_alt: Generated barcode image showing a Planet barcode with empty outline
  bars
og_title: Gerar imagem de código de barras para a simbologia Planet – Guia Java
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Generate barcode image for Planet symbology using Java. Learn to create
    planet barcode with custom barcode dimensions and empty bars.
  headline: Generate barcode image for Planet symbology in Java
  type: TechArticle
tags:
- barcode
- Java
- imaging
title: Gerar imagem de código de barras para a simbologia Planet em Java
url: /pt/python-java/general/generate-barcode-image-for-planet-symbology-in-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gerar imagem de código de barras para a simbologia Planet em Java

Se você precisa **gerar imagem de código de barras** para a simbologia Planet, este guia o conduzirá por todo o processo. Seja construindo um sistema de automação postal ou uma solução de rastreamento personalizada, você aprenderá como **criar código de barras planet** com **dimensões de código de barras personalizadas** e barras de contorno (vazias).

O exemplo usa a biblioteca Aspose.BarCode for Java, que fornece uma API fluente para todos os principais padrões de código de barras. Nenhuma ferramenta adicional de processamento de imagem é necessária, e o código roda em qualquer runtime Java 8+.

## Prerequisites

Antes de começar, certifique‑se de que você tem:

* Java 8 ou mais recente instalado (o tutorial foi testado com JDK 17).
* Maven ou Gradle para gerenciar dependências.
* Familiaridade básica com a sintaxe Java e o conceito de código de barras.

Se você é novo no Maven, pode criar um projeto simples com `mvn archetype:generate` e adicionar a dependência Aspose.BarCode mostrada abaixo.

## Add the Aspose.BarCode dependency

```xml
<!-- pom.xml -->
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-barcode</artifactId>
    <version>23.12</version> <!-- Use the latest version available -->
</dependency>
```

> **Dica profissional:** Trave o número da versão para evitar alterações inesperadas que quebrem o código quando a biblioteca for atualizada.

## Step 1: Initialize the barcode generator for Planet symbology

```java
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generator.BarcodeGenerator;

public class PlanetBarcodeDemo {
    public static void main(String[] args) {
        // Step 1 – create a generator that encodes data using the Planet symbology
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.PLANET,          // Planet is the barcode type
                "123456");                   // Data to encode
```

**Why this step matters:**  
`EncodeTypes.PLANET` informa à biblioteca para usar a especificação de código de barras Planet, que é comumente usada por serviços postais. A string de dados `"123456"` é a carga útil que aparecerá na imagem gerada.

## Step 2: Set custom barcode dimensions (X dimension)

```java
        // Step 2 – adjust the X dimension (module width) to 4 pixels.
        // This controls the thickness of each bar.
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .getXDimension()
                        .setPixels(4);
```

**Why this step matters:**  
A *dimensão X* define quão larga cada barra individual é. Definindo‑a para **4 pixels**, você obtém um código de barras que é facilmente legível pela maioria dos scanners, ainda cabendo em uma etiqueta padrão. Alterar esse valor é a principal forma de alcançar **dimensões de código de barras personalizadas**.

## Step 3: Use empty (outline) bars instead of solid bars

```java
        // Step 3 – configure the generator to draw empty bars (outline only)
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .setFilledBars(false);
```

**Why this step matters:**  
`setFilledBars(false)` indica ao renderizador que desenhe apenas os contornos das barras, deixando o interior transparente. Esse estilo costuma ser exigido para códigos de barras postais onde o fundo pode conter outras informações impressas.

## Step 4: Save the barcode image as PNG

```java
        // Step 4 – save the generated barcode as a PNG file
        String outputPath = "output/PlanetEmptyBars.png";
        barcodeGenerator.save(outputPath, BarCodeImageFormat.Png);

        System.out.println("Barcode image generated at: " + outputPath);
    }
}
```

**Why this step matters:**  
Escolher `BarCodeImageFormat.Png` fornece uma imagem sem perdas que preserva as bordas nítidas das barras de contorno. O caminho do arquivo pode ser qualquer diretório onde você tenha permissão de escrita; o exemplo usa uma pasta `output` relativa à raiz do projeto.

### Expected output

Executar o programa cria um arquivo semelhante à imagem abaixo:

![Imagem de código de barras gerada para a simbologia Planet](/images/planet-barcode.png){.align-center alt="Imagem de código de barras gerada mostrando um código de barras Planet com barras de contorno vazias"}

A imagem exibe um **código de barras Planet** com barras finas e vazias, correspondendo exatamente às dimensões personalizadas que você definiu.

## Common variations and edge cases

| Situação | Ajuste |
|-----------|------------|
| **Comprimento de dados diferente** | Códigos de barras Planet suportam até 12 caracteres numéricos. Altere o segundo argumento do construtor de acordo. |
| **Resolução mais alta** | Aumente a dimensão X (`setPixels`) ou defina o `YDimension` para controlar a altura das barras. |
| **Código de barras colorido** | Use `barcodeGenerator.getParameters().getImageOptions().setForeColor(Color.BLUE);` para mudar a cor das barras. |
| **Salvar como SVG** | Substitua `BarCodeImageFormat.Png` por `BarCodeImageFormat.Svg` para uma saída vetorial. |
| **Executando no Android** | Use a versão compatível com Android do Aspose.BarCode para Android e substitua os caminhos do sistema de arquivos por `Context.getFilesDir()`. |

> **Atenção:** Definir a dimensão X muito baixa (por exemplo, 1 pixel) pode tornar o código de barras ilegível em impressoras de baixa resolução. Sempre teste com um scanner real após alterar as dimensões.

## Full source code for quick copy‑paste

```java
package com.example.barcode;

import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generator.BarcodeGenerator;

public class PlanetBarcodeDemo {
    public static void main(String[] args) {
        // Create the generator for Planet barcode with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.PLANET,
                "123456");

        // Custom X dimension – 4 pixels per module
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .getXDimension()
                        .setPixels(4);

        // Use outline (empty) bars
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .setFilledBars(false);

        // Save as PNG
        String outputPath = "output/PlanetEmptyBars.png";
        barcodeGenerator.save(outputPath, BarCodeImageFormat.Png);

        System.out.println("Barcode image generated at: " + outputPath);
    }
}
```

Copie o código para um arquivo chamado `PlanetBarcodeDemo.java`, coloque‑o em `src/main/java/com/example/barcode/`, execute `mvn compile exec:java` e você verá o resultado da **geração de imagem de código de barras** na pasta `output`.

## Conclusion

Agora você sabe como **gerar imagem de código de barras** para a simbologia Planet em Java, como **criar código de barras planet** com **dimensões de código de barras personalizadas**, e como alternar de barras sólidas para vazias para um estilo visual mais limpo. O exemplo completo demonstra todas as chamadas de API necessárias, desde a inicialização do gerador até a gravação de um arquivo PNG.

**Próximos passos** – explore outros tipos de código de barras (`EncodeTypes.CODE_128`, `EncodeTypes.QR`) e experimente opções de imagem adicionais, como cor de fundo, margens e configurações de DPI. Se precisar incorporar o código de barras em um PDF, combine este código com Aspose.PDF for Java para uma solução completa de ponta a ponta.

Feliz codificação!

## What Should You Learn Next?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como criar código de barras planet com barras preenchidas e vazias](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [Criar imagem de código de barras planet – Guia passo a passo](/barcode/english/python-java/general/create-planet-barcode-image-step-by-step-guide/)
- [Como gerar código de barras java: Criar uma imagem de código de barras exata](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}