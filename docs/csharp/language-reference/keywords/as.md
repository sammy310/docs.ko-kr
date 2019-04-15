---
title: as - C# 참조
ms.custom: seodec18
ms.date: 10/11/2018
f1_keywords:
- as_CSharpKeyword
- as
helpviewer_keywords:
- type conversion [C#], as keyword
- as keyword [C#]
ms.assetid: a9be126b-cbf4-4990-a70d-d0e1983cad0e
ms.openlocfilehash: b87e75bd4866a191e84465e44d53850e6e2e9723
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59169925"
---
# <a name="as-c-reference"></a><span data-ttu-id="8e373-102">as(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="8e373-102">as (C# Reference)</span></span>
<span data-ttu-id="8e373-103">`as` 연산자를 사용하여 호환되는 참조 형식 또는 [nullable 형식](../../../csharp/programming-guide/nullable-types/index.md) 간에 특정 형식의 변환을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e373-103">You can use the `as` operator to perform certain types of conversions between compatible reference types or [nullable types](../../../csharp/programming-guide/nullable-types/index.md).</span></span> <span data-ttu-id="8e373-104">다음 코드는 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8e373-104">The following code shows an example.</span></span>  
  
[!code-csharp[csrefKeywordsOperator#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#1)]

<span data-ttu-id="8e373-105">예제에 나와 있는 대로 `as` 식의 결과를 `null`과 비교하여 변환에 성공했는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e373-105">As the example shows, you need to compare the result of the `as` expression with `null` to check if a conversion is successful.</span></span> <span data-ttu-id="8e373-106">C# 7.0부터는 [is](is.md) 식을 사용하여 변환에 성공했는지 테스트하고 변환 성공 시 조건부로 변수를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e373-106">Beginning with C# 7.0, you can use the [is](is.md) expression both to test that a conversion succeeds and conditionally assign a variable when the conversion succeeds.</span></span> <span data-ttu-id="8e373-107">대부분 시나리오에서는 `as` 연산자를 사용하는 것보다 더 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="8e373-107">In many scenarios, it's more concise than using the `as` operator.</span></span> <span data-ttu-id="8e373-108">자세한 내용은 [`is` 연산자](is.md) 문서의 [형식 패턴](is.md#type) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e373-108">For more information, see the [Type pattern](is.md#type) section of the [`is` operator](is.md) article.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="8e373-109">주의</span><span class="sxs-lookup"><span data-stu-id="8e373-109">Remarks</span></span>  
 <span data-ttu-id="8e373-110">`as` 연산자는 캐스트 작업과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="8e373-110">The `as` operator is like a cast operation.</span></span> <span data-ttu-id="8e373-111">하지만 변환할 수 없는 경우 `as`는 예외를 발생시키지 않고 `null`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8e373-111">However, if the conversion isn't possible, `as` returns `null` instead of raising an exception.</span></span> <span data-ttu-id="8e373-112">다음 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e373-112">Consider the following example:</span></span>  
  
```csharp  
expression as type  
```  
  
 <span data-ttu-id="8e373-113">`expression` 변수가 한 번만 계산된다는 점을 제외하고 코드는 다음 식과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8e373-113">The code is equivalent to the following expression except that the `expression` variable is evaluated only one time.</span></span>  
  
```csharp  
expression is type ? (type)expression : (type)null  
```  
  
 <span data-ttu-id="8e373-114">`as` 연산자는 참조 변환, nullable 변환 및 boxing 변환만 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="8e373-114">Note that the `as` operator performs only reference conversions, nullable conversions, and boxing conversions.</span></span> <span data-ttu-id="8e373-115">`as` 연산자는 캐스트 식을 사용하여 수행해야 하는 사용자 정의 변환 등의 기타 변환을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8e373-115">The `as` operator can't perform other conversions, such as user-defined conversions, which should instead be performed by using cast expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e373-116">예제</span><span class="sxs-lookup"><span data-stu-id="8e373-116">Example</span></span>  

[!code-csharp[csrefKeywordsOperator#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#2)]
  
## <a name="c-language-specification"></a><span data-ttu-id="8e373-117">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="8e373-117">C# Language Specification</span></span>  

<span data-ttu-id="8e373-118">자세한 내용은 [C# 언어 사양](../language-specification/index.md)의 [as 연산자](~/_csharplang/spec/expressions.md#the-as-operator)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e373-118">For more information, see [The as operator](~/_csharplang/spec/expressions.md#the-as-operator) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="8e373-119">언어 사양은 C# 구문 및 사용법에 대 한 신뢰할 수 있는 소스 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e373-119">The language specification is the definitive source for C# syntax and usage.</span></span>
 
## <a name="see-also"></a><span data-ttu-id="8e373-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8e373-120">See also</span></span>

- [<span data-ttu-id="8e373-121">C# 참조</span><span class="sxs-lookup"><span data-stu-id="8e373-121">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="8e373-122">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="8e373-122">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="8e373-123">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="8e373-123">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="8e373-124">is</span><span class="sxs-lookup"><span data-stu-id="8e373-124">is</span></span>](../../../csharp/language-reference/keywords/is.md)
- [<span data-ttu-id="8e373-125">?: 연산자</span><span class="sxs-lookup"><span data-stu-id="8e373-125">?: Operator</span></span>](../../../csharp/language-reference/operators/conditional-operator.md)
- [<span data-ttu-id="8e373-126">연산자 키워드</span><span class="sxs-lookup"><span data-stu-id="8e373-126">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)
