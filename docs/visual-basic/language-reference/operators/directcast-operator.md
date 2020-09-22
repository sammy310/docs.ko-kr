---
title: DirectCast 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.directCast
- directCast
helpviewer_keywords:
- DirectCast keyword [Visual Basic]
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
ms.openlocfilehash: 7b070b8eba240440821f7984a9336c2ecaf61706
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867085"
---
# <a name="directcast-operator-visual-basic"></a><span data-ttu-id="b03ec-102">DirectCast 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b03ec-102">DirectCast Operator (Visual Basic)</span></span>

<span data-ttu-id="b03ec-103">상속 또는 구현을 기반으로 하는 형식 변환 작업을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="b03ec-103">Introduces a type conversion operation based on inheritance or implementation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b03ec-104">설명</span><span class="sxs-lookup"><span data-stu-id="b03ec-104">Remarks</span></span>  

 <span data-ttu-id="b03ec-105">`DirectCast` 는 변환에 Visual Basic 런타임 도우미 루틴을 사용 하지 않으므로 `CType` 데이터 형식으로 변환 하는 경우 보다 약간 더 나은 성능을 제공할 수 있습니다 `Object` .</span><span class="sxs-lookup"><span data-stu-id="b03ec-105">`DirectCast` does not use the Visual Basic run-time helper routines for conversion, so it can provide somewhat better performance than `CType` when converting to and from data type `Object`.</span></span>  
  
 <span data-ttu-id="b03ec-106">`DirectCast` [CType 함수와](../functions/ctype-function.md) [TryCast Operator](trycast-operator.md) 키워드를 사용 하는 방법과 유사 하 게 키워드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b03ec-106">You use the `DirectCast` keyword similar to the way you use the [CType Function](../functions/ctype-function.md) and the [TryCast Operator](trycast-operator.md) keyword.</span></span> <span data-ttu-id="b03ec-107">식을 첫 번째 인수로 제공 하 고이를 두 번째 인수로 변환할 형식으로 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b03ec-107">You supply an expression as the first argument and a type to convert it to as the second argument.</span></span> <span data-ttu-id="b03ec-108">`DirectCast` 두 인수의 데이터 형식 간에 상속 또는 구현 관계가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b03ec-108">`DirectCast` requires an inheritance or implementation relationship between the data types of the two arguments.</span></span> <span data-ttu-id="b03ec-109">즉, 한 형식이 다른 형식에서 상속 되거나 다른 형식에서 구현 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b03ec-109">This means that one type must inherit from or implement the other.</span></span>  
  
## <a name="errors-and-failures"></a><span data-ttu-id="b03ec-110">오류 및 오류</span><span class="sxs-lookup"><span data-stu-id="b03ec-110">Errors and Failures</span></span>  

 <span data-ttu-id="b03ec-111">`DirectCast` 는 상속 또는 구현 관계가 없다는 것을 감지 하면 컴파일러 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b03ec-111">`DirectCast` generates a compiler error if it detects that no inheritance or implementation relationship exists.</span></span> <span data-ttu-id="b03ec-112">그러나 컴파일러 오류가 없으면 변환이 성공적으로 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b03ec-112">But the lack of a compiler error does not guarantee a successful conversion.</span></span> <span data-ttu-id="b03ec-113">원하는 변환이 축소 인 경우 런타임에 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b03ec-113">If the desired conversion is narrowing, it could fail at run time.</span></span> <span data-ttu-id="b03ec-114">이 경우 런타임에서 오류를 throw <xref:System.InvalidCastException> 합니다.</span><span class="sxs-lookup"><span data-stu-id="b03ec-114">If this happens, the runtime throws an <xref:System.InvalidCastException> error.</span></span>  
  
## <a name="conversion-keywords"></a><span data-ttu-id="b03ec-115">변환 키워드</span><span class="sxs-lookup"><span data-stu-id="b03ec-115">Conversion Keywords</span></span>  

 <span data-ttu-id="b03ec-116">형식 변환 키워드의 비교는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b03ec-116">A comparison of the type conversion keywords is as follows.</span></span>  
  
|<span data-ttu-id="b03ec-117">키워드</span><span class="sxs-lookup"><span data-stu-id="b03ec-117">Keyword</span></span>|<span data-ttu-id="b03ec-118">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b03ec-118">Data types</span></span>|<span data-ttu-id="b03ec-119">인수 관계</span><span class="sxs-lookup"><span data-stu-id="b03ec-119">Argument relationship</span></span>|<span data-ttu-id="b03ec-120">런타임 오류</span><span class="sxs-lookup"><span data-stu-id="b03ec-120">Run-time failure</span></span>|  
|---|---|---|---|  
|[<span data-ttu-id="b03ec-121">CType Function</span><span class="sxs-lookup"><span data-stu-id="b03ec-121">CType Function</span></span>](../functions/ctype-function.md)|<span data-ttu-id="b03ec-122">모든 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b03ec-122">Any data types</span></span>|<span data-ttu-id="b03ec-123">두 데이터 형식 간에 확대 또는 축소 변환을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b03ec-123">Widening or narrowing conversion must be defined between the two data types</span></span>|<span data-ttu-id="b03ec-124">되거나 <xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="b03ec-124">Throws <xref:System.InvalidCastException></span></span>|  
|`DirectCast`|<span data-ttu-id="b03ec-125">모든 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b03ec-125">Any data types</span></span>|<span data-ttu-id="b03ec-126">한 형식이 다른 형식에서 상속 되거나 다른 형식으로 구현 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b03ec-126">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="b03ec-127">되거나 <xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="b03ec-127">Throws <xref:System.InvalidCastException></span></span>|  
|[<span data-ttu-id="b03ec-128">TryCast 연산자</span><span class="sxs-lookup"><span data-stu-id="b03ec-128">TryCast Operator</span></span>](trycast-operator.md)|<span data-ttu-id="b03ec-129">참조 형식만</span><span class="sxs-lookup"><span data-stu-id="b03ec-129">Reference types only</span></span>|<span data-ttu-id="b03ec-130">한 형식이 다른 형식에서 상속 되거나 다른 형식으로 구현 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b03ec-130">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="b03ec-131">[아무 것도](../nothing.md) 반환 하지 않음</span><span class="sxs-lookup"><span data-stu-id="b03ec-131">Returns [Nothing](../nothing.md)</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b03ec-132">예제</span><span class="sxs-lookup"><span data-stu-id="b03ec-132">Example</span></span>  

 <span data-ttu-id="b03ec-133">다음 예제에서는 두 가지 사용 방법을 보여 줍니다 `DirectCast` . 하나는 런타임에 실패 하 고 다른 하나는 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b03ec-133">The following example demonstrates two uses of `DirectCast`, one that fails at run time and one that succeeds.</span></span>  
  
 [!code-vb[VbVbalrKeywords#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#1)]  
  
 <span data-ttu-id="b03ec-134">앞의 예제에서의 런타임 형식은입니다 `q` `Double` .</span><span class="sxs-lookup"><span data-stu-id="b03ec-134">In the preceding example, the run-time type of `q` is `Double`.</span></span> <span data-ttu-id="b03ec-135">`CType``Double`는로 변환 될 수 있으므로 성공 `Integer` 합니다.</span><span class="sxs-lookup"><span data-stu-id="b03ec-135">`CType` succeeds because `Double` can be converted to `Integer`.</span></span> <span data-ttu-id="b03ec-136">그러나 `DirectCast` 변환이 있는 경우에도의 런타임 형식은와의 상속 관계가 없기 때문에 첫 번째는 런타임에 실패 합니다 `Double` `Integer` .</span><span class="sxs-lookup"><span data-stu-id="b03ec-136">However, the first `DirectCast` fails at run time because the run-time type of `Double` has no inheritance relationship with `Integer`, even though a conversion exists.</span></span> <span data-ttu-id="b03ec-137">두 번째는 `DirectCast` 형식에서를 <xref:System.Windows.Forms.Form> 상속 하는 형식으로 변환 하기 때문에 성공 합니다 <xref:System.Windows.Forms.Control> <xref:System.Windows.Forms.Form> .</span><span class="sxs-lookup"><span data-stu-id="b03ec-137">The second `DirectCast` succeeds because it converts from type <xref:System.Windows.Forms.Form> to type <xref:System.Windows.Forms.Control>, from which <xref:System.Windows.Forms.Form> inherits.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b03ec-138">참조</span><span class="sxs-lookup"><span data-stu-id="b03ec-138">See also</span></span>

- <xref:System.Convert.ChangeType%2A?displayProperty=nameWithType>
- [<span data-ttu-id="b03ec-139">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="b03ec-139">Widening and Narrowing Conversions</span></span>](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="b03ec-140">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="b03ec-140">Implicit and Explicit Conversions</span></span>](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
