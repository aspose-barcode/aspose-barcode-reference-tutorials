---
title: Gerando vários códigos de barras em uma única imagem em Java com Aspose.BarCode
linktitle: Gerando vários códigos de barras em uma única imagem
second_title: API Java Aspose.BarCode
description: Gere vários códigos de barras em uma única imagem sem esforço usando Aspose.BarCode for Java. Siga nosso guia passo a passo para uma integração perfeita.
weight: 19
url: /pt/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gerando vários códigos de barras em uma única imagem em Java com Aspose.BarCode

## Introdução

No mundo dinâmico da programação Java, criar e gerenciar códigos de barras de forma eficiente é crucial para diversas aplicações. Aspose.BarCode para Java simplifica esse processo, permitindo que os desenvolvedores gerem vários códigos de barras em uma única imagem de forma integrada. Este tutorial irá guiá-lo pelas etapas para conseguir isso usando Aspose.BarCode em um ambiente Java.

## Pré-requisitos

Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos:

- Compreensão básica de programação Java.
- Java Development Kit (JDK) instalado em seu sistema.
- Biblioteca Aspose.BarCode para Java baixada e configurada. Você pode baixá-lo[aqui](https://releases.aspose.com/barcode/java/).
- Um ambiente de desenvolvimento integrado (IDE), como Eclipse ou IntelliJ IDEA.

## Importar namespaces

Em seu projeto Java, importe os namespaces necessários para acessar a funcionalidade Aspose.BarCode. Adicione as seguintes instruções de importação no início da sua classe Java:

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

## Etapa 1: definir o diretório de recursos

Defina o caminho para o diretório de recursos onde os códigos de barras gerados serão salvos. Este diretório é crucial para organizar e gerenciar suas imagens de código de barras.

```java
// O caminho para o diretório de recursos.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Etapa 2: crie uma coleção de códigos de barras

Inicialize um HashMap para armazenar os dados do código de barras. Cada entrada na coleção representa um código de barras com seu respectivo tipo de codificação.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## Etapa 3: gerar imagens de código de barras

Itere pela coleção e gere imagens de código de barras usando a biblioteca Aspose.BarCode. Armazene as imagens em um ArrayList para processamento posterior.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## Etapa 4: crie uma imagem combinada

Determine a largura máxima e a altura total das imagens de código de barras. Crie um BufferedImage para combinar imagens de código de barras individuais em uma única imagem de saída.

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
## Etapa 5: salve o resultado

Salve a imagem combinada final em um local de arquivo especificado.

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## Conclusão

Parabéns! Você gerou vários códigos de barras em uma única imagem usando Aspose.BarCode para Java. Esta poderosa biblioteca simplifica o manuseio de códigos de barras, tornando-a uma ferramenta inestimável para desenvolvedores Java.

## Perguntas frequentes

### Q1: Posso personalizar a aparência de códigos de barras individuais na imagem gerada?

A1: Sim, Aspose.BarCode oferece amplas opções de personalização para a aparência do código de barras, permitindo que você adapte o estilo de cada código de barras às suas preferências.

### Q2: O Aspose.BarCode é compatível com diferentes simbologias de código de barras?

A2: Com certeza! Aspose.BarCode oferece suporte a uma ampla variedade de simbologias, incluindo CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 e AZTEC, conforme demonstrado neste tutorial.

### Q3: Como posso integrar Aspose.BarCode em meu projeto Java?

 A3: Basta baixar a biblioteca Aspose.BarCode para Java em[aqui](https://releases.aspose.com/barcode/java/) e siga as instruções de instalação fornecidas na documentação.

### Q4: Posso usar Aspose.BarCode para aplicações comerciais?

 A4: Sim, você pode obter uma licença de[aqui](https://purchase.aspose.com/buy) usar Aspose.BarCode para fins comerciais.

### Q5: Há alguma opção de teste disponível para Aspose.BarCode?

 A5: Certamente! Você pode explorar os recursos do Aspose.BarCode obtendo uma licença de teste gratuita[aqui](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
