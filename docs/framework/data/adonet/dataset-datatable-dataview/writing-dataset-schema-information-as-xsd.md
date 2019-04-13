---
title: 데이터 집합 스키마 정보를 XSD로 작성
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4e530831-695e-49ff-8f0b-e5b0c526b8eb
ms.openlocfilehash: 8403f9d9be88f34e473fd3512f5499193245d227
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099445"
---
# <a name="writing-dataset-schema-information-as-xsd"></a>데이터 집합 스키마 정보를 XSD로 작성
<xref:System.Data.DataSet>의 스키마를 XSD(XML 스키마 정의 언어) 스키마로 작성하여, 작성한 스키마를 관련된 데이터와 함께 또는 데이터 없이 XML 문서에서 전송할 수 있습니다. XML 스키마 파일, 스트림, 쓸 수는 <xref:System.Xml.XmlWriter>, 문자열 또는 강력한 형식의 생성 하는 데 유용 **데이터 집합**합니다. 에 대 한 자세한 내용은 강력한 **데이터 집합** 개체를 참조 하십시오 [형식화 된 데이터 집합](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)합니다.  
  
 XML 스키마에서 테이블의 열을 표현 하는 방법을 지정할 수 있습니다를 사용 하 여는 **ColumnMapping** 의 속성을 <xref:System.Data.DataColumn> 개체입니다. 자세한 내용은 "열을 XML 요소, 특성 및 텍스트에 매핑"를 참조 하세요 [쓰기 데이터 집합 콘텐츠를 XML 데이터로](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)합니다.  
  
 스키마를 작성 하는 **데이터 집합** 파일에 XML 스키마로 스트림 또는 **XmlWriter**를 사용 하 여는 **WriteXmlSchema** 메서드의 **데이터 집합**. **WriteXmlSchema** 결과로 나타나는 XML 스키마의 대상을 지정 하는 하나의 매개 변수를 사용 합니다. 다음 코드 예제에서는 XML 스키마를 작성 하는 방법을 보여 줍니다는 **데이터 집합** 파일 이름을 포함 하는 문자열을 전달 하 여 파일 및 <xref:System.IO.StreamWriter> 개체입니다.  
  
```vb  
dataSet.WriteXmlSchema("Customers.xsd")  
```  
  
```csharp  
dataSet.WriteXmlSchema("Customers.xsd");  
```  
  
```vb  
Dim writer As System.IO.StreamWriter = New System.IO.StreamWriter("Customers.xsd")  
dataSet.WriteXmlSchema(writer)  
writer.Close()  
```  
  
```csharp  
System.IO.StreamWriter writer = new System.IO.StreamWriter("Customers.xsd");  
dataSet.WriteXmlSchema(writer);  
writer.Close();  
```  
  
 스키마를 가져올는 **데이터 집합** XML 스키마 문자열로 작성을 사용 하 여 합니다 **GetXmlSchema** 메서드를 다음 예제에서와 같이 합니다.  
  
```vb  
Dim schemaString As String = dataSet.GetXmlSchema()  
```  
  
```csharp  
string schemaString = dataSet.GetXmlSchema();  
```  
  
## <a name="see-also"></a>참고자료

- [데이터 집합에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [데이터 집합 콘텐츠를 XML 데이터로 작성](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)
- [형식화된 데이터 집합](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)
- [DataSets, DataTables 및 DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
