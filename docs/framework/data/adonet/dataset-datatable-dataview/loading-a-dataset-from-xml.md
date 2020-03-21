---
title: XML에서 데이터 세트 로드
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49c083b7-a5ed-41cf-aabc-5aaba96f00e6
ms.openlocfilehash: c21ed3bb31add285d64272040680433fff4e16fd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151067"
---
# <a name="loading-a-dataset-from-xml"></a>XML에서 데이터 세트 로드
ADO.NET <xref:System.Data.DataSet>의 내용은 XML 스트림이나 문서로부터 만들 수 있습니다. 또한, .NET Framework를 사용하면 XML로부터 로드할 정보와 <xref:System.Data.DataSet>의 스키마나 관계형 구조를 만드는 방법을 매우 융통성 있게 선택할 수 있습니다.  
  
 XML의 <xref:System.Data.DataSet> 데이터로 채우려면 개체의 **ReadXml** 메서드를 <xref:System.Data.DataSet> 사용합니다. **ReadXml** 메서드는 파일, 스트림 또는 **XmlReader에서**읽으며 XML소스와 선택적 **XmlReadMode** 인수를 인수로 사용합니다. **XmlReader에**대한 자세한 내용은 [XmlTextReader를 사용하여 XML 데이터 읽기를](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/tfz3cz6w(v=vs.100))참조하십시오. **ReadXml** 메서드는 XML 스트림 또는 문서의 내용을 <xref:System.Data.DataSet> 읽고 데이터로 로드합니다. 또한 지정된 <xref:System.Data.DataSet> **XmlReadMode** 및 관계형 스키마가 이미 있는지 여부에 따라 관계형 스키마를 만듭니다.  
  
 다음 표는 **XmlReadMode** 인수에 대한 옵션을 설명합니다.  
  
|옵션|Description|  
|------------|-----------------|  
|**자동**|이것이 기본값입니다. XML을 검사하고 다음 순서에 따라 가장 적합한 옵션을 선택합니다.<br /><br /> - XML이 DiffGram인 경우 **DiffGram이** 사용됩니다.<br />- 스키마가 <xref:System.Data.DataSet> 포함되어 있거나 XML에 인라인 스키마가 포함된 경우 **ReadSchema가** 사용됩니다.<br />- 스키마를 <xref:System.Data.DataSet> 포함하지 않고 XML에 인라인 스키마가 포함되어 있지 않으면 **InferSchema가** 사용됩니다.<br /><br /> XML의 형식을 읽는 경우 최상의 성능을 위해 **자동** 기본값을 수락하는 대신 명시적 **XmlReadMode를**설정하는 것이 좋습니다.|  
|**ReadSchema**|모든 인라인 스키마를 읽은 다음 데이터와 스키마를 로드합니다.<br /><br /> <xref:System.Data.DataSet>에 이미 스키마가 있으면 인라인 스키마의 새 테이블이 <xref:System.Data.DataSet>에 있는 기존 스키마에 추가됩니다. 인라인 스키마의 모든 테이블이 <xref:System.Data.DataSet>에 이미 있으면 예외가 throw됩니다. **XmlReadMode.ReadSchema**을 사용 하 여 기존 테이블의 스키마를 수정할 수 없습니다.<br /><br /> <xref:System.Data.DataSet>에 스키마도 없고 인라인 스키마도 없으면 데이터를 읽지 않습니다.<br /><br /> 인라인 스키마는 XSD(XML 스키마 정의 언어) 스키마를 사용하여 정의할 수 있습니다. XML 스키마로 인라인 스키마를 작성하는 것에 대한 자세한 내용은 [XML 스키마(XSD)의 데이터 집합 관계형 구조 파생을](deriving-dataset-relational-structure-from-xml-schema-xsd.md)참조하십시오.|  
|**무시스키마**|모든 인라인 스키마를 무시하고 데이터를 기존 <xref:System.Data.DataSet> 스키마로 로드합니다. 기존 스키마와 일치하지 않는 모든 데이터는 삭제됩니다. <xref:System.Data.DataSet>에 스키마가 없으면 데이터를 로드하지 않습니다.<br /><br /> 데이터가 DiffGram인 경우 **IgnoreSchema는** **DiffGram** *과* 동일한 기능을 가짐을 가지며|  
|**InferSchema**|모든 인라인 스키마를 무시하며 XML 데이터의 구조마다 스키마를 유추한 다음 데이터를 로드합니다.<br /><br /> <xref:System.Data.DataSet>에 이미 스키마가 있으면 기존 테이블에 열을 추가하여 현재 스키마를 확장합니다. 기존 테이블이 없으면 테이블이 추가되지 않습니다. 유추된 테이블이 다른 네임스페이스로 이미 존재하거나 유추된 열이 기존 열과 충돌하면 예외가 throw됩니다.<br /><br /> **ReadXmlSchema가** XML 문서에서 스키마를 유추하는 방법에 대한 자세한 내용은 [XML의 데이터 집합 관계형 구조 추론을](inferring-dataset-relational-structure-from-xml.md)참조하십시오.|  
|**Diffgram**|DiffGram을 읽은 다음 해당 데이터를 현재 스키마에 추가합니다. **DiffGram은** 고유 식별자 값이 일치하는 기존 행과 새 행을 병합합니다. 이 항목의 맨 뒤에 나오는 "XML로부터 데이터 병합"을 참조하세요. DiffGrams에 대한 자세한 내용은 [DiffGrams](diffgrams.md)를 참조하십시오.|  
|**조각**|스트림의 끝에 도달할 때까지 여러 개의 XML 조각을 계속 읽습니다. <xref:System.Data.DataSet> 스키마에 일치하는 조각이 해당 테이블의 뒤에 추가됩니다. <xref:System.Data.DataSet> 스키마에 일치하지 않는 조각은 삭제됩니다.|  
  
> [!NOTE]
> XML 문서에 위치하는 **ReadXml에** **XmlReader를** 전달하면 **ReadXml은** 다음 요소 노드로 읽고 요소 노드가 끝날 때까지 읽는 루트 요소로 처리합니다. **XmlReadMode.Fragment.**  
  
## <a name="dtd-entities"></a>DTD 엔터티  
 XML에 문서 형식 정의(DTD) 스키마에 정의된 엔터티가 포함되어 있는 경우 파일 이름, 스트림 또는 유효성이 검사되지 않는 <xref:System.Data.DataSet> **XmlReader를** **ReadXml에**전달하여 로드하려고 하면 예외가 throw됩니다. 대신 **엔터티 처리가 EntityHandling.ExpandEntities로** 설정된 **EntityHandling.ExpandEntities** **XmlValidatingReader를**만들고 **XmlValidatingReader를** **ReadXml로**전달해야 합니다. **XmlValidatingReader는** <xref:System.Data.DataSet>을 읽기 전에 엔터티를 확장합니다.  
  
 다음 코드 예제에서는 XML 스트림으로부터 <xref:System.Data.DataSet>을 로드하는 방법을 보여 줍니다. 첫 번째 예제에서는 **ReadXml** 메서드에 전달되는 파일 이름을 보여 주습니다. 두 번째 예제에서는 <xref:System.IO.StringReader>를 사용하여 로드될 XML이 포함된 문자열을 보여 줍니다.  
  
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
> **ReadXml을** 호출하여 매우 큰 파일을 로드하면 성능이 저하될 수 있습니다. **ReadXml에**대한 최상의 성능을 보장하려면 큰 <xref:System.Data.DataTable.BeginLoadData%2A> 파일에서 <xref:System.Data.DataSet>의 각 테이블에 대한 메서드를 호출한 다음 **ReadXml을**호출합니다. 마지막으로 다음 예제와 같이 <xref:System.Data.DataTable.EndLoadData%2A>의 각 테이블에 대해 <xref:System.Data.DataSet>를 호출합니다.  
  
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
> <xref:System.Data.DataSet> **대상Namespace에**대한 XSD 스키마에 데이터가 읽을 수 없는 경우 **ReadXml을** 호출하여 적격네임스페이스가 없는 요소를 포함하는 <xref:System.Data.DataSet> XML을 로드할 때 예외가 발생할 수 있습니다. 이 경우 정규화되지 않은 요소를 읽으려면 XSD 스키마에서 "정규화"와 동일한 **elementFormDefault를** 설정합니다. 다음은 그 예입니다.  
  
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
 <xref:System.Data.DataSet>에 데이터가 이미 있으면 XML의 새 데이터는 <xref:System.Data.DataSet>에 이미 있는 데이터에 추가됩니다. **ReadXml은** XML에서 일치하는 기본 <xref:System.Data.DataSet> 키가 있는 행 정보로 병합되지 않습니다. XML의 새 정보로 기존 행 정보를 덮어쓰려면 **ReadXml을** <xref:System.Data.DataSet>사용하여 새 을 만든 다음 <xref:System.Data.DataSet.Merge%2A> 새 <xref:System.Data.DataSet> 를 기존 <xref:System.Data.DataSet>에 새 로 만듭니다. **ReadXML을** 사용하여 **DiffGram을 DiffGram의** **XmlReadMode로** 로드하면 동일한 고유 식별자가 있는 행이 병합됩니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Data.DataSet.Merge%2A?displayProperty=nameWithType>
- [데이터 세트에서 XML 사용](using-xml-in-a-dataset.md)
- [DiffGram](diffgrams.md)
- [XML 스키마에서 데이터 세트 관계형 구조 파생(XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [XML에서 데이터 세트 관계형 구조 유추](inferring-dataset-relational-structure-from-xml.md)
- [XML에서 데이터 세트 스키마 정보 로드](loading-dataset-schema-information-from-xml.md)
- [DataSets, DataTables 및 DataViews](index.md)
- [ADO.NET 개요](../ado-net-overview.md)
