---
title: '방법: 개체 변수 (Visual Basic)를 참조 형식 확인'
ms.date: 07/20/2015
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
ms.openlocfilehash: 6499dfce880cc9ce16e5d77887afc0598692f48e
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59342871"
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a><span data-ttu-id="2d137-102">방법: 개체 변수 (Visual Basic)를 참조 형식 확인</span><span class="sxs-lookup"><span data-stu-id="2d137-102">How to: Determine What Type an Object Variable Refers To (Visual Basic)</span></span>
<span data-ttu-id="2d137-103">개체 변수를 다른 곳에 저장 된 데이터에 대 한 포인터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d137-103">An object variable contains a pointer to data that is stored elsewhere.</span></span> <span data-ttu-id="2d137-104">런타임에 해당 데이터 형식을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d137-104">The type of that data can change during run time.</span></span> <span data-ttu-id="2d137-105">언제 든 지 사용할 수 있습니다는 <xref:System.Type.GetTypeCode%2A> , 현재 런타임 형식을 확인 하는 방법 또는 [TypeOf 연산자](../../../../visual-basic/language-reference/operators/typeof-operator.md) 런타임 형식 현재 확인 하려면 지정된 된 형식과 호환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d137-105">At any moment, you can use the <xref:System.Type.GetTypeCode%2A> method to determine the current run-time type, or the [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) to find out if the current run-time type is compatible with a specified type.</span></span>  
  
### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a><span data-ttu-id="2d137-106">참조 형식을 결정 하려면 정확한 개체 변수에 현재</span><span class="sxs-lookup"><span data-stu-id="2d137-106">To determine the exact type an object variable currently refers to</span></span>  
  
1. <span data-ttu-id="2d137-107">개체 변수를 호출 합니다 <xref:System.Object.GetType%2A> 검색 하는 메서드를 <xref:System.Type?displayProperty=nameWithType> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="2d137-107">On the object variable, call the <xref:System.Object.GetType%2A> method to retrieve a <xref:System.Type?displayProperty=nameWithType> object.</span></span>  
  
    ```  
    Dim myObject As Object  
    myObject.GetType()  
    ```  
  
2. <span data-ttu-id="2d137-108">에 <xref:System.Type?displayProperty=nameWithType> 클래스, 메서드 호출 하 여 공유 <xref:System.Type.GetTypeCode%2A> 검색할를 <xref:System.TypeCode> 개체의 형식에 대 한 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2d137-108">On the <xref:System.Type?displayProperty=nameWithType> class, call the shared method <xref:System.Type.GetTypeCode%2A> to retrieve the <xref:System.TypeCode> enumeration value for the object's type.</span></span>  
  
    ```  
    Dim myObject As Object  
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())  
    MsgBox("myObject currently has type code " & CStr(datTyp))  
    ```  
  
     <span data-ttu-id="2d137-109">테스트할 수 있습니다 합니다 <xref:System.TypeCode> 열거형 값과 같은 관심는 모든 열거형 멤버에 대해 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="2d137-109">You can test the <xref:System.TypeCode> enumeration value against whichever enumeration members are of interest, such as `Double`.</span></span>  
  
### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a><span data-ttu-id="2d137-110">개체 여부를 확인 하려면 변수의 형식이 호환 지정된 된 형식</span><span class="sxs-lookup"><span data-stu-id="2d137-110">To determine whether an object variable's type is compatible with a specified type</span></span>  
  
-   <span data-ttu-id="2d137-111">사용 하 여는 `TypeOf` 연산자와 조합 하는 [Is 연산자](../../../../visual-basic/language-reference/operators/is-operator.md) 사용 하 여 개체를 테스트 하려면를 `TypeOf`... `Is` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="2d137-111">Use the `TypeOf` operator in combination with the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) to test the object with a `TypeOf`...`Is` expression.</span></span>  
  
    ```  
    If TypeOf objA Is System.Windows.Forms.Control Then  
        MsgBox("objA is compatible with the Control class")  
    End If  
    ```  
  
     <span data-ttu-id="2d137-112">`TypeOf`... `Is` 식 반환 `True` 개체의 런타임 형식은 지정 된 형식과 호환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d137-112">The `TypeOf`...`Is` expression returns `True` if the object's run-time type is compatible with the specified type.</span></span>  
  
     <span data-ttu-id="2d137-113">호환성에 대 한 조건은 클래스, 구조체 또는 인터페이스에 지정된 된 형식 인지에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="2d137-113">The criterion for compatibility depends on whether the specified type is a class, structure, or interface.</span></span> <span data-ttu-id="2d137-114">일반적으로 형식은 호환 개체와 동일한 형식이에서 상속 하거나 지정 된 형식을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d137-114">In general, the types are compatible if the object is of the same type as, inherits from, or implements the specified type.</span></span> <span data-ttu-id="2d137-115">자세한 내용은 [TypeOf 연산자](../../../../visual-basic/language-reference/operators/typeof-operator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2d137-115">For more information, see [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2d137-116">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="2d137-116">Compiling the Code</span></span>  
 <span data-ttu-id="2d137-117">참고는 지정된 된 형식의 변수 또는 식 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2d137-117">Note that the specified type cannot be a variable or expression.</span></span> <span data-ttu-id="2d137-118">클래스, 구조체 또는 인터페이스와 같은 정의 된 유형의 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d137-118">It must be the name of a defined type, such as a class, structure, or interface.</span></span> <span data-ttu-id="2d137-119">여기에 내장 형식이 같은 `Integer` 고 `String`입니다.</span><span class="sxs-lookup"><span data-stu-id="2d137-119">This includes intrinsic types such as `Integer` and `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d137-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="2d137-120">See also</span></span>

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.GetTypeCode%2A>
- <xref:System.TypeCode>
- [<span data-ttu-id="2d137-121">개체 변수</span><span class="sxs-lookup"><span data-stu-id="2d137-121">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="2d137-122">개체 변수 값</span><span class="sxs-lookup"><span data-stu-id="2d137-122">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="2d137-123">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="2d137-123">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
