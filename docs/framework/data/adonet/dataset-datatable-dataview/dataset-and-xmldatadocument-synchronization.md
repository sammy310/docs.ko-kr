---
title: 데이터 세트 및 XmlDataDocument 동기화
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0ce3793d-54b2-47e4-8cf7-b0591cc4dd21
ms.openlocfilehash: 2790f0a9edd5bfde96683e00725dd04555379adf
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153302"
---
# <a name="dataset-and-xmldatadocument-synchronization"></a><span data-ttu-id="e6e5b-102">데이터 세트 및 XmlDataDocument 동기화</span><span class="sxs-lookup"><span data-stu-id="e6e5b-102">DataSet and XmlDataDocument Synchronization</span></span>

<span data-ttu-id="e6e5b-103">ADO.NET <xref:System.Data.DataSet>으로 데이터의 관계형 표현을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-103">The ADO.NET <xref:System.Data.DataSet> provides you with a relational representation of data.</span></span> <span data-ttu-id="e6e5b-104">계층적으로 데이터에 액세스하기 위해 .NET Framework에서 사용 가능한 XML 클래스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-104">For hierarchical data access, you can use the XML classes available in the .NET Framework.</span></span> <span data-ttu-id="e6e5b-105">지금까지는 데이터의 이와 같은 두 가지 표현이 별도로 사용되어 왔습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-105">Historically, these two representations of data have been used separately.</span></span> <span data-ttu-id="e6e5b-106">그러나 .NET Framework를 사용 하면 데이터 **집합** 개체와 개체를 통해 각각 관계형 및 계층적 데이터 표현에 대 한 실시간 동기 액세스를 사용할 수 있습니다 <xref:System.Xml.XmlDataDocument> .</span><span class="sxs-lookup"><span data-stu-id="e6e5b-106">However, the .NET Framework enables real-time, synchronous access to both the relational and hierarchical representations of data through the **DataSet** object and the <xref:System.Xml.XmlDataDocument> object, respectively.</span></span>  
  
 <span data-ttu-id="e6e5b-107">**데이터 집합이** **XmlDataDocument**와 동기화 되 면 두 개체가 모두 단일 데이터 집합을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-107">When a **DataSet** is synchronized with an **XmlDataDocument**, both objects are working with a single set of data.</span></span> <span data-ttu-id="e6e5b-108">즉, **데이터 집합이**변경 되 면 변경 내용이 **XmlDataDocument**적용 되 고 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-108">This means that if a change is made to the **DataSet**, the change will be reflected in the **XmlDataDocument**, and vice versa.</span></span> <span data-ttu-id="e6e5b-109">**데이터 집합과** **XmlDataDocument** 간의 관계는 단일 응용 프로그램을 허용 하 여 상당한 유연성을 만듭니다. 단일 데이터 집합을 사용 하 여 데이터 **집합** (예: Web Forms 및 Windows Forms 컨트롤, Visual Studio .net 디자이너)을 기반으로 하는 전체 서비스 모음 뿐만 아니라 xsl (Extensible STYLESHEET Language), XSLT (XSL 변환), XPath (xml PATH language)를 비롯 한 xml 서비스 모음에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-109">The relationship between the **DataSet** and the **XmlDataDocument** creates great flexibility by allowing a single application, using a single set of data, to access the entire suite of services built around the **DataSet** (such as Web Forms and Windows Forms controls, and Visual Studio .NET designers), as well as the suite of XML services including Extensible Stylesheet Language (XSL), XSL Transformations (XSLT), and XML Path Language (XPath).</span></span> <span data-ttu-id="e6e5b-110">두 서비스를 모두 사용할 수 있으므로 애플리케이션의 대상이 될 서비스 집합을 선택할 필요도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-110">You do not have to choose which set of services to target with the application; both are available.</span></span>  
  
 <span data-ttu-id="e6e5b-111">**데이터 집합** 을 **XmlDataDocument**와 동기화 하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-111">There are several ways that you can synchronize a **DataSet** with an **XmlDataDocument**.</span></span> <span data-ttu-id="e6e5b-112">다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-112">You can:</span></span>  
  
- <span data-ttu-id="e6e5b-113">스키마 (즉, 관계형 구조)와 데이터를 사용 하 여 데이터 **집합** 을 채운 다음 새 **XmlDataDocument**와 동기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-113">Populate a **DataSet** with schema (that is, a relational structure) and data and then synchronize it with a new **XmlDataDocument**.</span></span> <span data-ttu-id="e6e5b-114">이렇게 하면 기존 관계형 데이터를 계층적으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-114">This provides a hierarchical view of existing relational data.</span></span> <span data-ttu-id="e6e5b-115">다음은 그 예입니다. </span><span class="sxs-lookup"><span data-stu-id="e6e5b-115">For example:</span></span>  
  
    ```vb  
    Dim dataSet As DataSet = New DataSet  
  
    ' Add code here to populate the DataSet with schema and data.  
  
    Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)  
    ```  
  
    ```csharp  
    DataSet dataSet = new DataSet();  
  
    // Add code here to populate the DataSet with schema and data.  
  
    XmlDataDocument xmlDoc = new XmlDataDocument(dataSet);  
    ```  
  
- <span data-ttu-id="e6e5b-116">스키마만 포함 하는 **데이터 집합** (예: 강력한 형식의 **데이터 집합**)을 채운 다음 **XMLDATADOCUMENT**와 동기화 하 고 XML 문서에서 **XmlDataDocument** 을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-116">Populate a **DataSet** with schema only (such as a strongly typed **DataSet**), synchronize it with an **XmlDataDocument**, and then load the **XmlDataDocument** from an XML document.</span></span> <span data-ttu-id="e6e5b-117">이렇게 하면 기존 계층적 데이터를 관계형으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-117">This provides a relational view of existing hierarchical data.</span></span> <span data-ttu-id="e6e5b-118">**데이터 집합** 스키마의 테이블 이름과 열 이름은 함께 동기화 할 XML 요소의 이름과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-118">The table names and column names in your **DataSet** schema must match the names of the XML elements that you want them synchronized with.</span></span> <span data-ttu-id="e6e5b-119">이 때 대/소문자도 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-119">This matching is case-sensitive.</span></span>  
  
     <span data-ttu-id="e6e5b-120">**데이터 집합** 의 스키마는 관계형 보기에 노출할 XML 요소와만 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-120">Note that the schema of the **DataSet** only needs to match the XML elements that you want to expose in your relational view.</span></span> <span data-ttu-id="e6e5b-121">이렇게 하면 XML 문서는 아주 크게, 이 문서의 관계형 "창"은 매우 작게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-121">This way, you can have a very large XML document and a very small relational "window" on that document.</span></span> <span data-ttu-id="e6e5b-122">**XmlDataDocument** 는 **데이터 집합이** 작은 부분만 노출 하는 경우에도 전체 XML 문서를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-122">The **XmlDataDocument** preserves the entire XML document even though the **DataSet** only exposes a small portion of it.</span></span> <span data-ttu-id="e6e5b-123">이에 대 한 자세한 예제는 [데이터 집합을 XmlDataDocument와 동기화](synchronizing-a-dataset-with-an-xmldatadocument.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-123">(For a detailed example of this, see [Synchronizing a DataSet with an XmlDataDocument](synchronizing-a-dataset-with-an-xmldatadocument.md).)</span></span>  
  
     <span data-ttu-id="e6e5b-124">다음 코드 예제에서는 **데이터 집합** 을 만들고 해당 스키마를 채운 다음 **XmlDataDocument**와 동기화 하는 단계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-124">The following code example shows the steps for creating a **DataSet** and populating its schema, then synchronizing it with an **XmlDataDocument**.</span></span> <span data-ttu-id="e6e5b-125">**데이터 집합** 스키마는 **데이터 집합**을 사용 하 여 노출 하려는 **XmlDataDocument** 의 요소만 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-125">Note that the **DataSet** schema only needs to match the elements from the **XmlDataDocument** that you want to expose using the **DataSet**.</span></span>  
  
    ```vb  
    Dim dataSet As DataSet = New DataSet  
  
    ' Add code here to populate the DataSet with schema, but not data.  
  
    Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)  
    xmlDoc.Load("XMLDocument.xml")  
    ```  
  
    ```csharp  
    DataSet dataSet = new DataSet();  
  
    // Add code here to populate the DataSet with schema, but not data.  
  
    XmlDataDocument xmlDoc = new XmlDataDocument(dataSet);  
    xmlDoc.Load("XMLDocument.xml");  
    ```  
  
     <span data-ttu-id="e6e5b-126">데이터가 포함 된 데이터 **집합과** 동기화 된 경우에는 **XmlDataDocument** 을 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-126">You cannot load an **XmlDataDocument** if it is synchronized with a **DataSet** that contains data.</span></span> <span data-ttu-id="e6e5b-127">로드하는 경우에는 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-127">An exception will be thrown.</span></span>  
  
- <span data-ttu-id="e6e5b-128">새 **XmlDataDocument** 을 만들고 XML 문서에서 로드 한 다음 **XmlDataDocument**의 **DataSet** 속성을 사용 하 여 데이터의 관계형 뷰에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-128">Create a new **XmlDataDocument** and load it from an XML document, and then access the relational view of the data using the **DataSet** property of the **XmlDataDocument**.</span></span> <span data-ttu-id="e6e5b-129">데이터 **집합의** 스키마를 설정 해야 데이터 **집합**을 사용 하 여 **XmlDataDocument** 에서 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-129">You need to set the schema of the **DataSet** before you can view any of the data in the **XmlDataDocument** using the **DataSet**.</span></span> <span data-ttu-id="e6e5b-130">**데이터 집합** 스키마의 테이블 이름과 열 이름은 함께 동기화 할 XML 요소의 이름과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-130">Again, the table names and column names in your **DataSet** schema must match the names of the XML elements that you want them synchronized with.</span></span> <span data-ttu-id="e6e5b-131">이 때 대/소문자도 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-131">This matching is case-sensitive.</span></span>  
  
     <span data-ttu-id="e6e5b-132">다음 코드 예제에서는 **XmlDataDocument**에서 데이터의 관계형 뷰에 액세스 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-132">The following code example shows how to access the relational view of the data in an **XmlDataDocument**.</span></span>  
  
    ```vb  
    Dim xmlDoc As XmlDataDocument = New XmlDataDocument  
    Dim dataSet As DataSet = xmlDoc.DataSet  
  
    ' Add code here to create the schema of the DataSet to view the data.  
  
    xmlDoc.Load("XMLDocument.xml")  
    ```  
  
    ```csharp  
    XmlDataDocument xmlDoc = new XmlDataDocument();  
    DataSet dataSet = xmlDoc.DataSet;  
  
    // Add code here to create the schema of the DataSet to view the data.  
  
    xmlDoc.Load("XMLDocument.xml");  
    ```  
  
 <span data-ttu-id="e6e5b-133">**XmlDataDocument** 를 **DataSet** 과 동기화 하는 또 다른 이점은 XML 문서의 충실도가 유지 된다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-133">Another advantage of synchronizing an **XmlDataDocument** with a **DataSet** is that the fidelity of an XML document is preserved.</span></span> <span data-ttu-id="e6e5b-134">데이터 **집합이** **ReadXml**를 사용 하 여 xml 문서에서 채워지는 경우 **WriteXml** 을 사용 하 여 데이터를 XML 문서로 다시 쓸 때 원래 xml 문서와 크게 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-134">If the **DataSet** is populated from an XML document using **ReadXml**, when the data is written back as an XML document using **WriteXml** it may differ dramatically from the original XML document.</span></span> <span data-ttu-id="e6e5b-135">이는 **데이터 집합이** XML 문서에서 공백 등의 서식 지정 이나 요소 순서와 같은 계층적 정보를 유지 하지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-135">This is because the **DataSet** does not maintain formatting, such as white space, or hierarchical information, such as element order, from the XML document.</span></span> <span data-ttu-id="e6e5b-136">데이터 **집합은** **데이터 집합**의 스키마와 일치 하지 않기 때문에 무시 된 XML 문서의 요소도 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-136">The **DataSet** also does not contain elements from the XML document that were ignored because they did not match the schema of the **Dataset**.</span></span> <span data-ttu-id="e6e5b-137">**XmlDataDocument** 를 **dataset** 과 동기화 하면 원래 XML 문서의 서식 지정 및 계층 구조 요소를 **XmlDataDocument**에서 유지 관리할 수 있으며 데이터 집합에는 데이터 **집합**에 적합 한 데이터 및 스키마 **정보만 포함 됩니다** .</span><span class="sxs-lookup"><span data-stu-id="e6e5b-137">Synchronizing an **XmlDataDocument** with a **DataSet** allows the formatting and hierarchical element structure of the original XML document to be maintained in the **XmlDataDocument**, while the **DataSet** contains only data and schema information appropriate to the **DataSet**.</span></span>  
  
 <span data-ttu-id="e6e5b-138">**데이터 집합** 을 **XmlDataDocument**와 동기화 하는 경우에는 개체가 중첩 되었는지 여부에 따라 결과가 다를 수 있습니다 <xref:System.Data.DataRelation> .</span><span class="sxs-lookup"><span data-stu-id="e6e5b-138">When synchronizing a **DataSet** with an **XmlDataDocument**, results may differ depending on whether or not your <xref:System.Data.DataRelation> objects are nested.</span></span> <span data-ttu-id="e6e5b-139">자세한 내용은 [DataRelations 중첩](nesting-datarelations.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-139">For more information, see [Nesting DataRelations](nesting-datarelations.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e6e5b-140">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="e6e5b-140">In This Section</span></span>  

 [<span data-ttu-id="e6e5b-141">XmlDataDocument로 데이터 세트 동기화</span><span class="sxs-lookup"><span data-stu-id="e6e5b-141">Synchronizing a DataSet with an XmlDataDocument</span></span>](synchronizing-a-dataset-with-an-xmldatadocument.md)  
 <span data-ttu-id="e6e5b-142">**XmlDataDocument**를 사용 하 여 강력한 형식의 **데이터 집합**을 최소 스키마와 동기화 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-142">Demonstrates synchronizing a strongly typed **DataSet**, with minimal schema, with an **XmlDataDocument**.</span></span>  
  
 [<span data-ttu-id="e6e5b-143">데이터 세트에서 XPath 쿼리 수행</span><span class="sxs-lookup"><span data-stu-id="e6e5b-143">Performing an XPath Query on a DataSet</span></span>](performing-an-xpath-query-on-a-dataset.md)  
 <span data-ttu-id="e6e5b-144">**데이터 집합**의 내용에 대해 XPath 쿼리를 수행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-144">Demonstrates performing an XPath query on the contents of a **DataSet**.</span></span>  
  
 [<span data-ttu-id="e6e5b-145">XSLT 변형을 DataSet에 적용</span><span class="sxs-lookup"><span data-stu-id="e6e5b-145">Applying an XSLT Transform to a DataSet</span></span>](applying-an-xslt-transform-to-a-dataset.md)  
 <span data-ttu-id="e6e5b-146">XSLT 변환을 **데이터 집합**의 내용에 적용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-146">Demonstrates applying an XSLT transform to the contents of a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e6e5b-147">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="e6e5b-147">Related Sections</span></span>  

 [<span data-ttu-id="e6e5b-148">데이터 세트에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="e6e5b-148">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)  
 <span data-ttu-id="e6e5b-149">**Dataset의** 내용을 xml 데이터로 로드 하 고 유지 하는 것을 포함 하 여 데이터 **집합이** xml과 데이터 원본으로 상호 작용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-149">Describes how the **DataSet** interacts with XML as a data source, including loading and persisting the contents of a **DataSet** as XML data.</span></span>  
  
 [<span data-ttu-id="e6e5b-150">DataRelation 중첩</span><span class="sxs-lookup"><span data-stu-id="e6e5b-150">Nesting DataRelations</span></span>](nesting-datarelations.md)  
 <span data-ttu-id="e6e5b-151">**데이터 집합** 의 내용을 XML 데이터로 표현할 때 중첩 된 **DataRelation** 개체의 중요도를 설명 하 고 이러한 관계를 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-151">Discusses the importance of nested **DataRelation** objects when representing the contents of a **DataSet** as XML data, and describes how to create these relations.</span></span>  
  
 [<span data-ttu-id="e6e5b-152">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="e6e5b-152">DataSets, DataTables, and DataViews</span></span>](index.md)  
 <span data-ttu-id="e6e5b-153">**데이터 집합** 및 데이터 집합을 사용 하 여 응용 프로그램 데이터를 관리 하 고 관계형 데이터베이스 및 XML을 비롯 한 데이터 원본과 상호 작용 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-153">Describes the **DataSet** and how to use it to manage application data and to interact with data sources including relational databases and XML.</span></span>  
  
 <xref:System.Xml.XmlDataDocument>  
 <span data-ttu-id="e6e5b-154">**XmlDataDocument** 클래스에 대 한 참조 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e5b-154">Contains reference information about the **XmlDataDocument** class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6e5b-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e6e5b-155">See also</span></span>

- [<span data-ttu-id="e6e5b-156">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="e6e5b-156">ADO.NET Overview</span></span>](../ado-net-overview.md)
