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
# <a name="loading-a-dataset-from-xml"></a><span data-ttu-id="0ffe7-102">XML에서 데이터 세트 로드</span><span class="sxs-lookup"><span data-stu-id="0ffe7-102">Loading a DataSet from XML</span></span>
<span data-ttu-id="0ffe7-103">ADO.NET <xref:System.Data.DataSet>의 내용은 XML 스트림이나 문서로부터 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-103">The contents of an ADO.NET <xref:System.Data.DataSet> can be created from an XML stream or document.</span></span> <span data-ttu-id="0ffe7-104">또한, .NET Framework를 사용하면 XML로부터 로드할 정보와 <xref:System.Data.DataSet>의 스키마나 관계형 구조를 만드는 방법을 매우 융통성 있게 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-104">In addition, with the .NET Framework you have great flexibility over what information is loaded from XML, and how the schema or relational structure of the <xref:System.Data.DataSet> is created.</span></span>  
  
 <span data-ttu-id="0ffe7-105">XML의 <xref:System.Data.DataSet> 데이터로 채우려면 개체의 **ReadXml** 메서드를 <xref:System.Data.DataSet> 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-105">To fill a <xref:System.Data.DataSet> with data from XML, use the **ReadXml** method of the <xref:System.Data.DataSet> object.</span></span> <span data-ttu-id="0ffe7-106">**ReadXml** 메서드는 파일, 스트림 또는 **XmlReader에서**읽으며 XML소스와 선택적 **XmlReadMode** 인수를 인수로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-106">The **ReadXml** method reads from a file, a stream, or an **XmlReader**, and takes as arguments the source of the XML plus an optional **XmlReadMode** argument.</span></span> <span data-ttu-id="0ffe7-107">**XmlReader에**대한 자세한 내용은 [XmlTextReader를 사용하여 XML 데이터 읽기를](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/tfz3cz6w(v=vs.100))참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-107">For more information about the **XmlReader**, see [Reading XML Data with XmlTextReader](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/tfz3cz6w(v=vs.100)).</span></span> <span data-ttu-id="0ffe7-108">**ReadXml** 메서드는 XML 스트림 또는 문서의 내용을 <xref:System.Data.DataSet> 읽고 데이터로 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-108">The **ReadXml** method reads the contents of the XML stream or document and loads the <xref:System.Data.DataSet> with data.</span></span> <span data-ttu-id="0ffe7-109">또한 지정된 <xref:System.Data.DataSet> **XmlReadMode** 및 관계형 스키마가 이미 있는지 여부에 따라 관계형 스키마를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-109">It will also create the relational schema of the <xref:System.Data.DataSet> depending on the **XmlReadMode** specified and whether or not a relational schema already exists.</span></span>  
  
 <span data-ttu-id="0ffe7-110">다음 표는 **XmlReadMode** 인수에 대한 옵션을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-110">The following table describes the options for the **XmlReadMode** argument.</span></span>  
  
|<span data-ttu-id="0ffe7-111">옵션</span><span class="sxs-lookup"><span data-stu-id="0ffe7-111">Option</span></span>|<span data-ttu-id="0ffe7-112">Description</span><span class="sxs-lookup"><span data-stu-id="0ffe7-112">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="0ffe7-113">**자동**</span><span class="sxs-lookup"><span data-stu-id="0ffe7-113">**Auto**</span></span>|<span data-ttu-id="0ffe7-114">이것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-114">This is the default.</span></span> <span data-ttu-id="0ffe7-115">XML을 검사하고 다음 순서에 따라 가장 적합한 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-115">Examines the XML and chooses the most appropriate option in the following order:</span></span><br /><br /> <span data-ttu-id="0ffe7-116">- XML이 DiffGram인 경우 **DiffGram이** 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-116">-   If the XML is a DiffGram, **DiffGram** is used.</span></span><br /><span data-ttu-id="0ffe7-117">- 스키마가 <xref:System.Data.DataSet> 포함되어 있거나 XML에 인라인 스키마가 포함된 경우 **ReadSchema가** 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-117">-   If the <xref:System.Data.DataSet> contains a schema or the XML contains an inline schema, **ReadSchema** is used.</span></span><br /><span data-ttu-id="0ffe7-118">- 스키마를 <xref:System.Data.DataSet> 포함하지 않고 XML에 인라인 스키마가 포함되어 있지 않으면 **InferSchema가** 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-118">-   If the <xref:System.Data.DataSet> does not contain a schema and the XML does not contain an inline schema, **InferSchema** is used.</span></span><br /><br /> <span data-ttu-id="0ffe7-119">XML의 형식을 읽는 경우 최상의 성능을 위해 **자동** 기본값을 수락하는 대신 명시적 **XmlReadMode를**설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-119">If you know the format of the XML being read, for best performance it is recommended that you set an explicit **XmlReadMode**, rather than accept the **Auto** default.</span></span>|  
|<span data-ttu-id="0ffe7-120">**ReadSchema**</span><span class="sxs-lookup"><span data-stu-id="0ffe7-120">**ReadSchema**</span></span>|<span data-ttu-id="0ffe7-121">모든 인라인 스키마를 읽은 다음 데이터와 스키마를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-121">Reads any inline schema and loads the data and schema.</span></span><br /><br /> <span data-ttu-id="0ffe7-122"><xref:System.Data.DataSet>에 이미 스키마가 있으면 인라인 스키마의 새 테이블이 <xref:System.Data.DataSet>에 있는 기존 스키마에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-122">If the <xref:System.Data.DataSet> already contains a schema, new tables are added from the inline schema to the existing schema in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="0ffe7-123">인라인 스키마의 모든 테이블이 <xref:System.Data.DataSet>에 이미 있으면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-123">If any tables in the inline schema already exist in the <xref:System.Data.DataSet>, an exception is thrown.</span></span> <span data-ttu-id="0ffe7-124">**XmlReadMode.ReadSchema**을 사용 하 여 기존 테이블의 스키마를 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-124">You will not be able to modify the schema of an existing table using **XmlReadMode.ReadSchema**.</span></span><br /><br /> <span data-ttu-id="0ffe7-125"><xref:System.Data.DataSet>에 스키마도 없고 인라인 스키마도 없으면 데이터를 읽지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-125">If the <xref:System.Data.DataSet> does not contain a schema, and there is no inline schema, no data is read.</span></span><br /><br /> <span data-ttu-id="0ffe7-126">인라인 스키마는 XSD(XML 스키마 정의 언어) 스키마를 사용하여 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-126">Inline schema can be defined using XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="0ffe7-127">XML 스키마로 인라인 스키마를 작성하는 것에 대한 자세한 내용은 [XML 스키마(XSD)의 데이터 집합 관계형 구조 파생을](deriving-dataset-relational-structure-from-xml-schema-xsd.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-127">For details about writing inline schema as XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>|  
|<span data-ttu-id="0ffe7-128">**무시스키마**</span><span class="sxs-lookup"><span data-stu-id="0ffe7-128">**IgnoreSchema**</span></span>|<span data-ttu-id="0ffe7-129">모든 인라인 스키마를 무시하고 데이터를 기존 <xref:System.Data.DataSet> 스키마로 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-129">Ignores any inline schema and loads the data into the existing <xref:System.Data.DataSet> schema.</span></span> <span data-ttu-id="0ffe7-130">기존 스키마와 일치하지 않는 모든 데이터는 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-130">Any data that does not match the existing schema is discarded.</span></span> <span data-ttu-id="0ffe7-131"><xref:System.Data.DataSet>에 스키마가 없으면 데이터를 로드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-131">If no schema exists in the <xref:System.Data.DataSet>, no data is loaded.</span></span><br /><br /> <span data-ttu-id="0ffe7-132">데이터가 DiffGram인 경우 **IgnoreSchema는** **DiffGram** *과* 동일한 기능을 가짐을 가지며</span><span class="sxs-lookup"><span data-stu-id="0ffe7-132">If the data is a DiffGram, **IgnoreSchema** has the same functionality as **DiffGram** *.*</span></span>|  
|<span data-ttu-id="0ffe7-133">**InferSchema**</span><span class="sxs-lookup"><span data-stu-id="0ffe7-133">**InferSchema**</span></span>|<span data-ttu-id="0ffe7-134">모든 인라인 스키마를 무시하며 XML 데이터의 구조마다 스키마를 유추한 다음 데이터를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-134">Ignores any inline schema and infers the schema per the structure of the XML data, then loads the data.</span></span><br /><br /> <span data-ttu-id="0ffe7-135"><xref:System.Data.DataSet>에 이미 스키마가 있으면 기존 테이블에 열을 추가하여 현재 스키마를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-135">If the <xref:System.Data.DataSet> already contains a schema, the current schema is extended by adding columns to existing tables.</span></span> <span data-ttu-id="0ffe7-136">기존 테이블이 없으면 테이블이 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-136">Extra tables will not be added if there are not existing tables.</span></span> <span data-ttu-id="0ffe7-137">유추된 테이블이 다른 네임스페이스로 이미 존재하거나 유추된 열이 기존 열과 충돌하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-137">An exception is thrown if an inferred table already exists with a different namespace, or if any inferred columns conflict with existing columns.</span></span><br /><br /> <span data-ttu-id="0ffe7-138">**ReadXmlSchema가** XML 문서에서 스키마를 유추하는 방법에 대한 자세한 내용은 [XML의 데이터 집합 관계형 구조 추론을](inferring-dataset-relational-structure-from-xml.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-138">For details about how **ReadXmlSchema** infers a schema from an XML document, see [Inferring DataSet Relational Structure from XML](inferring-dataset-relational-structure-from-xml.md).</span></span>|  
|<span data-ttu-id="0ffe7-139">**Diffgram**</span><span class="sxs-lookup"><span data-stu-id="0ffe7-139">**DiffGram**</span></span>|<span data-ttu-id="0ffe7-140">DiffGram을 읽은 다음 해당 데이터를 현재 스키마에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-140">Reads a DiffGram and adds the data to the current schema.</span></span> <span data-ttu-id="0ffe7-141">**DiffGram은** 고유 식별자 값이 일치하는 기존 행과 새 행을 병합합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-141">**DiffGram** merges new rows with existing rows where the unique identifier values match.</span></span> <span data-ttu-id="0ffe7-142">이 항목의 맨 뒤에 나오는 "XML로부터 데이터 병합"을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-142">See "Merging Data from XML" at the end of this topic.</span></span> <span data-ttu-id="0ffe7-143">DiffGrams에 대한 자세한 내용은 [DiffGrams](diffgrams.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-143">For more information about DiffGrams, see [DiffGrams](diffgrams.md).</span></span>|  
|<span data-ttu-id="0ffe7-144">**조각**</span><span class="sxs-lookup"><span data-stu-id="0ffe7-144">**Fragment**</span></span>|<span data-ttu-id="0ffe7-145">스트림의 끝에 도달할 때까지 여러 개의 XML 조각을 계속 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-145">Continues reading multiple XML fragments until the end of the stream is reached.</span></span> <span data-ttu-id="0ffe7-146"><xref:System.Data.DataSet> 스키마에 일치하는 조각이 해당 테이블의 뒤에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-146">Fragments that match the <xref:System.Data.DataSet> schema are appended to the appropriate tables.</span></span> <span data-ttu-id="0ffe7-147"><xref:System.Data.DataSet> 스키마에 일치하지 않는 조각은 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-147">Fragments that do not match the <xref:System.Data.DataSet> schema are discarded.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="0ffe7-148">XML 문서에 위치하는 **ReadXml에** **XmlReader를** 전달하면 **ReadXml은** 다음 요소 노드로 읽고 요소 노드가 끝날 때까지 읽는 루트 요소로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-148">If you pass an **XmlReader** to **ReadXml** that is positioned part of the way into an XML document, **ReadXml** will read to the next element node and will treat that as the root element, reading until the end of the element node only.</span></span> <span data-ttu-id="0ffe7-149">**XmlReadMode.Fragment.**</span><span class="sxs-lookup"><span data-stu-id="0ffe7-149">This does not apply if you specify **XmlReadMode.Fragment**.</span></span>  
  
## <a name="dtd-entities"></a><span data-ttu-id="0ffe7-150">DTD 엔터티</span><span class="sxs-lookup"><span data-stu-id="0ffe7-150">DTD Entities</span></span>  
 <span data-ttu-id="0ffe7-151">XML에 문서 형식 정의(DTD) 스키마에 정의된 엔터티가 포함되어 있는 경우 파일 이름, 스트림 또는 유효성이 검사되지 않는 <xref:System.Data.DataSet> **XmlReader를** **ReadXml에**전달하여 로드하려고 하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-151">If your XML contains entities defined in a document type definition (DTD) schema, an exception will be thrown if you attempt to load a <xref:System.Data.DataSet> by passing a file name, stream, or non-validating **XmlReader** to **ReadXml**.</span></span> <span data-ttu-id="0ffe7-152">대신 **엔터티 처리가 EntityHandling.ExpandEntities로** 설정된 **EntityHandling.ExpandEntities** **XmlValidatingReader를**만들고 **XmlValidatingReader를** **ReadXml로**전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-152">Instead, you must create an **XmlValidatingReader**, with **EntityHandling** set to **EntityHandling.ExpandEntities**, and pass your **XmlValidatingReader** to **ReadXml**.</span></span> <span data-ttu-id="0ffe7-153">**XmlValidatingReader는** <xref:System.Data.DataSet>을 읽기 전에 엔터티를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-153">The **XmlValidatingReader** will expand the entities prior to being read by the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="0ffe7-154">다음 코드 예제에서는 XML 스트림으로부터 <xref:System.Data.DataSet>을 로드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-154">The following code examples show how to load a <xref:System.Data.DataSet> from an XML stream.</span></span> <span data-ttu-id="0ffe7-155">첫 번째 예제에서는 **ReadXml** 메서드에 전달되는 파일 이름을 보여 주습니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-155">The first example shows a file name being passed to the **ReadXml** method.</span></span> <span data-ttu-id="0ffe7-156">두 번째 예제에서는 <xref:System.IO.StringReader>를 사용하여 로드될 XML이 포함된 문자열을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-156">The second example shows a string that contains XML being loaded using a <xref:System.IO.StringReader>.</span></span>  
  
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
> <span data-ttu-id="0ffe7-157">**ReadXml을** 호출하여 매우 큰 파일을 로드하면 성능이 저하될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-157">If you call **ReadXml** to load a very large file, you may encounter slow performance.</span></span> <span data-ttu-id="0ffe7-158">**ReadXml에**대한 최상의 성능을 보장하려면 큰 <xref:System.Data.DataTable.BeginLoadData%2A> 파일에서 <xref:System.Data.DataSet>의 각 테이블에 대한 메서드를 호출한 다음 **ReadXml을**호출합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-158">To ensure best performance for **ReadXml**, on a large file, call the <xref:System.Data.DataTable.BeginLoadData%2A> method for each table in the <xref:System.Data.DataSet>, and then call **ReadXml**.</span></span> <span data-ttu-id="0ffe7-159">마지막으로 다음 예제와 같이 <xref:System.Data.DataTable.EndLoadData%2A>의 각 테이블에 대해 <xref:System.Data.DataSet>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-159">Finally, call <xref:System.Data.DataTable.EndLoadData%2A> for each table in the <xref:System.Data.DataSet>, as shown in the following example.</span></span>  
  
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
> <span data-ttu-id="0ffe7-160"><xref:System.Data.DataSet> **대상Namespace에**대한 XSD 스키마에 데이터가 읽을 수 없는 경우 **ReadXml을** 호출하여 적격네임스페이스가 없는 요소를 포함하는 <xref:System.Data.DataSet> XML을 로드할 때 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-160">If the XSD schema for your <xref:System.Data.DataSet> includes a **targetNamespace**, data may not be read, and you may encounter exceptions, when calling **ReadXml** to load the <xref:System.Data.DataSet> with XML that contains elements with no qualifying namespace.</span></span> <span data-ttu-id="0ffe7-161">이 경우 정규화되지 않은 요소를 읽으려면 XSD 스키마에서 "정규화"와 동일한 **elementFormDefault를** 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-161">To read unqualified elements in this case, set **elementFormDefault** equal to "qualified" in your XSD schema.</span></span> <span data-ttu-id="0ffe7-162">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-162">For example:</span></span>  
  
```xml  
<xsd:schema id="customDataSet"
  elementFormDefault="qualified"  
  targetNamespace="http://www.tempuri.org/customDataSet.xsd"
  xmlns="http://www.tempuri.org/customDataSet.xsd"
  xmlns:xsd="http://www.w3.org/2001/XMLSchema"
  xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
</xsd:schema>  
```  
  
## <a name="merging-data-from-xml"></a><span data-ttu-id="0ffe7-163">XML로부터 데이터 병합</span><span class="sxs-lookup"><span data-stu-id="0ffe7-163">Merging Data from XML</span></span>  
 <span data-ttu-id="0ffe7-164"><xref:System.Data.DataSet>에 데이터가 이미 있으면 XML의 새 데이터는 <xref:System.Data.DataSet>에 이미 있는 데이터에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-164">If the <xref:System.Data.DataSet> already contains data, the new data from the XML is added to the data already present in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="0ffe7-165">**ReadXml은** XML에서 일치하는 기본 <xref:System.Data.DataSet> 키가 있는 행 정보로 병합되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-165">**ReadXml** does not merge from the XML into the <xref:System.Data.DataSet> any row information with matching primary keys.</span></span> <span data-ttu-id="0ffe7-166">XML의 새 정보로 기존 행 정보를 덮어쓰려면 **ReadXml을** <xref:System.Data.DataSet>사용하여 새 을 만든 다음 <xref:System.Data.DataSet.Merge%2A> 새 <xref:System.Data.DataSet> 를 기존 <xref:System.Data.DataSet>에 새 로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-166">To overwrite existing row information with new information from XML, use **ReadXml** to create a new <xref:System.Data.DataSet>, and then <xref:System.Data.DataSet.Merge%2A> the new <xref:System.Data.DataSet> into the existing <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="0ffe7-167">**ReadXML을** 사용하여 **DiffGram을 DiffGram의** **XmlReadMode로** 로드하면 동일한 고유 식별자가 있는 행이 병합됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ffe7-167">Note that loading a DiffGram using **ReadXML** with an **XmlReadMode** of **DiffGram** will merge rows that have the same unique identifier.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ffe7-168">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0ffe7-168">See also</span></span>

- <xref:System.Data.DataSet.Merge%2A?displayProperty=nameWithType>
- [<span data-ttu-id="0ffe7-169">데이터 세트에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="0ffe7-169">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="0ffe7-170">DiffGram</span><span class="sxs-lookup"><span data-stu-id="0ffe7-170">DiffGrams</span></span>](diffgrams.md)
- [<span data-ttu-id="0ffe7-171">XML 스키마에서 데이터 세트 관계형 구조 파생(XSD)</span><span class="sxs-lookup"><span data-stu-id="0ffe7-171">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [<span data-ttu-id="0ffe7-172">XML에서 데이터 세트 관계형 구조 유추</span><span class="sxs-lookup"><span data-stu-id="0ffe7-172">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="0ffe7-173">XML에서 데이터 세트 스키마 정보 로드</span><span class="sxs-lookup"><span data-stu-id="0ffe7-173">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="0ffe7-174">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="0ffe7-174">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="0ffe7-175">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="0ffe7-175">ADO.NET Overview</span></span>](../ado-net-overview.md)
