---
title: XML에서 데이터 세트 스키마 정보 로드
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
ms.openlocfilehash: 69994c546fea842ffef1c8c43d6d6f5bc35e0629
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151054"
---
# <a name="loading-dataset-schema-information-from-xml"></a>XML에서 데이터 세트 스키마 정보 로드
a의 <xref:System.Data.DataSet> 스키마(해당 테이블, 열, 관계식 및 제약 조건)는 프로그래밍 방식으로 정의하거나, **의 Fill** 또는 **FillSchema** 메서드에 <xref:System.Data.Common.DataAdapter>의해 만들어지거나 XML 문서에서 로드될 수 있습니다. XML 문서에서 **DataSet** 스키마 정보를 로드하려면 **ReadXmlSchema** 또는 **DataSet의** **InferXmlSchema** 메서드를 사용할 수 있습니다. **ReadXmlSchema를** 사용하면 XML 스키마 정의 언어(XSD) 스키마또는 인라인 XML 스키마가 포함된 XML 문서가 포함된 문서에서 **DataSet** 스키마 정보를 로드하거나 추론할 수 있습니다. **InferXmlSchema를** 사용하면 지정한 특정 XML 네임스페이스를 무시하면서 XML 문서에서 스키마를 유추할 수 있습니다.  
  
> [!NOTE]
> 웹 서비스 또는 XML 직렬화를 사용하여 XSD 구문(예: 중첩 된 관계)을 사용하여 메모리내로 만든 **DataSet을** 전송하는 경우 **DataSet의** 테이블 순서가 유지되지 않을 수 있습니다. 따라서 **DataSet의** 받는 사람은 이 경우 테이블 순서에 의존해서는 안 됩니다. 그러나 전송중인 **DataSet의** 스키마가 메모리 내로 생성되는 대신 XSD 파일에서 읽은 경우 테이블 순서는 항상 유지됩니다.  
  
## <a name="readxmlschema"></a>ReadXmlSchema  
 데이터를 로드하지 않고 XML 문서에서 **DataSet** 스키마를 로드하려면 **DataSet의** **ReadXmlSchema** 메서드를 사용할 수 있습니다. **ReadXmlSchema는** XML 스키마 정의 언어(XSD) 스키마를 사용하여 정의된 **데이터 집합** 스키마를 만듭니다.  
  
 **ReadXmlSchema** 메서드는 로드할 XML 문서를 포함하는 파일 이름, 스트림 또는 **XmlReader의** 단일 인수를 사용합니다. XML 문서에는 스키마만 있을 수도 있고 데이터가 포함된 XML 요소를 가진 스키마 인라인이 있을 수도 있습니다. XML 스키마로 인라인 스키마를 작성하는 것에 대한 자세한 내용은 [XML 스키마(XSD)의 데이터 집합 관계형 구조 파생을](deriving-dataset-relational-structure-from-xml-schema-xsd.md)참조하십시오.  
  
 **ReadXmlSchema에** 전달된 XML 문서에 인라인 스키마 정보가 없는 경우 **ReadXmlSchema는** XML 문서의 요소에서 스키마를 추론합니다. **DataSet에** 스키마가 이미 포함되어 있는 경우 아직 존재하지 않는 경우 새 테이블을 추가하여 현재 스키마가 확장됩니다. 새 열은 기존 테이블에 추가되지 않습니다. 추가중인 열이 **DataSet에** 이미 있지만 XML에 있는 열과 호환되지 않는 형식이 있는 경우 예외가 throw됩니다. **ReadXmlSchema가** XML 문서에서 스키마를 유추하는 방법에 대한 자세한 내용은 [XML의 데이터 집합 관계형 구조 추론을](inferring-dataset-relational-structure-from-xml.md)참조하십시오.  
  
 **ReadXmlSchema는** **DataSet의**스키마만 로드하거나 유추하지만 **DataSet의** **ReadXml** 메서드는 스키마와 XML 문서에 포함된 데이터를 로드하거나 유추합니다. 자세한 내용은 [XML에서 데이터 집합 로드를](loading-a-dataset-from-xml.md)참조하십시오.  
  
 다음 코드 예제는 XML 문서 또는 스트림에서 **DataSet** 스키마를 로드하는 방법을 보여 주며 있습니다. 첫 번째 예제에서는 **ReadXmlSchema** 메서드에 전달 되는 XML 스키마 파일 이름을 보여 주다. 두 번째 예제에서는 **System.IO.StreamReader**.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXmlSchema("schema.xsd")  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.ReadXmlSchema("schema.xsd");  
```  
  
```vb  
Dim xmlStream As New System.IO.StreamReader("schema.xsd")
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXmlSchema(xmlStream)  
xmlStream.Close()  
```  
  
```csharp  
System.IO.StreamReader xmlStream = new System.IO.StreamReader("schema.xsd");  
DataSet dataSet = new DataSet();  
dataSet.ReadXmlSchema(xmlStream);  
xmlStream.Close();  
```  
  
## <a name="inferxmlschema"></a>InferXmlSchema  
 **DataSet의** **InferXmlSchema** 메서드를 사용하여 XML 문서에서 해당 스키마를 유추하도록 **데이터 집합에**지시할 수도 있습니다. **InferXmlSchema** 함수는 **InferSchema의** **XmlReadMode(데이터** 로드 및 스키마 추론)를 사용하여 **ReadXml을** 모두 수행하는 것과 동일하며, 읽을 수 있는 문서에 인라인 스키마가 없는 경우 **ReadXmlSchema가** 있습니다. 그러나 **InferXmlSchema는** 스키마가 유추될 때 무시할 특정 XML 네임스페이스를 지정할 수 있는 추가 기능을 제공합니다. **InferXmlSchema는** 파일 이름, 스트림 또는 **XmlReader로**지정된 XML 문서의 위치라는 두 가지 필수 인수를 취합니다. 및 XML 네임스페이스의 문자열 배열은 작업에서 무시할 수 있습니다.  
  
 예를 들어, 다음과 같은 XML을 가정해 봅시다.  
  
```xml  
<NewDataSet xmlns:od="urn:schemas-microsoft-com:officedata">  
<Categories>  
  <CategoryID od:adotype="3">1</CategoryID>
  <CategoryName od:maxLength="15" od:adotype="130">Beverages</CategoryName>
  <Description od:adotype="203">Soft drinks and teas</Description>
</Categories>  
<Products>  
  <ProductID od:adotype="20">1</ProductID>
  <ReorderLevel od:adotype="3">10</ReorderLevel>
  <Discontinued od:adotype="11">0</Discontinued>
</Products>  
</NewDataSet>  
```  
  
 이전 XML 문서의 요소에 대해 지정된 특성으로 인해 **InferSchema의** **XmlReadMode를** 사용하는 **ReadXml** 메서드와 **ReadXml** 메서드는 **범주,** **범주ID,** **범주 이름,** **설명,** **제품** **ID,** **ReorderLevel**및 **단종**. 자세한 내용은 [XML에서 데이터 집합 관계형 구조 유추를](inferring-dataset-relational-structure-from-xml.md)참조하십시오. 그러나 더 적절한 구조는 **범주** 및 **제품** 테이블만 만든 다음 범주 **테이블에서 CategoryID,** **CategoryName**및 **설명** 열을 만들고 **제품** **테이블에서** **ProductID,** **ReorderLevel**및 **단종** 열을 만드는 것입니다. 추론된 스키마가 XML 요소에 지정된 특성을 무시하도록 하려면 **InferXmlSchema** 메서드를 사용하고 다음 예제와 같이 무시할 **Officedata의** XML 네임스페이스를 지정합니다.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a>참고 항목

- [데이터 세트에서 XML 사용](using-xml-in-a-dataset.md)
- [XML 스키마에서 데이터 세트 관계형 구조 파생(XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [XML에서 데이터 세트 관계형 구조 유추](inferring-dataset-relational-structure-from-xml.md)
- [XML에서 데이터 세트 로드](loading-a-dataset-from-xml.md)
- [DataSets, DataTables 및 DataViews](index.md)
- [ADO.NET 개요](../ado-net-overview.md)
