---
title: TryCast 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.trycast
- trycast
helpviewer_keywords:
- TryCast keyword [Visual Basic]
ms.assetid: d1ef5d47-fef4-491e-b014-1d910628f65c
ms.openlocfilehash: 53306575cfc385039be3939fd87cf993b4509af4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348210"
---
# <a name="trycast-operator-visual-basic"></a><span data-ttu-id="0a0e9-102">TryCast 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0a0e9-102">TryCast Operator (Visual Basic)</span></span>
<span data-ttu-id="0a0e9-103">에는 예외를 throw 하지 않는 형식 변환 연산이 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0a0e9-103">Introduces a type conversion operation that does not throw an exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a0e9-104">주의</span><span class="sxs-lookup"><span data-stu-id="0a0e9-104">Remarks</span></span>  
 <span data-ttu-id="0a0e9-105">시도한 변환이 실패 하면 `CType`와 `DirectCast` 모두 <xref:System.InvalidCastException> 오류가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a0e9-105">If an attempted conversion fails, `CType` and `DirectCast` both throw an <xref:System.InvalidCastException> error.</span></span> <span data-ttu-id="0a0e9-106">이로 인해 응용 프로그램의 성능에 부정적인 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a0e9-106">This can adversely affect the performance of your application.</span></span> <span data-ttu-id="0a0e9-107">`TryCast`은 [아무 것도](../../../visual-basic/language-reference/nothing.md)반환 하지 않으므로 가능한 예외를 처리 하지 않고 `Nothing`에 대해 반환 된 결과만 테스트 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a0e9-107">`TryCast` returns [Nothing](../../../visual-basic/language-reference/nothing.md), so that instead of having to handle a possible exception, you need only test the returned result against `Nothing`.</span></span>  
  
 <span data-ttu-id="0a0e9-108">[CType 함수와](../../../visual-basic/language-reference/functions/ctype-function.md) [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) 키워드를 사용 하는 것과 같은 방법으로 `TryCast` 키워드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a0e9-108">You use the `TryCast` keyword the same way you use the [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) and the [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) keyword.</span></span> <span data-ttu-id="0a0e9-109">식을 첫 번째 인수로 제공 하 고이를 두 번째 인수로 변환할 형식으로 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a0e9-109">You supply an expression as the first argument and a type to convert it to as the second argument.</span></span> <span data-ttu-id="0a0e9-110">`TryCast`는 클래스 및 인터페이스와 같은 참조 형식에만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a0e9-110">`TryCast` operates only on reference types, such as classes and interfaces.</span></span> <span data-ttu-id="0a0e9-111">두 형식 간에 상속 또는 구현 관계가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a0e9-111">It requires an inheritance or implementation relationship between the two types.</span></span> <span data-ttu-id="0a0e9-112">즉, 한 형식이 다른 형식에서 상속 되거나 다른 형식에서 구현 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a0e9-112">This means that one type must inherit from or implement the other.</span></span>  
  
## <a name="errors-and-failures"></a><span data-ttu-id="0a0e9-113">오류 및 오류</span><span class="sxs-lookup"><span data-stu-id="0a0e9-113">Errors and Failures</span></span>  
 <span data-ttu-id="0a0e9-114">상속 또는 구현 관계가 없다는 것을 감지 하면 `TryCast` 컴파일러 오류가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a0e9-114">`TryCast` generates a compiler error if it detects that no inheritance or implementation relationship exists.</span></span> <span data-ttu-id="0a0e9-115">그러나 컴파일러 오류가 없으면 변환이 성공적으로 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0a0e9-115">But the lack of a compiler error does not guarantee a successful conversion.</span></span> <span data-ttu-id="0a0e9-116">원하는 변환이 축소 인 경우 런타임에 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a0e9-116">If the desired conversion is narrowing, it could fail at run time.</span></span> <span data-ttu-id="0a0e9-117">이 경우 `TryCast`은 [아무 것도](../../../visual-basic/language-reference/nothing.md)반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0a0e9-117">If this happens, `TryCast` returns [Nothing](../../../visual-basic/language-reference/nothing.md).</span></span>  
  
## <a name="conversion-keywords"></a><span data-ttu-id="0a0e9-118">변환 키워드</span><span class="sxs-lookup"><span data-stu-id="0a0e9-118">Conversion Keywords</span></span>  
 <span data-ttu-id="0a0e9-119">형식 변환 키워드의 비교는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0a0e9-119">A comparison of the type conversion keywords is as follows.</span></span>  
  
|<span data-ttu-id="0a0e9-120">키워드</span><span class="sxs-lookup"><span data-stu-id="0a0e9-120">Keyword</span></span>|<span data-ttu-id="0a0e9-121">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="0a0e9-121">Data types</span></span>|<span data-ttu-id="0a0e9-122">인수 관계</span><span class="sxs-lookup"><span data-stu-id="0a0e9-122">Argument relationship</span></span>|<span data-ttu-id="0a0e9-123">런타임 오류</span><span class="sxs-lookup"><span data-stu-id="0a0e9-123">Run-time failure</span></span>|  
|---|---|---|---|  
|[<span data-ttu-id="0a0e9-124">CType Function</span><span class="sxs-lookup"><span data-stu-id="0a0e9-124">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)|<span data-ttu-id="0a0e9-125">모든 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="0a0e9-125">Any data types</span></span>|<span data-ttu-id="0a0e9-126">두 데이터 형식 간에 확대 또는 축소 변환을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a0e9-126">Widening or narrowing conversion must be defined between the two data types</span></span>|<span data-ttu-id="0a0e9-127"><xref:System.InvalidCastException>를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a0e9-127">Throws <xref:System.InvalidCastException></span></span>|  
|[<span data-ttu-id="0a0e9-128">DirectCast 연산자</span><span class="sxs-lookup"><span data-stu-id="0a0e9-128">DirectCast Operator</span></span>](../../../visual-basic/language-reference/operators/directcast-operator.md)|<span data-ttu-id="0a0e9-129">모든 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="0a0e9-129">Any data types</span></span>|<span data-ttu-id="0a0e9-130">한 형식이 다른 형식에서 상속 되거나 다른 형식으로 구현 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a0e9-130">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="0a0e9-131"><xref:System.InvalidCastException>를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a0e9-131">Throws <xref:System.InvalidCastException></span></span>|  
|`TryCast`|<span data-ttu-id="0a0e9-132">참조 형식만</span><span class="sxs-lookup"><span data-stu-id="0a0e9-132">Reference types only</span></span>|<span data-ttu-id="0a0e9-133">한 형식이 다른 형식에서 상속 되거나 다른 형식으로 구현 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a0e9-133">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="0a0e9-134">[아무 것도](../../../visual-basic/language-reference/nothing.md) 반환 하지 않음</span><span class="sxs-lookup"><span data-stu-id="0a0e9-134">Returns [Nothing](../../../visual-basic/language-reference/nothing.md)</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0a0e9-135">예제</span><span class="sxs-lookup"><span data-stu-id="0a0e9-135">Example</span></span>  
 <span data-ttu-id="0a0e9-136">다음 예제에서는 `TryCast`을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0a0e9-136">The following example shows how to use `TryCast`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="0a0e9-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a0e9-137">See also</span></span>

- [<span data-ttu-id="0a0e9-138">확대 변환과 축소 변환</span><span class="sxs-lookup"><span data-stu-id="0a0e9-138">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="0a0e9-139">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="0a0e9-139">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
