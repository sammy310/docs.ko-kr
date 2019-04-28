---
title: Of 절(Visual Basic)
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
ms.openlocfilehash: 880570c714292b0c11eef4e2cd4c4b410bb075f1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61784152"
---
# <a name="of-clause-visual-basic"></a><span data-ttu-id="4e2b7-102">Of 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e2b7-102">Of Clause (Visual Basic)</span></span>
<span data-ttu-id="4e2b7-103">소개는 `Of` 식별 하는 절을 *형식 매개 변수* 에 *제네릭* 클래스, 구조체, 인터페이스, 대리자 또는 프로시저.</span><span class="sxs-lookup"><span data-stu-id="4e2b7-103">Introduces an `Of` clause, which identifies a *type parameter* on a *generic* class, structure, interface, delegate, or procedure.</span></span> <span data-ttu-id="4e2b7-104">제네릭 형식에 대 한 자세한 내용은 [Visual Basic의 제네릭 형식](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4e2b7-104">For information on generic types, see [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span>  
  
## <a name="using-the-of-keyword"></a><span data-ttu-id="4e2b7-105">사용 하는 키워드</span><span class="sxs-lookup"><span data-stu-id="4e2b7-105">Using the Of Keyword</span></span>  
 <span data-ttu-id="4e2b7-106">다음 코드 예제에서는 `Of` 두 형식 매개 변수를 사용 하는 클래스의 윤곽선을 정의 하는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="4e2b7-106">The following code example uses the `Of` keyword to define the outline of a class that takes two type parameters.</span></span> <span data-ttu-id="4e2b7-107">것 *제한* 는 `keyType` 매개 변수를 <xref:System.IComparable> 인터페이스를 사용 하는 코드를 구현 하는 형식 인수를 제공 해야 합니다 즉 <xref:System.IComparable>.</span><span class="sxs-lookup"><span data-stu-id="4e2b7-107">It *constrains* the `keyType` parameter by the <xref:System.IComparable> interface, which means the consuming code must supply a type argument that implements <xref:System.IComparable>.</span></span> <span data-ttu-id="4e2b7-108">이 작업은 필요 있도록 합니다 `add` 프로시저를 호출할 수는 <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="4e2b7-108">This is necessary so that the `add` procedure can call the <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="4e2b7-109">제약 조건에 대한 자세한 내용은 [Type List](../../../visual-basic/language-reference/statements/type-list.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e2b7-109">For more information on constraints, see [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
```  
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
  
 <span data-ttu-id="4e2b7-110">위의 클래스 정의 완료 하는 경우에 다양 한을 생성할 수 있습니다 `dictionary` 에서 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4e2b7-110">If you complete the preceding class definition, you can construct a variety of `dictionary` classes from it.</span></span> <span data-ttu-id="4e2b7-111">제공 하는 형식을 `entryType` 및 `keyType` 어떤 유형의 항목 클래스를 보유 하 고 각 항목에 연결 하는 키의 형식을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e2b7-111">The types you supply to `entryType` and `keyType` determine what type of entry the class holds and what type of key it associates with each entry.</span></span> <span data-ttu-id="4e2b7-112">제공 해야는 제약 조건으로 인해 `keyType` 구현 하는 형식을 <xref:System.IComparable>합니다.</span><span class="sxs-lookup"><span data-stu-id="4e2b7-112">Because of the constraint, you must supply to `keyType` a type that implements <xref:System.IComparable>.</span></span>  
  
 <span data-ttu-id="4e2b7-113">다음 코드 예제를 보유 하는 개체를 만듭니다 `String` 항목과 연결 된 `Integer` 각각 키입니다.</span><span class="sxs-lookup"><span data-stu-id="4e2b7-113">The following code example creates an object that holds `String` entries and associates an `Integer` key with each one.</span></span> <span data-ttu-id="4e2b7-114">`Integer` 구현 <xref:System.IComparable> 따라서에서 제약 조건을 만족 하 고 `keyType`입니다.</span><span class="sxs-lookup"><span data-stu-id="4e2b7-114">`Integer` implements <xref:System.IComparable> and therefore satisfies the constraint on `keyType`.</span></span>  
  
```  
Dim d As New dictionary(Of String, Integer)  
```  
  
 <span data-ttu-id="4e2b7-115">`Of` 키워드는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e2b7-115">The `Of` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="4e2b7-116">Class 문</span><span class="sxs-lookup"><span data-stu-id="4e2b7-116">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="4e2b7-117">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="4e2b7-117">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="4e2b7-118">Function 문</span><span class="sxs-lookup"><span data-stu-id="4e2b7-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="4e2b7-119">Interface 문</span><span class="sxs-lookup"><span data-stu-id="4e2b7-119">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="4e2b7-120">Structure 문</span><span class="sxs-lookup"><span data-stu-id="4e2b7-120">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="4e2b7-121">Sub 문</span><span class="sxs-lookup"><span data-stu-id="4e2b7-121">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="4e2b7-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="4e2b7-122">See also</span></span>

- <xref:System.IComparable>
- [<span data-ttu-id="4e2b7-123">형식 목록</span><span class="sxs-lookup"><span data-stu-id="4e2b7-123">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="4e2b7-124">Visual Basic의 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="4e2b7-124">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="4e2b7-125">In</span><span class="sxs-lookup"><span data-stu-id="4e2b7-125">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [<span data-ttu-id="4e2b7-126">Out</span><span class="sxs-lookup"><span data-stu-id="4e2b7-126">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
