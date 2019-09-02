---
title: 데이터 세트 스키마 유추 프로세스 요약
ms.date: 03/30/2017
ms.assetid: fd0891c8-d068-4e30-a76f-7c375f078bf7
ms.openlocfilehash: 5266d08212e5259bd5b242a70d61e29ad9008006
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203250"
---
# <a name="summary-of-the-dataset-schema-inference-process"></a><span data-ttu-id="48c49-102">데이터 세트 스키마 유추 프로세스 요약</span><span class="sxs-lookup"><span data-stu-id="48c49-102">Summary of the DataSet Schema Inference Process</span></span>
<span data-ttu-id="48c49-103">유추 과정에서는 우선 XML 문서에서 테이블로 유추될 요소를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="48c49-103">The inference process first determines, from the XML document, which elements will be inferred as tables.</span></span> <span data-ttu-id="48c49-104">그런 다음 남아 있는 XML에서 해당 테이블의 열을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="48c49-104">From the remaining XML, the inference process determines the columns for those tables.</span></span> <span data-ttu-id="48c49-105">중첩된 테이블인 경우에는 유추 과정에서 중첩된 <xref:System.Data.DataRelation> 및 <xref:System.Data.ForeignKeyConstraint> 개체를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="48c49-105">For nested tables, the inference process generates nested <xref:System.Data.DataRelation> and <xref:System.Data.ForeignKeyConstraint> objects.</span></span>  
  
 <span data-ttu-id="48c49-106">다음은 유추 규칙에 대해 간략히 요약한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="48c49-106">Following is a brief summary of inference rules:</span></span>  
  
- <span data-ttu-id="48c49-107">특성이 있는 요소는 테이블로 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="48c49-107">Elements that have attributes are inferred as tables.</span></span>  
  
- <span data-ttu-id="48c49-108">자식 요소가 있는 요소는 테이블로 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="48c49-108">Elements that have child elements are inferred as tables.</span></span>  
  
- <span data-ttu-id="48c49-109">반복되는 요소는 하나의 테이블로 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="48c49-109">Elements that repeat are inferred as a single table.</span></span>  
  
- <span data-ttu-id="48c49-110">문서 요소에 열로 유추되는 특성이나 자식 요소가 없으면 문서 요소 또는 루트 요소는 <xref:System.Data.DataSet>으로 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="48c49-110">If the document, or root, element has no attributes, and no child elements that would be inferred as columns, it is inferred as a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="48c49-111">그렇지 않으면 문서 요소는 테이블로 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="48c49-111">Otherwise, the document element is inferred as a table.</span></span>  
  
- <span data-ttu-id="48c49-112">특성은 열로 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="48c49-112">Attributes are inferred as columns.</span></span>  
  
- <span data-ttu-id="48c49-113">특성이나 자식 요소가 없거나 반복되지 않는 요소는 열로 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="48c49-113">Elements that have no attributes or child elements, and that do not repeat, are inferred as columns.</span></span>  
  
- <span data-ttu-id="48c49-114">테이블로 유추 되는 다른 요소 내에서 중첩 테이블로 유추 되는 요소의 경우 두 테이블 간에 중첩 된 **DataRelation** 이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48c49-114">For elements that are inferred as nested tables within other elements that are also inferred as tables, a nested **DataRelation** is created between the two tables.</span></span> <span data-ttu-id="48c49-115">**TableName_Id** 라는 새 기본 키 열이 두 테이블에 모두 추가 되 고 **DataRelation**에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48c49-115">A new, primary key column named **TableName_Id** is added to both tables and used by the **DataRelation**.</span></span> <span data-ttu-id="48c49-116">**TableName_Id** 열을 사용 하 여 두 테이블 간에 **ForeignKeyConstraint** 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48c49-116">A **ForeignKeyConstraint** is created between the two tables using the **TableName_Id** column.</span></span>  
  
- <span data-ttu-id="48c49-117">테이블로 유추 되 고 텍스트가 포함 되지만 자식 요소가 없는 요소의 경우 각 요소의 텍스트에 대해 **TableName_Text** 라는 새 열이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="48c49-117">For elements that are inferred as tables and that contain text but have no child elements, a new column named **TableName_Text** is created for the text of each of the elements.</span></span> <span data-ttu-id="48c49-118">테이블로 유추되는 요소에 텍스트와 자식 요소가 모두 있으면 해당 텍스트는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="48c49-118">If an element is inferred as a table and has text, but also has child elements, the text is ignored.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48c49-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="48c49-119">See also</span></span>

- [<span data-ttu-id="48c49-120">XML에서 데이터 세트 관계형 구조 유추</span><span class="sxs-lookup"><span data-stu-id="48c49-120">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="48c49-121">XML에서 데이터 세트 로드</span><span class="sxs-lookup"><span data-stu-id="48c49-121">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="48c49-122">XML에서 데이터 세트 스키마 정보 로드</span><span class="sxs-lookup"><span data-stu-id="48c49-122">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="48c49-123">데이터 집합에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="48c49-123">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="48c49-124">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="48c49-124">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="48c49-125">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="48c49-125">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
