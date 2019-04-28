---
title: XML에서 데이터 집합 스키마 정보 로드
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
ms.openlocfilehash: 06dcbbedf8c1533b3da52b447c121746ce705083
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785452"
---
# <a name="loading-dataset-schema-information-from-xml"></a>XML에서 데이터 집합 스키마 정보 로드
스키마를 <xref:System.Data.DataSet> (해당 테이블, 열, 관계 및 제약 조건) 정의할 수 있습니다 프로그래밍 방식으로 만든 합니다 **채우기** 또는 **FillSchema** 의 메서드는 <xref:System.Data.Common.DataAdapter>에서 로드 또는 XML 문서입니다. 로드할 **데이터 집합** 스키마 정보 XML 문서에서 사용할 수 있습니다 합니다 **ReadXmlSchema** 또는 **InferXmlSchema** 메서드의 **데이터집합**. **ReadXmlSchema** 로드 하거나 유추할 수 있습니다 **데이터 집합** XML 스키마 정의 언어 (XSD), 또는 인라인 XML 스키마를 사용 하 여 XML 문서를 포함 하는 문서에서 스키마 정보입니다. **InferXmlSchema** 지정 하는 특정 XML 네임 스페이스를 무시 하는 동안 XML 문서에서 스키마를 유추할 수 있습니다.  
  
> [!NOTE]
>  테이블에서 순서를 **데이터 집합** 전송할 웹 서비스나 XML serialization을 사용할 때 유지 되지 않을 수 있습니다는 **데이터 집합** XSD 구문 (예: 중첩된 관계)를 사용 하 여 메모리에 생성 된 합니다. 따라서 받는 사람을 **데이터 집합** 테이블이 경우 순서에 따라 달라 지지 합니다. 그러나 테이블 순서는 항상 유지 하는 경우의 스키마를 **데이터 집합** 메모리를 생성 하는 대신 XSD 파일에서 읽은 전송할 합니다.  
  
## <a name="readxmlschema"></a>ReadXmlSchema  
 스키마를 로드할 수는 **데이터 집합** 모든 데이터를 로드 하지 않고 XML 문서에서 사용할 수 있습니다 합니다 **ReadXmlSchema** 메서드를 **데이터 집합**. **ReadXmlSchema** 만듭니다 **데이터 집합** XML 스키마 정의 언어 (XSD)를 사용 하 여 정의 된 스키마입니다.  
  
 합니다 **ReadXmlSchema** 메서드는 파일 이름, 스트림, 단일 인수 또는 **XmlReader** 로드할 XML 문서가 포함 된 합니다. XML 문서에는 스키마만 있을 수도 있고 데이터가 포함된 XML 요소를 가진 스키마 인라인이 있을 수도 있습니다. XML 스키마로 인라인 스키마를 작성 하는 방법에 대 한 자세한 내용은 참조 하세요 [파생 데이터 집합 관계형 구조에서 XSD (XML 스키마)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)합니다.  
  
 XML 문서를 전달 하면 **ReadXmlSchema** 인라인 스키마 정보가 없으면 포함 **ReadXmlSchema** XML 문서의 요소에서 스키마를 유추 됩니다. 경우는 **데이터 집합** 이미 스키마가 포함 되어 아직 존재 하지 않는 경우 새 테이블을 추가 하 여 현재 스키마를 확장 합니다. 새 열은 기존 테이블에 추가되지 않습니다. 이미 추가 되는 열에 있는 경우는 **데이터 집합** 있지만 열과는 호환 되지 않는 형식이 있는 XML에서 예외가 throw 됩니다. 방법에 대 한 자세한 **ReadXmlSchema** 스키마를 유추에서 XML 문서를 참조 하십시오 [유추에서 데이터 집합 관계형 구조 XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)합니다.  
  
 하지만 **ReadXmlSchema** 로드 하거나 유추의 스키마만을 **데이터 집합**의 **ReadXml** 메서드를 **데이터 집합** 로드 하거나 유추 둘 다 스키마 및 XML 문서에 포함 된 데이터입니다. 자세한 내용은 [XML에서 DataSet 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)합니다.  
  
 다음 코드 예제에 로드 하는 방법을 보여 줍니다는 **데이터 집합** 스키마는 XML 문서 또는 스트림에에서. 첫 번째 예제로 전달 되는 XML 스키마 파일 이름을 표시 합니다 **ReadXmlSchema** 메서드. 에서는 두 번째 예제는 **System.IO.StreamReader**합니다.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXmlSchema("schema.xsd")  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.ReadXmlSchema("schema.xsd");  
```  
  
```vb  
Dim xmlStream As System.IO.StreamReader = New System.IO.StreamReader ("schema.xsd");  
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
 지시할 수도 있습니다는 **데이터 집합** 사용 하 여 XML 문서에서 해당 스키마를 유추 하는 **InferXmlSchema** 메서드를 **데이터 집합**합니다. **InferXmlSchema** 동일한 기능을 모두 수행 하는 대로 **ReadXml** 사용 하 여를 **XmlReadMode** 의 **InferSchema** (데이터 로드 뿐만 아니라 스키마를 유추), 및 **ReadXmlSchema** 읽고 있는 문서에 인라인 스키마가 없는 경우. 그러나 **InferXmlSchema** 스키마가 유추 될 때 무시할 특정 XML 네임 스페이스를 지정 하는 수의 추가 기능을 제공 합니다. **InferXmlSchema** 는 두 개의 필수 인수: 스트림, 파일 이름으로 지정 된 XML 문서의 위치 또는 **XmlReader**; 및 작업에 의해 무시 될 XML 네임 스페이스의 문자열 배열입니다.  
  
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
  
 이전 XML 문서의 요소에 대 한 지정 된 특성으로 인해 모두를 **ReadXmlSchema** 메서드 및 **ReadXml** 메서드를 **XmlReadMode** 의 **InferSchema** 문서의 모든 요소에 대 한 테이블을 만듭니다. **범주**, **CategoryID**를 **CategoryName**를 **설명을**를 **제품**, **ProductID**하십시오 **ReorderLevel**, 및 **지원 되지 않는**합니다. (자세한 내용은 [유추에서 데이터 집합 관계형 구조 XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).) 그러나 더 적절 한 구조를 만드는 것만 합니다 **범주** 및 **제품** 테이블을 만든 다음 **CategoryID**, **CategoryName** , 및 **설명을** 열에는 **범주** 테이블 및 **ProductID**를 **ReorderLevel**, 및 **Discontinued** 열에는 **제품** 테이블입니다. 유추 된 스키마는 XML 요소에 지정 된 특성을 무시 하도록 사용 합니다 **InferXmlSchema** 메서드 XML 네임 스페이스를 지정 하 고 **officedata** 에서처럼 무시할는 다음 예입니다.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a>참고자료

- [데이터 집합에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [XML 스키마에서 데이터 세트 관계형 구조 파생(XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [XML에서 데이터 세트 관계형 구조 유추](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [XML에서 데이터 세트 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [DataSet, DataTable 및 DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
