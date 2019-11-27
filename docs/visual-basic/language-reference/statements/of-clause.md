---
title: Of 절
ms.date: 07/20/2015
f1_keywords:
- Of
- vb.Of
- vb.of
helpviewer_keywords:
- Of keyword [Visual Basic]
- arguments [Visual Basic], data types
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- parameters [Visual Basic], type
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- type parameters
- data type arguments
ms.assetid: 0db8f65c-65af-4089-ab7f-6fcfecb60444
ms.openlocfilehash: d88c43efe858d6b81b7d8d2470b234ff5d40632a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353835"
---
# <a name="of-clause-visual-basic"></a><span data-ttu-id="d34c6-102">Of 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d34c6-102">Of Clause (Visual Basic)</span></span>
<span data-ttu-id="d34c6-103">*제네릭* 클래스, 구조체, 인터페이스, 대리자 또는 프로시저에서 *형식 매개 변수* 를 식별 하는 `Of` 절을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="d34c6-103">Introduces an `Of` clause, which identifies a *type parameter* on a *generic* class, structure, interface, delegate, or procedure.</span></span> <span data-ttu-id="d34c6-104">제네릭 형식에 대 한 자세한 내용은 [Visual Basic의 제네릭 형식](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d34c6-104">For information on generic types, see [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span>  
  
## <a name="using-the-of-keyword"></a><span data-ttu-id="d34c6-105">Of 키워드 사용</span><span class="sxs-lookup"><span data-stu-id="d34c6-105">Using the Of Keyword</span></span>  
 <span data-ttu-id="d34c6-106">다음 코드 예제에서는 `Of` 키워드를 사용 하 여 두 개의 형식 매개 변수를 사용 하는 클래스의 개요를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d34c6-106">The following code example uses the `Of` keyword to define the outline of a class that takes two type parameters.</span></span> <span data-ttu-id="d34c6-107"><xref:System.IComparable> 인터페이스를 사용 하 여 `keyType` 매개 변수를 *제한* 합니다. 즉, 사용 하는 코드에서 <xref:System.IComparable>를 구현 하는 형식 인수를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d34c6-107">It *constrains* the `keyType` parameter by the <xref:System.IComparable> interface, which means the consuming code must supply a type argument that implements <xref:System.IComparable>.</span></span> <span data-ttu-id="d34c6-108">`add` 프로시저가 <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> 메서드를 호출할 수 있도록이 작업이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d34c6-108">This is necessary so that the `add` procedure can call the <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="d34c6-109">제약 조건에 대한 자세한 내용은 [Type List](../../../visual-basic/language-reference/statements/type-list.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d34c6-109">For more information on constraints, see [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
```vb  
Public Class Dictionary(Of entryType, keyType As IComparable)  
    Public Sub add(ByVal e As entryType, ByVal k As keyType)  
        Dim dk As keyType  
        If k.CompareTo(dk) = 0 Then  
        End If  
    End Sub  
    Public Function find(ByVal k As keyType) As entryType  
    End Function  
End Class  
```  
  
 <span data-ttu-id="d34c6-110">위의 클래스 정의를 완료 하는 경우 여기에서 다양 한 `dictionary` 클래스를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d34c6-110">If you complete the preceding class definition, you can construct a variety of `dictionary` classes from it.</span></span> <span data-ttu-id="d34c6-111">`entryType` 및 `keyType`에 제공 하는 형식은 클래스에서 보유 하는 항목의 형식과 각 항목에 연결 하는 키 형식을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d34c6-111">The types you supply to `entryType` and `keyType` determine what type of entry the class holds and what type of key it associates with each entry.</span></span> <span data-ttu-id="d34c6-112">제약 조건 때문에 <xref:System.IComparable>를 구현 하는 형식을 `keyType`를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d34c6-112">Because of the constraint, you must supply to `keyType` a type that implements <xref:System.IComparable>.</span></span>  
  
 <span data-ttu-id="d34c6-113">다음 코드 예제에서는 `String` 항목을 보유 하는 개체를 만들고 `Integer` 키를 각각 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="d34c6-113">The following code example creates an object that holds `String` entries and associates an `Integer` key with each one.</span></span> <span data-ttu-id="d34c6-114">`Integer`는 <xref:System.IComparable>를 구현 하므로 `keyType`의 제약 조건을 충족 합니다.</span><span class="sxs-lookup"><span data-stu-id="d34c6-114">`Integer` implements <xref:System.IComparable> and therefore satisfies the constraint on `keyType`.</span></span>  
  
```vb  
Dim d As New dictionary(Of String, Integer)  
```  
  
 <span data-ttu-id="d34c6-115">`Of` 키워드는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d34c6-115">The `Of` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="d34c6-116">Class 문</span><span class="sxs-lookup"><span data-stu-id="d34c6-116">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="d34c6-117">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="d34c6-117">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="d34c6-118">Function 문</span><span class="sxs-lookup"><span data-stu-id="d34c6-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="d34c6-119">Interface 문</span><span class="sxs-lookup"><span data-stu-id="d34c6-119">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="d34c6-120">Structure 문</span><span class="sxs-lookup"><span data-stu-id="d34c6-120">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="d34c6-121">Sub 문</span><span class="sxs-lookup"><span data-stu-id="d34c6-121">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="d34c6-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d34c6-122">See also</span></span>

- <xref:System.IComparable>
- [<span data-ttu-id="d34c6-123">형식 목록</span><span class="sxs-lookup"><span data-stu-id="d34c6-123">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="d34c6-124">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d34c6-124">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="d34c6-125">In</span><span class="sxs-lookup"><span data-stu-id="d34c6-125">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [<span data-ttu-id="d34c6-126">Out</span><span class="sxs-lookup"><span data-stu-id="d34c6-126">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
