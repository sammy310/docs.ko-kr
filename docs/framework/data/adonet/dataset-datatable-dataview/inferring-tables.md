---
title: 테이블 유추
ms.date: 03/30/2017
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
ms.openlocfilehash: 2c2a93d413f301dc3006b701e4bc7979a3fa7a1d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59181833"
---
# <a name="inferring-tables"></a><span data-ttu-id="492e1-102">테이블 유추</span><span class="sxs-lookup"><span data-stu-id="492e1-102">Inferring Tables</span></span>
<span data-ttu-id="492e1-103">XML 문서로부터 <xref:System.Data.DataSet>의 스키마를 유추할 때 ADO.NET에서는 우선 테이블을 나타내는 XML 요소를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="492e1-103">When inferring a schema for a <xref:System.Data.DataSet> from an XML document, ADO.NET first determines which XML elements represent tables.</span></span> <span data-ttu-id="492e1-104">다음 XML 구조에 대 한 테이블의 결과 **데이터 집합** 스키마:</span><span class="sxs-lookup"><span data-stu-id="492e1-104">The following XML structures result in a table for the **DataSet** schema:</span></span>  
  
-   <span data-ttu-id="492e1-105">특성이 있는 요소</span><span class="sxs-lookup"><span data-stu-id="492e1-105">Elements with attributes</span></span>  
  
-   <span data-ttu-id="492e1-106">자식 요소가 있는 요소</span><span class="sxs-lookup"><span data-stu-id="492e1-106">Elements with child elements</span></span>  
  
-   <span data-ttu-id="492e1-107">반복되는 요소</span><span class="sxs-lookup"><span data-stu-id="492e1-107">Repeating elements</span></span>  
  
## <a name="elements-with-attributes"></a><span data-ttu-id="492e1-108">특성이 있는 요소</span><span class="sxs-lookup"><span data-stu-id="492e1-108">Elements with Attributes</span></span>  
 <span data-ttu-id="492e1-109">자신에 지정된 특성을 갖고 있는 요소는 유추된 테이블이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="492e1-109">Elements that have attributes specified in them result in inferred tables.</span></span> <span data-ttu-id="492e1-110">예를 들어, 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="492e1-110">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="492e1-111">위 유추 과정에서 "Element1"이라는 테이블이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="492e1-111">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="492e1-112">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="492e1-112">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="492e1-113">**테이블:** Element1</span><span class="sxs-lookup"><span data-stu-id="492e1-113">**Table:** Element1</span></span>  
  
|<span data-ttu-id="492e1-114">attr1</span><span class="sxs-lookup"><span data-stu-id="492e1-114">attr1</span></span>|<span data-ttu-id="492e1-115">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="492e1-115">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="492e1-116">value1</span><span class="sxs-lookup"><span data-stu-id="492e1-116">value1</span></span>||  
|<span data-ttu-id="492e1-117">value2</span><span class="sxs-lookup"><span data-stu-id="492e1-117">value2</span></span>|<span data-ttu-id="492e1-118">Text1</span><span class="sxs-lookup"><span data-stu-id="492e1-118">Text1</span></span>|  
  
## <a name="elements-with-child-elements"></a><span data-ttu-id="492e1-119">자식 요소가 있는 요소</span><span class="sxs-lookup"><span data-stu-id="492e1-119">Elements with Child Elements</span></span>  
 <span data-ttu-id="492e1-120">자식 요소를 갖고 있는 요소는 유추된 테이블이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="492e1-120">Elements that have child elements result in inferred tables.</span></span> <span data-ttu-id="492e1-121">예를 들어, 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="492e1-121">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="492e1-122">위 유추 과정에서 "Element1"이라는 테이블이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="492e1-122">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="492e1-123">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="492e1-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="492e1-124">**테이블:** Element1</span><span class="sxs-lookup"><span data-stu-id="492e1-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="492e1-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="492e1-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="492e1-126">Text1</span><span class="sxs-lookup"><span data-stu-id="492e1-126">Text1</span></span>|  
  
 <span data-ttu-id="492e1-127">문서 요소 또는 루트 요소는 열로 유추되는 특성이나 자식 요소를 갖고 있는 경우 유추된 테이블이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="492e1-127">The document, or root, element result in an inferred table if it has attributes or child elements that are inferred as columns.</span></span> <span data-ttu-id="492e1-128">문서 요소가 없는 특성과 열으로 유추 되는 자식 요소가 없는 요소도 유추 됩니다는 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="492e1-128">If the document element has no attributes and no child elements that would be inferred as columns, the element is inferred as a **DataSet**.</span></span> <span data-ttu-id="492e1-129">예를 들어, 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="492e1-129">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 <span data-ttu-id="492e1-130">위 유추 과정에서 "DocumentElement"라는 테이블이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="492e1-130">The inference process produces a table named "DocumentElement."</span></span>  
  
 <span data-ttu-id="492e1-131">**DataSet:** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="492e1-131">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="492e1-132">**테이블:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="492e1-132">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="492e1-133">Element1</span><span class="sxs-lookup"><span data-stu-id="492e1-133">Element1</span></span>|<span data-ttu-id="492e1-134">Element2</span><span class="sxs-lookup"><span data-stu-id="492e1-134">Element2</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="492e1-135">Text1</span><span class="sxs-lookup"><span data-stu-id="492e1-135">Text1</span></span>|<span data-ttu-id="492e1-136">Text2</span><span class="sxs-lookup"><span data-stu-id="492e1-136">Text2</span></span>|  
  
 <span data-ttu-id="492e1-137">또는 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="492e1-137">Alternatively, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="492e1-138">유추 과정에서 생성 된 **데이터 집합** "Element1." 라는 테이블을 포함 하는 "DocumentElement" 라는</span><span class="sxs-lookup"><span data-stu-id="492e1-138">The inference process produces a **DataSet** named "DocumentElement" that contains a table named "Element1."</span></span>  
  
 <span data-ttu-id="492e1-139">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="492e1-139">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="492e1-140">**테이블:** Element1</span><span class="sxs-lookup"><span data-stu-id="492e1-140">**Table:** Element1</span></span>  
  
|<span data-ttu-id="492e1-141">attr1</span><span class="sxs-lookup"><span data-stu-id="492e1-141">attr1</span></span>|<span data-ttu-id="492e1-142">attr2</span><span class="sxs-lookup"><span data-stu-id="492e1-142">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="492e1-143">value1</span><span class="sxs-lookup"><span data-stu-id="492e1-143">value1</span></span>|<span data-ttu-id="492e1-144">value2</span><span class="sxs-lookup"><span data-stu-id="492e1-144">value2</span></span>|  
  
## <a name="repeating-elements"></a><span data-ttu-id="492e1-145">반복되는 요소</span><span class="sxs-lookup"><span data-stu-id="492e1-145">Repeating Elements</span></span>  
 <span data-ttu-id="492e1-146">반복되는 요소는 하나의 유추된 테이블이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="492e1-146">Elements that repeat result in a single inferred table.</span></span> <span data-ttu-id="492e1-147">예를 들어, 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="492e1-147">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="492e1-148">위 유추 과정에서 "Element1"이라는 테이블이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="492e1-148">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="492e1-149">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="492e1-149">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="492e1-150">**테이블:** Element1</span><span class="sxs-lookup"><span data-stu-id="492e1-150">**Table:** Element1</span></span>  
  
|<span data-ttu-id="492e1-151">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="492e1-151">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="492e1-152">Text1</span><span class="sxs-lookup"><span data-stu-id="492e1-152">Text1</span></span>|  
|<span data-ttu-id="492e1-153">Text2</span><span class="sxs-lookup"><span data-stu-id="492e1-153">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="492e1-154">참고자료</span><span class="sxs-lookup"><span data-stu-id="492e1-154">See also</span></span>

- [<span data-ttu-id="492e1-155">XML에서 데이터 집합 관계형 구조 유추</span><span class="sxs-lookup"><span data-stu-id="492e1-155">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="492e1-156">XML에서 데이터 집합 로드</span><span class="sxs-lookup"><span data-stu-id="492e1-156">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [<span data-ttu-id="492e1-157">XML에서 데이터 집합 스키마 정보 로드</span><span class="sxs-lookup"><span data-stu-id="492e1-157">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="492e1-158">데이터 집합에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="492e1-158">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [<span data-ttu-id="492e1-159">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="492e1-159">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="492e1-160">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="492e1-160">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
