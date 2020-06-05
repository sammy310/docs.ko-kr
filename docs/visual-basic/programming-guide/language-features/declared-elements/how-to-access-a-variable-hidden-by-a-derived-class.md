---
title: '방법: 파생 클래스에 의해 숨겨진 변수에 액세스'
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- base classes [Visual Basic], accessing elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declared elements [Visual Basic], referencing
- variables [Visual Basic], accessing hidden
ms.assetid: ae21a8ac-9cd4-4fba-a3ec-ecc4321ef93c
ms.openlocfilehash: c5ff802a0f6e081acd00d7cdfab4a8296b4daad9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392859"
---
# <a name="how-to-access-a-variable-hidden-by-a-derived-class-visual-basic"></a><span data-ttu-id="4ce14-102">방법: 파생 클래스에 의해 숨겨진 변수에 액세스(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4ce14-102">How to: Access a Variable Hidden by a Derived Class (Visual Basic)</span></span>

<span data-ttu-id="4ce14-103">파생 클래스의 코드가 변수에 액세스 하는 경우 컴파일러는 일반적으로 가장 가까운 액세스 가능 버전에 대 한 참조를 확인 합니다. 즉, 액세스 하는 클래스에서 derivational 가장 적은 수의 액세스 가능 버전을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="4ce14-103">When code in a derived class accesses a variable, the compiler normally resolves the reference to the closest accessible version, that is, the accessible version the fewest derivational steps backward from the accessing class.</span></span> <span data-ttu-id="4ce14-104">변수가 파생 클래스에서 정의 된 경우이 코드는 일반적으로 해당 정의에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce14-104">If the variable is defined in the derived class, the code normally accesses that definition.</span></span>

<span data-ttu-id="4ce14-105">파생 클래스 변수가 기본 클래스의 변수를 숨기면 기본 클래스 버전을 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="4ce14-105">If the derived class variable shadows a variable in the base class, it hides the base class version.</span></span> <span data-ttu-id="4ce14-106">그러나 키워드를 사용 하 여 정규화 함으로써 기본 클래스 변수에 액세스할 수 있습니다 `MyBase` .</span><span class="sxs-lookup"><span data-stu-id="4ce14-106">However, you can access the base class variable by qualifying it with the `MyBase` keyword.</span></span>

### <a name="to-access-a-base-class-variable-hidden-by-a-derived-class"></a><span data-ttu-id="4ce14-107">파생 클래스에 의해 숨겨진 기본 클래스 변수에 액세스 하려면</span><span class="sxs-lookup"><span data-stu-id="4ce14-107">To access a base class variable hidden by a derived class</span></span>

- <span data-ttu-id="4ce14-108">식 또는 대입문에서 변수 이름 앞에 `MyBase` 키워드와 마침표 ()를 붙입니다 `.` .</span><span class="sxs-lookup"><span data-stu-id="4ce14-108">In an expression or assignment statement, precede the variable name with the `MyBase` keyword and a period (`.`).</span></span>

    <span data-ttu-id="4ce14-109">컴파일러는 변수의 기본 클래스 버전에 대 한 참조를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce14-109">The compiler resolves the reference to the base class version of the variable.</span></span>

    <span data-ttu-id="4ce14-110">다음 예제에서는 상속을 통한 숨김을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4ce14-110">The following example illustrates shadowing through inheritance.</span></span> <span data-ttu-id="4ce14-111">두 참조를 만듭니다. 하나는 숨기는 변수에 액세스 하 고 다른 하나는 숨김을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce14-111">It makes two references, one that accesses the shadowing variable and one that bypasses the shadowing.</span></span>

    ```vb
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

    <span data-ttu-id="4ce14-112">앞의 예제에서는 `shadowString` 기본 클래스에서 변수를 선언 하 고 파생 클래스에서 해당 변수를 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="4ce14-112">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="4ce14-113">`showStrings`파생 클래스의 프로시저는 이름이 한정 되지 않은 경우 문자열의 숨김 버전을 표시 합니다 `shadowString` .</span><span class="sxs-lookup"><span data-stu-id="4ce14-113">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="4ce14-114">그런 다음 `shadowString` 키워드를 사용 하 여 정규화 된 버전을 표시 `MyBase` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce14-114">It then displays the shadowed version when `shadowString` is qualified with the `MyBase`  keyword.</span></span>

## <a name="robust-programming"></a><span data-ttu-id="4ce14-115">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="4ce14-115">Robust Programming</span></span>

<span data-ttu-id="4ce14-116">숨겨진 변수의 의도 하지 않은 버전을 참조 하는 위험을 줄이려면 숨겨진 변수에 대 한 모든 참조를 정규화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ce14-116">To lower the risk of referring to an unintended version of a shadowed variable, you can fully qualify all references to a shadowed variable.</span></span> <span data-ttu-id="4ce14-117">섀도잉 시 이름이 같은 변수의 버전이 두 개 이상 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4ce14-117">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="4ce14-118">코드 문이 변수 이름을 참조 하는 경우 컴파일러가 참조를 확인 하는 버전은 코드 문의 위치 및 한정 된 문자열이 있는지 여부와 같은 요소에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="4ce14-118">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="4ce14-119">이로 인해 잘못 된 버전의 변수를 참조 하는 위험이 늘어날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ce14-119">This can increase the risk of referring to the wrong version of the variable.</span></span>

## <a name="see-also"></a><span data-ttu-id="4ce14-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4ce14-120">See also</span></span>

- [<span data-ttu-id="4ce14-121">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="4ce14-121">References to Declared Elements</span></span>](references-to-declared-elements.md)
- [<span data-ttu-id="4ce14-122">Visual Basic에서 숨김</span><span class="sxs-lookup"><span data-stu-id="4ce14-122">Shadowing in Visual Basic</span></span>](shadowing.md)
- [<span data-ttu-id="4ce14-123">섀도잉과 재정의 간의 차이점</span><span class="sxs-lookup"><span data-stu-id="4ce14-123">Differences Between Shadowing and Overriding</span></span>](differences-between-shadowing-and-overriding.md)
- [<span data-ttu-id="4ce14-124">방법: 사용자 변수와 이름이 같은 변수 숨기기</span><span class="sxs-lookup"><span data-stu-id="4ce14-124">How to: Hide a Variable with the Same Name as Your Variable</span></span>](how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [<span data-ttu-id="4ce14-125">방법: 상속된 변수 숨기기</span><span class="sxs-lookup"><span data-stu-id="4ce14-125">How to: Hide an Inherited Variable</span></span>](how-to-hide-an-inherited-variable.md)
- [<span data-ttu-id="4ce14-126">Overloads</span><span class="sxs-lookup"><span data-stu-id="4ce14-126">Shadows</span></span>](../../../language-reference/modifiers/shadows.md)
- [<span data-ttu-id="4ce14-127">재정의</span><span class="sxs-lookup"><span data-stu-id="4ce14-127">Overrides</span></span>](../../../language-reference/modifiers/overrides.md)
- [<span data-ttu-id="4ce14-128">Me, My, MyBase 및 MyClass</span><span class="sxs-lookup"><span data-stu-id="4ce14-128">Me, My, MyBase, and MyClass</span></span>](../../program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="4ce14-129">상속 기본 사항</span><span class="sxs-lookup"><span data-stu-id="4ce14-129">Inheritance Basics</span></span>](../objects-and-classes/inheritance-basics.md)
