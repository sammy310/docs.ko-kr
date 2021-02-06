---
description: '자세히 알아보기: 테이블 유추'
title: 테이블 유추
ms.date: 03/30/2017
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
ms.openlocfilehash: 00a24cbfc44aea4279b0a115214ec26d3eac59ad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652161"
---
# <a name="inferring-tables"></a><span data-ttu-id="accae-103">테이블 유추</span><span class="sxs-lookup"><span data-stu-id="accae-103">Inferring Tables</span></span>

<span data-ttu-id="accae-104">XML 문서로부터 <xref:System.Data.DataSet>의 스키마를 유추할 때 ADO.NET에서는 우선 테이블을 나타내는 XML 요소를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="accae-104">When inferring a schema for a <xref:System.Data.DataSet> from an XML document, ADO.NET first determines which XML elements represent tables.</span></span> <span data-ttu-id="accae-105">다음 XML 구조는 **데이터 집합** 스키마에 대 한 테이블을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="accae-105">The following XML structures result in a table for the **DataSet** schema:</span></span>  
  
- <span data-ttu-id="accae-106">특성이 있는 요소</span><span class="sxs-lookup"><span data-stu-id="accae-106">Elements with attributes</span></span>  
  
- <span data-ttu-id="accae-107">자식 요소가 있는 요소</span><span class="sxs-lookup"><span data-stu-id="accae-107">Elements with child elements</span></span>  
  
- <span data-ttu-id="accae-108">반복되는 요소</span><span class="sxs-lookup"><span data-stu-id="accae-108">Repeating elements</span></span>  
  
## <a name="elements-with-attributes"></a><span data-ttu-id="accae-109">특성이 있는 요소</span><span class="sxs-lookup"><span data-stu-id="accae-109">Elements with Attributes</span></span>  

 <span data-ttu-id="accae-110">자신에 지정된 특성을 갖고 있는 요소는 유추된 테이블이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="accae-110">Elements that have attributes specified in them result in inferred tables.</span></span> <span data-ttu-id="accae-111">예를 들어, 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="accae-111">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="accae-112">위 유추 과정에서 "Element1"이라는 테이블이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="accae-112">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="accae-113">**데이터 집합:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="accae-113">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="accae-114">**테이블:** Element1</span><span class="sxs-lookup"><span data-stu-id="accae-114">**Table:** Element1</span></span>  
  
|<span data-ttu-id="accae-115">attr1</span><span class="sxs-lookup"><span data-stu-id="accae-115">attr1</span></span>|<span data-ttu-id="accae-116">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="accae-116">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="accae-117">value1</span><span class="sxs-lookup"><span data-stu-id="accae-117">value1</span></span>||  
|<span data-ttu-id="accae-118">value2</span><span class="sxs-lookup"><span data-stu-id="accae-118">value2</span></span>|<span data-ttu-id="accae-119">Text1</span><span class="sxs-lookup"><span data-stu-id="accae-119">Text1</span></span>|  
  
## <a name="elements-with-child-elements"></a><span data-ttu-id="accae-120">자식 요소가 있는 요소</span><span class="sxs-lookup"><span data-stu-id="accae-120">Elements with Child Elements</span></span>  

 <span data-ttu-id="accae-121">자식 요소를 갖고 있는 요소는 유추된 테이블이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="accae-121">Elements that have child elements result in inferred tables.</span></span> <span data-ttu-id="accae-122">예를 들어, 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="accae-122">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="accae-123">위 유추 과정에서 "Element1"이라는 테이블이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="accae-123">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="accae-124">**데이터 집합:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="accae-124">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="accae-125">**테이블:** Element1</span><span class="sxs-lookup"><span data-stu-id="accae-125">**Table:** Element1</span></span>  
  
|<span data-ttu-id="accae-126">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="accae-126">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="accae-127">Text1</span><span class="sxs-lookup"><span data-stu-id="accae-127">Text1</span></span>|  
  
 <span data-ttu-id="accae-128">문서 요소 또는 루트 요소는 열로 유추되는 특성이나 자식 요소를 갖고 있는 경우 유추된 테이블이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="accae-128">The document, or root, element result in an inferred table if it has attributes or child elements that are inferred as columns.</span></span> <span data-ttu-id="accae-129">문서 요소에 특성이 없고 열로 유추 되는 자식 요소가 없는 경우 요소는 **데이터 집합** 으로 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="accae-129">If the document element has no attributes and no child elements that would be inferred as columns, the element is inferred as a **DataSet**.</span></span> <span data-ttu-id="accae-130">예를 들어, 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="accae-130">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 <span data-ttu-id="accae-131">위 유추 과정에서 "DocumentElement"라는 테이블이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="accae-131">The inference process produces a table named "DocumentElement."</span></span>  
  
 <span data-ttu-id="accae-132">**데이터 집합:** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="accae-132">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="accae-133">**테이블:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="accae-133">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="accae-134">Element1</span><span class="sxs-lookup"><span data-stu-id="accae-134">Element1</span></span>|<span data-ttu-id="accae-135">Element2</span><span class="sxs-lookup"><span data-stu-id="accae-135">Element2</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="accae-136">Text1</span><span class="sxs-lookup"><span data-stu-id="accae-136">Text1</span></span>|<span data-ttu-id="accae-137">Text2</span><span class="sxs-lookup"><span data-stu-id="accae-137">Text2</span></span>|  
  
 <span data-ttu-id="accae-138">또는 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="accae-138">Alternatively, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="accae-139">유추 프로세스는 "Element1" 라는 테이블을 포함 하는 "DocumentElement" 라는 **데이터 집합** 을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="accae-139">The inference process produces a **DataSet** named "DocumentElement" that contains a table named "Element1."</span></span>  
  
 <span data-ttu-id="accae-140">**데이터 집합:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="accae-140">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="accae-141">**테이블:** Element1</span><span class="sxs-lookup"><span data-stu-id="accae-141">**Table:** Element1</span></span>  
  
|<span data-ttu-id="accae-142">attr1</span><span class="sxs-lookup"><span data-stu-id="accae-142">attr1</span></span>|<span data-ttu-id="accae-143">attr2</span><span class="sxs-lookup"><span data-stu-id="accae-143">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="accae-144">value1</span><span class="sxs-lookup"><span data-stu-id="accae-144">value1</span></span>|<span data-ttu-id="accae-145">value2</span><span class="sxs-lookup"><span data-stu-id="accae-145">value2</span></span>|  
  
## <a name="repeating-elements"></a><span data-ttu-id="accae-146">반복되는 요소</span><span class="sxs-lookup"><span data-stu-id="accae-146">Repeating Elements</span></span>  

 <span data-ttu-id="accae-147">반복되는 요소는 하나의 유추된 테이블이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="accae-147">Elements that repeat result in a single inferred table.</span></span> <span data-ttu-id="accae-148">예를 들어, 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="accae-148">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="accae-149">위 유추 과정에서 "Element1"이라는 테이블이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="accae-149">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="accae-150">**데이터 집합:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="accae-150">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="accae-151">**테이블:** Element1</span><span class="sxs-lookup"><span data-stu-id="accae-151">**Table:** Element1</span></span>  
  
|<span data-ttu-id="accae-152">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="accae-152">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="accae-153">Text1</span><span class="sxs-lookup"><span data-stu-id="accae-153">Text1</span></span>|  
|<span data-ttu-id="accae-154">Text2</span><span class="sxs-lookup"><span data-stu-id="accae-154">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="accae-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="accae-155">See also</span></span>

- [<span data-ttu-id="accae-156">XML에서 데이터 세트 관계형 구조 유추</span><span class="sxs-lookup"><span data-stu-id="accae-156">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="accae-157">XML에서 데이터 세트 로드</span><span class="sxs-lookup"><span data-stu-id="accae-157">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="accae-158">XML에서 데이터 세트 스키마 정보 로드</span><span class="sxs-lookup"><span data-stu-id="accae-158">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="accae-159">데이터 세트에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="accae-159">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="accae-160">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="accae-160">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="accae-161">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="accae-161">ADO.NET Overview</span></span>](../ado-net-overview.md)
