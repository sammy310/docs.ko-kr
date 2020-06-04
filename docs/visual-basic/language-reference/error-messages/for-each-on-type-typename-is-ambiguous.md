---
title: "'<typename>' 형식은 'System.Collections.Generic.IEnumerable(Of T)'의 여러 인스턴스를 구현하므로 이 형식의 'For Each'가 모호합니다."
ms.date: 07/20/2015
f1_keywords:
- vbc32096
- bc32096
helpviewer_keywords:
- BC32096
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
ms.openlocfilehash: 153a2640d66f48660f21339aaf0ecc8eaa10f51f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402968"
---
# <a name="for-each-on-type-typename-is-ambiguous-because-the-type-implements-multiple-instantiations-of-systemcollectionsgenericienumerableof-t"></a><span data-ttu-id="fdb97-102">'\<typename>' 형식은 'System.Collections.Generic.IEnumerable(Of T)'의 여러 인스턴스를 구현하므로 이 형식의 'For Each'가 모호합니다.</span><span class="sxs-lookup"><span data-stu-id="fdb97-102">'For Each' on type '\<typename>' is ambiguous because the type implements multiple instantiations of 'System.Collections.Generic.IEnumerable(Of T)'</span></span>
<span data-ttu-id="fdb97-103">`For Each`문이 둘 이상의 메서드를 포함 하는 반복기 변수를 지정 합니다 <xref:System.Collections.IEnumerable.GetEnumerator%2A> .</span><span class="sxs-lookup"><span data-stu-id="fdb97-103">A `For Each` statement specifies an iterator variable that has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span>  
  
 <span data-ttu-id="fdb97-104">반복기 변수는 <xref:System.Collections.IEnumerable?displayProperty=nameWithType> <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> .NET Framework 네임 스페이스 중 하나에서 또는 인터페이스를 구현 하는 형식 이어야 합니다 `Collections` .</span><span class="sxs-lookup"><span data-stu-id="fdb97-104">The iterator variable must be of a type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface in one of the `Collections` namespaces of the .NET Framework.</span></span> <span data-ttu-id="fdb97-105">클래스에서 각 생성에 대해 다른 형식 인수를 사용 하 여 생성 된 제네릭 인터페이스를 둘 이상 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdb97-105">It is possible for a class to implement more than one constructed generic interface, using a different type argument for each construction.</span></span> <span data-ttu-id="fdb97-106">이를 수행 하는 클래스가 반복기 변수에 사용 되는 경우 해당 변수에 둘 이상의 <xref:System.Collections.IEnumerable.GetEnumerator%2A> 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdb97-106">If a class that does this is used for the iterator variable, that variable has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span> <span data-ttu-id="fdb97-107">이 경우 Visual Basic 호출할 메서드를 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fdb97-107">In such a case, Visual Basic cannot choose which method to call.</span></span>  
  
 <span data-ttu-id="fdb97-108">**오류 ID:** BC32096</span><span class="sxs-lookup"><span data-stu-id="fdb97-108">**Error ID:** BC32096</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fdb97-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="fdb97-109">To correct this error</span></span>  
  
- <span data-ttu-id="fdb97-110">[DirectCast operator](../operators/directcast-operator.md) 또는 [TryCast 연산자](../operators/trycast-operator.md) 를 사용 하 여 반복기 변수 형식을 사용 하려는 메서드를 정의 하는 인터페이스로 캐스팅 합니다 <xref:System.Collections.IEnumerable.GetEnumerator%2A> .</span><span class="sxs-lookup"><span data-stu-id="fdb97-110">Use [DirectCast Operator](../operators/directcast-operator.md) or [TryCast Operator](../operators/trycast-operator.md) to cast the iterator variable type to the interface defining the <xref:System.Collections.IEnumerable.GetEnumerator%2A> method you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdb97-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fdb97-111">See also</span></span>

- [<span data-ttu-id="fdb97-112">For Each...Next 문</span><span class="sxs-lookup"><span data-stu-id="fdb97-112">For Each...Next Statement</span></span>](../statements/for-each-next-statement.md)
- [<span data-ttu-id="fdb97-113">인터페이스</span><span class="sxs-lookup"><span data-stu-id="fdb97-113">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
