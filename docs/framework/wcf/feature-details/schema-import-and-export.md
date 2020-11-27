---
title: 스키마 가져오기 및 내보내기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, schema import and export
- XsdDataContractExporter class
- XsdDataContractImporter class
ms.assetid: 0da32b50-ccd9-463a-844c-7fe803d3bf44
ms.openlocfilehash: 52a9e1bf4c9442bd42beb55b133a185c4a42148d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288569"
---
# <a name="schema-import-and-export"></a>스키마 가져오기 및 내보내기

WCF (Windows Communication Foundation)에는 새로운 serialization 엔진인가 포함 되어 있습니다 <xref:System.Runtime.Serialization.DataContractSerializer> . 는 `DataContractSerializer` .NET Framework 개체와 XML 사이를 변환 합니다 (양방향). WCF에는 serializer 자체 외에도 연결 된 스키마 가져오기 및 스키마 내보내기 메커니즘이 포함 되어 있습니다. *스키마* 는 serializer가 생성 하거나 역직렬 변환기가 액세스할 수 있는 XML의 모양에 대 한 공식적이 고 정확 하며 컴퓨터에서 읽을 수 있는 설명입니다. WCF에서는 W3C (World Wide Web 컨소시엄) XSD (XML 스키마 정의 언어)를 스키마 표현으로 사용 하며,이는 다양 한 타사 플랫폼과 크게 상호 운용할 수 있습니다.  
  
 스키마 가져오기 구성 요소인는 <xref:System.Runtime.Serialization.XsdDataContractImporter> XSD 스키마 문서를 사용 하 고 serialize 된 형식이 지정 된 스키마에 해당 하는 .NET Framework 클래스 (일반적으로 데이터 계약 클래스)를 생성 합니다.  
  
 예를 들어 다음과 같은 스키마 단편이 있습니다.  
  
 [!code-csharp[c_SchemaImportExport#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#8)]
 [!code-vb[c_SchemaImportExport#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#8)]  
  
 코드를 보다 쉽게 파악할 수 있도록 간소화된 다음과 같은 형식을 생성합니다.  
  
 [!code-csharp[c_SchemaImportExport#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#1)]
 [!code-vb[c_SchemaImportExport#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#1)]  
  
 생성 된 형식은 다음과 같은 몇 가지 데이터 계약 모범 사례를 따릅니다 ( [모범 사례: 데이터 계약 버전 관리](../best-practices-data-contract-versioning.md)참조).  
  
- 이 형식은 <xref:System.Runtime.Serialization.IExtensibleDataObject> 인터페이스를 구현합니다. 자세한 내용은 [호환 가능한 데이터 계약](forward-compatible-data-contracts.md)을 참조하세요.  
  
- 데이터 멤버는 private 필드를 래핑하는 public 속성으로 구현됩니다.  
  
- 클래스는 부분 클래스로, 생성된 코드를 수정하지 않고 추가 클래스를 만들 수 있습니다.  
  
 <xref:System.Runtime.Serialization.XsdDataContractExporter>를 사용하면 반대로 작업할 수 있습니다. 즉 `DataContractSerializer`로 serialize할 수 있는 형식을 사용하고 XSD 스키마 문서를 생성할 수 있습니다.  
  
## <a name="fidelity-is-not-guaranteed"></a>정확도는 보장되지 않음  

 스키마나 형식을 통해 완벽히 정확한 라운드트립을 만든다고 보장할 수 없습니다. *라운드트립* 이란 스키마를 가져와서 클래스 집합을 만들고 결과를 내보내 스키마를 다시 만드는 것을 의미 합니다. 동일한 스키마가 반환 되지 않을 수 있습니다. 이 프로세스를 반대로 해도 정확도는 보장되지 않습니다. (형식의 스키마를 생성하기 위해 형식을 내보낸 다음 그 형식을 다시 가져옵니다.) 이때도 동일한 형식은 반환되지 않을 것입니다.  
  
## <a name="supported-types"></a>지원 형식  

 데이터 계약 모델은 WC3 스키마의 제한된 하위 집합만 지원합니다. 이 하위 집합을 따르지 않는 스키마는 가져오기 프로세스 동안 예외를 발생시킵니다. 예를 들어 데이터 계약의 데이터 멤버가 XML 특성으로 serialize되도록 지정하는 방법이 없다고 가정합니다. 이 경우, XML 특성을 사용하도록 하는 스키마는 지원되지 않고, 올바른 XML 프로젝션으로 데이터 계약을 생성할 수 없으므로 가져오기 작업 동안 예외가 발생됩니다.  
  
 예를 들어 다음과 같은 스키마 단편은 가져오기 기본 설정을 사용하여 가져올 수 없습니다.  
  
 [!code-xml[c_SchemaImportExport#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/common/source.config#9)]  
  
 자세한 내용은 [데이터 계약 스키마 참조](data-contract-schema-reference.md)를 참조 하세요. 스키마가 데이터 계약 규칙을 따르지 않으면 다른 serialization 엔진을 사용합니다. 예를 들어 <xref:System.Xml.Serialization.XmlSerializer>는 별도의 자체 스키마 가져오기 메커니즘을 사용합니다. 또한 지원되는 스키마 범위가 확장되는 특별한 가져오기 모드도 있습니다. 자세한 내용은 <xref:System.Xml.Serialization.IXmlSerializable> [클래스 생성을 위한 스키마 가져오기](importing-schema-to-generate-classes.md)에서 형식 생성에 대 한 섹션을 참조 하세요.  
  
 는를 사용 하 여 `XsdDataContractExporter` serialize 할 수 있는 모든 .NET Framework 형식을 지원 합니다 `DataContractSerializer` . 자세한 내용은 [데이터 계약 Serializer에서 지 원하는 형식](types-supported-by-the-data-contract-serializer.md)을 참조 하세요. `XsdDataContractExporter`를 사용하여 스키마를 생성하지 않는 이상, `XsdDataContractImporter`를 통해 생성된 스키마는 일반적으로 <xref:System.Xml.Serialization.XmlSchemaProviderAttribute>가 사용할 수 있는 유효한 데이터가 됩니다.  
  
 를 사용 하는 방법에 대 한 자세한 내용은 <xref:System.Runtime.Serialization.XsdDataContractImporter> [클래스 생성을 위한 스키마 가져오기](importing-schema-to-generate-classes.md)를 참조 하세요.  
  
 를 사용 하는 방법에 대 한 자세한 내용은 <xref:System.Runtime.Serialization.XsdDataContractExporter> [클래스에서 스키마 내보내기](exporting-schemas-from-classes.md)를 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Runtime.Serialization.XsdDataContractImporter>
- <xref:System.Runtime.Serialization.XsdDataContractExporter>
- [스키마를 가져와 클래스 생성](importing-schema-to-generate-classes.md)
- [클래스에서 스키마 내보내기](exporting-schemas-from-classes.md)
