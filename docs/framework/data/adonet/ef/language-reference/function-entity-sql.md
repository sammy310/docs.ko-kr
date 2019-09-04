---
title: 함수(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 0bb88992-37ed-4991-ace5-55be612a2c4d
ms.openlocfilehash: ae8da3985f11a2e9f52852876a21f50a412e3b27
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250933"
---
# <a name="function-entity-sql"></a><span data-ttu-id="cce19-102">함수(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="cce19-102">FUNCTION (Entity SQL)</span></span>
<span data-ttu-id="cce19-103">Entity SQL 쿼리 명령의 범위에서 함수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="cce19-103">Defines a function in the scope of an Entity SQL query command.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cce19-104">구문</span><span class="sxs-lookup"><span data-stu-id="cce19-104">Syntax</span></span>  
  
```  
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
  
## <a name="arguments"></a><span data-ttu-id="cce19-105">인수</span><span class="sxs-lookup"><span data-stu-id="cce19-105">Arguments</span></span>  
 `function-name`  
 <span data-ttu-id="cce19-106">함수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cce19-106">Name of the function.</span></span>  
  
 `parameter-name`  
 <span data-ttu-id="cce19-107">함수에 있는 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cce19-107">Name of a parameter in the function.</span></span>  
  
 `function_expression`  
 <span data-ttu-id="cce19-108">함수인 유효한 Entity SQL 식입니다.</span><span class="sxs-lookup"><span data-stu-id="cce19-108">A valid Entity SQL expression that is the function.</span></span> <span data-ttu-id="cce19-109">함수의 명령은 함수에 전달된 `parameter_name` 매개 변수에 대해 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cce19-109">The command in the function can act on `parameter_name` parameters passed to the function.</span></span>  
  
 `data_type`  
 <span data-ttu-id="cce19-110">지원되는 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cce19-110">Name of a supported type.</span></span>  
  
 <span data-ttu-id="cce19-111">컬렉션 (< type_definition`>` )</span><span class="sxs-lookup"><span data-stu-id="cce19-111">COLLECTION ( <type_definition`>` )</span></span>  
 <span data-ttu-id="cce19-112">지원되는 형식, 행 또는 참조 컬렉션을 반환하는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="cce19-112">An expression that returns a collection of supported types, rows, or references.</span></span>  
  
 <span data-ttu-id="cce19-113">REF **(** `data_type` **)**</span><span class="sxs-lookup"><span data-stu-id="cce19-113">REF **(**`data_type`**)**</span></span>  
 <span data-ttu-id="cce19-114">엔터티 형식에 대한 참조를 반환하는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="cce19-114">An expression that returns a reference to an entity type.</span></span>  
  
 <span data-ttu-id="cce19-115">ROW **(** `row_expression` **)**</span><span class="sxs-lookup"><span data-stu-id="cce19-115">ROW **(**`row_expression`**)**</span></span>  
 <span data-ttu-id="cce19-116">하나 이상의 값에서 구조적으로 형식화된 익명 레코드를 반환하는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="cce19-116">An expression that returns anonymous, structurally typed records from one or more values.</span></span> <span data-ttu-id="cce19-117">자세한 내용은 [ROW](row-entity-sql.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cce19-117">For more information, see [ROW](row-entity-sql.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cce19-118">설명</span><span class="sxs-lookup"><span data-stu-id="cce19-118">Remarks</span></span>  
 <span data-ttu-id="cce19-119">함수 시그니처가 다르면 이름이 같은 여러 함수를 인라인으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cce19-119">Multiple functions with the same name can be declared inline, as long as the function signatures are different.</span></span> <span data-ttu-id="cce19-120">자세한 내용은 [Function Overload Resolution](function-overload-resolution-entity-sql.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cce19-120">For more information, see [Function Overload Resolution](function-overload-resolution-entity-sql.md).</span></span>  
  
 <span data-ttu-id="cce19-121">인라인 함수는 Entity SQL 명령에서 정의된 이후에야 해당 명령에서 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cce19-121">An inline function can be called in an Entity SQL command only after it has been defined in that command.</span></span> <span data-ttu-id="cce19-122">그러나 인라인 함수는 호출된 함수가 정의되기 이전 또는 이후에 다른 인라인 함수 내에서 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cce19-122">However, an inline function can be called inside another inline function either before or after the called function has been defined.</span></span> <span data-ttu-id="cce19-123">다음 예제에서는 함수 B가 정의되기 전에 함수 A에서 함수 B를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="cce19-123">In the following example, function A calls function B before function B is defined:</span></span>  
  
 `Function A() as ('A calls B. ' + B())`  
  
 `Function B() as ('B was called.')`  
  
 `A()`  
  
 <span data-ttu-id="cce19-124">자세한 내용은 [방법: 사용자 정의 함수](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="cce19-124">For more information, see [How to: Call a User-Defined Function](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100)).</span></span>  
  
 <span data-ttu-id="cce19-125">함수는 모델 자체에서도 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cce19-125">Functions can also be declared in the model itself.</span></span> <span data-ttu-id="cce19-126">모델에서 선언된 함수는 명령에서 인라인으로 선언된 함수와 동일한 방식으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="cce19-126">Functions declared in the model are executed in the same way as functions declared inline in the command.</span></span> <span data-ttu-id="cce19-127">자세한 내용은 [사용자 정의 함수](user-defined-functions-entity-sql.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cce19-127">For more information, see [User-Defined Functions](user-defined-functions-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cce19-128">예제</span><span class="sxs-lookup"><span data-stu-id="cce19-128">Example</span></span>  
 <span data-ttu-id="cce19-129">다음 Entity SQL 명령에서는 정수 값을 사용하여 반환된 제품을 필터링하는 `Products` 함수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="cce19-129">The following Entity SQL command defines a function `Products` that takes an integer value to filter the returned products.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#FUNCTION1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#function1)]  
  
## <a name="example"></a><span data-ttu-id="cce19-130">예제</span><span class="sxs-lookup"><span data-stu-id="cce19-130">Example</span></span>  
 <span data-ttu-id="cce19-131">다음 Entity SQL 명령에서는 문자열 컬렉션을 사용하여 반환된 연락처를 필터링하는 `StringReturnsCollection` 함수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="cce19-131">The following Entity SQL command defines a function `StringReturnsCollection` that takes a collection of strings to filter the returned contacts.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#FUNCTION2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#function2)]  
  
## <a name="see-also"></a><span data-ttu-id="cce19-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="cce19-132">See also</span></span>

- [<span data-ttu-id="cce19-133">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="cce19-133">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="cce19-134">Entity SQL 언어</span><span class="sxs-lookup"><span data-stu-id="cce19-134">Entity SQL Language</span></span>](entity-sql-language.md)
