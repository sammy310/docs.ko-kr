---
title: '방법: 파생된 클래스 (Visual Basic)에 의해 숨겨진 변수에 액세스'
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- base classes [Visual Basic], accessing elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declared elements [Visual Basic], referencing
- variables [Visual Basic], accessing hidden
ms.assetid: ae21a8ac-9cd4-4fba-a3ec-ecc4321ef93c
ms.openlocfilehash: a97a51d4570d87eaa873fb3152ad810f528dff46
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61829662"
---
# <a name="how-to-access-a-variable-hidden-by-a-derived-class-visual-basic"></a><span data-ttu-id="0c120-102">방법: 파생된 클래스 (Visual Basic)에 의해 숨겨진 변수에 액세스</span><span class="sxs-lookup"><span data-stu-id="0c120-102">How to: Access a Variable Hidden by a Derived Class (Visual Basic)</span></span>
<span data-ttu-id="0c120-103">변수에 액세스 하는 파생된 클래스에서 코드를 컴파일러가 파생 단계의 이전 버전과 액세스 하는 클래스에서 액세스할 수 있는 버전 즉, 가장 가까운 액세스할 수 있는 버전에 대 한 참조에 확인 일반적으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c120-103">When code in a derived class accesses a variable, the compiler normally resolves the reference to the closest accessible version, that is, the accessible version the fewest derivational steps backward from the accessing class.</span></span> <span data-ttu-id="0c120-104">파생된 클래스에서 변수를 정의 하는 경우 코드에 일반적으로 해당 정의 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c120-104">If the variable is defined in the derived class, the code normally accesses that definition.</span></span>  
  
 <span data-ttu-id="0c120-105">파생된 클래스 변수의 기본 클래스에서 변수를 숨기면이 기본 클래스 버전을 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="0c120-105">If the derived class variable shadows a variable in the base class, it hides the base class version.</span></span> <span data-ttu-id="0c120-106">한정 하면 기본 클래스 변수에 액세스할 수는 있지만 `MyBase` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="0c120-106">However, you can access the base class variable by qualifying it with the `MyBase` keyword.</span></span>  
  
### <a name="to-access-a-base-class-variable-hidden-by-a-derived-class"></a><span data-ttu-id="0c120-107">파생된 클래스에 의해 숨겨진 기본 클래스 변수에 액세스</span><span class="sxs-lookup"><span data-stu-id="0c120-107">To access a base class variable hidden by a derived class</span></span>  
  
-   <span data-ttu-id="0c120-108">식 또는 대입문, 변수 이름 앞에 야 합니다 `MyBase` 키워드와 마침표 (`.`).</span><span class="sxs-lookup"><span data-stu-id="0c120-108">In an expression or assignment statement, precede the variable name with the `MyBase` keyword and a period (`.`).</span></span>  
  
     <span data-ttu-id="0c120-109">컴파일러는 변수의 기본 클래스 버전에 대 한 참조를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0c120-109">The compiler resolves the reference to the base class version of the variable.</span></span>  
  
     <span data-ttu-id="0c120-110">다음 예제에서는 상속을 통한 숨김 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0c120-110">The following example illustrates shadowing through inheritance.</span></span> <span data-ttu-id="0c120-111">두 참조가 숨기는 변수에 액세스 하는, 하나는 숨기기를 무시 하는 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c120-111">It makes two references, one that accesses the shadowing variable and one that bypasses the shadowing.</span></span>  
  
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
  
     <span data-ttu-id="0c120-112">앞의 예제는 변수를 선언 `shadowString` 기본 클래스에서 파생된 클래스에서이 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="0c120-112">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="0c120-113">절차 `showStrings` 파생된 클래스에서 문자열의 숨김 버전을 표시 하면 이름을 `shadowString` 한정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c120-113">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="0c120-114">다음 숨겨진된 버전을 표시 하면 `shadowString` 으로 한정 됩니다는 `MyBase` 키워드.</span><span class="sxs-lookup"><span data-stu-id="0c120-114">It then displays the shadowed version when `shadowString` is qualified with the `MyBase`  keyword.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="0c120-115">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="0c120-115">Robust Programming</span></span>  
 <span data-ttu-id="0c120-116">위험을 낮추기 위해서는 숨겨진 변수의 의도 하지 않은 버전에 대 한 참조를 완전히 숨겨진된 변수에 대 한 모든 참조를 한정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c120-116">To lower the risk of referring to an unintended version of a shadowed variable, you can fully qualify all references to a shadowed variable.</span></span> <span data-ttu-id="0c120-117">숨김 변수 이름이 같은 둘 이상의 버전을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="0c120-117">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="0c120-118">코드 문이 변수 이름에는 참조, 컴파일러 참조를 확인 하는 버전 코드 문의 위치 및 한정 문자열의 현재 상태 등의 요인에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="0c120-118">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="0c120-119">잘못 된 버전의 변수 참조의 위험이 있습니다이 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c120-119">This can increase the risk of referring to the wrong version of the variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c120-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="0c120-120">See also</span></span>

- [<span data-ttu-id="0c120-121">선언된 요소 참조</span><span class="sxs-lookup"><span data-stu-id="0c120-121">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="0c120-122">Visual Basic의 숨김 기능</span><span class="sxs-lookup"><span data-stu-id="0c120-122">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="0c120-123">숨기기와 재정의의 차이점</span><span class="sxs-lookup"><span data-stu-id="0c120-123">Differences Between Shadowing and Overriding</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [<span data-ttu-id="0c120-124">방법: 변수 이름이 같은 변수 숨기기</span><span class="sxs-lookup"><span data-stu-id="0c120-124">How to: Hide a Variable with the Same Name as Your Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [<span data-ttu-id="0c120-125">방법: 상속된 된 변수 숨기기</span><span class="sxs-lookup"><span data-stu-id="0c120-125">How to: Hide an Inherited Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [<span data-ttu-id="0c120-126">Shadows</span><span class="sxs-lookup"><span data-stu-id="0c120-126">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="0c120-127">재정의</span><span class="sxs-lookup"><span data-stu-id="0c120-127">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="0c120-128">Me, My, MyBase 및 MyClass</span><span class="sxs-lookup"><span data-stu-id="0c120-128">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="0c120-129">상속 기본 사항</span><span class="sxs-lookup"><span data-stu-id="0c120-129">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
