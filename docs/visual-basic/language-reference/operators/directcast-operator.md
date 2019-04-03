---
title: DirectCast 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.directCast
- directCast
helpviewer_keywords:
- DirectCast keyword [Visual Basic]
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
ms.openlocfilehash: 628ce4f06b91d0f514f71dea3aad8ea0fee6dccf
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58821506"
---
# <a name="directcast-operator-visual-basic"></a><span data-ttu-id="83be3-102">DirectCast 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83be3-102">DirectCast Operator (Visual Basic)</span></span>
<span data-ttu-id="83be3-103">상속 또는 구현에 따라 형식 변환 작업을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="83be3-103">Introduces a type conversion operation based on inheritance or implementation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83be3-104">설명</span><span class="sxs-lookup"><span data-stu-id="83be3-104">Remarks</span></span>  
 <span data-ttu-id="83be3-105">`DirectCast` 향상 된 성능을 어느 정도 제공할 수 있도록 변환에 대 한 런타임 도우미 루틴 Visual Basic을 사용 하지 않습니다 `CType` 데이터 형식에서 변환할 때 `Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="83be3-105">`DirectCast` does not use the Visual Basic run-time helper routines for conversion, so it can provide somewhat better performance than `CType` when converting to and from data type `Object`.</span></span>  
  
 <span data-ttu-id="83be3-106">사용할 합니다 `DirectCast` 키워드를 사용 하는 방법은 비슷합니다는 [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) 및 [TryCast 연산자](../../../visual-basic/language-reference/operators/trycast-operator.md) 키워드.</span><span class="sxs-lookup"><span data-stu-id="83be3-106">You use the `DirectCast` keyword similar to the way you use the [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) and the [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) keyword.</span></span> <span data-ttu-id="83be3-107">첫 번째 인수와 두 번째 인수로 변환 하는 형식으로 식을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="83be3-107">You supply an expression as the first argument and a type to convert it to as the second argument.</span></span> <span data-ttu-id="83be3-108">`DirectCast` 두 인수의 데이터 형식 간의 상속 또는 구현 관계를 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="83be3-108">`DirectCast` requires an inheritance or implementation relationship between the data types of the two arguments.</span></span> <span data-ttu-id="83be3-109">즉, 한 형식에서 상속 하거나 다른 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83be3-109">This means that one type must inherit from or implement the other.</span></span>  
  
## <a name="errors-and-failures"></a><span data-ttu-id="83be3-110">오류 및 실패</span><span class="sxs-lookup"><span data-stu-id="83be3-110">Errors and Failures</span></span>  
 <span data-ttu-id="83be3-111">`DirectCast` 상속 또는 구현 관계 없는 있는지 검색 하는 경우 컴파일러 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="83be3-111">`DirectCast` generates a compiler error if it detects that no inheritance or implementation relationship exists.</span></span> <span data-ttu-id="83be3-112">하지만 컴파일러 오류가 없다고 성공적인 변환을 보장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83be3-112">But the lack of a compiler error does not guarantee a successful conversion.</span></span> <span data-ttu-id="83be3-113">원하는 변환에 축소 하는 경우에 런타임에 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83be3-113">If the desired conversion is narrowing, it could fail at run time.</span></span> <span data-ttu-id="83be3-114">이 경우 런타임에서 throw는 <xref:System.InvalidCastException> 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="83be3-114">If this happens, the runtime throws an <xref:System.InvalidCastException> error.</span></span>  
  
## <a name="conversion-keywords"></a><span data-ttu-id="83be3-115">변환 키워드</span><span class="sxs-lookup"><span data-stu-id="83be3-115">Conversion Keywords</span></span>  
 <span data-ttu-id="83be3-116">형식 변환 키워드의 비교는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="83be3-116">A comparison of the type conversion keywords is as follows.</span></span>  
  
|<span data-ttu-id="83be3-117">키워드</span><span class="sxs-lookup"><span data-stu-id="83be3-117">Keyword</span></span>|<span data-ttu-id="83be3-118">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="83be3-118">Data types</span></span>|<span data-ttu-id="83be3-119">인수가 관계</span><span class="sxs-lookup"><span data-stu-id="83be3-119">Argument relationship</span></span>|<span data-ttu-id="83be3-120">런타임 오류</span><span class="sxs-lookup"><span data-stu-id="83be3-120">Run-time failure</span></span>|  
|---|---|---|---|  
|[<span data-ttu-id="83be3-121">CType 함수</span><span class="sxs-lookup"><span data-stu-id="83be3-121">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)|<span data-ttu-id="83be3-122">모든 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="83be3-122">Any data types</span></span>|<span data-ttu-id="83be3-123">두 데이터 형식 간에 확대 또는 축소 변환을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83be3-123">Widening or narrowing conversion must be defined between the two data types</span></span>|<span data-ttu-id="83be3-124">Throw <xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="83be3-124">Throws <xref:System.InvalidCastException></span></span>|  
|`DirectCast`|<span data-ttu-id="83be3-125">모든 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="83be3-125">Any data types</span></span>|<span data-ttu-id="83be3-126">형식에서 상속 하거나 다른 형식을 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83be3-126">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="83be3-127">Throw <xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="83be3-127">Throws <xref:System.InvalidCastException></span></span>|  
|[<span data-ttu-id="83be3-128">TryCast 연산자</span><span class="sxs-lookup"><span data-stu-id="83be3-128">TryCast Operator</span></span>](../../../visual-basic/language-reference/operators/trycast-operator.md)|<span data-ttu-id="83be3-129">참조 형식에만</span><span class="sxs-lookup"><span data-stu-id="83be3-129">Reference types only</span></span>|<span data-ttu-id="83be3-130">형식에서 상속 하거나 다른 형식을 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83be3-130">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="83be3-131">반환 [Nothing](../../../visual-basic/language-reference/nothing.md)</span><span class="sxs-lookup"><span data-stu-id="83be3-131">Returns [Nothing](../../../visual-basic/language-reference/nothing.md)</span></span>|  
  
## <a name="example"></a><span data-ttu-id="83be3-132">예제</span><span class="sxs-lookup"><span data-stu-id="83be3-132">Example</span></span>  
 <span data-ttu-id="83be3-133">다음 예제에서는 두 개의 사용 `DirectCast`, 런타임에 하나는 실패 하는 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="83be3-133">The following example demonstrates two uses of `DirectCast`, one that fails at run time and one that succeeds.</span></span>  
  
 [!code-vb[VbVbalrKeywords#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#1)]  
  
 <span data-ttu-id="83be3-134">런타임 형식의 이전 예제의 `q` 는 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="83be3-134">In the preceding example, the run-time type of `q` is `Double`.</span></span> <span data-ttu-id="83be3-135">`CType` 때문에 성공 `Double` 변환할 수 `Integer`입니다.</span><span class="sxs-lookup"><span data-stu-id="83be3-135">`CType` succeeds because `Double` can be converted to `Integer`.</span></span> <span data-ttu-id="83be3-136">그러나 첫 번째 `DirectCast` 런타임 유형의 때문에 런타임에 실패 `Double` 사용 하 여 상속 관계가 없는 `Integer`한 변환이 존재 하는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="83be3-136">However, the first `DirectCast` fails at run time because the run-time type of `Double` has no inheritance relationship with `Integer`, even though a conversion exists.</span></span> <span data-ttu-id="83be3-137">두 번째 `DirectCast` 형식에서 변환 되기 때문에 성공 <xref:System.Windows.Forms.Form> 입력할 <xref:System.Windows.Forms.Control>, 올 <xref:System.Windows.Forms.Form> 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="83be3-137">The second `DirectCast` succeeds because it converts from type <xref:System.Windows.Forms.Form> to type <xref:System.Windows.Forms.Control>, from which <xref:System.Windows.Forms.Form> inherits.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83be3-138">참고자료</span><span class="sxs-lookup"><span data-stu-id="83be3-138">See also</span></span>

- <xref:System.Convert.ChangeType%2A?displayProperty=nameWithType>
- [<span data-ttu-id="83be3-139">확대 변환과 축소 변환</span><span class="sxs-lookup"><span data-stu-id="83be3-139">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="83be3-140">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="83be3-140">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
