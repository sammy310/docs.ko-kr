---
title: XML에서 데이터 세트 로드
description: XML에서 ADO.NET 데이터 집합에 내용을 추가 하는 방법에 대해 알아봅니다. .NET Framework는 로드할 항목과 데이터 집합의 구조에 대 한 유연성을 제공 합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49c083b7-a5ed-41cf-aabc-5aaba96f00e6
ms.openlocfilehash: 8c81e6e29678fe2e30af7c15d8d6e90f23dd0762
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286885"
---
# <a name="loading-a-dataset-from-xml"></a><span data-ttu-id="1375d-104">XML에서 데이터 세트 로드</span><span class="sxs-lookup"><span data-stu-id="1375d-104">Loading a DataSet from XML</span></span>
<span data-ttu-id="1375d-105">ADO.NET <xref:System.Data.DataSet>의 내용은 XML 스트림이나 문서로부터 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-105">The contents of an ADO.NET <xref:System.Data.DataSet> can be created from an XML stream or document.</span></span> <span data-ttu-id="1375d-106">또한, .NET Framework를 사용하면 XML로부터 로드할 정보와 <xref:System.Data.DataSet>의 스키마나 관계형 구조를 만드는 방법을 매우 융통성 있게 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-106">In addition, with the .NET Framework you have great flexibility over what information is loaded from XML, and how the schema or relational structure of the <xref:System.Data.DataSet> is created.</span></span>  
  
 <span data-ttu-id="1375d-107">XML의 데이터로를 채우려면 <xref:System.Data.DataSet> 개체의 **ReadXml** 메서드를 사용 합니다 <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="1375d-107">To fill a <xref:System.Data.DataSet> with data from XML, use the **ReadXml** method of the <xref:System.Data.DataSet> object.</span></span> <span data-ttu-id="1375d-108">**ReadXml** 메서드는 파일, 스트림 또는 **XMLREADER**에서 읽고 XML 소스와 선택적 **XmlReadMode** 인수를 인수로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-108">The **ReadXml** method reads from a file, a stream, or an **XmlReader**, and takes as arguments the source of the XML plus an optional **XmlReadMode** argument.</span></span> <span data-ttu-id="1375d-109">**XmlReader**에 대 한 자세한 내용은 [XmlTextReader를 사용 하 여 XML 데이터 읽기](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/tfz3cz6w(v=vs.100))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1375d-109">For more information about the **XmlReader**, see [Reading XML Data with XmlTextReader](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/tfz3cz6w(v=vs.100)).</span></span> <span data-ttu-id="1375d-110">**ReadXml** 메서드는 XML 스트림이나 문서의 내용을 읽고를 사용 하 여 데이터를 로드 합니다 <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="1375d-110">The **ReadXml** method reads the contents of the XML stream or document and loads the <xref:System.Data.DataSet> with data.</span></span> <span data-ttu-id="1375d-111">또한 <xref:System.Data.DataSet> 관계형 스키마가 이미 있는지 여부에 따라 지정 된 **XmlReadMode** 에 따라의 관계형 스키마를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-111">It will also create the relational schema of the <xref:System.Data.DataSet> depending on the **XmlReadMode** specified and whether or not a relational schema already exists.</span></span>  
  
 <span data-ttu-id="1375d-112">다음 표에서는 **XmlReadMode** 인수에 대 한 옵션을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-112">The following table describes the options for the **XmlReadMode** argument.</span></span>  
  
|<span data-ttu-id="1375d-113">옵션</span><span class="sxs-lookup"><span data-stu-id="1375d-113">Option</span></span>|<span data-ttu-id="1375d-114">Description</span><span class="sxs-lookup"><span data-stu-id="1375d-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="1375d-115">**자동**</span><span class="sxs-lookup"><span data-stu-id="1375d-115">**Auto**</span></span>|<span data-ttu-id="1375d-116">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-116">This is the default.</span></span> <span data-ttu-id="1375d-117">XML을 검사하고 다음 순서에 따라 가장 적합한 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-117">Examines the XML and chooses the most appropriate option in the following order:</span></span><br /><br /> <span data-ttu-id="1375d-118">-XML이 DiffGram 인 경우 **diffgram** 이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-118">-   If the XML is a DiffGram, **DiffGram** is used.</span></span><br /><span data-ttu-id="1375d-119">-에 <xref:System.Data.DataSet> 스키마가 포함 되어 있거나 XML에 인라인 스키마가 포함 되어 있으면 **readschema** 가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-119">-   If the <xref:System.Data.DataSet> contains a schema or the XML contains an inline schema, **ReadSchema** is used.</span></span><br /><span data-ttu-id="1375d-120">-에 스키마가 없고 <xref:System.Data.DataSet> XML에 인라인 스키마가 포함 되어 있지 않으면 **InferSchema** 가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-120">-   If the <xref:System.Data.DataSet> does not contain a schema and the XML does not contain an inline schema, **InferSchema** is used.</span></span><br /><br /> <span data-ttu-id="1375d-121">읽을 XML의 형식을 알고 있는 경우 최상의 성능을 위해 **자동** 기본값을 허용 하는 대신 명시적 **XmlReadMode**를 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-121">If you know the format of the XML being read, for best performance it is recommended that you set an explicit **XmlReadMode**, rather than accept the **Auto** default.</span></span>|  
|<span data-ttu-id="1375d-122">**ReadSchema**</span><span class="sxs-lookup"><span data-stu-id="1375d-122">**ReadSchema**</span></span>|<span data-ttu-id="1375d-123">모든 인라인 스키마를 읽은 다음 데이터와 스키마를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-123">Reads any inline schema and loads the data and schema.</span></span><br /><br /> <span data-ttu-id="1375d-124"><xref:System.Data.DataSet>에 이미 스키마가 있으면 인라인 스키마의 새 테이블이 <xref:System.Data.DataSet>에 있는 기존 스키마에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-124">If the <xref:System.Data.DataSet> already contains a schema, new tables are added from the inline schema to the existing schema in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="1375d-125">인라인 스키마의 모든 테이블이 <xref:System.Data.DataSet>에 이미 있으면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-125">If any tables in the inline schema already exist in the <xref:System.Data.DataSet>, an exception is thrown.</span></span> <span data-ttu-id="1375d-126">**XmlReadMode 스키마**를 사용 하 여 기존 테이블의 스키마를 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-126">You will not be able to modify the schema of an existing table using **XmlReadMode.ReadSchema**.</span></span><br /><br /> <span data-ttu-id="1375d-127"><xref:System.Data.DataSet>에 스키마도 없고 인라인 스키마도 없으면 데이터를 읽지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-127">If the <xref:System.Data.DataSet> does not contain a schema, and there is no inline schema, no data is read.</span></span><br /><br /> <span data-ttu-id="1375d-128">인라인 스키마는 XSD(XML 스키마 정의 언어) 스키마를 사용하여 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-128">Inline schema can be defined using XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="1375d-129">인라인 스키마를 XML 스키마로 작성 하는 방법에 대 한 자세한 내용은 [Xml 스키마에서 데이터 집합 관계형 구조 파생 (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1375d-129">For details about writing inline schema as XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>|  
|<span data-ttu-id="1375d-130">**IgnoreSchema**</span><span class="sxs-lookup"><span data-stu-id="1375d-130">**IgnoreSchema**</span></span>|<span data-ttu-id="1375d-131">모든 인라인 스키마를 무시하고 데이터를 기존 <xref:System.Data.DataSet> 스키마로 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-131">Ignores any inline schema and loads the data into the existing <xref:System.Data.DataSet> schema.</span></span> <span data-ttu-id="1375d-132">기존 스키마와 일치하지 않는 모든 데이터는 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-132">Any data that does not match the existing schema is discarded.</span></span> <span data-ttu-id="1375d-133"><xref:System.Data.DataSet>에 스키마가 없으면 데이터를 로드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-133">If no schema exists in the <xref:System.Data.DataSet>, no data is loaded.</span></span><br /><br /> <span data-ttu-id="1375d-134">데이터가 DiffGram 인 경우 **IgnoreSchema** 는 **diffgram** 과 동일한 기능을 갖습니다 *.*</span><span class="sxs-lookup"><span data-stu-id="1375d-134">If the data is a DiffGram, **IgnoreSchema** has the same functionality as **DiffGram** *.*</span></span>|  
|<span data-ttu-id="1375d-135">**InferSchema**</span><span class="sxs-lookup"><span data-stu-id="1375d-135">**InferSchema**</span></span>|<span data-ttu-id="1375d-136">모든 인라인 스키마를 무시하며 XML 데이터의 구조마다 스키마를 유추한 다음 데이터를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-136">Ignores any inline schema and infers the schema per the structure of the XML data, then loads the data.</span></span><br /><br /> <span data-ttu-id="1375d-137"><xref:System.Data.DataSet>에 이미 스키마가 있으면 기존 테이블에 열을 추가하여 현재 스키마를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-137">If the <xref:System.Data.DataSet> already contains a schema, the current schema is extended by adding columns to existing tables.</span></span> <span data-ttu-id="1375d-138">기존 테이블이 없으면 테이블이 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-138">Extra tables will not be added if there are not existing tables.</span></span> <span data-ttu-id="1375d-139">유추된 테이블이 다른 네임스페이스로 이미 존재하거나 유추된 열이 기존 열과 충돌하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-139">An exception is thrown if an inferred table already exists with a different namespace, or if any inferred columns conflict with existing columns.</span></span><br /><br /> <span data-ttu-id="1375d-140">**Readxmlschema** 에서 xml 문서의 스키마를 유추 하는 방법에 대 한 자세한 내용은 [Xml에서 데이터 집합 관계형 구조 유추](inferring-dataset-relational-structure-from-xml.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1375d-140">For details about how **ReadXmlSchema** infers a schema from an XML document, see [Inferring DataSet Relational Structure from XML](inferring-dataset-relational-structure-from-xml.md).</span></span>|  
|<span data-ttu-id="1375d-141">**DiffGram**</span><span class="sxs-lookup"><span data-stu-id="1375d-141">**DiffGram**</span></span>|<span data-ttu-id="1375d-142">DiffGram을 읽은 다음 해당 데이터를 현재 스키마에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-142">Reads a DiffGram and adds the data to the current schema.</span></span> <span data-ttu-id="1375d-143">**DiffGram** 은 고유 식별자 값이 일치 하는 기존 행과 새 행을 병합 합니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-143">**DiffGram** merges new rows with existing rows where the unique identifier values match.</span></span> <span data-ttu-id="1375d-144">이 항목의 맨 뒤에 나오는 "XML로부터 데이터 병합"을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1375d-144">See "Merging Data from XML" at the end of this topic.</span></span> <span data-ttu-id="1375d-145">Diffgram에 대 한 자세한 내용은 [diffgram](diffgrams.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1375d-145">For more information about DiffGrams, see [DiffGrams](diffgrams.md).</span></span>|  
|<span data-ttu-id="1375d-146">**Don't**</span><span class="sxs-lookup"><span data-stu-id="1375d-146">**Fragment**</span></span>|<span data-ttu-id="1375d-147">스트림의 끝에 도달할 때까지 여러 개의 XML 조각을 계속 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-147">Continues reading multiple XML fragments until the end of the stream is reached.</span></span> <span data-ttu-id="1375d-148"><xref:System.Data.DataSet> 스키마에 일치하는 조각이 해당 테이블의 뒤에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-148">Fragments that match the <xref:System.Data.DataSet> schema are appended to the appropriate tables.</span></span> <span data-ttu-id="1375d-149"><xref:System.Data.DataSet> 스키마에 일치하지 않는 조각은 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-149">Fragments that do not match the <xref:System.Data.DataSet> schema are discarded.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="1375d-150">XML 문서로 배치 된 **ReadXml** 에 **XmlReader** 를 전달 하는 경우 **ReadXml** 는 다음 요소 노드를 읽고이를 루트 요소로 처리 하 여 요소 노드 끝 까지만 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-150">If you pass an **XmlReader** to **ReadXml** that is positioned part of the way into an XML document, **ReadXml** will read to the next element node and will treat that as the root element, reading until the end of the element node only.</span></span> <span data-ttu-id="1375d-151">**XmlReadMode**를 지정 하는 경우에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-151">This does not apply if you specify **XmlReadMode.Fragment**.</span></span>  
  
## <a name="dtd-entities"></a><span data-ttu-id="1375d-152">DTD 엔터티</span><span class="sxs-lookup"><span data-stu-id="1375d-152">DTD Entities</span></span>  
 <span data-ttu-id="1375d-153">XML이 DTD (문서 종류 정의) 스키마에 정의 된 엔터티를 포함 하는 경우 <xref:System.Data.DataSet> 파일 이름, 스트림 또는 유효성 검사를 수행 하지 않는 **XmlReader** 를 **ReadXml**에 전달 하 여를 로드 하려고 하면 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-153">If your XML contains entities defined in a document type definition (DTD) schema, an exception will be thrown if you attempt to load a <xref:System.Data.DataSet> by passing a file name, stream, or non-validating **XmlReader** to **ReadXml**.</span></span> <span data-ttu-id="1375d-154">대신 **Entityhandling** 을 **entityhandling.expandentities**로 설정 하 여 **XmlValidatingReader**를 만들고 **XmlValidatingReader** 를 **ReadXml**에 전달 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-154">Instead, you must create an **XmlValidatingReader**, with **EntityHandling** set to **EntityHandling.ExpandEntities**, and pass your **XmlValidatingReader** to **ReadXml**.</span></span> <span data-ttu-id="1375d-155">**XmlValidatingReader** 는에서 읽기 전에 엔터티를 확장 합니다 <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="1375d-155">The **XmlValidatingReader** will expand the entities prior to being read by the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="1375d-156">다음 코드 예제에서는 XML 스트림으로부터 <xref:System.Data.DataSet>을 로드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-156">The following code examples show how to load a <xref:System.Data.DataSet> from an XML stream.</span></span> <span data-ttu-id="1375d-157">첫 번째 예제에서는 **ReadXml** 메서드에 전달 되는 파일 이름을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-157">The first example shows a file name being passed to the **ReadXml** method.</span></span> <span data-ttu-id="1375d-158">두 번째 예제에서는 <xref:System.IO.StringReader>를 사용하여 로드될 XML이 포함된 문자열을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-158">The second example shows a string that contains XML being loaded using a <xref:System.IO.StringReader>.</span></span>  
  
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
> <span data-ttu-id="1375d-159">**ReadXml** 를 호출 하 여 매우 큰 파일을 로드 하는 경우 성능이 저하 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-159">If you call **ReadXml** to load a very large file, you may encounter slow performance.</span></span> <span data-ttu-id="1375d-160">**ReadXml**에 대 한 최상의 성능을 보장 하려면의 <xref:System.Data.DataTable.BeginLoadData%2A> 각 테이블에 대해 메서드를 호출한 <xref:System.Data.DataSet> 다음 **ReadXml**를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-160">To ensure best performance for **ReadXml**, on a large file, call the <xref:System.Data.DataTable.BeginLoadData%2A> method for each table in the <xref:System.Data.DataSet>, and then call **ReadXml**.</span></span> <span data-ttu-id="1375d-161">마지막으로 다음 예제와 같이 <xref:System.Data.DataTable.EndLoadData%2A>의 각 테이블에 대해 <xref:System.Data.DataSet>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-161">Finally, call <xref:System.Data.DataTable.EndLoadData%2A> for each table in the <xref:System.Data.DataSet>, as shown in the following example.</span></span>  
  
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
> <span data-ttu-id="1375d-162">의 XSD 스키마에 <xref:System.Data.DataSet> **targetNamespace**가 포함 된 경우 데이터를 읽을 수 없으며 **ReadXml** 를 호출 하 여 <xref:System.Data.DataSet> 정규화 된 네임 스페이스가 없는 요소가 포함 된 XML로를 로드 하는 경우 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-162">If the XSD schema for your <xref:System.Data.DataSet> includes a **targetNamespace**, data may not be read, and you may encounter exceptions, when calling **ReadXml** to load the <xref:System.Data.DataSet> with XML that contains elements with no qualifying namespace.</span></span> <span data-ttu-id="1375d-163">이 경우 정규화 되지 않은 요소를 읽으려면 XSD 스키마에서 **Elementformdefault** 를 "정규화 된"로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-163">To read unqualified elements in this case, set **elementFormDefault** equal to "qualified" in your XSD schema.</span></span> <span data-ttu-id="1375d-164">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-164">For example:</span></span>  
  
```xml  
<xsd:schema id="customDataSet"
  elementFormDefault="qualified"  
  targetNamespace="http://www.tempuri.org/customDataSet.xsd"
  xmlns="http://www.tempuri.org/customDataSet.xsd"
  xmlns:xsd="http://www.w3.org/2001/XMLSchema"
  xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
</xsd:schema>  
```  
  
## <a name="merging-data-from-xml"></a><span data-ttu-id="1375d-165">XML로부터 데이터 병합</span><span class="sxs-lookup"><span data-stu-id="1375d-165">Merging Data from XML</span></span>  
 <span data-ttu-id="1375d-166"><xref:System.Data.DataSet>에 데이터가 이미 있으면 XML의 새 데이터는 <xref:System.Data.DataSet>에 이미 있는 데이터에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-166">If the <xref:System.Data.DataSet> already contains data, the new data from the XML is added to the data already present in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="1375d-167">**ReadXml** 는 XML에서 기본 키가 일치 하는 행 정보로 병합 되지 않습니다 <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="1375d-167">**ReadXml** does not merge from the XML into the <xref:System.Data.DataSet> any row information with matching primary keys.</span></span> <span data-ttu-id="1375d-168">기존 행 정보를 XML의 새 정보로 덮어쓰려면 **ReadXml** 를 사용 하 여 새를 만든 <xref:System.Data.DataSet> 다음 새를 기존에 만듭니다 <xref:System.Data.DataSet.Merge%2A> <xref:System.Data.DataSet> <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="1375d-168">To overwrite existing row information with new information from XML, use **ReadXml** to create a new <xref:System.Data.DataSet>, and then <xref:System.Data.DataSet.Merge%2A> the new <xref:System.Data.DataSet> into the existing <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="1375d-169">**Diffgram** **XmlReadMode** 를 사용 하 여 **ReadXML** 를 사용 하 여 diffgram을 로드 하면 동일한 고유 식별자를 가진 행이 병합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1375d-169">Note that loading a DiffGram using **ReadXML** with an **XmlReadMode** of **DiffGram** will merge rows that have the same unique identifier.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1375d-170">참조</span><span class="sxs-lookup"><span data-stu-id="1375d-170">See also</span></span>

- <xref:System.Data.DataSet.Merge%2A?displayProperty=nameWithType>
- [<span data-ttu-id="1375d-171">데이터 세트에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="1375d-171">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="1375d-172">DiffGram</span><span class="sxs-lookup"><span data-stu-id="1375d-172">DiffGrams</span></span>](diffgrams.md)
- [<span data-ttu-id="1375d-173">XML 스키마에서 데이터 세트 관계형 구조 파생(XSD)</span><span class="sxs-lookup"><span data-stu-id="1375d-173">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [<span data-ttu-id="1375d-174">XML에서 데이터 세트 관계형 구조 유추</span><span class="sxs-lookup"><span data-stu-id="1375d-174">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="1375d-175">XML에서 데이터 세트 스키마 정보 로드</span><span class="sxs-lookup"><span data-stu-id="1375d-175">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="1375d-176">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="1375d-176">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="1375d-177">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="1375d-177">ADO.NET Overview</span></span>](../ado-net-overview.md)
