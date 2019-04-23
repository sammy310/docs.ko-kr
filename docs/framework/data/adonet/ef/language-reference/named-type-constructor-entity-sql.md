---
title: 명명된 형식 생성자(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 549dea04-d93d-4c87-a292-f81b1598dbfd
ms.openlocfilehash: f95f0dcb92068675b2efff0af7e97b349976bf42
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59329468"
---
# <a name="named-type-constructor-entity-sql"></a><span data-ttu-id="3c126-102">명명된 형식 생성자(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="3c126-102">Named Type Constructor (Entity SQL)</span></span>
<span data-ttu-id="3c126-103">엔터티 형식이나 복합 형식과 같은 개념적 모델 명목 형식의 인스턴스를 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c126-103">Used to create instances of conceptual model nominal types such as Entity or Complex types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c126-104">구문</span><span class="sxs-lookup"><span data-stu-id="3c126-104">Syntax</span></span>  
  
```  
[{identifier. }] identifier( [expression [{, expression }]] )  
```  
  
## <a name="arguments"></a><span data-ttu-id="3c126-105">인수</span><span class="sxs-lookup"><span data-stu-id="3c126-105">Arguments</span></span>  
 `identifier`  
 <span data-ttu-id="3c126-106">단순 식별자 또는 따옴표 붙은 식별자인 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3c126-106">Value that is a simple or quoted identifier.</span></span> <span data-ttu-id="3c126-107">자세한 내용은 [식별자](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)</span><span class="sxs-lookup"><span data-stu-id="3c126-107">For more information see, [Identifiers](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)</span></span>  
  
 `expression`  
 <span data-ttu-id="3c126-108">형식의 특성으로서, 형식 선언에 나타나는 것과 동일한 순서일 것으로 가정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c126-108">Attributes of the type that are assumed to be in the same order as they appear in the declaration of the type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c126-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="3c126-109">Return Value</span></span>  
 <span data-ttu-id="3c126-110">명명된 복합 형식 및 엔터티 형식의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="3c126-110">Instances of named complex types and entity types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c126-111">설명</span><span class="sxs-lookup"><span data-stu-id="3c126-111">Remarks</span></span>  
 <span data-ttu-id="3c126-112">다음 예제에서는 명목 형식 및 복합 형식을 생성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3c126-112">The following examples show how to construct nominal and complex types:</span></span>  
  
 <span data-ttu-id="3c126-113">다음 식은 `Person` 형식의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3c126-113">The expression below creates an instance of a `Person` type:</span></span>  
  
 `Person("abc", 12)`  
  
 <span data-ttu-id="3c126-114">다음 식은 복합 형식의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3c126-114">The expression below creates an instance of a complex type:</span></span>  
  
 `MyModel.ZipCode(‘98118’, ‘4567’)`  
  
 <span data-ttu-id="3c126-115">다음 식은 중첩된 복합 형식의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3c126-115">The expression below creates an instance of a nested complex type:</span></span>  
  
 `MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567'))`  
  
 <span data-ttu-id="3c126-116">다음 식은 중첩된 복합 형식을 가진 엔터티의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3c126-116">The expression below creates an instance of an entity with a nested complex type:</span></span>  
  
 `MyModel.Person("Bill", MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567')))`  
  
 <span data-ttu-id="3c126-117">다음 예제에서는 복합 형식의 속성을 null로 초기화하는 방법을 보여 줍니다.`MyModel.ZipCode(‘98118’, null)`</span><span class="sxs-lookup"><span data-stu-id="3c126-117">The following example shows how to initialize a property of a complex type to null:`MyModel.ZipCode(‘98118’, null)`</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c126-118">예제</span><span class="sxs-lookup"><span data-stu-id="3c126-118">Example</span></span>  
 <span data-ttu-id="3c126-119">다음 Entity SQL 쿼리에서는 명명된 형식 생성자를 사용하여 개념적 모델 형식의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3c126-119">The following Entity SQL query uses the named type constructor to create an instance of a conceptual model type.</span></span> <span data-ttu-id="3c126-120">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c126-120">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="3c126-121">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="3c126-121">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="3c126-122">절차에 따라 [방법: StructuralType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3c126-122">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="3c126-123">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="3c126-123">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NAMED_TYPE_CONSTRUCTOR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#named_type_constructor)]  
  
## <a name="see-also"></a><span data-ttu-id="3c126-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="3c126-124">See also</span></span>

- [<span data-ttu-id="3c126-125">형식 생성</span><span class="sxs-lookup"><span data-stu-id="3c126-125">Constructing Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)
- [<span data-ttu-id="3c126-126">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="3c126-126">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
