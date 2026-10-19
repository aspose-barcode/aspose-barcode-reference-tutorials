---
date: 2026-10-19
description: Aprenda a criar QR code java e gerar vários códigos de barras em uma
  única imagem usando Aspose.BarCode for Java. Inclui configuração, código e solução
  de problemas.
keywords:
- create qr code java
- how to create qr
- java barcode library
- generate multiple barcodes
- aspose trial license
lastmod: 2026-10-19
linktitle: Gerando vários códigos de barras em uma única imagem
og_description: Crie QR code java e combine vários tipos de códigos de barras em uma
  única imagem com Aspose.BarCode for Java. Siga o guia passo a passo, veja trechos
  de código e aprenda dicas de solução de problemas.
og_image_alt: Screenshot of a Java application generating a QR code and other barcodes
  on one combined image
og_title: Criar QR code java – gerar vários códigos de barras em uma imagem
schemas:
- author: Aspose
  dateModified: '2026-10-19'
  description: Learn how to create QR code java and generate multiple barcodes on
    a single image using Aspose.BarCode for Java. Includes setup, code, and troubleshooting.
  headline: Create QR code java – generate multiple barcodes on one image
  type: TechArticle
- questions:
  - answer: Yes. Use the `BarcodeGenerator` properties such as `setBarColor`, `setBackgroundColor`,
      and `setXDimension` to style each barcode independently before adding it to
      the canvas.
    question: Can I customize the appearance of individual barcodes in the generated
      image?
  - answer: Absolutely. The library supports 50+ symbologies, including CODE_39, DATA_MATRIX,
      QR, CODE_128, EAN_13, and AZTEC, as demonstrated in this tutorial.
    question: Is Aspose.BarCode compatible with different barcode symbologies?
  - answer: Download the JAR from the Aspose.BarCode for Java library download page,
      add it to your project’s classpath, and import the required namespaces as shown
      in the “Import namespaces” section.
    question: How do I integrate Aspose.BarCode into my Java project?
  - answer: Yes. Purchase a license from the Aspose.BarCode license purchase page
      to remove trial limitations and obtain full production support.
    question: Can I use Aspose.BarCode for commercial applications?
  - answer: Certainly. A free trial license is available from the Aspose.BarCode free
      trial download page, giving you full API access for evaluation.
    question: Are there trial options available for Aspose.BarCode?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- create qr code
- aspose barcode
- java barcode generation
- multiple barcodes image
title: Criar QR code java – gerar vários códigos de barras em uma imagem
url: /pt/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar QR code java – gerar múltiplos códigos de barras em uma imagem

## Introdução

Neste tutorial você aprenderá **como criar QR code java** e mesclar vários tipos diferentes de códigos de barras em uma única tela usando **Aspose.BarCode for Java**. Seja você precisar de um rótulo QR compacto, um código de barras de produto, ou uma combinação de simbologias 2‑D e lineares, este guia conduz você por cada passo — desde a configuração do projeto até a gravação da imagem combinada final — para que você possa começar a integrar a geração de códigos de barras em suas aplicações Java imediatamente.

## Respostas rápidas
- **Qual biblioteca devo usar?** Aspose.BarCode for Java fornece o conjunto mais completo de simbologias.  
- **Posso gerar diferentes tipos de códigos de barras juntos?** Sim, você pode misturar CODE_39, QR, AZTEC e mais em uma única tela.  
- **Preciso de uma licença para desenvolvimento?** Uma avaliação gratuita funciona para testes; uma licença comercial é necessária para produção.  
- **Qual versão do Java é suportada?** Java 8 e superiores são totalmente compatíveis.  
- **O formato de saída é configurável?** Você pode exportar a imagem combinada como PNG, JPEG, BMP ou TIFF.

## O que é criar QR code java?

`create QR code java` refere-se ao processo de transformar uma cadeia de texto em uma matriz bidimensional que pode ser escaneada por smartphones ou leitores de código de barras. Aspose.BarCode for Java realiza a codificação e renderização, permitindo que você se concentre na lógica de negócios em vez de lidar com imagens em nível de pixel.

## Por que usar Aspose.BarCode Java para gerar códigos de barras java?

Aspose.BarCode suporta **mais de 50 simbologias de códigos de barras** — incluindo QR, Data Matrix, Code 128, AZTEC e códigos lineares tradicionais — tornando‑a a biblioteca Java de códigos de barras mais versátil. Ela renderiza **imagens anti‑alias a até 1200 dpi**, garantindo leituras nítidas na tela e na impressão. A API requer apenas a JVM e fornece um modelo de configuração fluente para personalizar tamanho, cor, margens e correção de erro em apenas algumas linhas de código.

## Pré-requisitos

- Um sólido domínio dos fundamentos de Java.  
- JDK 8 ou superior instalado e configurado no seu PATH.  
- O JAR do Aspose.BarCode for Java (download na página oficial de download do Aspose.BarCode for Java).  
- Uma IDE como IntelliJ IDEA ou Eclipse para editar e executar o exemplo.  

## Importar namespaces

As declarações de importação trazem classes do Aspose.BarCode como `BarcodeGenerator`, `EncodeTypes` e `BarCodeImageFormat` para o escopo, permitindo referenciá‑las sem nomes totalmente qualificados.  
`BarcodeGenerator` é a classe principal usada para configurar e gerar imagens de códigos de barras.  
`EncodeTypes` é um enum no Aspose.BarCode que especifica a simbologia de código de barras a ser gerada.  
`BarCodeImageFormat` define o formato de imagem de saída para o código de barras gerado.

## Etapa 1: definir o diretório de recursos

O **diretório de recursos** é a pasta no seu sistema de arquivos onde todas as imagens de códigos de barras geradas serão gravadas. Defini‑lo uma única vez mantém seu projeto organizado e facilita a limpeza de arquivos antigos.

```java
import java.awt.Color;
import java.awt.Graphics;
import java.awt.image.BufferedImage;
import java.io.File;
import java.util.ArrayList;
import java.util.HashMap;

import javax.imageio.ImageIO;

import com.aspose.barcode.BaseEncodeType;
import com.aspose.barcode.EncodeTypes;


import com.aspose.barcode.generation.BarcodeGenerator;
```

## Etapa 2: criar uma coleção de códigos de barras

Um `HashMap<String, EncodeTypes>` armazena a cadeia de dados de cada código de barras juntamente com a simbologia que você deseja usar. `HashMap` é uma coleção Java que mapeia chaves para valores. Essa coleção alimenta o loop de geração que se segue. `EncodeTypes` é um enum que especifica qual tipo de código de barras gerar.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Etapa 3: gerar imagens de códigos de barras

O loop de geração itera sobre o `HashMap`, cria um `BarcodeGenerator` para cada entrada e chama `generateBarCodeImage()` para obter um `BufferedImage`. `generateBarCodeImage()` cria um `BufferedImage` contendo o código de barras renderizado. `BufferedImage` é uma classe Java que representa uma imagem na memória. Todas as imagens são adicionadas a um `ArrayList<BufferedImage>` para composição posterior. `ArrayList` é uma implementação de lista redimensionável em Java.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## Etapa 4: criar uma imagem combinada

Primeiro, o algoritmo calcula a **largura máxima** entre todas as imagens de códigos de barras e a **altura total** necessária para empilhá‑las verticalmente com espaçamento opcional. Em seguida, cria um `BufferedImage` desse tamanho e desenha cada código de barras na tela usando um objeto `Graphics2D`. `Graphics2D` é uma classe Java que fornece recursos de renderização 2D para desenhar formas e imagens.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## Etapa 5: salvar o resultado

Finalmente, a imagem composta é gravada no disco com `ImageIO.write`, usando o formato que você especificou (PNG, JPEG, BMP ou TIFF). `ImageIO.write` grava um `BufferedImage` em um arquivo no formato especificado. O caminho do arquivo é relativo ao diretório de recursos definido anteriormente.

```java
int maxWidth = 0;
int sumHeight = 0;
for (BufferedImage bmp : images) {
    sumHeight += bmp.getHeight();
    if (maxWidth < bmp.getWidth())
        maxWidth = bmp.getWidth();
}

int offset = 10;
BufferedImage resultBitmap = new BufferedImage(maxWidth + offset * 2, sumHeight + offset * images.size(),
        BufferedImage.TYPE_INT_ARGB);
Graphics g = resultBitmap.getGraphics();
g.setColor(Color.white);
g.fillRect(0, 0, resultBitmap.getWidth(), resultBitmap.getHeight());

int yPosition = offset;
for (int i = 0; i < images.size(); ++i) {
    BufferedImage currentBitmap = images.get(i);
    g.drawImage(currentBitmap, offset, yPosition, null);
    yPosition += currentBitmap.getHeight() + offset;
}
```

## Casos de uso comuns para gerar múltiplos códigos de barras

- **Rótulos de embalagem** – combine códigos de produto, lote e envio em um único rótulo para reduzir custos de impressão.  
- **Ingressos de eventos** – incorpore identificadores QR, Data Matrix e Code 128 para diferentes estações de leitura em um local.  
- **Gestão de inventário** – exiba SKU, dados de etiqueta RFID e números de série juntos para auditoria rápida e rastreabilidade.

## Solução de problemas e dicas

- **Problemas de tamanho da imagem** – ajuste a variável `offset` para aumentar ou diminuir o espaçamento entre os códigos de barras.  
- **Simbologia não suportada** – verifique se a sua versão do Aspose.BarCode suporta o tipo de código de barras desejado; versões mais recentes adicionam códigos 2‑D adicionais.  
- **Desempenho** – reutilize um único objeto `Graphics2D` ao gerar muitas imagens em um loop para minimizar a sobrecarga de alocação de objetos.  

## Perguntas frequentes

**Q: Posso personalizar a aparência de códigos de barras individuais na imagem gerada?**  
A: Sim. Use as propriedades do `BarcodeGenerator` como `setBarColor`, `setBackgroundColor` e `setXDimension` para estilizar cada código de barras independentemente antes de adicioná‑lo ao canvas.

**Q: O Aspose.BarCode é compatível com diferentes simbologias de códigos de barras?**  
A: Absolutamente. A biblioteca suporta mais de 50 simbologias, incluindo CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 e AZTEC, conforme demonstrado neste tutorial.

**Q: Como integrar o Aspose.BarCode ao meu projeto Java?**  
A: Baixe o JAR na página de download da biblioteca Aspose.BarCode for Java, adicione‑o ao classpath do seu projeto e importe os namespaces necessários conforme mostrado na seção “Importar namespaces”.

**Q: Posso usar o Aspose.BarCode em aplicações comerciais?**  
A: Sim. Adquira uma licença na página de compra de licença do Aspose.BarCode para remover as limitações da versão de avaliação e obter suporte completo para produção.

**Q: Existem opções de avaliação disponíveis para o Aspose.BarCode?**  
A: Certamente. Uma licença de avaliação gratuita está disponível na página de download da avaliação gratuita do Aspose.BarCode, oferecendo acesso total à API para avaliação.

**Q: Como gerar um QR code de alta resolução para impressão?**  
A: Defina a propriedade `setResolutionDpi` no `BarcodeGenerator` antes de chamar `generateBarCodeImage()`, então salve o resultado em um formato sem perdas como PNG.

**Q: O que fazer se a imagem combinada aparecer truncada?**  
A: Verifique se os cálculos de `offset` e do tamanho do canvas consideram corretamente todas as alturas dos códigos de barras; aumentar a altura do canvas ou reduzir o tamanho dos códigos de barras individuais resolve a maioria dos problemas de truncamento.

**Última atualização:** 2026-10-19  
**Testado com:** Aspose.BarCode for Java 24.11  
**Autor:** Aspose  








```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## Tutoriais relacionados

- [Como criar imagem de código de barras Java – adicionar borda com Aspose](/barcode/java/image-manipulation/adding-borders-barcode-image/)
- [Como gerar código de barras Java: salvar em streams com Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/saving-barcode-image-streams/)
- [Como gerar código de barras Java e imprimir código de barras com Aspose](/barcode/java/barcode-rendering-techniques/rendering-barcode-printer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}