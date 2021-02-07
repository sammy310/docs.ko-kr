---
description: '자세한 정보: 명명 된 형식 생성자 (Entity SQL)'
title: 명명된 형식 생성자(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 549dea04-d93d-4c87-a292-f81b1598dbfd
ms.openlocfilehash: e5ec811f814898661cf8de28de1fb8406647332d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696544"
---
# <a name="named-type-constructor-entity-sql"></a><span data-ttu-id="b6214-103">명명된 형식 생성자(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b6214-103">Named Type Constructor (Entity SQL)</span></span>

<span data-ttu-id="b6214-104">엔터티 형식이나 복합 형식과 같은 개념적 모델 명목 형식의 인스턴스를 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6214-104">Used to create instances of conceptual model nominal types such as Entity or Complex types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6214-105">구문</span><span class="sxs-lookup"><span data-stu-id="b6214-105">Syntax</span></span>  
  
```sql  
[{identifier. }] identifier( [expression [{, expression }]] )  
```  
  
## <a name="arguments"></a><span data-ttu-id="b6214-106">인수</span><span class="sxs-lookup"><span data-stu-id="b6214-106">Arguments</span></span>  

 `identifier`  
 <span data-ttu-id="b6214-107">단순 식별자 또는 따옴표 붙은 식별자인 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b6214-107">Value that is a simple or quoted identifier.</span></span> <span data-ttu-id="b6214-108">자세한 내용은 [식별자](identifiers-entity-sql.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b6214-108">For more information see, [Identifiers](identifiers-entity-sql.md)</span></span>  
  
 `expression`  
 <span data-ttu-id="b6214-109">형식의 특성으로서, 형식 선언에 나타나는 것과 동일한 순서일 것으로 가정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6214-109">Attributes of the type that are assumed to be in the same order as they appear in the declaration of the type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b6214-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="b6214-110">Return Value</span></span>  

 <span data-ttu-id="b6214-111">명명된 복합 형식 및 엔터티 형식의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="b6214-111">Instances of named complex types and entity types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6214-112">설명</span><span class="sxs-lookup"><span data-stu-id="b6214-112">Remarks</span></span>  

 <span data-ttu-id="b6214-113">다음 예제에서는 명목 형식 및 복합 형식을 생성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b6214-113">The following examples show how to construct nominal and complex types:</span></span>  
  
 <span data-ttu-id="b6214-114">다음 식은 `Person` 형식의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b6214-114">The expression below creates an instance of a `Person` type:</span></span>  
  
 `Person("abc", 12)`  
  
 <span data-ttu-id="b6214-115">다음 식은 복합 형식의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b6214-115">The expression below creates an instance of a complex type:</span></span>  
  
 `MyModel.ZipCode(‘98118’, ‘4567’)`  
  
 <span data-ttu-id="b6214-116">다음 식은 중첩된 복합 형식의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b6214-116">The expression below creates an instance of a nested complex type:</span></span>  
  
 `MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567'))`  
  
 <span data-ttu-id="b6214-117">다음 식은 중첩된 복합 형식을 가진 엔터티의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b6214-117">The expression below creates an instance of an entity with a nested complex type:</span></span>  
  
 `MyModel.Person("Bill", MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567')))`  
  
 <span data-ttu-id="b6214-118">다음 예제에서는 복합 형식의 속성을 null로 초기화하는 방법을 보여 줍니다.`MyModel.ZipCode(‘98118’, null)`</span><span class="sxs-lookup"><span data-stu-id="b6214-118">The following example shows how to initialize a property of a complex type to null:`MyModel.ZipCode(‘98118’, null)`</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6214-119">예제</span><span class="sxs-lookup"><span data-stu-id="b6214-119">Example</span></span>  

 <span data-ttu-id="b6214-120">다음 Entity SQL 쿼리에서는 명명된 형식 생성자를 사용하여 개념적 모델 형식의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b6214-120">The following Entity SQL query uses the named type constructor to create an instance of a conceptual model type.</span></span> <span data-ttu-id="b6214-121">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6214-121">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="b6214-122">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="b6214-122">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="b6214-123">[How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="b6214-123">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="b6214-124">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="b6214-124">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#NAMED_TYPE_CONSTRUCTOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#named_type_constructor)]  
  
## <a name="see-also"></a><span data-ttu-id="b6214-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b6214-125">See also</span></span>

- [<span data-ttu-id="b6214-126">형식 생성</span><span class="sxs-lookup"><span data-stu-id="b6214-126">Constructing Types</span></span>](constructing-types-entity-sql.md)
- [<span data-ttu-id="b6214-127">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="b6214-127">Entity SQL Reference</span></span>](entity-sql-reference.md)
