---
title: 반복기
ms.date: 07/20/2015
f1_keywords:
- vb.Iterator
helpviewer_keywords:
- Iterator keyword [Visual Basic]
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
ms.openlocfilehash: 9d7eaf186bae544031487ce027505e1e0d4ae0f3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351532"
---
# <a name="iterator-visual-basic"></a><span data-ttu-id="da895-102">반복기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="da895-102">Iterator (Visual Basic)</span></span>
<span data-ttu-id="da895-103">함수 또는 `Get` 접근자가 반복기 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="da895-103">Specifies that a function or `Get` accessor is an iterator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da895-104">설명</span><span class="sxs-lookup"><span data-stu-id="da895-104">Remarks</span></span>  
 <span data-ttu-id="da895-105">*반복기* 는 컬렉션에 대해 사용자 지정 반복을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="da895-105">An *iterator* performs a custom iteration over a collection.</span></span> <span data-ttu-id="da895-106">반복기는 [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) 문을 사용 하 여 컬렉션의 각 요소를 한 번에 하나씩 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="da895-106">An iterator uses the [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) statement to return each element in the collection one at a time.</span></span> <span data-ttu-id="da895-107">`Yield` 문에 도달 하면 코드의 현재 위치가 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da895-107">When a `Yield` statement is reached, the current location in code is retained.</span></span> <span data-ttu-id="da895-108">다음에 반복기 함수가 호출되면 해당 위치에서 실행이 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="da895-108">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="da895-109">반복기는 함수 또는 속성 정의의 `Get` 접근자로 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da895-109">An iterator can be implemented as a function or as a `Get` accessor of a property definition.</span></span> <span data-ttu-id="da895-110">`Iterator` 한정자는 반복기 함수 또는 `Get` 접근자의 선언에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="da895-110">The `Iterator` modifier appears in the declaration of the iterator function or `Get` accessor.</span></span>  
  
 <span data-ttu-id="da895-111">For Each ...를 사용 하 여 클라이언트 코드에서 반복기를 호출 합니다. [ 다음 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="da895-111">You call an iterator from client code by using a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
 <span data-ttu-id="da895-112">반복기 함수 또는 `Get` 접근자의 반환 형식은 <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>또는 <xref:System.Collections.Generic.IEnumerator%601>수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da895-112">The return type of an iterator function or `Get` accessor can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="da895-113">반복기에는 `ByRef` 매개 변수를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da895-113">An iterator cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="da895-114">반복기는 이벤트, 인스턴스 생성자, 정적 생성자 또는 정적 소멸자에서 발생할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da895-114">An iterator cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="da895-115">반복기는 익명 함수 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da895-115">An iterator can be an anonymous function.</span></span> <span data-ttu-id="da895-116">자세한 내용은 [반복기](../../programming-guide/concepts/iterators.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="da895-116">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="usage"></a><span data-ttu-id="da895-117">사용법</span><span class="sxs-lookup"><span data-stu-id="da895-117">Usage</span></span>  
 <span data-ttu-id="da895-118">`Iterator` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da895-118">The `Iterator` modifier can be used in these contexts:</span></span>  
  
- [<span data-ttu-id="da895-119">Function 문</span><span class="sxs-lookup"><span data-stu-id="da895-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
- [<span data-ttu-id="da895-120">Property 문</span><span class="sxs-lookup"><span data-stu-id="da895-120">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="example"></a><span data-ttu-id="da895-121">예제</span><span class="sxs-lookup"><span data-stu-id="da895-121">Example</span></span>  
 <span data-ttu-id="da895-122">다음 예제에서는 반복기 함수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="da895-122">The following example demonstrates an iterator function.</span></span> <span data-ttu-id="da895-123">반복기 함수에는 [에 대 한 `Yield` 문이 있습니다. Next](../../../visual-basic/language-reference/statements/for-next-statement.md) 루프.</span><span class="sxs-lookup"><span data-stu-id="da895-123">The iterator function has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="da895-124">`Main`의 각 문 본문 [에 대 한](../../../visual-basic/language-reference/statements/for-each-next-statement.md) 각 반복은 `Power` 반복기 함수에 대 한 호출을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="da895-124">Each iteration of the [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="da895-125">반복기 함수를 호출할 때마다 다음에 `Yield` 루프를 반복하는 도중에 `For…Next` 문이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="da895-125">Each call to the iterator function proceeds to the next execution of the `Yield` statement, which occurs during the next iteration of the `For…Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a><span data-ttu-id="da895-126">예제</span><span class="sxs-lookup"><span data-stu-id="da895-126">Example</span></span>  
 <span data-ttu-id="da895-127">다음 예제는 반복기인 `Get` 접근자에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="da895-127">The following example demonstrates a `Get` accessor that is an iterator.</span></span> <span data-ttu-id="da895-128">`Iterator` 한정자는 속성 선언에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da895-128">The `Iterator` modifier is in the property declaration.</span></span>  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 <span data-ttu-id="da895-129">추가 예제는 [반복기](../../programming-guide/concepts/iterators.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="da895-129">For additional examples, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da895-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="da895-130">See also</span></span>

- <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>
- [<span data-ttu-id="da895-131">반복기</span><span class="sxs-lookup"><span data-stu-id="da895-131">Iterators</span></span>](../../programming-guide/concepts/iterators.md)
- [<span data-ttu-id="da895-132">Yield 문</span><span class="sxs-lookup"><span data-stu-id="da895-132">Yield Statement</span></span>](../../../visual-basic/language-reference/statements/yield-statement.md)
