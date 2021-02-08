---
description: '자세한 정보: 함수 (Entity SQL)'
title: 함수(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 0bb88992-37ed-4991-ace5-55be612a2c4d
ms.openlocfilehash: d61aafce03dc7b82b678f1eb107afb79c6c3ed2f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786318"
---
# <a name="function-entity-sql"></a><span data-ttu-id="e5288-103">함수(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e5288-103">FUNCTION (Entity SQL)</span></span>

<span data-ttu-id="e5288-104">Entity SQL 쿼리 명령의 범위에서 함수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e5288-104">Defines a function in the scope of an Entity SQL query command.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5288-105">구문</span><span class="sxs-lookup"><span data-stu-id="e5288-105">Syntax</span></span>  
  
```sql  
FUNCTION function-name  
( [ { parameter_name <type_definition>
        [ ,...n ]  
  ]  
) AS ( function_expression )
  
<type_definition>::=  
    { data_type | COLLECTION ( <type_definition> )
                | REF ( data_type )
                | ROW ( row_expression )
        }
```  
  
## <a name="arguments"></a><span data-ttu-id="e5288-106">인수</span><span class="sxs-lookup"><span data-stu-id="e5288-106">Arguments</span></span>  

 `function-name`  
 <span data-ttu-id="e5288-107">함수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e5288-107">Name of the function.</span></span>  
  
 `parameter-name`  
 <span data-ttu-id="e5288-108">함수에 있는 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e5288-108">Name of a parameter in the function.</span></span>  
  
 `function_expression`  
 <span data-ttu-id="e5288-109">함수인 유효한 Entity SQL 식입니다.</span><span class="sxs-lookup"><span data-stu-id="e5288-109">A valid Entity SQL expression that is the function.</span></span> <span data-ttu-id="e5288-110">함수의 명령은 함수에 전달된 `parameter_name` 매개 변수에 대해 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5288-110">The command in the function can act on `parameter_name` parameters passed to the function.</span></span>  
  
 `data_type`  
 <span data-ttu-id="e5288-111">지원되는 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e5288-111">Name of a supported type.</span></span>  
  
 <span data-ttu-id="e5288-112">컬렉션 (<type_definition `>` )</span><span class="sxs-lookup"><span data-stu-id="e5288-112">COLLECTION ( <type_definition`>` )</span></span>  
 <span data-ttu-id="e5288-113">지원되는 형식, 행 또는 참조 컬렉션을 반환하는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="e5288-113">An expression that returns a collection of supported types, rows, or references.</span></span>  
  
 <span data-ttu-id="e5288-114">REF **(** `data_type` **)**</span><span class="sxs-lookup"><span data-stu-id="e5288-114">REF **(**`data_type`**)**</span></span>  
 <span data-ttu-id="e5288-115">엔터티 형식에 대한 참조를 반환하는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="e5288-115">An expression that returns a reference to an entity type.</span></span>  
  
 <span data-ttu-id="e5288-116">ROW **(** `row_expression` **)**</span><span class="sxs-lookup"><span data-stu-id="e5288-116">ROW **(**`row_expression`**)**</span></span>  
 <span data-ttu-id="e5288-117">하나 이상의 값에서 구조적으로 형식화된 익명 레코드를 반환하는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="e5288-117">An expression that returns anonymous, structurally typed records from one or more values.</span></span> <span data-ttu-id="e5288-118">자세한 내용은 [ROW](row-entity-sql.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e5288-118">For more information, see [ROW](row-entity-sql.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5288-119">설명</span><span class="sxs-lookup"><span data-stu-id="e5288-119">Remarks</span></span>  

 <span data-ttu-id="e5288-120">함수 시그니처가 다르면 이름이 같은 여러 함수를 인라인으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5288-120">Multiple functions with the same name can be declared inline, as long as the function signatures are different.</span></span> <span data-ttu-id="e5288-121">자세한 내용은 [Function Overload Resolution](function-overload-resolution-entity-sql.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e5288-121">For more information, see [Function Overload Resolution](function-overload-resolution-entity-sql.md).</span></span>  
  
 <span data-ttu-id="e5288-122">인라인 함수는 Entity SQL 명령에서 정의된 이후에야 해당 명령에서 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5288-122">An inline function can be called in an Entity SQL command only after it has been defined in that command.</span></span> <span data-ttu-id="e5288-123">그러나 인라인 함수는 호출된 함수가 정의되기 이전 또는 이후에 다른 인라인 함수 내에서 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5288-123">However, an inline function can be called inside another inline function either before or after the called function has been defined.</span></span> <span data-ttu-id="e5288-124">다음 예제에서는 함수 B가 정의되기 전에 함수 A에서 함수 B를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="e5288-124">In the following example, function A calls function B before function B is defined:</span></span>  
  
 `Function A() as ('A calls B. ' + B())`  
  
 `Function B() as ('B was called.')`  
  
 `A()`  
  
 <span data-ttu-id="e5288-125">자세한 내용은 [방법: 사용자 정의 함수 호출](/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e5288-125">For more information, see [How to: Call a User-Defined Function](/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100)).</span></span>  
  
 <span data-ttu-id="e5288-126">함수는 모델 자체에서도 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5288-126">Functions can also be declared in the model itself.</span></span> <span data-ttu-id="e5288-127">모델에서 선언된 함수는 명령에서 인라인으로 선언된 함수와 동일한 방식으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5288-127">Functions declared in the model are executed in the same way as functions declared inline in the command.</span></span> <span data-ttu-id="e5288-128">자세한 내용은 [사용자 정의 함수](user-defined-functions-entity-sql.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e5288-128">For more information, see [User-Defined Functions](user-defined-functions-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5288-129">예제</span><span class="sxs-lookup"><span data-stu-id="e5288-129">Example</span></span>  

 <span data-ttu-id="e5288-130">다음 Entity SQL 명령에서는 정수 값을 사용하여 반환된 제품을 필터링하는 `Products` 함수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e5288-130">The following Entity SQL command defines a function `Products` that takes an integer value to filter the returned products.</span></span>  
  
 [!code-sql[DP EntityServices Concepts#FUNCTION1](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#function1)]  
  
## <a name="example"></a><span data-ttu-id="e5288-131">예제</span><span class="sxs-lookup"><span data-stu-id="e5288-131">Example</span></span>  

 <span data-ttu-id="e5288-132">다음 Entity SQL 명령에서는 문자열 컬렉션을 사용하여 반환된 연락처를 필터링하는 `StringReturnsCollection` 함수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e5288-132">The following Entity SQL command defines a function `StringReturnsCollection` that takes a collection of strings to filter the returned contacts.</span></span>  
  
 [!code-sql[DP EntityServices Concepts#FUNCTION2](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#function2)]  
  
## <a name="see-also"></a><span data-ttu-id="e5288-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e5288-133">See also</span></span>

- [<span data-ttu-id="e5288-134">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="e5288-134">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="e5288-135">Entity SQL 언어</span><span class="sxs-lookup"><span data-stu-id="e5288-135">Entity SQL Language</span></span>](entity-sql-language.md)
