---
title: XML에서 데이터 세트 스키마 정보 로드
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
ms.openlocfilehash: d834f0c4517f4ff9fe8645257d5a947c03893881
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968404"
---
# <a name="loading-dataset-schema-information-from-xml"></a><span data-ttu-id="dc3b6-102">XML에서 데이터 세트 스키마 정보 로드</span><span class="sxs-lookup"><span data-stu-id="dc3b6-102">Loading DataSet Schema Information from XML</span></span>
<span data-ttu-id="dc3b6-103"><xref:System.Data.DataSet>의 스키마 (테이블, 열, 관계 및 제약 조건)는 <xref:System.Data.Common.DataAdapter>의 **Fill** 또는 **FillSchema** 메서드를 통해 만들거나 XML 문서에서 로드 하 여 프로그래밍 방식으로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc3b6-103">The schema of a <xref:System.Data.DataSet> (its tables, columns, relations, and constraints) can be defined programmatically, created by the **Fill** or **FillSchema** methods of a <xref:System.Data.Common.DataAdapter>, or loaded from an XML document.</span></span> <span data-ttu-id="dc3b6-104">XML 문서에서 **데이터 집합** 스키마 정보를 로드 하기 위해 **데이터 집합**의 **readxmlschema** 또는 **InferXmlSchema** 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc3b6-104">To load **DataSet** schema information from an XML document, you can use either the **ReadXmlSchema** or the **InferXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="dc3b6-105">**Readxmlschema** 를 사용 하면 XSD (xml 스키마 정의 언어) 스키마가 포함 된 문서나 인라인 xml 스키마를 사용 하는 xml 문서에서 **데이터 집합** 스키마 정보를 로드 하거나 유추할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc3b6-105">**ReadXmlSchema** allows you to load or infer **DataSet** schema information from the document containing XML Schema definition language (XSD) schema, or an XML document with inline XML Schema.</span></span> <span data-ttu-id="dc3b6-106">**InferXmlSchema** 를 사용 하면 지정한 특정 xml 네임 스페이스를 무시 하 고 xml 문서에서 스키마를 유추할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc3b6-106">**InferXmlSchema** allows you to infer the schema from the XML document while ignoring certain XML namespaces that you specify.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dc3b6-107">웹 서비스 또는 XML serialization을 사용 하 여 XSD 구문을 사용 하 여 메모리 내에 생성 된 **데이터 집합** 을 전송 하는 경우 (예: 중첩 된 관계) **데이터 집합** 의 테이블 순서가 유지 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc3b6-107">Table ordering in a **DataSet** might not be preserved when you use Web services or XML serialization to transfer a **DataSet** that was created in-memory by using XSD constructs (such as nested relations).</span></span> <span data-ttu-id="dc3b6-108">따라서이 경우에는 **데이터 집합** 의 수신자가 테이블 순서에 종속 되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc3b6-108">Therefore, the recipient of the **DataSet** should not depend on table ordering in this case.</span></span> <span data-ttu-id="dc3b6-109">그러나 전송 중인 **데이터 집합** 의 스키마를 메모리 내에서 만들지 않고 XSD 파일에서 읽는 경우에는 항상 테이블 순서가 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc3b6-109">However, table ordering is always preserved if the schema of the **DataSet** being transferred was read from XSD files, instead of being created in-memory.</span></span>  
  
## <a name="readxmlschema"></a><span data-ttu-id="dc3b6-110">ReadXmlSchema</span><span class="sxs-lookup"><span data-stu-id="dc3b6-110">ReadXmlSchema</span></span>  
 <span data-ttu-id="dc3b6-111">데이터를 로드 하지 않고 XML 문서에서 데이터 **집합** 의 스키마를 로드 하려면 데이터 **집합**의 **readxmlschema** 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc3b6-111">To load the schema of a **DataSet** from an XML document without loading any data, you can use the **ReadXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="dc3b6-112">**Readxmlschema** 는 XSD (XML 스키마 정의 언어) 스키마를 사용 하 여 정의 된 **데이터 집합** 스키마를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dc3b6-112">**ReadXmlSchema** creates **DataSet** schema defined using XML Schema definition language (XSD) schema.</span></span>  
  
 <span data-ttu-id="dc3b6-113">**Readxmlschema** 메서드는 로드할 XML 문서가 포함 된 파일 이름, 스트림 또는 **XmlReader** 의 단일 인수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc3b6-113">The **ReadXmlSchema** method takes a single argument of a file name, a stream, or an **XmlReader** containing the XML document to be loaded.</span></span> <span data-ttu-id="dc3b6-114">XML 문서에는 스키마만 있을 수도 있고 데이터가 포함된 XML 요소를 가진 스키마 인라인이 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc3b6-114">The XML document can contain only schema, or can contain schema inline with XML elements containing data.</span></span> <span data-ttu-id="dc3b6-115">인라인 스키마를 XML 스키마로 작성 하는 방법에 대 한 자세한 내용은 [Xml 스키마에서 데이터 집합 관계형 구조 파생 (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dc3b6-115">For details about writing inline schema as XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
 <span data-ttu-id="dc3b6-116">**Readxmlschema** 에 전달 된 xml 문서에 인라인 스키마 정보가 포함 되어 있지 않은 경우 **READXMLSCHEMA** 는 xml 문서의 요소에서 스키마를 유추 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc3b6-116">If the XML document passed to **ReadXmlSchema** contains no inline schema information, **ReadXmlSchema** will infer the schema from the elements in the XML document.</span></span> <span data-ttu-id="dc3b6-117">**데이터 집합** 에 이미 스키마가 있으면 새 테이블을 추가 하 여 현재 스키마를 확장 하는 것입니다 (아직 없는 경우).</span><span class="sxs-lookup"><span data-stu-id="dc3b6-117">If the **DataSet** already contains a schema, the current schema will be extended by adding new tables if they do not already exist.</span></span> <span data-ttu-id="dc3b6-118">새 열은 기존 테이블에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc3b6-118">New columns will not be added to added to existing tables.</span></span> <span data-ttu-id="dc3b6-119">추가 되는 열이 **DataSet** 에 이미 있지만 XML에 있는 열과 호환 되지 않는 형식을 포함 하는 경우 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc3b6-119">If a column being added already exists in the **DataSet** but has an incompatible type with the column found in the XML, an exception is thrown.</span></span> <span data-ttu-id="dc3b6-120">**Readxmlschema** 에서 xml 문서의 스키마를 유추 하는 방법에 대 한 자세한 내용은 [Xml에서 데이터 집합 관계형 구조 유추](inferring-dataset-relational-structure-from-xml.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dc3b6-120">For details about how **ReadXmlSchema** infers a schema from an XML document, see [Inferring DataSet Relational Structure from XML](inferring-dataset-relational-structure-from-xml.md).</span></span>  
  
 <span data-ttu-id="dc3b6-121">**Readxmlschema** 는 **데이터 집합**의 스키마만 로드 하거나 유추 하지만 **데이터 집합** 의 **ReadXml** 메서드는 XML 문서에 포함 된 스키마와 데이터를 모두 로드 하거나 유추 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc3b6-121">Although **ReadXmlSchema** loads or infers only the schema of a **DataSet**, the **ReadXml** method of the **DataSet** loads or infers both the schema and the data contained in the XML document.</span></span> <span data-ttu-id="dc3b6-122">자세한 내용은 [XML에서 데이터 집합 로드](loading-a-dataset-from-xml.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dc3b6-122">For more information, see [Loading a DataSet from XML](loading-a-dataset-from-xml.md).</span></span>  
  
 <span data-ttu-id="dc3b6-123">다음 코드 예제에서는 XML 문서 또는 스트림에서 **데이터 집합** 스키마를 로드 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dc3b6-123">The following code examples show how to load a **DataSet** schema from an XML document or stream.</span></span> <span data-ttu-id="dc3b6-124">첫 번째 예에서는 **Readxmlschema** 메서드에 전달 되는 XML 스키마 파일 이름을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dc3b6-124">The first example shows an XML Schema file name being passed to the **ReadXmlSchema** method.</span></span> <span data-ttu-id="dc3b6-125">두 번째 예제에서는 **system.web**을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dc3b6-125">The second example shows a **System.IO.StreamReader**.</span></span>  
  
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
  
## <a name="inferxmlschema"></a><span data-ttu-id="dc3b6-126">InferXmlSchema</span><span class="sxs-lookup"><span data-stu-id="dc3b6-126">InferXmlSchema</span></span>  
 <span data-ttu-id="dc3b6-127">데이터 **집합**의 **InferXmlSchema** 메서드를 사용 하 여 XML 문서에서 스키마를 유추 하도록 **데이터 집합** 에 지시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc3b6-127">You can also instruct the **DataSet** to infer its schema from an XML document using the **InferXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="dc3b6-128">**InferXmlSchema** 는 **InferSchema** 의 **XmlReadMode** (데이터 로드 및 스키마 유추)를 사용 하 여 두 **ReadXml** 를 모두 수행 하는 것과 동일 하 게 작동 하며 읽을 문서에 인라인 스키마가 없는 경우에는 **readxmlschema** 를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc3b6-128">**InferXmlSchema** functions the same as do both **ReadXml** with an **XmlReadMode** of **InferSchema** (loads data as well as infers schema), and **ReadXmlSchema** if the document being read contains no inline schema.</span></span> <span data-ttu-id="dc3b6-129">그러나 **InferXmlSchema** 는 스키마를 유추할 때 무시할 특정 XML 네임 스페이스를 지정할 수 있는 추가 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc3b6-129">However, **InferXmlSchema** provides the additional capability of allowing you to specify particular XML namespaces to be ignored when the schema is inferred.</span></span> <span data-ttu-id="dc3b6-130">**InferXmlSchema** 은 파일 이름, 스트림 또는 **XmlReader**로 지정 된 XML 문서의 위치를 사용 하 여 두 개의 필수 인수를 사용 합니다. 작업에서 무시할 XML 네임 스페이스의 문자열 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="dc3b6-130">**InferXmlSchema** takes two required arguments: the location of the XML document, specified by a file name, a stream, or an **XmlReader**; and a string array of XML namespaces to be ignored by the operation.</span></span>  
  
 <span data-ttu-id="dc3b6-131">예를 들어, 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="dc3b6-131">For example, consider the following XML:</span></span>  
  
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
  
 <span data-ttu-id="dc3b6-132">이전 XML 문서의 요소에 대해 지정 된 특성으로 인해 **Readxmlschema** 메서드와 **XmlReadMode** of **InferSchema** 를 사용 하는 **ReadXml** 메서드는 모두 문서의 모든 요소에 대 한 **테이블을 만듭니다**. **Categories**, **CategoryID**, 범주, **설명**, **제품**, **ProductID**, **ReorderLevel**및 **단종**.</span><span class="sxs-lookup"><span data-stu-id="dc3b6-132">Because of the attributes specified for the elements in the preceding XML document, both the **ReadXmlSchema** method and the **ReadXml** method with an **XmlReadMode** of **InferSchema** would create tables for every element in the document: **Categories**, **CategoryID**, **CategoryName**, **Description**, **Products**, **ProductID**, **ReorderLevel**, and **Discontinued**.</span></span> <span data-ttu-id="dc3b6-133">자세한 내용은 [XML에서 데이터 집합 관계형 구조 유추](inferring-dataset-relational-structure-from-xml.md)를 참조 하세요. 그러나 더 적절 한 구조는 **범주** 및 **Products** 테이블만 만든 다음, categories 테이블에 **CategoryID**, **Categories** 및 **Description** 열을만들고 **Products** 테이블에 **ProductID**, **ReorderLevel**및 **단종** 열을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dc3b6-133">(For more information, see [Inferring DataSet Relational Structure from XML](inferring-dataset-relational-structure-from-xml.md).) However, a more appropriate structure would be to create only the **Categories** and **Products** tables, and then to create **CategoryID**, **CategoryName**, and **Description** columns in the **Categories** table, and **ProductID**, **ReorderLevel**, and **Discontinued** columns in the **Products** table.</span></span> <span data-ttu-id="dc3b6-134">유추 된 스키마가 XML 요소에 지정 된 특성을 무시 하도록 하려면 다음 예제와 같이 **InferXmlSchema** 메서드를 사용 하 고 삭제할 **데이터** 의 XML 네임 스페이스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc3b6-134">To ensure that the inferred schema ignores the attributes specified in the XML elements, use the **InferXmlSchema** method and specify the XML namespace for **officedata** to be ignored, as shown in the following example.</span></span>  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a><span data-ttu-id="dc3b6-135">참조</span><span class="sxs-lookup"><span data-stu-id="dc3b6-135">See also</span></span>

- [<span data-ttu-id="dc3b6-136">데이터 세트에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="dc3b6-136">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="dc3b6-137">XML 스키마에서 데이터 세트 관계형 구조 파생(XSD)</span><span class="sxs-lookup"><span data-stu-id="dc3b6-137">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [<span data-ttu-id="dc3b6-138">XML에서 데이터 세트 관계형 구조 유추</span><span class="sxs-lookup"><span data-stu-id="dc3b6-138">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="dc3b6-139">XML에서 데이터 세트 로드</span><span class="sxs-lookup"><span data-stu-id="dc3b6-139">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="dc3b6-140">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="dc3b6-140">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="dc3b6-141">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="dc3b6-141">ADO.NET Overview</span></span>](../ado-net-overview.md)
