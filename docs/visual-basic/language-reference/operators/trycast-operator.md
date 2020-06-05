---
title: TryCast 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.trycast
- trycast
helpviewer_keywords:
- TryCast keyword [Visual Basic]
ms.assetid: d1ef5d47-fef4-491e-b014-1d910628f65c
ms.openlocfilehash: 8f0d4f612cd5a96e0b0ab7305c41e00790613cc8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406391"
---
# <a name="trycast-operator-visual-basic"></a><span data-ttu-id="69688-102">TryCast 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="69688-102">TryCast Operator (Visual Basic)</span></span>
<span data-ttu-id="69688-103">에는 예외를 throw 하지 않는 형식 변환 연산이 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="69688-103">Introduces a type conversion operation that does not throw an exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69688-104">설명</span><span class="sxs-lookup"><span data-stu-id="69688-104">Remarks</span></span>  
 <span data-ttu-id="69688-105">시도 된 변환이 실패 하 `CType` 고 `DirectCast` 둘 다 오류를 throw 하는 경우 <xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="69688-105">If an attempted conversion fails, `CType` and `DirectCast` both throw an <xref:System.InvalidCastException> error.</span></span> <span data-ttu-id="69688-106">이로 인해 응용 프로그램의 성능에 부정적인 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69688-106">This can adversely affect the performance of your application.</span></span> <span data-ttu-id="69688-107">`TryCast`은 [아무 것도](../nothing.md)반환 하지 않으므로 가능한 예외를 처리 하지 않고 반환 된 결과만 테스트 하면 `Nothing` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69688-107">`TryCast` returns [Nothing](../nothing.md), so that instead of having to handle a possible exception, you need only test the returned result against `Nothing`.</span></span>  
  
 <span data-ttu-id="69688-108">`TryCast` [CType 함수와](../functions/ctype-function.md) [DirectCast Operator](directcast-operator.md) 키워드를 사용 하는 것과 동일한 방식으로 키워드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="69688-108">You use the `TryCast` keyword the same way you use the [CType Function](../functions/ctype-function.md) and the [DirectCast Operator](directcast-operator.md) keyword.</span></span> <span data-ttu-id="69688-109">식을 첫 번째 인수로 제공 하 고이를 두 번째 인수로 변환할 형식으로 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="69688-109">You supply an expression as the first argument and a type to convert it to as the second argument.</span></span> <span data-ttu-id="69688-110">`TryCast`는 클래스 및 인터페이스와 같은 참조 형식 에서만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="69688-110">`TryCast` operates only on reference types, such as classes and interfaces.</span></span> <span data-ttu-id="69688-111">두 형식 간에 상속 또는 구현 관계가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="69688-111">It requires an inheritance or implementation relationship between the two types.</span></span> <span data-ttu-id="69688-112">즉, 한 형식이 다른 형식에서 상속 되거나 다른 형식에서 구현 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69688-112">This means that one type must inherit from or implement the other.</span></span>  
  
## <a name="errors-and-failures"></a><span data-ttu-id="69688-113">오류 및 오류</span><span class="sxs-lookup"><span data-stu-id="69688-113">Errors and Failures</span></span>  
 <span data-ttu-id="69688-114">`TryCast`는 상속 또는 구현 관계가 없다는 것을 감지 하면 컴파일러 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="69688-114">`TryCast` generates a compiler error if it detects that no inheritance or implementation relationship exists.</span></span> <span data-ttu-id="69688-115">그러나 컴파일러 오류가 없으면 변환이 성공적으로 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69688-115">But the lack of a compiler error does not guarantee a successful conversion.</span></span> <span data-ttu-id="69688-116">원하는 변환이 축소 인 경우 런타임에 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69688-116">If the desired conversion is narrowing, it could fail at run time.</span></span> <span data-ttu-id="69688-117">이 경우 `TryCast` [아무 것도](../nothing.md)반환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69688-117">If this happens, `TryCast` returns [Nothing](../nothing.md).</span></span>  
  
## <a name="conversion-keywords"></a><span data-ttu-id="69688-118">변환 키워드</span><span class="sxs-lookup"><span data-stu-id="69688-118">Conversion Keywords</span></span>  
 <span data-ttu-id="69688-119">형식 변환 키워드의 비교는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="69688-119">A comparison of the type conversion keywords is as follows.</span></span>  
  
|<span data-ttu-id="69688-120">키워드</span><span class="sxs-lookup"><span data-stu-id="69688-120">Keyword</span></span>|<span data-ttu-id="69688-121">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="69688-121">Data types</span></span>|<span data-ttu-id="69688-122">인수 관계</span><span class="sxs-lookup"><span data-stu-id="69688-122">Argument relationship</span></span>|<span data-ttu-id="69688-123">런타임 오류</span><span class="sxs-lookup"><span data-stu-id="69688-123">Run-time failure</span></span>|  
|---|---|---|---|  
|[<span data-ttu-id="69688-124">CType Function</span><span class="sxs-lookup"><span data-stu-id="69688-124">CType Function</span></span>](../functions/ctype-function.md)|<span data-ttu-id="69688-125">모든 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="69688-125">Any data types</span></span>|<span data-ttu-id="69688-126">두 데이터 형식 간에 확대 또는 축소 변환을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69688-126">Widening or narrowing conversion must be defined between the two data types</span></span>|<span data-ttu-id="69688-127">되거나<xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="69688-127">Throws <xref:System.InvalidCastException></span></span>|  
|[<span data-ttu-id="69688-128">DirectCast 연산자</span><span class="sxs-lookup"><span data-stu-id="69688-128">DirectCast Operator</span></span>](directcast-operator.md)|<span data-ttu-id="69688-129">모든 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="69688-129">Any data types</span></span>|<span data-ttu-id="69688-130">한 형식이 다른 형식에서 상속 되거나 다른 형식으로 구현 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69688-130">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="69688-131">되거나<xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="69688-131">Throws <xref:System.InvalidCastException></span></span>|  
|`TryCast`|<span data-ttu-id="69688-132">참조 형식만</span><span class="sxs-lookup"><span data-stu-id="69688-132">Reference types only</span></span>|<span data-ttu-id="69688-133">한 형식이 다른 형식에서 상속 되거나 다른 형식으로 구현 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69688-133">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="69688-134">[아무 것도](../nothing.md) 반환 하지 않음</span><span class="sxs-lookup"><span data-stu-id="69688-134">Returns [Nothing](../nothing.md)</span></span>|  
  
## <a name="example"></a><span data-ttu-id="69688-135">예제</span><span class="sxs-lookup"><span data-stu-id="69688-135">Example</span></span>  
 <span data-ttu-id="69688-136">다음 예제에서는 `TryCast`을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="69688-136">The following example shows how to use `TryCast`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="69688-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="69688-137">See also</span></span>

- [<span data-ttu-id="69688-138">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="69688-138">Widening and Narrowing Conversions</span></span>](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="69688-139">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="69688-139">Implicit and Explicit Conversions</span></span>](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
