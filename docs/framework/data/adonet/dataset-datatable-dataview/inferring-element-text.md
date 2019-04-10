---
title: 요소 텍스트 유추
ms.date: 03/30/2017
ms.assetid: 789799e5-716f-459f-a168-76c5cf22178b
ms.openlocfilehash: 6ffe8f2fbf01fbe8dfa9d78f3dfb9e39b6e80b16
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224964"
---
# <a name="inferring-element-text"></a><span data-ttu-id="a4a47-102">요소 텍스트 유추</span><span class="sxs-lookup"><span data-stu-id="a4a47-102">Inferring Element Text</span></span>
<span data-ttu-id="a4a47-103">요소 텍스트를 포함 하 고 테이블로 유추 될 (특성이 있는 요소) 또는 반복 되는 요소와 같은 이름 가진 새 열을 자식 요소가 없는 경우 **TableName_Text** 요소의 유추 테이블에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4a47-103">If an element contains text and has no child elements to be inferred as tables (such as elements with attributes or repeated elements), a new column with the name **TableName_Text** will be added to the table that is inferred for the element.</span></span> <span data-ttu-id="a4a47-104">이 요소에 포함된 텍스트는 테이블의 행에 추가되어 새 열에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4a47-104">The text contained in the element will be added to a row in the table and stored in the new column.</span></span> <span data-ttu-id="a4a47-105">합니다 **ColumnMapping** 새 열의 속성에 설정할 **MappingType.SimpleContent**합니다.</span><span class="sxs-lookup"><span data-stu-id="a4a47-105">The **ColumnMapping** property of the new column will be set to **MappingType.SimpleContent**.</span></span>  
  
 <span data-ttu-id="a4a47-106">예를 들어, 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="a4a47-106">For example, consider the following XML.</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="a4a47-107">유추 과정 이라는 테이블이 생성 됩니다 **Element1** 두 개의 열을 사용 하 여: **attr1** 하 고 **Element1_Text**합니다.</span><span class="sxs-lookup"><span data-stu-id="a4a47-107">The inference process will produce a table named **Element1** with two columns: **attr1** and **Element1_Text**.</span></span> <span data-ttu-id="a4a47-108">합니다 **ColumnMapping** 의 속성을 **attr1** 열으로 설정 됩니다 **MappingType.Attribute**합니다.</span><span class="sxs-lookup"><span data-stu-id="a4a47-108">The **ColumnMapping** property of the **attr1** column will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="a4a47-109">합니다 **ColumnMapping** 의 속성을 **Element1_Text** 열으로 설정 됩니다 **MappingType.SimpleContent**합니다.</span><span class="sxs-lookup"><span data-stu-id="a4a47-109">The **ColumnMapping** property of the **Element1_Text** column will be set to **MappingType.SimpleContent**.</span></span>  
  
 <span data-ttu-id="a4a47-110">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="a4a47-110">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="a4a47-111">**테이블:** Element1</span><span class="sxs-lookup"><span data-stu-id="a4a47-111">**Table:** Element1</span></span>  
  
|<span data-ttu-id="a4a47-112">attr1</span><span class="sxs-lookup"><span data-stu-id="a4a47-112">attr1</span></span>|<span data-ttu-id="a4a47-113">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="a4a47-113">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="a4a47-114">value1</span><span class="sxs-lookup"><span data-stu-id="a4a47-114">value1</span></span>|<span data-ttu-id="a4a47-115">Text1</span><span class="sxs-lookup"><span data-stu-id="a4a47-115">Text1</span></span>|  
  
 <span data-ttu-id="a4a47-116">요소에 텍스트뿐만 아니라 텍스트가 포함된 자식 요소도 있는 경우에는 해당 요소에 포함된 텍스트를 저장할 열이 테이블에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4a47-116">If an element contains text, but also has child elements that contain text, a column will not be added to the table to store the text contained in the element.</span></span> <span data-ttu-id="a4a47-117">따라서 이 요소에 포함된 텍스트는 무시되지만 자식 요소에 있는 텍스트는 해당 테이블의 행에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4a47-117">The text contained in the element will be ignored, while the text in the child elements is included in a row in the table.</span></span> <span data-ttu-id="a4a47-118">예를 들어, 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="a4a47-118">For example, consider the following XML.</span></span>  
  
```xml  
<Element1>  
  Text1  
  <ChildElement1>Text2</ChildElement1>  
  Text3  
</Element1>  
```  
  
 <span data-ttu-id="a4a47-119">유추 과정 이라는 테이블이 생성 됩니다 **Element1** 라는 열이 하나인 **ChildElement1**합니다.</span><span class="sxs-lookup"><span data-stu-id="a4a47-119">The inference process will produce a table named **Element1** with one column named **ChildElement1**.</span></span> <span data-ttu-id="a4a47-120">에 대 한 텍스트를 **ChildElement1** 요소는 테이블의 행에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4a47-120">The text for the **ChildElement1** element will be included in a row in the table.</span></span> <span data-ttu-id="a4a47-121">다른 텍스트는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4a47-121">The other text will be ignored.</span></span> <span data-ttu-id="a4a47-122">합니다 **ColumnMapping** 의 속성을 **ChildElement1** 열으로 설정 됩니다 **MappingType.Element**합니다.</span><span class="sxs-lookup"><span data-stu-id="a4a47-122">The **ColumnMapping** property of the **ChildElement1** column will be set to **MappingType.Element**.</span></span>  
  
 <span data-ttu-id="a4a47-123">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="a4a47-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="a4a47-124">**테이블:** Element1</span><span class="sxs-lookup"><span data-stu-id="a4a47-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="a4a47-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="a4a47-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="a4a47-126">Text2</span><span class="sxs-lookup"><span data-stu-id="a4a47-126">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a4a47-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="a4a47-127">See also</span></span>

- [<span data-ttu-id="a4a47-128">XML에서 데이터 집합 관계형 구조 유추</span><span class="sxs-lookup"><span data-stu-id="a4a47-128">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="a4a47-129">XML에서 데이터 집합 로드</span><span class="sxs-lookup"><span data-stu-id="a4a47-129">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [<span data-ttu-id="a4a47-130">XML에서 데이터 집합 스키마 정보 로드</span><span class="sxs-lookup"><span data-stu-id="a4a47-130">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="a4a47-131">데이터 집합에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="a4a47-131">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [<span data-ttu-id="a4a47-132">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="a4a47-132">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="a4a47-133">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="a4a47-133">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
