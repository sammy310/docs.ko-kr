---
description: '자세히 알아보기: Of 절 (Visual Basic)'
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
ms.openlocfilehash: d6002041a2fe8db5b07e12e9e396a65fde30b716
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768846"
---
# <a name="of-clause-visual-basic"></a><span data-ttu-id="77ef0-103">Of 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77ef0-103">Of Clause (Visual Basic)</span></span>

<span data-ttu-id="77ef0-104">`Of` *제네릭* 클래스, 구조체, 인터페이스, 대리자 또는 프로시저에서 *형식 매개 변수* 를 식별 하는 절을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="77ef0-104">Introduces an `Of` clause, which identifies a *type parameter* on a *generic* class, structure, interface, delegate, or procedure.</span></span> <span data-ttu-id="77ef0-105">제네릭 형식에 대 한 자세한 내용은 [Visual Basic의 제네릭 형식](../../programming-guide/language-features/data-types/generic-types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="77ef0-105">For information on generic types, see [Generic Types in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md).</span></span>  
  
## <a name="using-the-of-keyword"></a><span data-ttu-id="77ef0-106">Of 키워드 사용</span><span class="sxs-lookup"><span data-stu-id="77ef0-106">Using the Of Keyword</span></span>  

 <span data-ttu-id="77ef0-107">다음 코드 예제에서는 키워드를 사용 하 여 `Of` 두 개의 형식 매개 변수를 사용 하는 클래스의 개요를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="77ef0-107">The following code example uses the `Of` keyword to define the outline of a class that takes two type parameters.</span></span> <span data-ttu-id="77ef0-108">인터페이스를 사용 하 여 매개 변수를 *제한* 합니다. 즉,를 사용 하는 `keyType` <xref:System.IComparable> 코드에서을 구현 하는 형식 인수를 제공 해야 합니다 <xref:System.IComparable> .</span><span class="sxs-lookup"><span data-stu-id="77ef0-108">It *constrains* the `keyType` parameter by the <xref:System.IComparable> interface, which means the consuming code must supply a type argument that implements <xref:System.IComparable>.</span></span> <span data-ttu-id="77ef0-109">프로시저에서 메서드를 호출할 수 있도록이 작업이 필요 `add` <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> 합니다.</span><span class="sxs-lookup"><span data-stu-id="77ef0-109">This is necessary so that the `add` procedure can call the <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="77ef0-110">제약 조건에 대한 자세한 내용은 [Type List](type-list.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="77ef0-110">For more information on constraints, see [Type List](type-list.md).</span></span>  
  
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
  
 <span data-ttu-id="77ef0-111">위의 클래스 정의를 완료 하는 경우 여기에서 다양 한 클래스를 생성할 수 있습니다 `dictionary` .</span><span class="sxs-lookup"><span data-stu-id="77ef0-111">If you complete the preceding class definition, you can construct a variety of `dictionary` classes from it.</span></span> <span data-ttu-id="77ef0-112">사용자가 제공 하는 `entryType` 형식과 `keyType` 클래스에서 보유 하는 항목 형식 및 각 항목과 연결 되는 키 형식에 대해 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="77ef0-112">The types you supply to `entryType` and `keyType` determine what type of entry the class holds and what type of key it associates with each entry.</span></span> <span data-ttu-id="77ef0-113">제약 조건 때문에를 `keyType` 구현 하는 형식에를 제공 해야 합니다 <xref:System.IComparable> .</span><span class="sxs-lookup"><span data-stu-id="77ef0-113">Because of the constraint, you must supply to `keyType` a type that implements <xref:System.IComparable>.</span></span>  
  
 <span data-ttu-id="77ef0-114">다음 코드 예제에서는 항목을 보유 하는 개체를 만들고 `String` 각 항목에 대 한 키를 연결 합니다 `Integer` .</span><span class="sxs-lookup"><span data-stu-id="77ef0-114">The following code example creates an object that holds `String` entries and associates an `Integer` key with each one.</span></span> <span data-ttu-id="77ef0-115">`Integer` 는를 구현 <xref:System.IComparable> 하므로에서 제약 조건을 충족 `keyType` 합니다.</span><span class="sxs-lookup"><span data-stu-id="77ef0-115">`Integer` implements <xref:System.IComparable> and therefore satisfies the constraint on `keyType`.</span></span>  
  
```vb  
Dim d As New dictionary(Of String, Integer)  
```  
  
 <span data-ttu-id="77ef0-116">`Of` 키워드는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77ef0-116">The `Of` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="77ef0-117">Class 문</span><span class="sxs-lookup"><span data-stu-id="77ef0-117">Class Statement</span></span>](class-statement.md)  
  
 [<span data-ttu-id="77ef0-118">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="77ef0-118">Delegate Statement</span></span>](delegate-statement.md)  
  
 [<span data-ttu-id="77ef0-119">Function 문</span><span class="sxs-lookup"><span data-stu-id="77ef0-119">Function Statement</span></span>](function-statement.md)  
  
 [<span data-ttu-id="77ef0-120">Interface 문</span><span class="sxs-lookup"><span data-stu-id="77ef0-120">Interface Statement</span></span>](interface-statement.md)  
  
 [<span data-ttu-id="77ef0-121">Structure 문</span><span class="sxs-lookup"><span data-stu-id="77ef0-121">Structure Statement</span></span>](structure-statement.md)  
  
 [<span data-ttu-id="77ef0-122">Sub 문</span><span class="sxs-lookup"><span data-stu-id="77ef0-122">Sub Statement</span></span>](sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="77ef0-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="77ef0-123">See also</span></span>

- <xref:System.IComparable>
- [<span data-ttu-id="77ef0-124">Type List</span><span class="sxs-lookup"><span data-stu-id="77ef0-124">Type List</span></span>](type-list.md)
- [<span data-ttu-id="77ef0-125">Visual Basic의 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="77ef0-125">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="77ef0-126">위치</span><span class="sxs-lookup"><span data-stu-id="77ef0-126">In</span></span>](../modifiers/in-generic-modifier.md)
- [<span data-ttu-id="77ef0-127">Out</span><span class="sxs-lookup"><span data-stu-id="77ef0-127">Out</span></span>](../modifiers/out-generic-modifier.md)
