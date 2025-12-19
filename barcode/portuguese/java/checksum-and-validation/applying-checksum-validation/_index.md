---
date: 2025-12-19
description: Aprenda a desativar a validação de checksum em Java com Aspose.BarCode.
  Este guia passo a passo mostra como ler códigos de barras, desativar o checksum
  e garantir um tratamento de dados confiável.
linktitle: How to Disable Checksum Validation
second_title: Aspose.BarCode Java API
title: Como desativar a validação de checksum no Java
url: /pt/java/checksum-and-validation/applying-checksum-validation/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Desativar a Validação de Checksum em Java

Em aplicações modernas de inventário e logística, **como desativar o checksum** pode ser a chave para ler códigos de barras legados que não incluem um dígito de checksum. Aspose.BarCode for Java torna fácil desativar a validação de checksum enquanto ainda extrai os dados codificados. Este tutorial guia você por todo o processo — desde a configuração do projeto até a leitura de um código de barras ONE‑CODE sem verificação de checksum.

## Respostas Rápidas
- **O que a desativação do checksum faz?** Ela instrui o leitor a ignorar o campo de checksum, permitindo que códigos de barras sem um checksum válido sejam processados.  
- **Quando você deve desativar o checksum?** Quando estiver trabalhando com sistemas legados ou códigos de barras não‑padrão que omitem ou corrompem o checksum.  
- **Qual classe controla a validação de checksum?** `BarCodeReader.setChecksumValidation(ChecksumValidation)`  
- **Desativar o checksum é seguro?** Apenas se você confiar na origem do código de barras; caso contrário, a validação ajuda a detectar erros.  
- **Isso afeta outros tipos de código de barras?** A configuração se aplica apenas à instância atual do `BarCodeReader`.

## O que é a Validação de Checksum?
A validação de checksum é uma verificação de integridade de dados que calcula um pequeno valor a partir do conteúdo do código de barras e o compara ao checksum incorporado. Se eles não coincidirem, o código de barras é considerado ilegível. Desativar essa verificação indica ao Aspose.BarCode que ignore a comparação.

## Por que Desativar o Checksum com Aspose.BarCode?
- **Suporte Legado:** Scanners mais antigos frequentemente geravam códigos de barras sem checksums.  
- **Desempenho:** Pular o cálculo pode acelerar leituras em lote.  
- **Flexibilidade:** Você pode decidir por instância de leitor se deve aplicar a validação.

## Pré-requisitos
- **Java Development Kit (JDK):** Certifique‑se de que você tem a versão mais recente do JDK instalada.  
- **Biblioteca Aspose.BarCode:** Baixe a biblioteca no site oficial [aqui](https://releases.aspose.com/barcode/java/).  

## Importar Pacotes
No seu projeto Java, importe as classes necessárias do Aspose.BarCode para trabalhar com o reconhecimento de códigos de barras.

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.ChecksumValidation;
import com.aspose.barcode.barcoderecognition.DecodeType;
```

## Guia Passo a Passo

### Passo 1: Configurar Seu Projeto
Crie um novo projeto Java (IDE de sua escolha) e adicione o JAR do Aspose.BarCode ao classpath do projeto.

### Passo 2: Inicializar `BarCodeReader`
Carregue a imagem que contém o código de barras ONE‑CODE que você deseja ler.

```java
String dataDir = "Your Document Directory";
BarCodeReader reader = new BarCodeReader(dataDir + "onecode.png", DecodeType.ONE_CODE);
```

### Passo 3: Como Desativar o Checksum
Instrua o leitor a ignorar a validação de checksum definindo a propriedade como `OFF`.

```java
reader.setChecksumValidation(ChecksumValidation.OFF);
```

### Passo 4: Ler Códigos de Barras
Itere pelos resultados e imprima o texto decodificado e o tipo de simbologia.

```java
for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println("CodeText: " + result.getCodeText());
    System.out.println("Symbology type: " + result.getCodeType());
}
```

**Resultado:** O texto do código de barras é exibido mesmo que a imagem original não possua um checksum válido.

## Problemas Comuns e Dicas
- **Caminho de arquivo incorreto:** Verifique se `dataDir` aponta para a pasta correta; use caminhos absolutos para testes.  
- **Tipo de código de barras não suportado:** Certifique‑se de que o `DecodeType` corresponde ao código de barras que você está lendo.  
- **Desempenho:** Desativar o checksum em grandes lotes pode melhorar a taxa de transferência, mas sempre reative-o para dados críticos.

## Perguntas Frequentes

### O Aspose.BarCode é compatível com diferentes tipos de código de barras?
Sim, o Aspose.BarCode suporta uma ampla variedade de simbologias de código de barras, desde QR e DataMatrix até códigos lineares tradicionais.

### Posso usar o Aspose.BarCode para fins comerciais?
Absolutamente. Licenças comerciais estão disponíveis para empresas que precisam de recursos prontos para produção.

### Como posso obter suporte para o Aspose.BarCode?
Visite o [Aspose.BarCode fórum](https://forum.aspose.com/c/barcode/13) para conectar-se com a comunidade e receber assistência da equipe do produto.

### Existe uma versão de avaliação gratuita disponível?
Sim, você pode explorar o conjunto completo de recursos baixando a [versão de avaliação gratuita](https://releases.aspose.com/).

### Onde posso encontrar documentação detalhada?
Consulte a abrangente [documentação](https://reference.aspose.com/barcode/java/) para detalhes da API, exemplos de código e boas práticas.

---

**Última atualização:** 2025-12-19  
**Testado com:** Aspose.BarCode for Java (latest release)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}