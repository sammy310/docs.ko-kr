---
title: 데이터 세트 콘텐츠를 XML 데이터로 작성
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fd15f8a5-3b4c-46d0-a561-4559ab2a4705
ms.openlocfilehash: c8a5c747e4ec60fcb97edf631aa3a0ae184ffec5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173720"
---
# <a name="writing-dataset-contents-as-xml-data"></a><span data-ttu-id="a41b2-102">데이터 세트 콘텐츠를 XML 데이터로 작성</span><span class="sxs-lookup"><span data-stu-id="a41b2-102">Writing DataSet Contents as XML Data</span></span>

<span data-ttu-id="a41b2-103">ADO.NET에서는 해당 스키마의 사용 여부와 관계없이 <xref:System.Data.DataSet>을 XML 표현으로 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a41b2-103">In ADO.NET you can write an XML representation of a <xref:System.Data.DataSet>, with or without its schema.</span></span> <span data-ttu-id="a41b2-104">스키마 정보가 XML과 함께 인라인에 포함된 경우에는 XSD(XML 스키마 정의 언어)를 사용하여 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a41b2-104">If schema information is included inline with the XML, it is written using the XML Schema definition language (XSD).</span></span> <span data-ttu-id="a41b2-105">이 스키마에는 <xref:System.Data.DataSet>의 테이블 정의와 관계 및 제약 조건 정의가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a41b2-105">The schema contains the table definitions of the <xref:System.Data.DataSet> as well as the relation and constraint definitions.</span></span>  
  
 <span data-ttu-id="a41b2-106"><xref:System.Data.DataSet>이 XML 데이터로 작성되면 <xref:System.Data.DataSet>의 행은 자신의 현재 버전으로 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a41b2-106">When a <xref:System.Data.DataSet> is written as XML data, the rows in the <xref:System.Data.DataSet> are written in their current versions.</span></span> <span data-ttu-id="a41b2-107">그러나 <xref:System.Data.DataSet>은 DiffGram으로 작성될 수도 있으므로 행의 현재 및 원래 값이 모두 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a41b2-107">However, the <xref:System.Data.DataSet> can also be written as a DiffGram so that both the current and the original values of the rows will be included.</span></span>  
  
 <span data-ttu-id="a41b2-108">의 XML 표현은 <xref:System.Data.DataSet> 파일, 스트림, **XmlWriter**또는 문자열에 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a41b2-108">The XML representation of the <xref:System.Data.DataSet> can be written to a file, a stream, an **XmlWriter**, or a string.</span></span> <span data-ttu-id="a41b2-109">이와 같이 다양한 작성이 가능하므로 <xref:System.Data.DataSet>의 XML 표현을 전송하는 방법은 매우 유연합니다.</span><span class="sxs-lookup"><span data-stu-id="a41b2-109">These choices provide great flexibility for how you transport the XML representation of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="a41b2-110">의 XML 표현을 <xref:System.Data.DataSet> 문자열로 가져오려면 다음 예제와 같이 **GetXml** 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a41b2-110">To obtain the XML representation of the <xref:System.Data.DataSet> as a string, use the **GetXml** method as shown in the following example.</span></span>  
  
```vb  
Dim xmlDS As String = custDS.GetXml()  
```  
  
```csharp  
string xmlDS = custDS.GetXml();  
```  
  
 <span data-ttu-id="a41b2-111">**GetXml** 는 스키마 정보가 없는의 XML 표현을 반환 합니다 <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="a41b2-111">**GetXml** returns the XML representation of the <xref:System.Data.DataSet> without schema information.</span></span> <span data-ttu-id="a41b2-112"><xref:System.Data.DataSet>(XML 스키마)에서 문자열로 스키마 정보를 쓰려면 **getxmlschema**를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a41b2-112">To write the schema information from the <xref:System.Data.DataSet> (as XML Schema) to a string, use **GetXmlSchema**.</span></span>  
  
 <span data-ttu-id="a41b2-113"><xref:System.Data.DataSet>파일, 스트림 또는 **XmlWriter**에를 쓰려면 **WriteXml** 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a41b2-113">To write a <xref:System.Data.DataSet> to a file, stream, or **XmlWriter**, use the **WriteXml** method.</span></span> <span data-ttu-id="a41b2-114">**WriteXml** 에 전달 하는 첫 번째 매개 변수는 XML 출력의 대상입니다.</span><span class="sxs-lookup"><span data-stu-id="a41b2-114">The first parameter you pass to **WriteXml** is the destination of the XML output.</span></span> <span data-ttu-id="a41b2-115">예를 들어, 파일 이름, **시스템. i n i** .</span><span class="sxs-lookup"><span data-stu-id="a41b2-115">For example, pass a string containing a file name, a **System.IO.TextWriter** object, and so on.</span></span> <span data-ttu-id="a41b2-116">**XmlWriteMode** 의 선택적인 두 번째 매개 변수를 전달 하 여 XML 출력을 작성 하는 방법을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a41b2-116">You can pass an optional second parameter of an **XmlWriteMode** to specify how the XML output is to be written.</span></span>  
  
 <span data-ttu-id="a41b2-117">다음 표에서는 **XmlWriteMode**에 대 한 옵션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a41b2-117">The following table shows the options for **XmlWriteMode**.</span></span>  
  
|<span data-ttu-id="a41b2-118">XmlWriteMode 옵션</span><span class="sxs-lookup"><span data-stu-id="a41b2-118">XmlWriteMode option</span></span>|<span data-ttu-id="a41b2-119">설명</span><span class="sxs-lookup"><span data-stu-id="a41b2-119">Description</span></span>|  
|-------------------------|-----------------|  
|<span data-ttu-id="a41b2-120">**IgnoreSchema**</span><span class="sxs-lookup"><span data-stu-id="a41b2-120">**IgnoreSchema**</span></span>|<span data-ttu-id="a41b2-121"><xref:System.Data.DataSet>의 현재 내용을 XML 스키마 없이 XML 데이터로 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="a41b2-121">Writes the current contents of the <xref:System.Data.DataSet> as XML data, without an XML Schema.</span></span> <span data-ttu-id="a41b2-122">이것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="a41b2-122">This is the default.</span></span>|  
|<span data-ttu-id="a41b2-123">**WriteSchema**</span><span class="sxs-lookup"><span data-stu-id="a41b2-123">**WriteSchema**</span></span>|<span data-ttu-id="a41b2-124"><xref:System.Data.DataSet>의 현재 내용을 인라인 XML 스키마와 동일한 관계형 구조를 가진 XML 데이터로 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="a41b2-124">Writes the current contents of the <xref:System.Data.DataSet> as XML data with the relational structure as inline XML Schema.</span></span>|  
|<span data-ttu-id="a41b2-125">**DiffGram**</span><span class="sxs-lookup"><span data-stu-id="a41b2-125">**DiffGram**</span></span>|<span data-ttu-id="a41b2-126">원래 값과 현재 값을 포함하여 전체 <xref:System.Data.DataSet>을 DiffGram으로 씁니다.</span><span class="sxs-lookup"><span data-stu-id="a41b2-126">Writes the entire <xref:System.Data.DataSet> as a DiffGram, including original and current values.</span></span> <span data-ttu-id="a41b2-127">자세한 내용은 [diffgram](diffgrams.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a41b2-127">For more information, see [DiffGrams](diffgrams.md).</span></span>|  
  
 <span data-ttu-id="a41b2-128"><xref:System.Data.DataSet> **DataRelation** 개체가 포함 된의 XML 표현을 작성 하는 경우 대부분의 결과 xml에는 관련 된 부모 요소 내에 중첩 된 각 관계의 자식 행이 포함 되도록 할 가능성이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="a41b2-128">When writing an XML representation of a <xref:System.Data.DataSet> that contains **DataRelation** objects, you will most likely want the resulting XML to have the child rows of each relation nested within their related parent elements.</span></span> <span data-ttu-id="a41b2-129">이를 수행 하려면에 **datarelation** 을 추가할 때 **datarelation** 의 **Nested** 속성을 **true** 로 설정 합니다 <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="a41b2-129">To accomplish this, set the **Nested** property of the **DataRelation** to **true** when you add the **DataRelation** to the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="a41b2-130">자세한 내용은 [DataRelations 중첩](nesting-datarelations.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a41b2-130">For more information, see [Nesting DataRelations](nesting-datarelations.md).</span></span>  
  
 <span data-ttu-id="a41b2-131">다음은 파일에의 XML 표현을 작성 하는 방법에 대 한 두 가지 예제입니다 <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="a41b2-131">The following are two examples of how to write the XML representation of a <xref:System.Data.DataSet> to a file.</span></span> <span data-ttu-id="a41b2-132">첫 번째 예에서는 결과 XML의 파일 이름을 **WriteXml**에 문자열로 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="a41b2-132">The first example passes the file name for the resulting XML as a string to **WriteXml**.</span></span> <span data-ttu-id="a41b2-133">두 번째 예제에서는 **system.object** 를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="a41b2-133">The second example passes a **System.IO.StreamWriter** object.</span></span>
  
```vb  
custDS.WriteXml("Customers.xml", XmlWriteMode.WriteSchema)  
```  
  
```csharp  
custDS.WriteXml("Customers.xml", XmlWriteMode.WriteSchema);  
```  
  
```vb  
Dim xmlSW As System.IO.StreamWriter = New System.IO.StreamWriter("Customers.xml")  
custDS.WriteXml(xmlSW, XmlWriteMode.WriteSchema)  
xmlSW.Close()  
```  
  
```csharp  
System.IO.StreamWriter xmlSW = new System.IO.StreamWriter("Customers.xml");  
custDS.WriteXml(xmlSW, XmlWriteMode.WriteSchema);  
xmlSW.Close();  
```  
  
## <a name="mapping-columns-to-xml-elements-attributes-and-text"></a><span data-ttu-id="a41b2-134">열을 XML 요소, 특성 및 텍스트에 매핑</span><span class="sxs-lookup"><span data-stu-id="a41b2-134">Mapping Columns to XML Elements, Attributes, and Text</span></span>  

 <span data-ttu-id="a41b2-135">**DataColumn** 개체의 **ColumnMapping** 속성을 사용 하 여 XML에서 테이블의 열을 표현 하는 방법을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a41b2-135">You can specify how a column of a table is represented in XML using the **ColumnMapping** property of the **DataColumn** object.</span></span> <span data-ttu-id="a41b2-136">다음 표에서는 테이블 열의 **ColumnMapping** 속성과 결과 XML에 대 한 다양 한 **mappingtype.attribute** 값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a41b2-136">The following table shows the different **MappingType** values for the **ColumnMapping** property of a table column, and the resulting XML.</span></span>  
  
|<span data-ttu-id="a41b2-137">MappingType 값</span><span class="sxs-lookup"><span data-stu-id="a41b2-137">MappingType value</span></span>|<span data-ttu-id="a41b2-138">설명</span><span class="sxs-lookup"><span data-stu-id="a41b2-138">Description</span></span>|  
|-----------------------|-----------------|  
|<span data-ttu-id="a41b2-139">**요소**</span><span class="sxs-lookup"><span data-stu-id="a41b2-139">**Element**</span></span>|<span data-ttu-id="a41b2-140">이것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="a41b2-140">This is the default.</span></span> <span data-ttu-id="a41b2-141">열이 XML 요소로 작성되며, 이 때 ColumnName이 요소의 이름이 되고 열의 내용은 요소의 텍스트로 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a41b2-141">The column is written as an XML element where the ColumnName is the name of the element and the contents of the column are written as the text of the element.</span></span> <span data-ttu-id="a41b2-142">다음은 그 예입니다. </span><span class="sxs-lookup"><span data-stu-id="a41b2-142">For example:</span></span><br /><br /> `<ColumnName>Column Contents</ColumnName>`|  
|<span data-ttu-id="a41b2-143">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="a41b2-143">**Attribute**</span></span>|<span data-ttu-id="a41b2-144">열이 현재 행에 대한 XML 요소의 XML 특성으로 작성되며, 이 때 특성의 이름은 ColumnName이며 열의 내용은 특성의 값으로 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a41b2-144">The column is written as an XML attribute of the XML element for the current row where the ColumnName is the name of the attribute and the contents of the column are written as the value of the attribute.</span></span> <span data-ttu-id="a41b2-145">다음은 그 예입니다. </span><span class="sxs-lookup"><span data-stu-id="a41b2-145">For example:</span></span><br /><br /> `<RowElement ColumnName="Column Contents" />`|  
|<span data-ttu-id="a41b2-146">**SimpleContent**</span><span class="sxs-lookup"><span data-stu-id="a41b2-146">**SimpleContent**</span></span>|<span data-ttu-id="a41b2-147">열의 내용이 현재 행에 대한 XML 요소의 텍스트로 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a41b2-147">The contents of the column are written as text in the XML element for the current row.</span></span> <span data-ttu-id="a41b2-148">다음은 그 예입니다. </span><span class="sxs-lookup"><span data-stu-id="a41b2-148">For example:</span></span><br /><br /> `<RowElement>Column Contents</RowElement>`<br /><br /> <span data-ttu-id="a41b2-149">**요소** 열 또는 중첩 관계가 있는 테이블의 열에는 **SimpleContent** 를 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a41b2-149">Note that **SimpleContent** cannot be set for a column of a table that has **Element** columns or nested relations.</span></span>|  
|<span data-ttu-id="a41b2-150">**숨김**</span><span class="sxs-lookup"><span data-stu-id="a41b2-150">**Hidden**</span></span>|<span data-ttu-id="a41b2-151">열이 XML 출력으로 작성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a41b2-151">The column is not written in the XML output.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a41b2-152">참조</span><span class="sxs-lookup"><span data-stu-id="a41b2-152">See also</span></span>

- [<span data-ttu-id="a41b2-153">데이터 세트에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="a41b2-153">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="a41b2-154">DiffGram</span><span class="sxs-lookup"><span data-stu-id="a41b2-154">DiffGrams</span></span>](diffgrams.md)
- [<span data-ttu-id="a41b2-155">DataRelation 중첩</span><span class="sxs-lookup"><span data-stu-id="a41b2-155">Nesting DataRelations</span></span>](nesting-datarelations.md)
- [<span data-ttu-id="a41b2-156">데이터 세트 스키마 정보를 XSD로 작성</span><span class="sxs-lookup"><span data-stu-id="a41b2-156">Writing DataSet Schema Information as XSD</span></span>](writing-dataset-schema-information-as-xsd.md)
- [<span data-ttu-id="a41b2-157">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="a41b2-157">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="a41b2-158">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="a41b2-158">ADO.NET Overview</span></span>](../ado-net-overview.md)
