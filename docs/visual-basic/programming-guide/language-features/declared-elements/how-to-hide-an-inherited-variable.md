---
title: '방법: 상속된 된 변수 (Visual Basic) 숨기기'
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
ms.openlocfilehash: 2b052b44043deba85c8b142a2bf1a684c1159809
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842514"
---
# <a name="how-to-hide-an-inherited-variable-visual-basic"></a><span data-ttu-id="7e119-102">방법: 상속된 된 변수 (Visual Basic) 숨기기</span><span class="sxs-lookup"><span data-stu-id="7e119-102">How to: Hide an Inherited Variable (Visual Basic)</span></span>
<span data-ttu-id="7e119-103">파생된 클래스는 기본 클래스의 모든 정의 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="7e119-103">A derived class inherits all the definitions of its base class.</span></span> <span data-ttu-id="7e119-104">기본 클래스의 요소와 동일한 이름으로 변수를 정의 하려는 경우 숨길 수 있습니다, 또는 *섀도*, 파생된 클래스에서 변수를 정의할 때 해당 기본 클래스 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7e119-104">If you want to define a variable using the same name as an element of the base class, you can hide, or *shadow*, that base class element when you define your variable in the derived class.</span></span> <span data-ttu-id="7e119-105">이 작업을 수행 하는 경우 파생된 클래스에서 코드 숨김 메커니즘을 명시적으로 무시 되지 않는 한 변수를 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e119-105">If you do this, code in the derived class accesses your variable unless it explicitly bypasses the shadowing mechanism.</span></span>  
  
 <span data-ttu-id="7e119-106">기본 클래스 수정에 대 한 보호는 또 다른 이유는 상속 된 변수를 숨기는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7e119-106">Another reason you might want to hide an inherited variable is to protect against base class revision.</span></span> <span data-ttu-id="7e119-107">기본 클래스를 상속 하는 요소를 변경 하는 변경을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e119-107">The base class might undergo a change that alters the element you are inheriting.</span></span> <span data-ttu-id="7e119-108">이 경우는 `Shadows` 한정자를 사용 하면 확인할 변수로 대신 기본 클래스 요소에 파생된 클래스에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e119-108">If this happens, the `Shadows` modifier forces references from the derived class to be resolved to your variable, instead of to the base class element.</span></span>  
  
### <a name="to-hide-an-inherited-variable"></a><span data-ttu-id="7e119-109">상속된 된 변수를 숨기려면</span><span class="sxs-lookup"><span data-stu-id="7e119-109">To hide an inherited variable</span></span>  
  
1.  <span data-ttu-id="7e119-110">숨기려는 변수가 (프로시저) 외부 클래스 수준에서 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e119-110">Be sure the variable you want to hide is declared at class level (outside any procedure).</span></span> <span data-ttu-id="7e119-111">그렇지 않은 경우 숨길 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7e119-111">Otherwise you do not need to hide it.</span></span>  
  
2.  <span data-ttu-id="7e119-112">파생된 클래스 내에서 작성 한 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md) 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e119-112">Inside your derived class, write a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) declaring your variable.</span></span> <span data-ttu-id="7e119-113">상속 된 변수는 동일한 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e119-113">Use the same name as that of the inherited variable.</span></span>  
  
3.  <span data-ttu-id="7e119-114">포함 된 [그림자](../../../../visual-basic/language-reference/modifiers/shadows.md) 선언에서 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="7e119-114">Include the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in the declaration.</span></span>  
  
     <span data-ttu-id="7e119-115">변수 이름에도 다른 여러 가지 파생된 클래스에서 코드를 참조 하는 경우 컴파일러는 변수에 대 한 참조를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e119-115">When code in the derived class refers to the variable name, the compiler resolves the reference to your variable.</span></span>  
  
     <span data-ttu-id="7e119-116">다음 예제에서는 상속 된 변수 숨기기</span><span class="sxs-lookup"><span data-stu-id="7e119-116">The following example illustrates shadowing of an inherited variable.</span></span>  
  
    ```  
    Public Class shadowBaseClass  
        Public shadowString As String = "This is the base class string."  
    End Class  
    Public Class shadowDerivedClass  
        Inherits shadowBaseClass  
        Public Shadows shadowString As String = "This is the derived class string."  
        Public Sub showStrings()  
            Dim s As String = "Unqualified shadowString: " & shadowString &  
                vbCrLf & "MyBase.shadowString: " & MyBase.shadowString  
            MsgBox(s)  
        End Sub  
    End Class  
    ```  
  
     <span data-ttu-id="7e119-117">앞의 예제는 변수를 선언 `shadowString` 기본 클래스에서 파생된 클래스에서이 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="7e119-117">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="7e119-118">절차 `showStrings` 파생된 클래스에서 문자열의 숨김 버전을 표시 하면 이름을 `shadowString` 한정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e119-118">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="7e119-119">다음 숨겨진된 버전을 표시 하면 `shadowString` 으로 한정 됩니다는 `MyBase` 키워드.</span><span class="sxs-lookup"><span data-stu-id="7e119-119">It then displays the shadowed version when `shadowString` is qualified with the `MyBase` keyword.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="7e119-120">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="7e119-120">Robust Programming</span></span>  
 <span data-ttu-id="7e119-121">숨김 변수 이름이 같은 둘 이상의 버전을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="7e119-121">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="7e119-122">코드 문이 변수 이름에는 참조, 컴파일러 참조를 확인 하는 버전 코드 문의 위치 및 한정 문자열의 현재 상태 등의 요인에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="7e119-122">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="7e119-123">숨겨진 변수의 의도 하지 않은 버전으로 참조 위험이 증가 수이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e119-123">This can increase the risk of referring to an unintended version of a shadowed variable.</span></span> <span data-ttu-id="7e119-124">숨겨진된 변수에 대 한 모든 참조를 정규화 하 여 위험을 낮출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e119-124">You can lower that risk by fully qualifying all references to a shadowed variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e119-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="7e119-125">See also</span></span>

- [<span data-ttu-id="7e119-126">선언된 요소 참조</span><span class="sxs-lookup"><span data-stu-id="7e119-126">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="7e119-127">Visual Basic의 숨김 기능</span><span class="sxs-lookup"><span data-stu-id="7e119-127">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="7e119-128">숨기기와 재정의의 차이점</span><span class="sxs-lookup"><span data-stu-id="7e119-128">Differences Between Shadowing and Overriding</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [<span data-ttu-id="7e119-129">방법: 변수 이름이 같은 변수 숨기기</span><span class="sxs-lookup"><span data-stu-id="7e119-129">How to: Hide a Variable with the Same Name as Your Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [<span data-ttu-id="7e119-130">방법: 파생된 클래스에 의해 숨겨진 변수에 액세스</span><span class="sxs-lookup"><span data-stu-id="7e119-130">How to: Access a Variable Hidden by a Derived Class</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)
- [<span data-ttu-id="7e119-131">재정의</span><span class="sxs-lookup"><span data-stu-id="7e119-131">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="7e119-132">Me, My, MyBase 및 MyClass</span><span class="sxs-lookup"><span data-stu-id="7e119-132">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="7e119-133">상속 기본 사항</span><span class="sxs-lookup"><span data-stu-id="7e119-133">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
