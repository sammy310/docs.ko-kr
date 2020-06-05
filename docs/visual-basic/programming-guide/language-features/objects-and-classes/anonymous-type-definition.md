---
title: 익명 형식 정의
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [Visual Basic], type definition
ms.assetid: 7a8a0ddc-55ba-4d67-869e-87a84d938bac
ms.openlocfilehash: 952eb295cc71eab5d0ad6e18f2b697a9b701b434
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404903"
---
# <a name="anonymous-type-definition-visual-basic"></a><span data-ttu-id="b9b9d-102">익명 형식 정의(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b9b9d-102">Anonymous Type Definition (Visual Basic)</span></span>

<span data-ttu-id="b9b9d-103">익명 형식의 인스턴스 선언에 대 한 응답으로 컴파일러는 해당 형식에 대해 지정 된 속성을 포함 하는 새 클래스 정의를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b9b9d-103">In response to the declaration of an instance of an anonymous type, the compiler creates a new class definition that contains the specified properties for the type.</span></span>

## <a name="compiler-generated-code"></a><span data-ttu-id="b9b9d-104">컴파일러 생성 코드</span><span class="sxs-lookup"><span data-stu-id="b9b9d-104">Compiler-Generated Code</span></span>

<span data-ttu-id="b9b9d-105">다음 정의의 경우 `product` 컴파일러는, 및 속성을 포함 하는 새 클래스 정의를 만듭니다 `Name` `Price` `OnHand` .</span><span class="sxs-lookup"><span data-stu-id="b9b9d-105">For the following definition of `product`, the compiler creates a new class definition that contains properties `Name`, `Price`, and `OnHand`.</span></span>

[!code-vb[VbVbalrAnonymousTypes#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#25)]

<span data-ttu-id="b9b9d-106">클래스 정의에는 다음과 유사한 속성 정의가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9b9d-106">The class definition contains property definitions similar to the following.</span></span> <span data-ttu-id="b9b9d-107">`Set`키 속성에 대 한 메서드가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b9b9d-107">Notice that there is no `Set` method for the key properties.</span></span> <span data-ttu-id="b9b9d-108">키 속성의 값은 읽기 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b9d-108">The values of key properties are read-only.</span></span>

```vb
Public Class $Anonymous1
    Private _name As String
    Private _price As Double
    Private _onHand As Integer
     Public ReadOnly Property Name() As String
        Get
            Return _name
        End Get
    End Property

    Public ReadOnly Property Price() As Double
        Get
            Return _price
        End Get
    End Property

    Public Property OnHand() As Integer
        Get
            Return _onHand
        End Get
        Set(ByVal Value As Integer)
            _onHand = Value
        End Set
    End Property

End Class
```

<span data-ttu-id="b9b9d-109">또한 익명 형식 정의에는 매개 변수가 없는 생성자가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9b9d-109">In addition, anonymous type definitions contain a parameterless constructor.</span></span> <span data-ttu-id="b9b9d-110">매개 변수를 필요로 하는 생성자는 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b9b9d-110">Constructors that require parameters are not permitted.</span></span>

<span data-ttu-id="b9b9d-111">익명 형식 선언에 하나 이상의 키 속성이 포함 된 경우 형식 정의는 <xref:System.Object> <xref:System.Object.Equals%2A> , <xref:System.Object.GetHashCode%2A> 및에서 상속 된 세 개의 멤버를 재정의 <xref:System.Object.ToString%2A> 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9b9d-111">If an anonymous type declaration contains at least one key property, the type definition overrides three members inherited from <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, and <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="b9b9d-112">키 속성이 선언 되지 않은 경우만 <xref:System.Object.ToString%2A> 재정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9b9d-112">If no key properties are declared, only <xref:System.Object.ToString%2A> is overridden.</span></span> <span data-ttu-id="b9b9d-113">재정의는 다음과 같은 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9b9d-113">The overrides provide the following functionality:</span></span>

- <span data-ttu-id="b9b9d-114">`Equals``True`두 익명 형식 인스턴스가 동일한 인스턴스이거나 다음 조건을 충족 하는 경우를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9b9d-114">`Equals` returns `True` if two anonymous type instances are the same instance, or if they meet the following conditions:</span></span>

  - <span data-ttu-id="b9b9d-115">속성의 수는 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9b9d-115">They have the same number of properties.</span></span>

  - <span data-ttu-id="b9b9d-116">속성은 같은 순서로 선언 되며 동일한 이름 및 유추 된 형식이 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9b9d-116">The properties are declared in the same order, with the same names and the same inferred types.</span></span> <span data-ttu-id="b9b9d-117">이름 비교는 대/소문자를 구분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b9b9d-117">Name comparisons are not case-sensitive.</span></span>

  - <span data-ttu-id="b9b9d-118">속성 중 하나 이상이 키 속성 이며 `Key` 키워드는 동일한 속성에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9b9d-118">At least one of the properties is a key property, and the `Key` keyword is applied to the same properties.</span></span>

  - <span data-ttu-id="b9b9d-119">각 해당 키 속성 쌍의 비교는를 반환 `True` 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9b9d-119">Comparison of each corresponding pair of key properties returns `True`.</span></span>

    <span data-ttu-id="b9b9d-120">예를 들어 다음 예제에서는 `Equals` `True` 및에 대해서만를 반환 합니다 `employee01` `employee08` .</span><span class="sxs-lookup"><span data-stu-id="b9b9d-120">For example, in the following examples, `Equals` returns `True` only for `employee01` and `employee08`.</span></span> <span data-ttu-id="b9b9d-121">각 줄 앞의 주석은 새 인스턴스가 일치 하지 않는 이유를 지정 합니다 `employee01` .</span><span class="sxs-lookup"><span data-stu-id="b9b9d-121">The comment before each line specifies the reason why the new instance does not match `employee01`.</span></span>

    [!code-vb[VbVbalrAnonymousTypes#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#24)]

- <span data-ttu-id="b9b9d-122">`GetHashcode`적절 한 고유 GetHashCode 알고리즘을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9b9d-122">`GetHashcode` provides an appropriately unique GetHashCode algorithm.</span></span> <span data-ttu-id="b9b9d-123">알고리즘은 키 속성만 사용 하 여 해시 코드를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9b9d-123">The algorithm uses only the key properties to compute the hash code.</span></span>

- <span data-ttu-id="b9b9d-124">`ToString`다음 예제와 같이 연결 된 속성 값의 문자열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9b9d-124">`ToString` returns a string of concatenated property values, as shown in the following example.</span></span> <span data-ttu-id="b9b9d-125">키와 키가 아닌 속성은 모두 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9b9d-125">Both key and non-key properties are included.</span></span>

  [!code-vb[VbVbalrAnonymousTypes#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#29)]

<span data-ttu-id="b9b9d-126">익명 형식의 명시적으로 명명 된 속성은 이러한 생성 된 메서드와 충돌할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b9b9d-126">Explicitly named properties of an anonymous type cannot conflict with these generated methods.</span></span> <span data-ttu-id="b9b9d-127">즉,, 또는를 사용 `.Equals` `.GetHashCode` `.ToString` 하 여 속성의 이름을 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b9b9d-127">That is, you cannot use `.Equals`, `.GetHashCode`, or `.ToString` to name a property.</span></span>

<span data-ttu-id="b9b9d-128">하나 이상의 키 속성을 포함 하는 익명 형식 정의도 인터페이스를 구현 합니다 <xref:System.IEquatable%601?displayProperty=nameWithType> `T` . 여기서은 익명 형식의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b9d-128">Anonymous type definitions that include at least one key property also implement the <xref:System.IEquatable%601?displayProperty=nameWithType> interface, where `T` is the type of the anonymous type.</span></span>

> [!NOTE]
> <span data-ttu-id="b9b9d-129">익명 형식 선언은 동일한 어셈블리에서 발생 하는 경우에만 동일한 익명 형식을 만들며, 해당 속성은 동일한 이름 및 유추 된 형식을 가지 며 속성은 동일한 순서로 선언 되며 동일한 속성이 키 속성으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9b9d-129">Anonymous type declarations create the same anonymous type only if they occur in the same assembly, their properties have the same names and the same inferred types, the properties are declared in the same order, and the same properties are marked as key properties.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9b9d-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b9b9d-130">See also</span></span>

- [<span data-ttu-id="b9b9d-131">익명 형식</span><span class="sxs-lookup"><span data-stu-id="b9b9d-131">Anonymous Types</span></span>](anonymous-types.md)
- [<span data-ttu-id="b9b9d-132">방법: 익명 형식 선언에서 속성 이름 및 형식 유추</span><span class="sxs-lookup"><span data-stu-id="b9b9d-132">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
