---
title: Gerando e salvando código de barras em Java
linktitle: Gerando e salvando código de barras
second_title: API Java Aspose.BarCode
description: Gere e salve códigos de barras sem esforço em Java com Aspose.BarCode. Integre-se perfeitamente, personalize a aparência e aproveite amplo suporte a códigos de barras.
weight: 12
url: /pt/java/symbology-and-format/generating-saving-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gerando e salvando código de barras em Java


## Introdução

Você deseja integrar perfeitamente a geração de código de barras ao seu aplicativo Java? Não procure mais! Neste guia passo a passo, orientaremos você no processo de uso do Aspose.BarCode for Java para gerar e salvar códigos de barras com eficiência. Aspose.BarCode é uma poderosa biblioteca Java que simplifica a criação e manipulação de códigos de barras, fornecendo as ferramentas necessárias para aprimorar seus aplicativos com funcionalidade de código de barras.

## Pré-requisitos

Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:

- Ambiente de desenvolvimento Java: certifique-se de ter um ambiente de desenvolvimento Java configurado em sua máquina.

- Biblioteca Aspose.BarCode: Baixe e instale a biblioteca Aspose.BarCode. Você pode encontrar o link para download[aqui](https://releases.aspose.com/barcode/java/).

- Banco de dados MySQL: Configure um banco de dados MySQL onde você pretende armazenar informações relacionadas ao código de barras.

- Conectividade do banco de dados: certifique-se de ter as credenciais e conectividade necessárias para interagir com o banco de dados MySQL.

## Importar pacotes

Em seu projeto Java, importe os pacotes necessários para conectividade Aspose.BarCode e MySQL.

```java
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generation.BarcodeGenerator;

import java.io.File;
import java.io.FileInputStream;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
```

## Etapa 1: gerar e salvar código de barras

```java
// Passo 1 – Gere código de barras e salve temporariamente em um arquivo
String strBarCodeImage = "c:\\temp\\code39.jpg";
String strCodeText = "NOK-E71";

BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD);
generator.setCodeText(strCodeText);
generator.save(strBarCodeImage);
```

Explicação: Esta etapa envolve a criação de um código de barras com Aspose.BarCode, a definição do texto do código e o salvamento da imagem do código de barras em um local especificado.

## Etapa 2: inserir registro no banco de dados MySQL

```java
// Passo 2 – Insira um novo registro no banco de dados MySQL
Connection con = null;

// Conexão aberta
Class.forName("com.mysql.jdbc.Driver").newInstance();
con = DriverManager.getConnection(Common.HOST_URI, Common.USERNAME, Common.PASSWORD);

// Preparar declaração
PreparedStatement pre = con.prepareCall(
        "Insert INTO Product (ProductNumber, ProductName, BarCodeImage) " + "VALUES (?, ?, ?) ");

// Defina o número e o nome do produto
pre.setString(1, "NOK-E71");
pre.setString(2, "Nokia E Series - E71");

// A terceira coluna é para imagem de código de barras. O tipo de banco de dados é BLOB
// Para salvar a imagem, precisamos criar um stream a partir do arquivo de imagem
File imgFile = new File(strBarCodeImage);
FileInputStream fin = new FileInputStream(imgFile);
pre.setBinaryStream(3, fin, (int) imgFile.length());

// Execute a instrução
pre.executeUpdate();
System.out.println("Insertion successful.");

// Fechar conexão
pre.close();
con.close();
```

Explicação: Esta etapa envolve conectar-se a um banco de dados MySQL e inserir um novo registro com informações do produto e a imagem do código de barras associada.

## Conclusão

Parabéns! Você integrou com sucesso o Aspose.BarCode for Java em seu aplicativo para gerar e salvar códigos de barras. Esta poderosa biblioteca simplifica o processo, facilitando a implementação do código de barras.

## perguntas frequentes

### P: O Aspose.BarCode é compatível com diferentes tipos de código de barras?
R: Sim, Aspose.BarCode oferece suporte a vários tipos de código de barras, incluindo CODE_39_STANDARD, CODE_128, QR e muito mais.

### P: Posso personalizar a aparência dos códigos de barras gerados?
R: Absolutamente! Aspose.BarCode oferece amplas opções de personalização para a aparência do código de barras, permitindo adaptá-lo às suas necessidades específicas.

### P: Existe uma avaliação gratuita disponível para Aspose.BarCode?
 R: Sim, você pode acessar uma avaliação gratuita[aqui](https://releases.aspose.com/).

### P: Onde posso encontrar documentação detalhada para Aspose.BarCode?
 R: Consulte a documentação[aqui](https://reference.aspose.com/barcode/java/).

### P: Como obtenho suporte para Aspose.BarCode?
 R: Visite o fórum de suporte[aqui](https://forum.aspose.com/c/barcode/13) para qualquer assistência ou dúvida.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
