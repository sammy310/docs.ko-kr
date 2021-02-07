---
description: '자세한 정보: TREAT (Entity SQL)'
title: TREAT(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5b77f156-55de-4cb4-8154-87f707d4c635
ms.openlocfilehash: 3f014cac631d246b35d145cdb80c9aa6ac401524
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99673429"
---
# <a name="treat-entity-sql"></a><span data-ttu-id="1d62e-103">TREAT(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="1d62e-103">TREAT (Entity SQL)</span></span>

<span data-ttu-id="1d62e-104">특정 기본 형식의 개체를 지정된 파생 형식의 개체로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="1d62e-104">Treats an object of a particular base type as an object of the specified derived type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d62e-105">구문</span><span class="sxs-lookup"><span data-stu-id="1d62e-105">Syntax</span></span>  
  
```sql  
TREAT ( expression as type)  
```  
  
## <a name="arguments"></a><span data-ttu-id="1d62e-106">인수</span><span class="sxs-lookup"><span data-stu-id="1d62e-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="1d62e-107">엔터티를 반환하는 모든 유효한 쿼리 식입니다.</span><span class="sxs-lookup"><span data-stu-id="1d62e-107">Any valid query expression that returns an entity.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1d62e-108">지정된 식의 형식이 지정된 데이터 형식의 하위 형식이어야 하거나, 데이터 형식이 식 형식의 하위 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d62e-108">The type of the specified expression must be a subtype of the specified data type, or the data type must be a subtype of the type of expression.</span></span>  
  
 `type`  
 <span data-ttu-id="1d62e-109">엔터티 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1d62e-109">An entity type.</span></span> <span data-ttu-id="1d62e-110">형식은 네임스페이스로 한정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d62e-110">The type must be qualified by a namespace.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1d62e-111">지정된 식이 지정된 데이터 형식의 하위 형식이어야 하거나, 데이터 형식이 식의 하위 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d62e-111">The specified expression must be a subtype of the specified data type, or the data type must be a subtype of the expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1d62e-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="1d62e-112">Return Value</span></span>  

 <span data-ttu-id="1d62e-113">지정된 데이터 형식의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1d62e-113">A value of the specified data type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d62e-114">설명</span><span class="sxs-lookup"><span data-stu-id="1d62e-114">Remarks</span></span>  

 <span data-ttu-id="1d62e-115">TREAT는 관련 클래스 간에 업캐스팅을 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d62e-115">TREAT is used to perform upcasting between related classes.</span></span> <span data-ttu-id="1d62e-116">예를 들어, `Employee` 가 `Person` 에서 파생되고 p가 `Person`형식인 경우 `TREAT(p AS NamespaceName.Employee)` 는 일반 `Person` 인스턴스를 `Employee`로 업캐스팅합니다. 다시 말해서, p를 `Employee`로 취급할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d62e-116">For example, if `Employee` derives from `Person` and p is of type `Person`, `TREAT(p AS NamespaceName.Employee)` upcasts a generic `Person` instance to `Employee`; that is, it allows you to treat p as `Employee`.</span></span>  
  
 <span data-ttu-id="1d62e-117">TREAT는 다음과 같이 쿼리할 수 있는 상속 시나리오에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d62e-117">TREAT is used in inheritance scenarios where you can do a query like the following:</span></span>  
  
```sql  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)
```  
  
 <span data-ttu-id="1d62e-118">이 쿼리는 `Person` 엔터티를 `Employee` 형식으로 업캐스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="1d62e-118">This query upcasts `Person` entities to the `Employee` type.</span></span> <span data-ttu-id="1d62e-119">p의 값이 실제로 `Employee`형식이 아닌 경우 식의 값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="1d62e-119">If the value of p is not actually of type `Employee`, the expression yields the value `null`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1d62e-120">지정 된 식이 `Employee` 지정 된 데이터 형식의 하위 형식 이어야 `Person` 하거나, 데이터 형식이 식의 하위 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d62e-120">The specified expression `Employee` must be a subtype of the specified data type `Person`, or the data type must be a subtype of the expression.</span></span> <span data-ttu-id="1d62e-121">그렇지 않으면 식에서 컴파일 시간 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="1d62e-121">Otherwise, the expression will result in a compile-time error.</span></span>  
  
 <span data-ttu-id="1d62e-122">다음 표에서는 일반 패턴 및 비교적 특수한 패턴에 대한 TREAT의 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1d62e-122">The following table shows the behavior of treat over some typical patterns and some less common patterns.</span></span> <span data-ttu-id="1d62e-123">공급자 호출 이전에 모든 예외가 클라이언트 측에서 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d62e-123">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="1d62e-124">무늬</span><span class="sxs-lookup"><span data-stu-id="1d62e-124">Pattern</span></span>|<span data-ttu-id="1d62e-125">동작</span><span class="sxs-lookup"><span data-stu-id="1d62e-125">Behavior</span></span>|  
|-------------|--------------|  
|`TREAT (null AS EntityType)`|<span data-ttu-id="1d62e-126">`DbNull`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1d62e-126">Returns `DbNull`.</span></span>|  
|`TREAT (null AS ComplexType)`|<span data-ttu-id="1d62e-127">예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="1d62e-127">Throws an exception.</span></span>|  
|`TREAT (null AS RowType)`|<span data-ttu-id="1d62e-128">예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="1d62e-128">Throws an exception/</span></span>|  
|`TREAT (EntityType AS EntityType)`|<span data-ttu-id="1d62e-129">`EntityType` 또는 `null`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1d62e-129">Returns `EntityType` or `null`.</span></span>|  
|`TREAT (ComplexType AS ComplexType)`|<span data-ttu-id="1d62e-130">예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="1d62e-130">Throws an exception.</span></span>|  
|`TREAT (RowType AS RowType)`|<span data-ttu-id="1d62e-131">예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="1d62e-131">Throws an exception.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1d62e-132">예제</span><span class="sxs-lookup"><span data-stu-id="1d62e-132">Example</span></span>  

 <span data-ttu-id="1d62e-133">다음 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리에서는 TREAT 연산자를 사용하여 Course 형식의 개체를 OnsiteCourse 형식의 개체 컬렉션으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="1d62e-133">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the TREAT operator to convert an object of the type Course to a collection of objects of the type OnsiteCourse.</span></span> <span data-ttu-id="1d62e-134">쿼리는 [School 모델](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100))을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d62e-134">The query is based on the [School Model](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span></span>  
  
 [!code-sql[DP EntityServices Concepts#TREAT_ISOF](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#treat_isof)]  
  
## <a name="see-also"></a><span data-ttu-id="1d62e-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d62e-135">See also</span></span>

- [<span data-ttu-id="1d62e-136">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="1d62e-136">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="1d62e-137">nullable 구조적 형식</span><span class="sxs-lookup"><span data-stu-id="1d62e-137">Nullable Structured Types</span></span>](nullable-structured-types-entity-sql.md)
