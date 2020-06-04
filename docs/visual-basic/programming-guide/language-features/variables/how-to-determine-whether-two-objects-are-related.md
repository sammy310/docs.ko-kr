---
title: '방법: 두 개체가 관련이 있는지 확인'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: 30e88a21e737aa57513745899577381ed34151a2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410466"
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a><span data-ttu-id="d9a29-102">방법: 두 개체가 관련이 있는지 확인(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9a29-102">How to: Determine Whether Two Objects Are Related (Visual Basic)</span></span>

<span data-ttu-id="d9a29-103">두 개체를 비교 하 여 해당 관계 (있는 경우)가 생성 된 클래스 간의 관계를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9a29-103">You can compare two objects to determine the relationship, if any, between the classes from which they are created.</span></span> <span data-ttu-id="d9a29-104"><xref:System.Type.IsInstanceOfType%2A>클래스의 메서드는 <xref:System.Type?displayProperty=nameWithType> `True` 지정 된 클래스가 현재 클래스에서 상속 되는 경우를 반환 하 고, 현재 형식이 지정 된 클래스에서 지 원하는 인터페이스인 경우를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a29-104">The <xref:System.Type.IsInstanceOfType%2A> method of the <xref:System.Type?displayProperty=nameWithType> class returns `True` if the specified class inherits from the current class, or if the current type is an interface supported by the specified class.</span></span>

### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a><span data-ttu-id="d9a29-105">한 개체가 다른 개체의 클래스 또는 인터페이스에서 상속 되는지 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="d9a29-105">To determine if one object inherits from another object's class or interface</span></span>

1. <span data-ttu-id="d9a29-106">기본 형식인 것으로 생각 되는 개체에서 메서드를 호출 <xref:System.Object.GetType%2A> 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a29-106">On the object you think might be of the base type, invoke the <xref:System.Object.GetType%2A> method.</span></span>

2. <span data-ttu-id="d9a29-107"><xref:System.Type?displayProperty=nameWithType>에서 반환 하는 개체에서 메서드를 호출 합니다 <xref:System.Object.GetType%2A> <xref:System.Type.IsInstanceOfType%2A> .</span><span class="sxs-lookup"><span data-stu-id="d9a29-107">On the <xref:System.Type?displayProperty=nameWithType> object returned by <xref:System.Object.GetType%2A>, invoke the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>

3. <span data-ttu-id="d9a29-108">에 대 한 인수 목록에서 <xref:System.Type.IsInstanceOfType%2A> 파생 된 형식으로 생각 되는 개체를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a29-108">In the argument list for <xref:System.Type.IsInstanceOfType%2A>, specify the object you think might be of the derived type.</span></span>

    <span data-ttu-id="d9a29-109"><xref:System.Type.IsInstanceOfType%2A>`True`해당 인수 형식이 개체 형식에서 상속 될 경우을 반환 <xref:System.Type?displayProperty=nameWithType> 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a29-109"><xref:System.Type.IsInstanceOfType%2A> returns `True` if its argument type inherits from the <xref:System.Type?displayProperty=nameWithType> object type.</span></span>

## <a name="example"></a><span data-ttu-id="d9a29-110">예제</span><span class="sxs-lookup"><span data-stu-id="d9a29-110">Example</span></span>
 <span data-ttu-id="d9a29-111">다음 예제에서는 한 개체가 다른 개체의 클래스에서 파생 된 클래스를 나타내는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9a29-111">The following example determines whether one object represents a class derived from another object's class.</span></span>

```vb
Public Class baseClass
End Class
Public Class derivedClass : Inherits baseClass
End Class
Public Class testTheseClasses
    Public Sub seeIfRelated()
        Dim baseObj As Object = New baseClass()
        Dim derivedObj As Object = New derivedClass()
        Dim related As Boolean
        related = baseObj.GetType().IsInstanceOfType(derivedObj)
        MsgBox(CStr(related))
    End Sub
End Class
```

<span data-ttu-id="d9a29-112">호출에서 두 개체 변수의 예기치 않은 배치를 확인 합니다 <xref:System.Type.IsInstanceOfType%2A> .</span><span class="sxs-lookup"><span data-stu-id="d9a29-112">Note the unexpected placement of the two object variables in the call to <xref:System.Type.IsInstanceOfType%2A>.</span></span> <span data-ttu-id="d9a29-113">예상 되는 기본 형식은 클래스를 생성 하는 데 사용 되 <xref:System.Type?displayProperty=nameWithType> 고, 예상 되는 파생 형식은 메서드에 인수로 전달 됩니다 <xref:System.Type.IsInstanceOfType%2A> .</span><span class="sxs-lookup"><span data-stu-id="d9a29-113">The supposed base type is used to generate the <xref:System.Type?displayProperty=nameWithType> class, and the supposed derived type is passed as an argument to the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>

## <a name="see-also"></a><span data-ttu-id="d9a29-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d9a29-114">See also</span></span>

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.IsInstanceOfType%2A>
- [<span data-ttu-id="d9a29-115">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="d9a29-115">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="d9a29-116">개체 변수</span><span class="sxs-lookup"><span data-stu-id="d9a29-116">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="d9a29-117">개체 변수 값</span><span class="sxs-lookup"><span data-stu-id="d9a29-117">Object Variable Values</span></span>](object-variable-values.md)
- [<span data-ttu-id="d9a29-118">방법: 두 개체가 동일한지 확인</span><span class="sxs-lookup"><span data-stu-id="d9a29-118">How to: Determine Whether Two Objects Are Identical</span></span>](how-to-determine-whether-two-objects-are-identical.md)
