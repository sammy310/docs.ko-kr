---
title: XML에서 데이터 집합 로드
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49c083b7-a5ed-41cf-aabc-5aaba96f00e6
ms.openlocfilehash: 0c53e3a15bcbe61db7da1edb31ecd3fd562603f5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099900"
---
# <a name="loading-a-dataset-from-xml"></a>XML에서 데이터 집합 로드
ADO.NET <xref:System.Data.DataSet>의 내용은 XML 스트림이나 문서로부터 만들 수 있습니다. 또한, .NET Framework를 사용하면 XML로부터 로드할 정보와 <xref:System.Data.DataSet>의 스키마나 관계형 구조를 만드는 방법을 매우 융통성 있게 선택할 수 있습니다.  
  
 에 맞게를 <xref:System.Data.DataSet> XML에서 데이터를 사용 합니다 **ReadXml** 메서드의 <xref:System.Data.DataSet> 개체입니다. **ReadXml** 스트림, 파일에서 읽는 메서드 또는 **XmlReader**, XML 및 선택적인 원본 인수로 및 **XmlReadMode** 인수. 에 대 한 자세한 내용은 합니다 **XmlReader**를 참조 하세요 [XmlTextReader 사용 하 여 XML 데이터 읽기](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/tfz3cz6w(v=vs.100)). 합니다 **ReadXml** 메서드는 XML 스트림 또는 문서 및 로드의 콘텐츠를 읽습니다는 <xref:System.Data.DataSet> 데이터를 사용 하 여 합니다. 관계형 스키마 생성 합니다 <xref:System.Data.DataSet> 에 따라 합니다 **XmlReadMode** 지정 하 고 관계형 스키마를 이미 있는지 여부입니다.  
  
 다음 표에서 옵션을 설명 합니다 **XmlReadMode** 인수입니다.  
  
|옵션|설명|  
|------------|-----------------|  
|**자동**|이 값이 기본값입니다. XML을 검사하고 다음 순서에 따라 가장 적합한 옵션을 선택합니다.<br /><br /> -있으면 XML이 DiffGram **DiffGram** 사용 됩니다.<br />-합니다 <xref:System.Data.DataSet> 스키마가 포함 되어 있거나 XML에 인라인 스키마가 **ReadSchema** 사용 됩니다.<br />-는 <xref:System.Data.DataSet> 스키마는 XML에 인라인 스키마가 포함 되어 있지 않습니다 **InferSchema** 사용 됩니다.<br /><br /> 읽고 있는 XML 형식의 알고 있는 경우 최상의 성능을 위해 것이 좋습니다 명시적으로 설정 하는 **XmlReadMode**아닌 하기 보다는 **자동** 기본입니다.|  
|**ReadSchema**|모든 인라인 스키마를 읽은 다음 데이터와 스키마를 로드합니다.<br /><br /> <xref:System.Data.DataSet>에 이미 스키마가 있으면 인라인 스키마의 새 테이블이 <xref:System.Data.DataSet>에 있는 기존 스키마에 추가됩니다. 인라인 스키마의 모든 테이블이 <xref:System.Data.DataSet>에 이미 있으면 예외가 throw됩니다. 사용 하 여 기존 테이블의 스키마를 수정할 수 없습니다 **XmlReadMode.ReadSchema**합니다.<br /><br /> <xref:System.Data.DataSet>에 스키마도 없고 인라인 스키마도 없으면 데이터를 읽지 않습니다.<br /><br /> 인라인 스키마는 XSD(XML 스키마 정의 언어) 스키마를 사용하여 정의할 수 있습니다. XML 스키마로 인라인 스키마를 작성 하는 방법에 대 한 자세한 내용은 참조 하세요 [파생 데이터 집합 관계형 구조에서 XSD (XML 스키마)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)합니다.|  
|**IgnoreSchema**|모든 인라인 스키마를 무시하고 데이터를 기존 <xref:System.Data.DataSet> 스키마로 로드합니다. 기존 스키마와 일치하지 않는 모든 데이터는 삭제됩니다. <xref:System.Data.DataSet>에 스키마가 없으면 데이터를 로드하지 않습니다.<br /><br /> 데이터가 DiffGram 이면 **IgnoreSchema** 와 동일한 기능 **DiffGram** *합니다.*|  
|**InferSchema**|모든 인라인 스키마를 무시하며 XML 데이터의 구조마다 스키마를 유추한 다음 데이터를 로드합니다.<br /><br /> <xref:System.Data.DataSet>에 이미 스키마가 있으면 기존 테이블에 열을 추가하여 현재 스키마를 확장합니다. 기존 테이블이 없으면 테이블이 추가되지 않습니다. 유추된 테이블이 다른 네임스페이스로 이미 존재하거나 유추된 열이 기존 열과 충돌하면 예외가 throw됩니다.<br /><br /> 방법에 대 한 자세한 **ReadXmlSchema** 스키마를 유추에서 XML 문서를 참조 하십시오 [유추에서 데이터 집합 관계형 구조 XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)합니다.|  
|**DiffGram**|DiffGram을 읽은 다음 해당 데이터를 현재 스키마에 추가합니다. **DiffGram** 기존 행의 고유 식별자 값과 일치 하는 위치를 사용 하 여 새 행을 병합 합니다. 이 항목의 맨 뒤에 나오는 "XML로부터 데이터 병합"을 참조하세요. Diffgram에 대 한 자세한 내용은 참조 하세요. [Diffgram](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)합니다.|  
|**Fragment**|스트림의 끝에 도달할 때까지 여러 개의 XML 조각을 계속 읽습니다. <xref:System.Data.DataSet> 스키마에 일치하는 조각이 해당 테이블의 뒤에 추가됩니다. <xref:System.Data.DataSet> 스키마에 일치하지 않는 조각은 삭제됩니다.|  
  
> [!NOTE]
>  전달 하는 경우는 **XmlReader** 하 **ReadXml** 위치 지정된의 일부인 XML 문서로 서 **ReadXml** 는 다음 요소 노드를 읽고 루트로 취급 요소 노드의 맨 끝까지 읽기만 요소입니다. 지정 하는 경우 적용 되지 않습니다 **XmlReadMode.Fragment**합니다.  
  
## <a name="dtd-entities"></a>DTD 엔터티  
 로드 하려고 하면 예외가 throw 됩니다 XML 문서 형식 정의 (DTD) 스키마에 정의 된 엔터티에 있으면 한 <xref:System.Data.DataSet> 파일을 전달 하 여 이름, 스트림 또는 비검증 **XmlReader** 에  **ReadXml**합니다. 대신 만들어야를 **XmlValidatingReader**를 사용 하 여 **EntityHandling** 로 설정 **EntityHandling.ExpandEntities**를 전달 하  **XmlValidatingReader** 하 **ReadXml**합니다. 합니다 **XmlValidatingReader** 에서는에서 읽기 전에 엔터티를 확장 하는 <xref:System.Data.DataSet>합니다.  
  
 다음 코드 예제에서는 XML 스트림으로부터 <xref:System.Data.DataSet>을 로드하는 방법을 보여 줍니다. 첫 번째 예제에 전달 되 고 파일 이름을 표시 합니다 **ReadXml** 메서드. 두 번째 예제에서는 <xref:System.IO.StringReader>를 사용하여 로드될 XML이 포함된 문자열을 보여 줍니다.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXml("input.xml", XmlReadMode.ReadSchema)  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.ReadXml("input.xml", XmlReadMode.ReadSchema);  
```  
  
```vb  
Dim dataSet As DataSet = New DataSet  
Dim dataTable As DataTable = New DataTable("table1")  
dataTable.Columns.Add("col1", Type.GetType("System.String"))  
dataSet.Tables.Add(dataTable)  
  
Dim xmlData As String = "<XmlDS><table1><col1>Value1</col1></table1><table1><col1>Value2</col1></table1></XmlDS>"  
  
Dim xmlSR As System.IO.StringReader = New System.IO.StringReader(xmlData)  
  
dataSet.ReadXml(xmlSR, XmlReadMode.IgnoreSchema)  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
DataTable dataTable = new DataTable("table1");  
dataTable.Columns.Add("col1", typeof(string));  
dataSet.Tables.Add(dataTable);  
  
string xmlData = "<XmlDS><table1><col1>Value1</col1></table1><table1><col1>Value2</col1></table1></XmlDS>";  
  
System.IO.StringReader xmlSR = new System.IO.StringReader(xmlData);  
  
dataSet.ReadXml(xmlSR, XmlReadMode.IgnoreSchema);  
```  
  
> [!NOTE]
>  호출 하는 경우 **ReadXml** 매우 큰 파일을 로드 하려면 성능 저하를 발생할 수 있습니다. 에 대 한 최적의 성능을 보장 **ReadXml**, 큰 파일을 호출 하는 <xref:System.Data.DataTable.BeginLoadData%2A> 의 각 테이블에 대 한 메서드를 <xref:System.Data.DataSet>를 호출 **ReadXml**합니다. 마지막으로 다음 예제와 같이 <xref:System.Data.DataTable.EndLoadData%2A>의 각 테이블에 대해 <xref:System.Data.DataSet>를 호출합니다.  
  
```vb  
Dim dataTable As DataTable  
  
For Each dataTable In dataSet.Tables  
   dataTable.BeginLoadData()  
Next  
  
dataSet.ReadXml("file.xml")  
  
For Each dataTable in dataSet.Tables  
   dataTable.EndLoadData()  
Next  
```  
  
```csharp  
foreach (DataTable dataTable in dataSet.Tables)  
   dataTable.BeginLoadData();  
  
dataSet.ReadXml("file.xml");   
  
foreach (DataTable dataTable in dataSet.Tables)  
   dataTable.EndLoadData();  
```  
  
> [!NOTE]
>  경우에 대 한 XSD 스키마에 <xref:System.Data.DataSet> 포함를 **targetNamespace**데이터를 읽을 수 있습니다, 및를 호출할 때 예외가 발생할 수 있습니다 **ReadXml** 로드 하는 <xref:System.Data.DataSet> 포함 된 xml을 정규화 네임 스페이스가 없는 요소입니다. 이 경우 비 정규화 된 요소를 읽기, 설정 **elementFormDefault** XSD 스키마를 "qualified" 같은 합니다. 예를 들어:  
  
```xml  
<xsd:schema id="customDataSet"   
  elementFormDefault="qualified"  
  targetNamespace="http://www.tempuri.org/customDataSet.xsd"   
  xmlns="http://www.tempuri.org/customDataSet.xsd"   
  xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
  xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
</xsd:schema>  
```  
  
## <a name="merging-data-from-xml"></a>XML로부터 데이터 병합  
 <xref:System.Data.DataSet>에 데이터가 이미 있으면 XML의 새 데이터는 <xref:System.Data.DataSet>에 이미 있는 데이터에 추가됩니다. **ReadXml** XML에서 병합 하지 않습니다는 <xref:System.Data.DataSet> 행 일치 하는 기본 키 정보입니다. XML에서 새 정보를 사용 하 여 기존 행 정보를 덮어쓸지를 사용 하 여 **ReadXml** 새 <xref:System.Data.DataSet>를 차례로 <xref:System.Data.DataSet.Merge%2A> 새 <xref:System.Data.DataSet> 기존 <xref:System.Data.DataSet>합니다. 사용 하 여 DiffGram을 로드 **ReadXML** 사용 하 여는 **XmlReadMode** 의 **DiffGram** 동일한 고유 식별자가 있는 행이 병합 됩니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Data.DataSet.Merge%2A?displayProperty=nameWithType>
- [데이터 집합에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [DiffGram](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)
- [XML 스키마에서 데이터 집합 관계형 구조 파생(XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [XML에서 데이터 집합 관계형 구조 유추](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [XML에서 데이터 집합 스키마 정보 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [DataSets, DataTables 및 DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
