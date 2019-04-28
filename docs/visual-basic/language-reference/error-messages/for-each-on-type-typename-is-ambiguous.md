---
title: "'<typename>' 형식은 'System.Collections.Generic.IEnumerable(Of T)'의 여러 인스턴스를 구현하므로 이 형식의 'For Each'가 모호합니다."
ms.date: 07/20/2015
f1_keywords:
- vbc32096
- bc32096
helpviewer_keywords:
- BC32096
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
ms.openlocfilehash: 6c34ca43decc3c5d8c72b529d8f51d7cc3b0c6b3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61801467"
---
# <a name="for-each-on-type-typename-is-ambiguous-because-the-type-implements-multiple-instantiations-of-systemcollectionsgenericienumerableof-t"></a><span data-ttu-id="92143-102">'For Each' 형식에 '\<typename >' 형식을 'System.Collections.Generic.IEnumerable (Of T)'의 여러 인스턴스화를 구현 하기 때문에 모호</span><span class="sxs-lookup"><span data-stu-id="92143-102">'For Each' on type '\<typename>' is ambiguous because the type implements multiple instantiations of 'System.Collections.Generic.IEnumerable(Of T)'</span></span>
<span data-ttu-id="92143-103">A `For Each` 둘 이상 있는 반복기 변수를 지정 하는 문을 <xref:System.Collections.IEnumerable.GetEnumerator%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="92143-103">A `For Each` statement specifies an iterator variable that has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span>  
  
 <span data-ttu-id="92143-104">반복기 변수를 구현 하는 형식 이어야 합니다는 <xref:System.Collections.IEnumerable?displayProperty=nameWithType> 또는 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> 인터페이스 중 하나에 `Collections` 의 네임 스페이스는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="92143-104">The iterator variable must be of a type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface in one of the `Collections` namespaces of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="92143-105">둘 이상의 생성 된 제네릭 인터페이스를 각 생성에 대 한 다양 한 형식 인수를 사용 하 여 구현 하는 클래스에 대 한 것 같습니다.</span><span class="sxs-lookup"><span data-stu-id="92143-105">It is possible for a class to implement more than one constructed generic interface, using a different type argument for each construction.</span></span> <span data-ttu-id="92143-106">이 작업을 수행 하는 클래스에서 반복기 변수를 사용 하는 경우 해당 변수가 둘 이상의 <xref:System.Collections.IEnumerable.GetEnumerator%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="92143-106">If a class that does this is used for the iterator variable, that variable has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span> <span data-ttu-id="92143-107">이러한 경우 Visual Basic 호출할 메서드를 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="92143-107">In such a case, Visual Basic cannot choose which method to call.</span></span>  
  
 <span data-ttu-id="92143-108">**오류 ID:** BC32096</span><span class="sxs-lookup"><span data-stu-id="92143-108">**Error ID:** BC32096</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="92143-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="92143-109">To correct this error</span></span>  
  
- <span data-ttu-id="92143-110">사용 하 여 [DirectCast 연산자](../../../visual-basic/language-reference/operators/directcast-operator.md) 또는 [TryCast 연산자](../../../visual-basic/language-reference/operators/trycast-operator.md) 정의 하는 인터페이스를 반복기 변수 형식으로 캐스팅할는 <xref:System.Collections.IEnumerable.GetEnumerator%2A> 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="92143-110">Use [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) or [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) to cast the iterator variable type to the interface defining the <xref:System.Collections.IEnumerable.GetEnumerator%2A> method you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92143-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="92143-111">See also</span></span>

- [<span data-ttu-id="92143-112">For Each...Next 문</span><span class="sxs-lookup"><span data-stu-id="92143-112">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="92143-113">인터페이스</span><span class="sxs-lookup"><span data-stu-id="92143-113">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
