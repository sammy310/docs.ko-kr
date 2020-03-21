---
title: 형식 시스템(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 818a505b-a196-41dd-aaac-2ccd5f7a2f1a
ms.openlocfilehash: b8b721aff5b7886fdb897ecaa3dcc163ec94ae79
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149833"
---
# <a name="type-system-entity-sql"></a><span data-ttu-id="d4b1a-102">형식 시스템(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d4b1a-102">Type System (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="d4b1a-103">다음과 같은 여러 가지 유형을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d4b1a-103">supports a number of types:</span></span>  
  
- <span data-ttu-id="d4b1a-104">기본(단순) 형식 - `Int32` 및 `String.`</span><span class="sxs-lookup"><span data-stu-id="d4b1a-104">Primitive (simple) types such as `Int32` and `String.`</span></span>  
  
- <span data-ttu-id="d4b1a-105">명목 형식 - 스키마에서 정의됨. <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.ComplexType> 및 <xref:System.Data.Metadata.Edm.RelationshipType></span><span class="sxs-lookup"><span data-stu-id="d4b1a-105">Nominal types that are defined in the schema, such as <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.ComplexType>, and <xref:System.Data.Metadata.Edm.RelationshipType>.</span></span>  
  
- <span data-ttu-id="d4b1a-106">익명 형식 - 스키마에서 명시적으로 정의되지 않음. <xref:System.Data.Metadata.Edm.CollectionType>, <xref:System.Data.Metadata.Edm.RowType> 및 <xref:System.Data.Metadata.Edm.RefType></span><span class="sxs-lookup"><span data-stu-id="d4b1a-106">Anonymous types that are not defined in the schema explicitly: <xref:System.Data.Metadata.Edm.CollectionType>, <xref:System.Data.Metadata.Edm.RowType>, and <xref:System.Data.Metadata.Edm.RefType>.</span></span>  
  
 <span data-ttu-id="d4b1a-107">이 섹션에서는 스키마에 명시적으로 정의되지 않았지만 Entity SQL에서 지원하는 익명 형식에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d4b1a-107">This section discusses the anonymous types that are not defined in the schema explicitly but are supported by Entity SQL.</span></span> <span data-ttu-id="d4b1a-108">기본 및 공칭 형식에 대한 자세한 내용은 [CSDL(개념식 모델 유형)을](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d4b1a-108">For information on primitive and nominal types, see [Conceptual Model Types (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl).</span></span>  
  
## <a name="rows"></a><span data-ttu-id="d4b1a-109">행</span><span class="sxs-lookup"><span data-stu-id="d4b1a-109">Rows</span></span>  
 <span data-ttu-id="d4b1a-110">행의 구조는 행이 구성된 형식화된 멤버 및 명명된 멤버의 시퀀스에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="d4b1a-110">The structure of a row depends on the sequence of typed and named members that the row consists of.</span></span> <span data-ttu-id="d4b1a-111">행 형식은 ID를 갖지 않으며 상속받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d4b1a-111">A row type has no identity and cannot be inherited from.</span></span> <span data-ttu-id="d4b1a-112">멤버가 각각 동일한 경우 같은 행 형식의 인스턴스는 서로 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="d4b1a-112">Instances of the same row type are equivalent if the members are respectively equivalent.</span></span> <span data-ttu-id="d4b1a-113">행은 구조가 동일한 것을 제외한 어떠한 동작도 갖지 않으며 공용 언어 런타임에 해당하는 항목이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d4b1a-113">Rows have no behavior beyond their structural equivalence and have no equivalent in the common language runtime.</span></span> <span data-ttu-id="d4b1a-114">쿼리를 실행하면 행 또는 행 컬렉션이 포함된 구조가 생성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4b1a-114">Queries can result in structures that contain rows or collections of rows.</span></span> <span data-ttu-id="d4b1a-115">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리와 호스트 언어 간의 API 바인딩은 결과를 생성하는 쿼리에서 행이 구현되는 방법을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d4b1a-115">The API binding between the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries and the host language defines how rows are realized in the query that produced the result.</span></span> <span data-ttu-id="d4b1a-116">행 인스턴스를 생성하는 방법에 대한 자세한 내용은 [유형 생성](constructing-types-entity-sql.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d4b1a-116">For information on how to construct a row instance, see [Constructing Types](constructing-types-entity-sql.md).</span></span>  
  
## <a name="collections"></a><span data-ttu-id="d4b1a-117">컬렉션</span><span class="sxs-lookup"><span data-stu-id="d4b1a-117">Collections</span></span>  
 <span data-ttu-id="d4b1a-118">컬렉션 형식은 다른 개체의 0개 이상 인스턴스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d4b1a-118">Collection types represent zero or more instances of other objects.</span></span> <span data-ttu-id="d4b1a-119">컬렉션을 생성하는 방법에 대한 자세한 내용은 [생성 형식을](constructing-types-entity-sql.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d4b1a-119">For information on how to construct collection, see [Constructing Types](constructing-types-entity-sql.md).</span></span>  
  
## <a name="references"></a><span data-ttu-id="d4b1a-120">참조</span><span class="sxs-lookup"><span data-stu-id="d4b1a-120">References</span></span>  
 <span data-ttu-id="d4b1a-121">참조는 특정 엔터티 집합 내의 특정 엔터티를 가리키는 논리 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d4b1a-121">A reference is a logical pointer to a specific entity in a specific entity set.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="d4b1a-122">에서는 참조를 통한 생성, 해체 및 탐색에 사용되는 다음 연산자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d4b1a-122">supports the following operators to construct, deconstruct, and navigate through references:</span></span>  
  
- [<span data-ttu-id="d4b1a-123">Ref</span><span class="sxs-lookup"><span data-stu-id="d4b1a-123">REF</span></span>](ref-entity-sql.md)  
  
- [<span data-ttu-id="d4b1a-124">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="d4b1a-124">CREATEREF</span></span>](createref-entity-sql.md)  
  
- [<span data-ttu-id="d4b1a-125">키</span><span class="sxs-lookup"><span data-stu-id="d4b1a-125">KEY</span></span>](key-entity-sql.md)  
  
- [<span data-ttu-id="d4b1a-126">DEREF</span><span class="sxs-lookup"><span data-stu-id="d4b1a-126">DEREF</span></span>](deref-entity-sql.md)  
  
 <span data-ttu-id="d4b1a-127">멤버 액세스(dot) 연산자(`.`)를 사용하여 참조를 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4b1a-127">You can navigate through a reference by using the member access (dot) operator(`.`).</span></span> <span data-ttu-id="d4b1a-128">다음 조각에서는 r(참조) 속성을 탐색하여 Id 속성(Order)을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="d4b1a-128">The following snippet extracts the Id property (of Order) by navigating through the r (reference) property.</span></span>  
  
```sql  
select o2.r.Id
from (select ref(o) as r from LOB.Orders as o) as o2
```  
  
 <span data-ttu-id="d4b1a-129">참조 값이 null이거나 참조 대상이 존재하지 않는 경우 결과는 null입니다.</span><span class="sxs-lookup"><span data-stu-id="d4b1a-129">If the reference value is null, or if the target of the reference does not exist, the result is null.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4b1a-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d4b1a-130">See also</span></span>

- [<span data-ttu-id="d4b1a-131">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="d4b1a-131">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="d4b1a-132">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="d4b1a-132">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="d4b1a-133">CAST</span><span class="sxs-lookup"><span data-stu-id="d4b1a-133">CAST</span></span>](cast-entity-sql.md)
- [<span data-ttu-id="d4b1a-134">CSDL, SSDL 및 MSL 사양</span><span class="sxs-lookup"><span data-stu-id="d4b1a-134">CSDL, SSDL, and MSL Specifications</span></span>](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
