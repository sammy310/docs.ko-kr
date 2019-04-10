---
title: ISOF(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5b2b0d34-d0a7-4bcd-baf2-58aa8456d00b
ms.openlocfilehash: 097d6e7d452ee62a2c8934d2c5fcfdddbeaffc73
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59195750"
---
# <a name="isof-entity-sql"></a><span data-ttu-id="6dcfe-102">ISOF(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="6dcfe-102">ISOF (Entity SQL)</span></span>
<span data-ttu-id="6dcfe-103">식의 형식이 지정된 형식 또는 그 하위 형식인지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6dcfe-103">Determines whether the type of an expression is of the specified type or one of its subtypes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6dcfe-104">구문</span><span class="sxs-lookup"><span data-stu-id="6dcfe-104">Syntax</span></span>  
  
```  
expression IS [ NOT ] OF ( [ ONLY ] type )  
```  
  
## <a name="arguments"></a><span data-ttu-id="6dcfe-105">인수</span><span class="sxs-lookup"><span data-stu-id="6dcfe-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="6dcfe-106">형식을 결정할 수 있는 모든 유효한 쿼리 식입니다.</span><span class="sxs-lookup"><span data-stu-id="6dcfe-106">Any valid query expression to determine the type of.</span></span>  
  
 <span data-ttu-id="6dcfe-107">NOT</span><span class="sxs-lookup"><span data-stu-id="6dcfe-107">NOT</span></span>  
 <span data-ttu-id="6dcfe-108">IS OF의 EDM.Boolean 결과를 부정합니다.</span><span class="sxs-lookup"><span data-stu-id="6dcfe-108">Negates the EDM.Boolean result of IS OF.</span></span>  
  
 <span data-ttu-id="6dcfe-109">ONLY</span><span class="sxs-lookup"><span data-stu-id="6dcfe-109">ONLY</span></span>  
 <span data-ttu-id="6dcfe-110">`true`이 `expression` 형식이며 그 하위 형식이 아닌 경우에만 IS OF가 `type`를 반환하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6dcfe-110">Specifies that IS OF returns `true` only if `expression` is of type `type` and not any of one its subtypes.</span></span>  
  
 `type`  
 <span data-ttu-id="6dcfe-111">`expression`을 테스트할 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6dcfe-111">The type to test `expression` against.</span></span> <span data-ttu-id="6dcfe-112">형식은 네임스페이스로 한정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6dcfe-112">The type must be namespace-qualified.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6dcfe-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="6dcfe-113">Return Value</span></span>  
 `true` <span data-ttu-id="6dcfe-114">하는 경우 `expression` 는 형식의 T T 이며 기본 형식 또는 파생된 형식의 `type`; 경우 null `expression` 이 고, 그렇지 않으면 런타임에 null `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="6dcfe-114">if `expression` is of type T and T is either a base type, or a derived type of `type`; null if `expression` is null at runtime; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6dcfe-115">설명</span><span class="sxs-lookup"><span data-stu-id="6dcfe-115">Remarks</span></span>  
 <span data-ttu-id="6dcfe-116">식을 `expression IS NOT OF (type)` 하 고 `expression IS NOT OF (ONLY type)` 하는 구문은 동일 `NOT (expression IS OF (type))` 및 `NOT (expression IS OF (ONLY type))`각각.</span><span class="sxs-lookup"><span data-stu-id="6dcfe-116">The expressions `expression IS NOT OF (type)` and `expression IS NOT OF (ONLY type)` are syntactically equivalent to `NOT (expression IS OF (type))` and `NOT (expression IS OF (ONLY type))`, respectively.</span></span>  
  
 <span data-ttu-id="6dcfe-117">다음 표에서는 일반 패턴 및 비교적 특수한 패턴에 대한 `IS OF` 연산자의 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6dcfe-117">The following table shows the behavior of `IS OF` operator over some typical- and corner patterns.</span></span> <span data-ttu-id="6dcfe-118">공급자 호출 이전에 모든 예외가 클라이언트 측에서 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="6dcfe-118">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="6dcfe-119">무늬</span><span class="sxs-lookup"><span data-stu-id="6dcfe-119">Pattern</span></span>|<span data-ttu-id="6dcfe-120">동작</span><span class="sxs-lookup"><span data-stu-id="6dcfe-120">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="6dcfe-121">null IS OF(EntityType)</span><span class="sxs-lookup"><span data-stu-id="6dcfe-121">null IS OF (EntityType)</span></span>|<span data-ttu-id="6dcfe-122">Throw</span><span class="sxs-lookup"><span data-stu-id="6dcfe-122">Throws</span></span>|  
|<span data-ttu-id="6dcfe-123">null IS OF(ComplexType)</span><span class="sxs-lookup"><span data-stu-id="6dcfe-123">null IS OF (ComplexType)</span></span>|<span data-ttu-id="6dcfe-124">Throw</span><span class="sxs-lookup"><span data-stu-id="6dcfe-124">Throws</span></span>|  
|<span data-ttu-id="6dcfe-125">null IS OF(RowType)</span><span class="sxs-lookup"><span data-stu-id="6dcfe-125">null IS OF (RowType)</span></span>|<span data-ttu-id="6dcfe-126">Throw</span><span class="sxs-lookup"><span data-stu-id="6dcfe-126">Throws</span></span>|  
|<span data-ttu-id="6dcfe-127">TREAT(null AS EntityType) IS OF(EntityType)</span><span class="sxs-lookup"><span data-stu-id="6dcfe-127">TREAT (null AS EntityType) IS OF (EntityType)</span></span>|<span data-ttu-id="6dcfe-128">DBNull 반환</span><span class="sxs-lookup"><span data-stu-id="6dcfe-128">Returns DBNull</span></span>|  
|<span data-ttu-id="6dcfe-129">TREAT(null AS ComplexType) IS OF(ComplexType)</span><span class="sxs-lookup"><span data-stu-id="6dcfe-129">TREAT (null AS ComplexType) IS OF (ComplexType)</span></span>|<span data-ttu-id="6dcfe-130">Throw</span><span class="sxs-lookup"><span data-stu-id="6dcfe-130">Throws</span></span>|  
|<span data-ttu-id="6dcfe-131">TREAT(null AS RowType) IS OF(RowType)</span><span class="sxs-lookup"><span data-stu-id="6dcfe-131">TREAT (null AS RowType) IS OF (RowType)</span></span>|<span data-ttu-id="6dcfe-132">Throw</span><span class="sxs-lookup"><span data-stu-id="6dcfe-132">Throws</span></span>|  
|<span data-ttu-id="6dcfe-133">EntityType IS OF(EntityType)</span><span class="sxs-lookup"><span data-stu-id="6dcfe-133">EntityType IS OF (EntityType)</span></span>|<span data-ttu-id="6dcfe-134">true/false 반환</span><span class="sxs-lookup"><span data-stu-id="6dcfe-134">Returns true/false</span></span>|  
|<span data-ttu-id="6dcfe-135">ComplexType IS OF(ComplexType)</span><span class="sxs-lookup"><span data-stu-id="6dcfe-135">ComplexType IS OF (ComplexType)</span></span>|<span data-ttu-id="6dcfe-136">Throw</span><span class="sxs-lookup"><span data-stu-id="6dcfe-136">Throws</span></span>|  
|<span data-ttu-id="6dcfe-137">RowType IS OF(RowType)</span><span class="sxs-lookup"><span data-stu-id="6dcfe-137">RowType IS OF (RowType)</span></span>|<span data-ttu-id="6dcfe-138">Throw</span><span class="sxs-lookup"><span data-stu-id="6dcfe-138">Throws</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6dcfe-139">예제</span><span class="sxs-lookup"><span data-stu-id="6dcfe-139">Example</span></span>  
 <span data-ttu-id="6dcfe-140">다음 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리에서는 IS OF 연산자를 사용하여 쿼리 식의 형식을 결정한 다음 TREAT 연산자를 사용하여 Course 형식의 개체를 OnsiteCourse 형식의 개체 컬렉션으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="6dcfe-140">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the IS OF operator to determine the type of a query expression, and then uses the TREAT operator to convert an object of the type Course to a collection of objects of the type OnsiteCourse.</span></span> <span data-ttu-id="6dcfe-141">쿼리는 [School 모델](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100))을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="6dcfe-141">The query is based on the [School Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#TREAT_ISOF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#treat_isof)]  
  
## <a name="see-also"></a><span data-ttu-id="6dcfe-142">참고자료</span><span class="sxs-lookup"><span data-stu-id="6dcfe-142">See also</span></span>

- [<span data-ttu-id="6dcfe-143">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="6dcfe-143">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
