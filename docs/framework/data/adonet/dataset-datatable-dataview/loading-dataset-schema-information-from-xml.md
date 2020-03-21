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
# <a name="loading-dataset-schema-information-from-xml"></a><span data-ttu-id="8605b-102">XML에서 데이터 세트 스키마 정보 로드</span><span class="sxs-lookup"><span data-stu-id="8605b-102">Loading DataSet Schema Information from XML</span></span>
<span data-ttu-id="8605b-103">a의 <xref:System.Data.DataSet> 스키마(해당 테이블, 열, 관계식 및 제약 조건)는 프로그래밍 방식으로 정의하거나, **의 Fill** 또는 **FillSchema** 메서드에 <xref:System.Data.Common.DataAdapter>의해 만들어지거나 XML 문서에서 로드될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8605b-103">The schema of a <xref:System.Data.DataSet> (its tables, columns, relations, and constraints) can be defined programmatically, created by the **Fill** or **FillSchema** methods of a <xref:System.Data.Common.DataAdapter>, or loaded from an XML document.</span></span> <span data-ttu-id="8605b-104">XML 문서에서 **DataSet** 스키마 정보를 로드하려면 **ReadXmlSchema** 또는 **DataSet의** **InferXmlSchema** 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8605b-104">To load **DataSet** schema information from an XML document, you can use either the **ReadXmlSchema** or the **InferXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="8605b-105">**ReadXmlSchema를** 사용하면 XML 스키마 정의 언어(XSD) 스키마또는 인라인 XML 스키마가 포함된 XML 문서가 포함된 문서에서 **DataSet** 스키마 정보를 로드하거나 추론할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8605b-105">**ReadXmlSchema** allows you to load or infer **DataSet** schema information from the document containing XML Schema definition language (XSD) schema, or an XML document with inline XML Schema.</span></span> <span data-ttu-id="8605b-106">**InferXmlSchema를** 사용하면 지정한 특정 XML 네임스페이스를 무시하면서 XML 문서에서 스키마를 유추할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8605b-106">**InferXmlSchema** allows you to infer the schema from the XML document while ignoring certain XML namespaces that you specify.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8605b-107">웹 서비스 또는 XML 직렬화를 사용하여 XSD 구문(예: 중첩 된 관계)을 사용하여 메모리내로 만든 **DataSet을** 전송하는 경우 **DataSet의** 테이블 순서가 유지되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8605b-107">Table ordering in a **DataSet** might not be preserved when you use Web services or XML serialization to transfer a **DataSet** that was created in-memory by using XSD constructs (such as nested relations).</span></span> <span data-ttu-id="8605b-108">따라서 **DataSet의** 받는 사람은 이 경우 테이블 순서에 의존해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8605b-108">Therefore, the recipient of the **DataSet** should not depend on table ordering in this case.</span></span> <span data-ttu-id="8605b-109">그러나 전송중인 **DataSet의** 스키마가 메모리 내로 생성되는 대신 XSD 파일에서 읽은 경우 테이블 순서는 항상 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="8605b-109">However, table ordering is always preserved if the schema of the **DataSet** being transferred was read from XSD files, instead of being created in-memory.</span></span>  
  
## <a name="readxmlschema"></a><span data-ttu-id="8605b-110">ReadXmlSchema</span><span class="sxs-lookup"><span data-stu-id="8605b-110">ReadXmlSchema</span></span>  
 <span data-ttu-id="8605b-111">데이터를 로드하지 않고 XML 문서에서 **DataSet** 스키마를 로드하려면 **DataSet의** **ReadXmlSchema** 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8605b-111">To load the schema of a **DataSet** from an XML document without loading any data, you can use the **ReadXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="8605b-112">**ReadXmlSchema는** XML 스키마 정의 언어(XSD) 스키마를 사용하여 정의된 **데이터 집합** 스키마를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8605b-112">**ReadXmlSchema** creates **DataSet** schema defined using XML Schema definition language (XSD) schema.</span></span>  
  
 <span data-ttu-id="8605b-113">**ReadXmlSchema** 메서드는 로드할 XML 문서를 포함하는 파일 이름, 스트림 또는 **XmlReader의** 단일 인수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8605b-113">The **ReadXmlSchema** method takes a single argument of a file name, a stream, or an **XmlReader** containing the XML document to be loaded.</span></span> <span data-ttu-id="8605b-114">XML 문서에는 스키마만 있을 수도 있고 데이터가 포함된 XML 요소를 가진 스키마 인라인이 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8605b-114">The XML document can contain only schema, or can contain schema inline with XML elements containing data.</span></span> <span data-ttu-id="8605b-115">XML 스키마로 인라인 스키마를 작성하는 것에 대한 자세한 내용은 [XML 스키마(XSD)의 데이터 집합 관계형 구조 파생을](deriving-dataset-relational-structure-from-xml-schema-xsd.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8605b-115">For details about writing inline schema as XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
 <span data-ttu-id="8605b-116">**ReadXmlSchema에** 전달된 XML 문서에 인라인 스키마 정보가 없는 경우 **ReadXmlSchema는** XML 문서의 요소에서 스키마를 추론합니다.</span><span class="sxs-lookup"><span data-stu-id="8605b-116">If the XML document passed to **ReadXmlSchema** contains no inline schema information, **ReadXmlSchema** will infer the schema from the elements in the XML document.</span></span> <span data-ttu-id="8605b-117">**DataSet에** 스키마가 이미 포함되어 있는 경우 아직 존재하지 않는 경우 새 테이블을 추가하여 현재 스키마가 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="8605b-117">If the **DataSet** already contains a schema, the current schema will be extended by adding new tables if they do not already exist.</span></span> <span data-ttu-id="8605b-118">새 열은 기존 테이블에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8605b-118">New columns will not be added to added to existing tables.</span></span> <span data-ttu-id="8605b-119">추가중인 열이 **DataSet에** 이미 있지만 XML에 있는 열과 호환되지 않는 형식이 있는 경우 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="8605b-119">If a column being added already exists in the **DataSet** but has an incompatible type with the column found in the XML, an exception is thrown.</span></span> <span data-ttu-id="8605b-120">**ReadXmlSchema가** XML 문서에서 스키마를 유추하는 방법에 대한 자세한 내용은 [XML의 데이터 집합 관계형 구조 추론을](inferring-dataset-relational-structure-from-xml.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8605b-120">For details about how **ReadXmlSchema** infers a schema from an XML document, see [Inferring DataSet Relational Structure from XML](inferring-dataset-relational-structure-from-xml.md).</span></span>  
  
 <span data-ttu-id="8605b-121">**ReadXmlSchema는** **DataSet의**스키마만 로드하거나 유추하지만 **DataSet의** **ReadXml** 메서드는 스키마와 XML 문서에 포함된 데이터를 로드하거나 유추합니다.</span><span class="sxs-lookup"><span data-stu-id="8605b-121">Although **ReadXmlSchema** loads or infers only the schema of a **DataSet**, the **ReadXml** method of the **DataSet** loads or infers both the schema and the data contained in the XML document.</span></span> <span data-ttu-id="8605b-122">자세한 내용은 [XML에서 데이터 집합 로드를](loading-a-dataset-from-xml.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8605b-122">For more information, see [Loading a DataSet from XML](loading-a-dataset-from-xml.md).</span></span>  
  
 <span data-ttu-id="8605b-123">다음 코드 예제는 XML 문서 또는 스트림에서 **DataSet** 스키마를 로드하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8605b-123">The following code examples show how to load a **DataSet** schema from an XML document or stream.</span></span> <span data-ttu-id="8605b-124">첫 번째 예제에서는 **ReadXmlSchema** 메서드에 전달 되는 XML 스키마 파일 이름을 보여 주다.</span><span class="sxs-lookup"><span data-stu-id="8605b-124">The first example shows an XML Schema file name being passed to the **ReadXmlSchema** method.</span></span> <span data-ttu-id="8605b-125">두 번째 예제에서는 **System.IO.StreamReader**.</span><span class="sxs-lookup"><span data-stu-id="8605b-125">The second example shows a **System.IO.StreamReader**.</span></span>  
  
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
  
## <a name="inferxmlschema"></a><span data-ttu-id="8605b-126">InferXmlSchema</span><span class="sxs-lookup"><span data-stu-id="8605b-126">InferXmlSchema</span></span>  
 <span data-ttu-id="8605b-127">**DataSet의** **InferXmlSchema** 메서드를 사용하여 XML 문서에서 해당 스키마를 유추하도록 **데이터 집합에**지시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8605b-127">You can also instruct the **DataSet** to infer its schema from an XML document using the **InferXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="8605b-128">**InferXmlSchema** 함수는 **InferSchema의** **XmlReadMode(데이터** 로드 및 스키마 추론)를 사용하여 **ReadXml을** 모두 수행하는 것과 동일하며, 읽을 수 있는 문서에 인라인 스키마가 없는 경우 **ReadXmlSchema가** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8605b-128">**InferXmlSchema** functions the same as do both **ReadXml** with an **XmlReadMode** of **InferSchema** (loads data as well as infers schema), and **ReadXmlSchema** if the document being read contains no inline schema.</span></span> <span data-ttu-id="8605b-129">그러나 **InferXmlSchema는** 스키마가 유추될 때 무시할 특정 XML 네임스페이스를 지정할 수 있는 추가 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8605b-129">However, **InferXmlSchema** provides the additional capability of allowing you to specify particular XML namespaces to be ignored when the schema is inferred.</span></span> <span data-ttu-id="8605b-130">**InferXmlSchema는** 파일 이름, 스트림 또는 **XmlReader로**지정된 XML 문서의 위치라는 두 가지 필수 인수를 취합니다. 및 XML 네임스페이스의 문자열 배열은 작업에서 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8605b-130">**InferXmlSchema** takes two required arguments: the location of the XML document, specified by a file name, a stream, or an **XmlReader**; and a string array of XML namespaces to be ignored by the operation.</span></span>  
  
 <span data-ttu-id="8605b-131">예를 들어, 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="8605b-131">For example, consider the following XML:</span></span>  
  
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
  
 <span data-ttu-id="8605b-132">이전 XML 문서의 요소에 대해 지정된 특성으로 인해 **InferSchema의** **XmlReadMode를** 사용하는 **ReadXml** 메서드와 **ReadXml** 메서드는 **범주,** **범주ID,** **범주 이름,** **설명,** **제품** **ID,** **ReorderLevel**및 **단종**.</span><span class="sxs-lookup"><span data-stu-id="8605b-132">Because of the attributes specified for the elements in the preceding XML document, both the **ReadXmlSchema** method and the **ReadXml** method with an **XmlReadMode** of **InferSchema** would create tables for every element in the document: **Categories**, **CategoryID**, **CategoryName**, **Description**, **Products**, **ProductID**, **ReorderLevel**, and **Discontinued**.</span></span> <span data-ttu-id="8605b-133">자세한 내용은 [XML에서 데이터 집합 관계형 구조 유추를](inferring-dataset-relational-structure-from-xml.md)참조하십시오. 그러나 더 적절한 구조는 **범주** 및 **제품** 테이블만 만든 다음 범주 **테이블에서 CategoryID,** **CategoryName**및 **설명** 열을 만들고 **제품** **테이블에서** **ProductID,** **ReorderLevel**및 **단종** 열을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8605b-133">(For more information, see [Inferring DataSet Relational Structure from XML](inferring-dataset-relational-structure-from-xml.md).) However, a more appropriate structure would be to create only the **Categories** and **Products** tables, and then to create **CategoryID**, **CategoryName**, and **Description** columns in the **Categories** table, and **ProductID**, **ReorderLevel**, and **Discontinued** columns in the **Products** table.</span></span> <span data-ttu-id="8605b-134">추론된 스키마가 XML 요소에 지정된 특성을 무시하도록 하려면 **InferXmlSchema** 메서드를 사용하고 다음 예제와 같이 무시할 **Officedata의** XML 네임스페이스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8605b-134">To ensure that the inferred schema ignores the attributes specified in the XML elements, use the **InferXmlSchema** method and specify the XML namespace for **officedata** to be ignored, as shown in the following example.</span></span>  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a><span data-ttu-id="8605b-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8605b-135">See also</span></span>

- [<span data-ttu-id="8605b-136">데이터 세트에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="8605b-136">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="8605b-137">XML 스키마에서 데이터 세트 관계형 구조 파생(XSD)</span><span class="sxs-lookup"><span data-stu-id="8605b-137">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [<span data-ttu-id="8605b-138">XML에서 데이터 세트 관계형 구조 유추</span><span class="sxs-lookup"><span data-stu-id="8605b-138">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="8605b-139">XML에서 데이터 세트 로드</span><span class="sxs-lookup"><span data-stu-id="8605b-139">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="8605b-140">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="8605b-140">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="8605b-141">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="8605b-141">ADO.NET Overview</span></span>](../ado-net-overview.md)
