---
title: 반복기(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Iterator
helpviewer_keywords:
- Iterator keyword [Visual Basic]
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
ms.openlocfilehash: 4f42cf864e836c53cff5e7d620f4bdfa43c4c7ec
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64661278"
---
# <a name="iterator-visual-basic"></a><span data-ttu-id="5670f-102">반복기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5670f-102">Iterator (Visual Basic)</span></span>
<span data-ttu-id="5670f-103">지정 된 함수 또는 `Get` 접근자가 반복기입니다.</span><span class="sxs-lookup"><span data-stu-id="5670f-103">Specifies that a function or `Get` accessor is an iterator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5670f-104">설명</span><span class="sxs-lookup"><span data-stu-id="5670f-104">Remarks</span></span>  
 <span data-ttu-id="5670f-105">*반복기* 컬렉션 사용자 지정 반복을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5670f-105">An *iterator* performs a custom iteration over a collection.</span></span> <span data-ttu-id="5670f-106">반복기를 사용 하는 [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) 문을 한 번에 하나씩 컬렉션의 각 요소를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5670f-106">An iterator uses the [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) statement to return each element in the collection one at a time.</span></span> <span data-ttu-id="5670f-107">경우는 `Yield` 문에 도달 하면, 코드의 현재 위치가 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5670f-107">When a `Yield` statement is reached, the current location in code is retained.</span></span> <span data-ttu-id="5670f-108">다음에 반복기 함수가 호출되면 해당 위치에서 실행이 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="5670f-108">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="5670f-109">함수 또는 반복기를 구현할 수 있습니다는 `Get` 속성 정의의 접근자입니다.</span><span class="sxs-lookup"><span data-stu-id="5670f-109">An iterator can be implemented as a function or as a `Get` accessor of a property definition.</span></span> <span data-ttu-id="5670f-110">합니다 `Iterator` 반복기 함수 선언에 표시 되는 한정자 또는 `Get` 접근자입니다.</span><span class="sxs-lookup"><span data-stu-id="5670f-110">The `Iterator` modifier appears in the declaration of the iterator function or `Get` accessor.</span></span>  
  
 <span data-ttu-id="5670f-111">사용 하 여 클라이언트 코드에서 반복기를 호출 하는 [각각에 대 한 중... 다음 문을](../../../visual-basic/language-reference/statements/for-each-next-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5670f-111">You call an iterator from client code by using a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
 <span data-ttu-id="5670f-112">반복기 함수의 반환 형식 또는 `Get` 접근자 수 <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>합니다 <xref:System.Collections.IEnumerator>, 또는 <xref:System.Collections.Generic.IEnumerator%601>합니다.</span><span class="sxs-lookup"><span data-stu-id="5670f-112">The return type of an iterator function or `Get` accessor can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="5670f-113">반복기를 사용할 수 없습니다 `ByRef` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="5670f-113">An iterator cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="5670f-114">반복기는 이벤트, 인스턴스 생성자, 정적 생성자 또는 정적 소멸자에서 발생할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5670f-114">An iterator cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="5670f-115">반복기는 익명 함수를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5670f-115">An iterator can be an anonymous function.</span></span> <span data-ttu-id="5670f-116">자세한 내용은 [반복기](../../programming-guide/concepts/iterators.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5670f-116">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="usage"></a><span data-ttu-id="5670f-117">사용법</span><span class="sxs-lookup"><span data-stu-id="5670f-117">Usage</span></span>  
 <span data-ttu-id="5670f-118">`Iterator` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5670f-118">The `Iterator` modifier can be used in these contexts:</span></span>  
  
- [<span data-ttu-id="5670f-119">Function 문</span><span class="sxs-lookup"><span data-stu-id="5670f-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
- [<span data-ttu-id="5670f-120">Property 문</span><span class="sxs-lookup"><span data-stu-id="5670f-120">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="example"></a><span data-ttu-id="5670f-121">예제</span><span class="sxs-lookup"><span data-stu-id="5670f-121">Example</span></span>  
 <span data-ttu-id="5670f-122">다음 예제에서는 반복기 함수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5670f-122">The following example demonstrates an iterator function.</span></span> <span data-ttu-id="5670f-123">반복기 함수에는 `Yield` 문 내에 있는 [에 대 한 중... 다음](../../../visual-basic/language-reference/statements/for-next-statement.md) 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="5670f-123">The iterator function has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="5670f-124">각 반복 합니다 [각각에 대 한](../../../visual-basic/language-reference/statements/for-each-next-statement.md) 문의 본문 `Main` 대 한 호출이 생성를 `Power` 반복기 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="5670f-124">Each iteration of the [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="5670f-125">반복기 함수를 호출할 때마다 다음에 `Yield` 루프를 반복하는 도중에 `For…Next` 문이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="5670f-125">Each call to the iterator function proceeds to the next execution of the `Yield` statement, which occurs during the next iteration of the `For…Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a><span data-ttu-id="5670f-126">예제</span><span class="sxs-lookup"><span data-stu-id="5670f-126">Example</span></span>  
 <span data-ttu-id="5670f-127">다음 예제는 반복기인 `Get` 접근자에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5670f-127">The following example demonstrates a `Get` accessor that is an iterator.</span></span> <span data-ttu-id="5670f-128">`Iterator` 속성 선언에서 한정자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5670f-128">The `Iterator` modifier is in the property declaration.</span></span>  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 <span data-ttu-id="5670f-129">추가 예제를 보려면 [반복기](../../programming-guide/concepts/iterators.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5670f-129">For additional examples, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5670f-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="5670f-130">See also</span></span>

- <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>
- [<span data-ttu-id="5670f-131">반복기</span><span class="sxs-lookup"><span data-stu-id="5670f-131">Iterators</span></span>](../../programming-guide/concepts/iterators.md)
- [<span data-ttu-id="5670f-132">Yield 문</span><span class="sxs-lookup"><span data-stu-id="5670f-132">Yield Statement</span></span>](../../../visual-basic/language-reference/statements/yield-statement.md)
