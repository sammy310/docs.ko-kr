---
description: '다음에 대 한 자세한 정보: TryCast 연산자 (Visual Basic)'
title: TryCast 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.trycast
- trycast
helpviewer_keywords:
- TryCast keyword [Visual Basic]
ms.assetid: d1ef5d47-fef4-491e-b014-1d910628f65c
ms.openlocfilehash: 5b941ec40c4ba0198fced64d0ef039605efad472
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795250"
---
# <a name="trycast-operator-visual-basic"></a><span data-ttu-id="6b14c-103">TryCast 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6b14c-103">TryCast Operator (Visual Basic)</span></span>

<span data-ttu-id="6b14c-104">에는 예외를 throw 하지 않는 형식 변환 연산이 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6b14c-104">Introduces a type conversion operation that does not throw an exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b14c-105">설명</span><span class="sxs-lookup"><span data-stu-id="6b14c-105">Remarks</span></span>  

 <span data-ttu-id="6b14c-106">시도 된 변환이 실패 하 `CType` 고 `DirectCast` 둘 다 오류를 throw 하는 경우 <xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="6b14c-106">If an attempted conversion fails, `CType` and `DirectCast` both throw an <xref:System.InvalidCastException> error.</span></span> <span data-ttu-id="6b14c-107">이로 인해 응용 프로그램의 성능에 부정적인 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b14c-107">This can adversely affect the performance of your application.</span></span> <span data-ttu-id="6b14c-108">`TryCast` 은 [아무 것도](../nothing.md)반환 하지 않으므로 가능한 예외를 처리 하지 않고 반환 된 결과만 테스트 하면 `Nothing` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b14c-108">`TryCast` returns [Nothing](../nothing.md), so that instead of having to handle a possible exception, you need only test the returned result against `Nothing`.</span></span>  
  
 <span data-ttu-id="6b14c-109">`TryCast` [CType 함수와](../functions/ctype-function.md) [DirectCast Operator](directcast-operator.md) 키워드를 사용 하는 것과 동일한 방식으로 키워드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b14c-109">You use the `TryCast` keyword the same way you use the [CType Function](../functions/ctype-function.md) and the [DirectCast Operator](directcast-operator.md) keyword.</span></span> <span data-ttu-id="6b14c-110">식을 첫 번째 인수로 제공 하 고이를 두 번째 인수로 변환할 형식으로 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b14c-110">You supply an expression as the first argument and a type to convert it to as the second argument.</span></span> <span data-ttu-id="6b14c-111">`TryCast` 는 클래스 및 인터페이스와 같은 참조 형식 에서만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b14c-111">`TryCast` operates only on reference types, such as classes and interfaces.</span></span> <span data-ttu-id="6b14c-112">두 형식 간에 상속 또는 구현 관계가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b14c-112">It requires an inheritance or implementation relationship between the two types.</span></span> <span data-ttu-id="6b14c-113">즉, 한 형식이 다른 형식에서 상속 되거나 다른 형식에서 구현 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b14c-113">This means that one type must inherit from or implement the other.</span></span>  
  
## <a name="errors-and-failures"></a><span data-ttu-id="6b14c-114">오류 및 오류</span><span class="sxs-lookup"><span data-stu-id="6b14c-114">Errors and Failures</span></span>  

 <span data-ttu-id="6b14c-115">`TryCast` 는 상속 또는 구현 관계가 없다는 것을 감지 하면 컴파일러 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b14c-115">`TryCast` generates a compiler error if it detects that no inheritance or implementation relationship exists.</span></span> <span data-ttu-id="6b14c-116">그러나 컴파일러 오류가 없으면 변환이 성공적으로 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6b14c-116">But the lack of a compiler error does not guarantee a successful conversion.</span></span> <span data-ttu-id="6b14c-117">원하는 변환이 축소 인 경우 런타임에 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b14c-117">If the desired conversion is narrowing, it could fail at run time.</span></span> <span data-ttu-id="6b14c-118">이 경우 `TryCast` [아무 것도](../nothing.md)반환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6b14c-118">If this happens, `TryCast` returns [Nothing](../nothing.md).</span></span>  
  
## <a name="conversion-keywords"></a><span data-ttu-id="6b14c-119">변환 키워드</span><span class="sxs-lookup"><span data-stu-id="6b14c-119">Conversion Keywords</span></span>  

 <span data-ttu-id="6b14c-120">형식 변환 키워드의 비교는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6b14c-120">A comparison of the type conversion keywords is as follows.</span></span>  
  
|<span data-ttu-id="6b14c-121">키워드</span><span class="sxs-lookup"><span data-stu-id="6b14c-121">Keyword</span></span>|<span data-ttu-id="6b14c-122">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="6b14c-122">Data types</span></span>|<span data-ttu-id="6b14c-123">인수 관계</span><span class="sxs-lookup"><span data-stu-id="6b14c-123">Argument relationship</span></span>|<span data-ttu-id="6b14c-124">런타임 오류</span><span class="sxs-lookup"><span data-stu-id="6b14c-124">Run-time failure</span></span>|  
|---|---|---|---|  
|[<span data-ttu-id="6b14c-125">CType Function</span><span class="sxs-lookup"><span data-stu-id="6b14c-125">CType Function</span></span>](../functions/ctype-function.md)|<span data-ttu-id="6b14c-126">모든 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="6b14c-126">Any data types</span></span>|<span data-ttu-id="6b14c-127">두 데이터 형식 간에 확대 또는 축소 변환을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b14c-127">Widening or narrowing conversion must be defined between the two data types</span></span>|<span data-ttu-id="6b14c-128">되거나 <xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="6b14c-128">Throws <xref:System.InvalidCastException></span></span>|  
|[<span data-ttu-id="6b14c-129">DirectCast 연산자</span><span class="sxs-lookup"><span data-stu-id="6b14c-129">DirectCast Operator</span></span>](directcast-operator.md)|<span data-ttu-id="6b14c-130">모든 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="6b14c-130">Any data types</span></span>|<span data-ttu-id="6b14c-131">한 형식이 다른 형식에서 상속 되거나 다른 형식으로 구현 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b14c-131">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="6b14c-132">되거나 <xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="6b14c-132">Throws <xref:System.InvalidCastException></span></span>|  
|`TryCast`|<span data-ttu-id="6b14c-133">참조 형식만</span><span class="sxs-lookup"><span data-stu-id="6b14c-133">Reference types only</span></span>|<span data-ttu-id="6b14c-134">한 형식이 다른 형식에서 상속 되거나 다른 형식으로 구현 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b14c-134">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="6b14c-135">[아무 것도](../nothing.md) 반환 하지 않음</span><span class="sxs-lookup"><span data-stu-id="6b14c-135">Returns [Nothing](../nothing.md)</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6b14c-136">예제</span><span class="sxs-lookup"><span data-stu-id="6b14c-136">Example</span></span>  

 <span data-ttu-id="6b14c-137">다음 예제에서는 `TryCast`을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6b14c-137">The following example shows how to use `TryCast`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="6b14c-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6b14c-138">See also</span></span>

- [<span data-ttu-id="6b14c-139">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="6b14c-139">Widening and Narrowing Conversions</span></span>](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="6b14c-140">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="6b14c-140">Implicit and Explicit Conversions</span></span>](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
