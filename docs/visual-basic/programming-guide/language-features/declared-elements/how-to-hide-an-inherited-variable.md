---
description: '자세히 알아보기: 방법: 상속 된 변수 숨기기 (Visual Basic)'
title: '방법: 상속된 변수 숨기기'
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declaration statements [Visual Basic], declared elements
- referencing declared elements [Visual Basic]
- declared elements [Visual Basic], referencing
- declared elements [Visual Basic], about declared elements
- variables [Visual Basic], hiding inherited
ms.assetid: 765728d9-7351-4a30-999d-b5f34f024412
ms.openlocfilehash: be2de980e27b318151c795ae36bd92a01d47d55e
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100429899"
---
# <a name="how-to-hide-an-inherited-variable-visual-basic"></a><span data-ttu-id="994a8-103">방법: 상속된 변수 숨기기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="994a8-103">How to: Hide an Inherited Variable (Visual Basic)</span></span>

<span data-ttu-id="994a8-104">파생 클래스는 기본 클래스의 모든 정의를 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="994a8-104">A derived class inherits all the definitions of its base class.</span></span> <span data-ttu-id="994a8-105">기본 클래스의 요소와 같은 이름을 사용 하 여 변수를 정의 하려면 파생 클래스에서 변수를 정의할 때 기본 클래스 요소 *를 숨기 거 나 숨길* 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="994a8-105">If you want to define a variable using the same name as an element of the base class, you can hide, or *shadow*, that base class element when you define your variable in the derived class.</span></span> <span data-ttu-id="994a8-106">이 작업을 수행 하는 경우 파생 클래스의 코드는 숨기는 메커니즘을 명시적으로 우회 하지 않는 한 변수에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="994a8-106">If you do this, code in the derived class accesses your variable unless it explicitly bypasses the shadowing mechanism.</span></span>

<span data-ttu-id="994a8-107">상속 된 변수를 숨기려는 또 다른 이유는 기본 클래스 수정 버전 으로부터 보호 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="994a8-107">Another reason you might want to hide an inherited variable is to protect against base class revision.</span></span> <span data-ttu-id="994a8-108">기본 클래스는 상속 하는 요소를 변경 하는 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="994a8-108">The base class might undergo a change that alters the element you are inheriting.</span></span> <span data-ttu-id="994a8-109">이 경우 `Shadows` 한정자는 파생 클래스의 참조를 기본 클래스 요소가 아니라 변수로 확인 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="994a8-109">If this happens, the `Shadows` modifier forces references from the derived class to be resolved to your variable, instead of to the base class element.</span></span>

## <a name="to-hide-an-inherited-variable"></a><span data-ttu-id="994a8-110">상속 된 변수를 숨기려면</span><span class="sxs-lookup"><span data-stu-id="994a8-110">To hide an inherited variable</span></span>

1. <span data-ttu-id="994a8-111">숨기려는 변수가 클래스 수준 (프로시저 외부)에서 선언 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="994a8-111">Be sure the variable you want to hide is declared at class level (outside any procedure).</span></span> <span data-ttu-id="994a8-112">그렇지 않으면 숨길 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="994a8-112">Otherwise, you do not need to hide it.</span></span>
  
2. <span data-ttu-id="994a8-113">파생 클래스 내에서 변수를 선언 하는 [Dim 문을](../../../language-reference/statements/dim-statement.md) 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="994a8-113">Inside your derived class, write a [Dim Statement](../../../language-reference/statements/dim-statement.md) declaring your variable.</span></span> <span data-ttu-id="994a8-114">상속 된 변수의 이름과 동일한 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="994a8-114">Use the same name as that of the inherited variable.</span></span>

3. <span data-ttu-id="994a8-115">선언에 [Shadows](../../../language-reference/modifiers/shadows.md) 키워드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="994a8-115">Include the [Shadows](../../../language-reference/modifiers/shadows.md) keyword in the declaration.</span></span>

     <span data-ttu-id="994a8-116">파생 클래스의 코드가 변수 이름을 참조 하는 경우 컴파일러는 변수에 대 한 참조를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="994a8-116">When code in the derived class refers to the variable name, the compiler resolves the reference to your variable.</span></span>

     <span data-ttu-id="994a8-117">다음 예에서는 상속 된 변수를 숨기는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="994a8-117">The following example illustrates shadowing of an inherited variable:</span></span>
  
    ```vb  
    Public Class ShadowBaseClass  
        Public shadowString As String = "This is the base class string."  
    End Class  
    Public Class ShadowDerivedClass  
        Inherits ShadowBaseClass  
        Public Shadows shadowString As String = "This is the derived class string."  
        Public Sub ShowStrings()  
            Dim s As String = $"Unqualified shadowString: {shadowString}{vbCrLf}MyBase.shadowString: {MyBase.shadowString}"
            MsgBox(s)  
        End Sub  
    End Class  
    ```  
  
     <span data-ttu-id="994a8-118">앞의 예제에서는 `shadowString` 기본 클래스에서 변수를 선언 하 고 파생 클래스에서 해당 변수를 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="994a8-118">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="994a8-119">`ShowStrings`파생 클래스의 프로시저는 이름이 한정 되지 않은 경우 문자열의 숨김 버전을 표시 합니다 `shadowString` .</span><span class="sxs-lookup"><span data-stu-id="994a8-119">The procedure `ShowStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="994a8-120">그런 다음 `shadowString` 키워드를 사용 하 여 정규화 된 버전을 표시 `MyBase` 합니다.</span><span class="sxs-lookup"><span data-stu-id="994a8-120">It then displays the shadowed version when `shadowString` is qualified with the `MyBase` keyword.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="994a8-121">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="994a8-121">Robust programming</span></span>

<span data-ttu-id="994a8-122">섀도잉 시 이름이 같은 변수의 버전이 두 개 이상 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="994a8-122">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="994a8-123">코드 문이 변수 이름을 참조 하는 경우 컴파일러가 참조를 확인 하는 버전은 코드 문의 위치 및 한정 된 문자열이 있는지 여부와 같은 요소에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="994a8-123">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="994a8-124">이로 인해 숨겨진 변수의 의도 하지 않은 버전을 참조 하는 위험이 늘어날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="994a8-124">This can increase the risk of referring to an unintended version of a shadowed variable.</span></span> <span data-ttu-id="994a8-125">숨겨진 변수에 대 한 모든 참조를 정규화 하 여이 위험을 낮출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="994a8-125">You can lower that risk by fully qualifying all references to a shadowed variable.</span></span>

## <a name="see-also"></a><span data-ttu-id="994a8-126">추가 정보</span><span class="sxs-lookup"><span data-stu-id="994a8-126">See also</span></span>

- [<span data-ttu-id="994a8-127">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="994a8-127">References to Declared Elements</span></span>](references-to-declared-elements.md)
- [<span data-ttu-id="994a8-128">Visual Basic에서 숨김</span><span class="sxs-lookup"><span data-stu-id="994a8-128">Shadowing in Visual Basic</span></span>](shadowing.md)
- [<span data-ttu-id="994a8-129">섀도잉과 재정의 간의 차이점</span><span class="sxs-lookup"><span data-stu-id="994a8-129">Differences Between Shadowing and Overriding</span></span>](differences-between-shadowing-and-overriding.md)
- [<span data-ttu-id="994a8-130">방법: 사용자 변수와 이름이 같은 변수 숨기기</span><span class="sxs-lookup"><span data-stu-id="994a8-130">How to: Hide a Variable with the Same Name as Your Variable</span></span>](how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [<span data-ttu-id="994a8-131">방법: 파생 클래스에 의해 숨겨진 변수에 액세스</span><span class="sxs-lookup"><span data-stu-id="994a8-131">How to: Access a Variable Hidden by a Derived Class</span></span>](how-to-access-a-variable-hidden-by-a-derived-class.md)
- [<span data-ttu-id="994a8-132">재정의</span><span class="sxs-lookup"><span data-stu-id="994a8-132">Overrides</span></span>](../../../language-reference/modifiers/overrides.md)
- [<span data-ttu-id="994a8-133">Me, My, MyBase 및 MyClass</span><span class="sxs-lookup"><span data-stu-id="994a8-133">Me, My, MyBase, and MyClass</span></span>](../../program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="994a8-134">상속 기본 사항</span><span class="sxs-lookup"><span data-stu-id="994a8-134">Inheritance Basics</span></span>](../objects-and-classes/inheritance-basics.md)
