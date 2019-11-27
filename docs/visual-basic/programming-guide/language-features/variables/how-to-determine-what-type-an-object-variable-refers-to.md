---
title: '방법: 개체 변수가 참조하는 형식 확인'
ms.date: 07/20/2015
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
ms.openlocfilehash: 9f9b89e2fea0bd69cba6d50fa1d1fb9cc3927685
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348608"
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a><span data-ttu-id="3b430-102">방법: 개체 변수가 참조하는 형식 확인(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3b430-102">How to: Determine What Type an Object Variable Refers To (Visual Basic)</span></span>

<span data-ttu-id="3b430-103">개체 변수는 다른 곳에 저장 된 데이터에 대 한 포인터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b430-103">An object variable contains a pointer to data that is stored elsewhere.</span></span> <span data-ttu-id="3b430-104">런타임에 변경 될 수 있는 데이터의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3b430-104">The type of that data can change during run time.</span></span> <span data-ttu-id="3b430-105">언제 든 지 <xref:System.Type.GetTypeCode%2A> 메서드를 사용 하 여 현재 런타임 형식을 확인 하거나 [TypeOf 연산자](../../../../visual-basic/language-reference/operators/typeof-operator.md) 를 사용 하 여 현재 런타임 형식이 지정 된 형식과 호환 되는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b430-105">At any moment, you can use the <xref:System.Type.GetTypeCode%2A> method to determine the current run-time type, or the [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) to find out if the current run-time type is compatible with a specified type.</span></span>

### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a><span data-ttu-id="3b430-106">개체 변수가 현재 참조 하는 정확한 형식을 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="3b430-106">To determine the exact type an object variable currently refers to</span></span>

1. <span data-ttu-id="3b430-107">개체 변수에서 <xref:System.Object.GetType%2A> 메서드를 호출 하 여 <xref:System.Type?displayProperty=nameWithType> 개체를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b430-107">On the object variable, call the <xref:System.Object.GetType%2A> method to retrieve a <xref:System.Type?displayProperty=nameWithType> object.</span></span>

    ```vb
    Dim myObject As Object
    myObject.GetType()
    ```

2. <span data-ttu-id="3b430-108"><xref:System.Type?displayProperty=nameWithType> 클래스에서 공유 메서드 <xref:System.Type.GetTypeCode%2A>를 호출 하 여 개체의 형식에 대 한 <xref:System.TypeCode> 열거형 값을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b430-108">On the <xref:System.Type?displayProperty=nameWithType> class, call the shared method <xref:System.Type.GetTypeCode%2A> to retrieve the <xref:System.TypeCode> enumeration value for the object's type.</span></span>

    ```vb
    Dim myObject As Object
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())
    MsgBox("myObject currently has type code " & CStr(datTyp))
    ```

    <span data-ttu-id="3b430-109">`Double`와 같이 관심 있는 열거형 멤버에 대 한 <xref:System.TypeCode> 열거형 값을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b430-109">You can test the <xref:System.TypeCode> enumeration value against whichever enumeration members are of interest, such as `Double`.</span></span>

### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a><span data-ttu-id="3b430-110">개체 변수의 형식이 지정 된 형식과 호환 되는지 여부를 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="3b430-110">To determine whether an object variable's type is compatible with a specified type</span></span>

- <span data-ttu-id="3b430-111">[Is 연산자](../../../../visual-basic/language-reference/operators/is-operator.md) 와 함께 `TypeOf` 연산자를 사용 하 여 `TypeOf`...`Is` 식으로 개체를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b430-111">Use the `TypeOf` operator in combination with the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) to test the object with a `TypeOf`...`Is` expression.</span></span>

    ```vb
    If TypeOf objA Is System.Windows.Forms.Control Then
        MsgBox("objA is compatible with the Control class")
    End If
    ```

    <span data-ttu-id="3b430-112">`TypeOf`...`Is` 식은 개체의 런타임 형식이 지정 된 형식과 호환 되는 경우 `True`를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b430-112">The `TypeOf`...`Is` expression returns `True` if the object's run-time type is compatible with the specified type.</span></span>

    <span data-ttu-id="3b430-113">호환성 기준은 지정 된 형식이 클래스, 구조체 또는 인터페이스 인지에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="3b430-113">The criterion for compatibility depends on whether the specified type is a class, structure, or interface.</span></span> <span data-ttu-id="3b430-114">일반적으로이 형식은 개체가와 동일한 형식 이거나,에서 상속 되거나, 지정 된 형식을 구현 하는 경우 호환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b430-114">In general, the types are compatible if the object is of the same type as, inherits from, or implements the specified type.</span></span> <span data-ttu-id="3b430-115">자세한 내용은 [TypeOf 연산자](../../../../visual-basic/language-reference/operators/typeof-operator.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3b430-115">For more information, see [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="3b430-116">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="3b430-116">Compiling the Code</span></span>

<span data-ttu-id="3b430-117">지정 된 형식은 변수나 식일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b430-117">Note that the specified type cannot be a variable or expression.</span></span> <span data-ttu-id="3b430-118">클래스, 구조체 또는 인터페이스와 같은 정의 된 형식의 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b430-118">It must be the name of a defined type, such as a class, structure, or interface.</span></span> <span data-ttu-id="3b430-119">여기에는 `Integer` 및 `String`와 같은 내장 형식이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b430-119">This includes intrinsic types such as `Integer` and `String`.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b430-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3b430-120">See also</span></span>

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.GetTypeCode%2A>
- <xref:System.TypeCode>
- [<span data-ttu-id="3b430-121">개체 변수</span><span class="sxs-lookup"><span data-stu-id="3b430-121">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="3b430-122">개체 변수 값</span><span class="sxs-lookup"><span data-stu-id="3b430-122">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="3b430-123">Object 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3b430-123">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
