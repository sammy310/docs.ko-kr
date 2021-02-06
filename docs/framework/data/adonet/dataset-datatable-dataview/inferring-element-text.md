---
description: '자세한 정보: 요소 텍스트 유추'
title: 요소 텍스트 유추
ms.date: 03/30/2017
ms.assetid: 789799e5-716f-459f-a168-76c5cf22178b
ms.openlocfilehash: 5d0d9b1b3bb6164cd3cf26b429a4c7d658ee4128
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652213"
---
# <a name="inferring-element-text"></a><span data-ttu-id="b61bf-103">요소 텍스트 유추</span><span class="sxs-lookup"><span data-stu-id="b61bf-103">Inferring Element Text</span></span>

<span data-ttu-id="b61bf-104">요소가 텍스트를 포함 하 고 테이블 (특성 또는 반복 요소가 포함 된 요소)로 유추 될 자식 요소가 없는 경우 **TableName_Text** 이름이 인 새 열이 요소에 대해 유추 되는 테이블에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b61bf-104">If an element contains text and has no child elements to be inferred as tables (such as elements with attributes or repeated elements), a new column with the name **TableName_Text** will be added to the table that is inferred for the element.</span></span> <span data-ttu-id="b61bf-105">이 요소에 포함된 텍스트는 테이블의 행에 추가되어 새 열에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="b61bf-105">The text contained in the element will be added to a row in the table and stored in the new column.</span></span> <span data-ttu-id="b61bf-106">새 열의 **ColumnMapping** 속성은 **mappingtype.attribute** 로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b61bf-106">The **ColumnMapping** property of the new column will be set to **MappingType.SimpleContent**.</span></span>  
  
 <span data-ttu-id="b61bf-107">예를 들어, 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="b61bf-107">For example, consider the following XML.</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="b61bf-108">유추 프로세스에서는 두 개의 열 ( **attr1** 및 **Element1_Text**)이 포함 된 **Element1** 라는 테이블을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b61bf-108">The inference process will produce a table named **Element1** with two columns: **attr1** and **Element1_Text**.</span></span> <span data-ttu-id="b61bf-109">**Attr1** 열의 **ColumnMapping** 속성은 **mappingtype.attribute** 로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b61bf-109">The **ColumnMapping** property of the **attr1** column will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="b61bf-110">**Element1_Text** 열의 **ColumnMapping** 속성은 **mappingtype.attribute** 로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b61bf-110">The **ColumnMapping** property of the **Element1_Text** column will be set to **MappingType.SimpleContent**.</span></span>  
  
 <span data-ttu-id="b61bf-111">**데이터 집합:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="b61bf-111">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="b61bf-112">**테이블:** Element1</span><span class="sxs-lookup"><span data-stu-id="b61bf-112">**Table:** Element1</span></span>  
  
|<span data-ttu-id="b61bf-113">attr1</span><span class="sxs-lookup"><span data-stu-id="b61bf-113">attr1</span></span>|<span data-ttu-id="b61bf-114">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="b61bf-114">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="b61bf-115">value1</span><span class="sxs-lookup"><span data-stu-id="b61bf-115">value1</span></span>|<span data-ttu-id="b61bf-116">Text1</span><span class="sxs-lookup"><span data-stu-id="b61bf-116">Text1</span></span>|  
  
 <span data-ttu-id="b61bf-117">요소에 텍스트뿐만 아니라 텍스트가 포함된 자식 요소도 있는 경우에는 해당 요소에 포함된 텍스트를 저장할 열이 테이블에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b61bf-117">If an element contains text, but also has child elements that contain text, a column will not be added to the table to store the text contained in the element.</span></span> <span data-ttu-id="b61bf-118">따라서 이 요소에 포함된 텍스트는 무시되지만 자식 요소에 있는 텍스트는 해당 테이블의 행에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="b61bf-118">The text contained in the element will be ignored, while the text in the child elements is included in a row in the table.</span></span> <span data-ttu-id="b61bf-119">예를 들어, 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="b61bf-119">For example, consider the following XML.</span></span>  
  
```xml  
<Element1>  
  Text1  
  <ChildElement1>Text2</ChildElement1>  
  Text3  
</Element1>  
```  
  
 <span data-ttu-id="b61bf-120">유추 프로세스는 **ChildElement1** 라는 열이 있는 **Element1** 이라는 테이블을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b61bf-120">The inference process will produce a table named **Element1** with one column named **ChildElement1**.</span></span> <span data-ttu-id="b61bf-121">**ChildElement1** 요소의 텍스트는 테이블의 행에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b61bf-121">The text for the **ChildElement1** element will be included in a row in the table.</span></span> <span data-ttu-id="b61bf-122">다른 텍스트는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b61bf-122">The other text will be ignored.</span></span> <span data-ttu-id="b61bf-123">**ChildElement1** 열의 **ColumnMapping** 속성은 **mappingtype.attribute** 로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b61bf-123">The **ColumnMapping** property of the **ChildElement1** column will be set to **MappingType.Element**.</span></span>  
  
 <span data-ttu-id="b61bf-124">**데이터 집합:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="b61bf-124">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="b61bf-125">**테이블:** Element1</span><span class="sxs-lookup"><span data-stu-id="b61bf-125">**Table:** Element1</span></span>  
  
|<span data-ttu-id="b61bf-126">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="b61bf-126">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="b61bf-127">Text2</span><span class="sxs-lookup"><span data-stu-id="b61bf-127">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b61bf-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b61bf-128">See also</span></span>

- [<span data-ttu-id="b61bf-129">XML에서 데이터 세트 관계형 구조 유추</span><span class="sxs-lookup"><span data-stu-id="b61bf-129">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="b61bf-130">XML에서 데이터 세트 로드</span><span class="sxs-lookup"><span data-stu-id="b61bf-130">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="b61bf-131">XML에서 데이터 세트 스키마 정보 로드</span><span class="sxs-lookup"><span data-stu-id="b61bf-131">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="b61bf-132">데이터 세트에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="b61bf-132">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="b61bf-133">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="b61bf-133">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="b61bf-134">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="b61bf-134">ADO.NET Overview</span></span>](../ado-net-overview.md)
