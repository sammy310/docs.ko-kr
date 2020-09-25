---
title: 데이터 세트 스키마 정보를 XSD로 작성
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4e530831-695e-49ff-8f0b-e5b0c526b8eb
ms.openlocfilehash: 7634dfc8415b6f73fc60f2ebe59c92a0c31f83a2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173733"
---
# <a name="writing-dataset-schema-information-as-xsd"></a><span data-ttu-id="279a6-102">데이터 세트 스키마 정보를 XSD로 작성</span><span class="sxs-lookup"><span data-stu-id="279a6-102">Writing DataSet Schema Information as XSD</span></span>

<span data-ttu-id="279a6-103"><xref:System.Data.DataSet>의 스키마를 XSD(XML 스키마 정의 언어) 스키마로 작성하여, 작성한 스키마를 관련된 데이터와 함께 또는 데이터 없이 XML 문서에서 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="279a6-103">You can write the schema of a <xref:System.Data.DataSet> as XML Schema definition language (XSD) schema, so that you can transport it, with or without related data, in an XML document.</span></span> <span data-ttu-id="279a6-104">XML 스키마는 파일, 스트림 또는 문자열에 쓸 수 있습니다. <xref:System.Xml.XmlWriter> 강력한 형식의 **데이터 집합**을 생성 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="279a6-104">XML Schema can be written to a file, a stream, an <xref:System.Xml.XmlWriter>, or a string; it is useful for generating a strongly typed **DataSet**.</span></span> <span data-ttu-id="279a6-105">강력한 형식의 **데이터 집합** 개체에 대 한 자세한 내용은 [형식화 된 데이터](typed-datasets.md)집합을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="279a6-105">For more information about strongly typed **DataSet** objects, see [Typed DataSets](typed-datasets.md).</span></span>  
  
 <span data-ttu-id="279a6-106">개체의 **ColumnMapping** 속성을 사용 하 여 XML 스키마에서 테이블의 열을 표현 하는 방법을 지정할 수 있습니다 <xref:System.Data.DataColumn> .</span><span class="sxs-lookup"><span data-stu-id="279a6-106">You can specify how a column of a table is represented in XML Schema using the **ColumnMapping** property of the <xref:System.Data.DataColumn> object.</span></span> <span data-ttu-id="279a6-107">자세한 내용은 [데이터 집합 콘텐츠를 Xml 데이터로 작성](writing-dataset-contents-as-xml-data.md)의 "xml 요소, 특성 및 텍스트에 열 매핑"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="279a6-107">For more information, see "Mapping Columns to XML Elements, Attributes, and Text" in [Writing DataSet Contents as XML Data](writing-dataset-contents-as-xml-data.md).</span></span>  
  
 <span data-ttu-id="279a6-108">**데이터 집합** 의 스키마를 XML 스키마로 작성 하려면 파일, 스트림 또는 **XmlWriter**에 **데이터 집합**의 **WriteXmlSchema** 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="279a6-108">To write the schema of a **DataSet** as XML Schema, to a file, stream, or **XmlWriter**, use the **WriteXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="279a6-109">**WriteXmlSchema** 는 결과 XML 스키마의 대상을 지정 하는 매개 변수 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="279a6-109">**WriteXmlSchema** takes one parameter that specifies the destination of the resulting XML Schema.</span></span> <span data-ttu-id="279a6-110">다음 코드 예제에서는 파일 이름 및 개체를 포함 하는 문자열을 전달 하 여 **데이터 집합** 의 XML 스키마를 파일에 쓰는 방법을 보여 줍니다 <xref:System.IO.StreamWriter> .</span><span class="sxs-lookup"><span data-stu-id="279a6-110">The following code examples demonstrate how to write the XML Schema of a **DataSet** to a file by passing a string containing a file name and a <xref:System.IO.StreamWriter> object.</span></span>  
  
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
  
 <span data-ttu-id="279a6-111">**데이터 집합** 의 스키마를 가져와서 XML 스키마 문자열로 작성 하려면 다음 예제와 같이 **getxmlschema** 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="279a6-111">To obtain the schema of a **DataSet** and write it as an XML Schema string, use the **GetXmlSchema** method, as shown in the following example.</span></span>  
  
```vb  
Dim schemaString As String = dataSet.GetXmlSchema()  
```  
  
```csharp  
string schemaString = dataSet.GetXmlSchema();  
```  
  
## <a name="see-also"></a><span data-ttu-id="279a6-112">참조</span><span class="sxs-lookup"><span data-stu-id="279a6-112">See also</span></span>

- [<span data-ttu-id="279a6-113">데이터 세트에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="279a6-113">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="279a6-114">데이터 세트 콘텐츠를 XML 데이터로 작성</span><span class="sxs-lookup"><span data-stu-id="279a6-114">Writing DataSet Contents as XML Data</span></span>](writing-dataset-contents-as-xml-data.md)
- [<span data-ttu-id="279a6-115">형식화된 데이터 세트</span><span class="sxs-lookup"><span data-stu-id="279a6-115">Typed DataSets</span></span>](typed-datasets.md)
- [<span data-ttu-id="279a6-116">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="279a6-116">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="279a6-117">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="279a6-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
