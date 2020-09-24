---
title: 요소 텍스트 유추
ms.date: 03/30/2017
ms.assetid: 789799e5-716f-459f-a168-76c5cf22178b
ms.openlocfilehash: 7389e24f39902edf041c3cd3502303b17fd008ba
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164690"
---
# <a name="inferring-element-text"></a><span data-ttu-id="823bf-102">요소 텍스트 유추</span><span class="sxs-lookup"><span data-stu-id="823bf-102">Inferring Element Text</span></span>

<span data-ttu-id="823bf-103">요소가 텍스트를 포함 하 고 테이블 (특성 또는 반복 요소가 포함 된 요소)로 유추 될 자식 요소가 없는 경우 **TableName_Text** 이름이 인 새 열이 요소에 대해 유추 되는 테이블에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="823bf-103">If an element contains text and has no child elements to be inferred as tables (such as elements with attributes or repeated elements), a new column with the name **TableName_Text** will be added to the table that is inferred for the element.</span></span> <span data-ttu-id="823bf-104">이 요소에 포함된 텍스트는 테이블의 행에 추가되어 새 열에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="823bf-104">The text contained in the element will be added to a row in the table and stored in the new column.</span></span> <span data-ttu-id="823bf-105">새 열의 **ColumnMapping** 속성은 **mappingtype.attribute**로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="823bf-105">The **ColumnMapping** property of the new column will be set to **MappingType.SimpleContent**.</span></span>  
  
 <span data-ttu-id="823bf-106">예를 들어, 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="823bf-106">For example, consider the following XML.</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="823bf-107">유추 프로세스에서는 두 개의 열 ( **attr1** 및 **Element1_Text**)이 포함 된 **Element1** 라는 테이블을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="823bf-107">The inference process will produce a table named **Element1** with two columns: **attr1** and **Element1_Text**.</span></span> <span data-ttu-id="823bf-108">**Attr1** 열의 **ColumnMapping** 속성은 **mappingtype.attribute**로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="823bf-108">The **ColumnMapping** property of the **attr1** column will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="823bf-109">**Element1_Text** 열의 **ColumnMapping** 속성은 **mappingtype.attribute**로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="823bf-109">The **ColumnMapping** property of the **Element1_Text** column will be set to **MappingType.SimpleContent**.</span></span>  
  
 <span data-ttu-id="823bf-110">**데이터 집합:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="823bf-110">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="823bf-111">**테이블:** Element1</span><span class="sxs-lookup"><span data-stu-id="823bf-111">**Table:** Element1</span></span>  
  
|<span data-ttu-id="823bf-112">attr1</span><span class="sxs-lookup"><span data-stu-id="823bf-112">attr1</span></span>|<span data-ttu-id="823bf-113">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="823bf-113">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="823bf-114">value1</span><span class="sxs-lookup"><span data-stu-id="823bf-114">value1</span></span>|<span data-ttu-id="823bf-115">Text1</span><span class="sxs-lookup"><span data-stu-id="823bf-115">Text1</span></span>|  
  
 <span data-ttu-id="823bf-116">요소에 텍스트뿐만 아니라 텍스트가 포함된 자식 요소도 있는 경우에는 해당 요소에 포함된 텍스트를 저장할 열이 테이블에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="823bf-116">If an element contains text, but also has child elements that contain text, a column will not be added to the table to store the text contained in the element.</span></span> <span data-ttu-id="823bf-117">따라서 이 요소에 포함된 텍스트는 무시되지만 자식 요소에 있는 텍스트는 해당 테이블의 행에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="823bf-117">The text contained in the element will be ignored, while the text in the child elements is included in a row in the table.</span></span> <span data-ttu-id="823bf-118">예를 들어, 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="823bf-118">For example, consider the following XML.</span></span>  
  
```xml  
<Element1>  
  Text1  
  <ChildElement1>Text2</ChildElement1>  
  Text3  
</Element1>  
```  
  
 <span data-ttu-id="823bf-119">유추 프로세스는 **ChildElement1**라는 열이 있는 **Element1** 이라는 테이블을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="823bf-119">The inference process will produce a table named **Element1** with one column named **ChildElement1**.</span></span> <span data-ttu-id="823bf-120">**ChildElement1** 요소의 텍스트는 테이블의 행에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="823bf-120">The text for the **ChildElement1** element will be included in a row in the table.</span></span> <span data-ttu-id="823bf-121">다른 텍스트는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="823bf-121">The other text will be ignored.</span></span> <span data-ttu-id="823bf-122">**ChildElement1** 열의 **ColumnMapping** 속성은 **mappingtype.attribute**로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="823bf-122">The **ColumnMapping** property of the **ChildElement1** column will be set to **MappingType.Element**.</span></span>  
  
 <span data-ttu-id="823bf-123">**데이터 집합:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="823bf-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="823bf-124">**테이블:** Element1</span><span class="sxs-lookup"><span data-stu-id="823bf-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="823bf-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="823bf-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="823bf-126">Text2</span><span class="sxs-lookup"><span data-stu-id="823bf-126">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="823bf-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="823bf-127">See also</span></span>

- [<span data-ttu-id="823bf-128">XML에서 데이터 세트 관계형 구조 유추</span><span class="sxs-lookup"><span data-stu-id="823bf-128">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="823bf-129">XML에서 데이터 세트 로드</span><span class="sxs-lookup"><span data-stu-id="823bf-129">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="823bf-130">XML에서 데이터 세트 스키마 정보 로드</span><span class="sxs-lookup"><span data-stu-id="823bf-130">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="823bf-131">데이터 세트에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="823bf-131">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="823bf-132">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="823bf-132">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="823bf-133">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="823bf-133">ADO.NET Overview</span></span>](../ado-net-overview.md)
