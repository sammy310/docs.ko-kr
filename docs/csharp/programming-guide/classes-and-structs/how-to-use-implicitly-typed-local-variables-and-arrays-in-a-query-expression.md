---
title: 쿼리 식에서 암시적으로 형식화된 지역 변수 및 배열을 사용하는 방법 - C# 프로그래밍 가이드
description: C#에서 암시적으로 형식화된 지역 변수를 사용하여 컴파일러에서 지역 변수의 형식을 확인하도록 할 수 있습니다. 반드시 익명 형식을 저장하기 위해 사용해야 합니다.
ms.date: 07/20/2015
helpviewer_keywords:
- implicitly-typed local variables [C#], how to use
ms.topic: how-to
ms.custom: contperf-fy21q2
ms.assetid: 6b7354d2-af79-427a-b6a8-f74eb8fd0b91
ms.openlocfilehash: bd68c913c6f0d410d97973fb28789218f88903b5
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/15/2020
ms.locfileid: "97512387"
---
# <a name="how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression-c-programming-guide"></a><span data-ttu-id="58b63-104">쿼리 식에서 암시적으로 형식화된 지역 변수 및 배열을 사용하는 방법(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="58b63-104">How to use implicitly typed local variables and arrays in a query expression (C# Programming Guide)</span></span>

<span data-ttu-id="58b63-105">컴파일러에서 지역 변수의 형식을 확인하려는 경우 항상 암시적으로 형식화된 지역 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58b63-105">You can use implicitly typed local variables whenever you want the compiler to determine the type of a local variable.</span></span> <span data-ttu-id="58b63-106">쿼리 식에 자주 사용되는 무명 형식을 저장하려면 암시적으로 형식화된 지역 변수를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58b63-106">You must use implicitly typed local variables to store anonymous types, which are often used in query expressions.</span></span> <span data-ttu-id="58b63-107">다음 예제에서는 쿼리에서 암시적으로 형식화된 지역 변수의 선택적 및 필수 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58b63-107">The following examples illustrate both optional and required uses of implicitly typed local variables in queries.</span></span>  
  
 <span data-ttu-id="58b63-108">암시적으로 형식화된 지역 변수는 [var](../../language-reference/keywords/var.md) 상황별 키워드를 사용하여 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="58b63-108">Implicitly typed local variables are declared by using the [var](../../language-reference/keywords/var.md) contextual keyword.</span></span> <span data-ttu-id="58b63-109">자세한 내용은 [암시적으로 형식화된 지역 변수](./implicitly-typed-local-variables.md) 및 [암시적으로 형식화된 배열](../arrays/implicitly-typed-arrays.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="58b63-109">For more information, see [Implicitly Typed Local Variables](./implicitly-typed-local-variables.md) and [Implicitly Typed Arrays](../arrays/implicitly-typed-arrays.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="58b63-110">예제</span><span class="sxs-lookup"><span data-stu-id="58b63-110">Example</span></span>  

 <span data-ttu-id="58b63-111">다음 예제에서는 `var` 키워드가 필요한 일반적인 시나리오로, 무명 형식의 시퀀스를 생성하는 쿼리 식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58b63-111">The following example shows a common scenario in which the `var` keyword is required: a query expression that produces a sequence of anonymous types.</span></span> <span data-ttu-id="58b63-112">이 시나리오에서는 무명 형식의 형식 이름에 대한 액세스 권한이 없기 때문에 `foreach` 문의 쿼리 변수와 반복 변수가 모두 `var`을 사용하여 암시적으로 형식화되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58b63-112">In this scenario, both the query variable and the iteration variable in the `foreach` statement must be implicitly typed by using `var` because you do not have access to a type name for the anonymous type.</span></span> <span data-ttu-id="58b63-113">무명 형식에 대한 자세한 내용은 [무명 형식](./anonymous-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="58b63-113">For more information about anonymous types, see [Anonymous Types](./anonymous-types.md).</span></span>  
  
 [!code-csharp[csProgGuideLINQ#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#32)]  
  
## <a name="example"></a><span data-ttu-id="58b63-114">예제</span><span class="sxs-lookup"><span data-stu-id="58b63-114">Example</span></span>  

 <span data-ttu-id="58b63-115">다음 예제에서는 유사하지만 `var` 사용이 선택 사항인 상황에서 `var` 키워드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="58b63-115">The following example uses the `var` keyword in a situation that is similar, but in which the use of `var` is optional.</span></span> <span data-ttu-id="58b63-116">`student.LastName`이 문자열이기 때문에 쿼리를 실행하면 문자열 시퀀스가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="58b63-116">Because `student.LastName` is a string, execution of the query returns a sequence of strings.</span></span> <span data-ttu-id="58b63-117">따라서 `queryID`의 형식을 `var` 대신 `System.Collections.Generic.IEnumerable<string>`로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58b63-117">Therefore, the type of `queryID` could be declared as `System.Collections.Generic.IEnumerable<string>` instead of `var`.</span></span> <span data-ttu-id="58b63-118">`var` 키워드는 편의상 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="58b63-118">Keyword `var` is used for convenience.</span></span> <span data-ttu-id="58b63-119">예제에서 `foreach` 문의 반복 변수는 명시적으로 문자열로 형식화되었지만, 대신 `var`을 사용하여 선언할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58b63-119">In the example, the iteration variable in the `foreach` statement is explicitly typed as a string, but it could instead be declared by using `var`.</span></span> <span data-ttu-id="58b63-120">반복 변수의 형식이 무명 형식이 아니기 때문에 `var` 사용은 요구 사항이 아니라 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="58b63-120">Because the type of the iteration variable is not an anonymous type, the use of `var` is an option, not a requirement.</span></span> <span data-ttu-id="58b63-121">`var` 자체는 형식이 아니라 형식을 유추하고 할당하도록 컴파일러에 지시하는 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="58b63-121">Remember, `var` itself is not a type, but an instruction to the compiler to infer and assign the type.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#33)]  
  
## <a name="see-also"></a><span data-ttu-id="58b63-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="58b63-122">See also</span></span>

- [<span data-ttu-id="58b63-123">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="58b63-123">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="58b63-124">확장명 메서드</span><span class="sxs-lookup"><span data-stu-id="58b63-124">Extension Methods</span></span>](./extension-methods.md)
- [<span data-ttu-id="58b63-125">LINQ(Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="58b63-125">LINQ (Language-Integrated Query)</span></span>](../../linq/index.md)
- [<span data-ttu-id="58b63-126">var</span><span class="sxs-lookup"><span data-stu-id="58b63-126">var</span></span>](../../language-reference/keywords/var.md)
- [<span data-ttu-id="58b63-127">C#의 LINQ</span><span class="sxs-lookup"><span data-stu-id="58b63-127">LINQ in C#</span></span>](../../linq/index.md)
