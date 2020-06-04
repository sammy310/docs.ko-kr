---
title: '방법: 사용자 변수와 이름이 같은 변수 숨기기'
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- declarations [Visual Basic], elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declaration statements [Visual Basic], declared elements
- declaring elements [Visual Basic]
- referencing declared elements [Visual Basic]
- declared elements [Visual Basic], referencing
- declared elements [Visual Basic], about declared elements
ms.assetid: e39c0752-f19f-4d2e-a453-00df1b5fc7ee
ms.openlocfilehash: c1f4c2fbf339358be77e76468b1db94616bf04a2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84357234"
---
# <a name="how-to-hide-a-variable-with-the-same-name-as-your-variable-visual-basic"></a><span data-ttu-id="984be-102">방법: 이름이 같은 변수 숨기기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="984be-102">How to: Hide a Variable with the Same Name as Your Variable (Visual Basic)</span></span>

<span data-ttu-id="984be-103">변수 *를 숨기는 방식으로* 숨길 수 있습니다. 즉, 동일한 이름의 변수를 사용 하 여 변수를 다시 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="984be-103">You can hide a variable by *shadowing* it, that is, by redefining it with a variable of the same name.</span></span> <span data-ttu-id="984be-104">다음 두 가지 방법으로 숨기려는 변수를 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="984be-104">You can shadow the variable you want to hide in two ways:</span></span>

- <span data-ttu-id="984be-105">**범위를 통한 숨김**</span><span class="sxs-lookup"><span data-stu-id="984be-105">**Shadowing Through Scope.**</span></span> <span data-ttu-id="984be-106">숨기려는 변수를 포함 하는 영역의 영역 영역 안에서 다시 선언할 하 여 범위를 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="984be-106">You can shadow it through scope by redeclaring it inside a subregion of the region containing the variable you want to hide.</span></span>

- <span data-ttu-id="984be-107">**상속을 통한 숨김**</span><span class="sxs-lookup"><span data-stu-id="984be-107">**Shadowing Through Inheritance.**</span></span> <span data-ttu-id="984be-108">숨기려는 변수가 클래스 수준에서 정의 되는 경우 상속을 통해 파생 클래스의 [Shadows](../../../language-reference/modifiers/shadows.md) 키워드로 다시 선언할 하 여 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="984be-108">If the variable you want to hide is defined at class level, you can shadow it through inheritance by redeclaring it with the [Shadows](../../../language-reference/modifiers/shadows.md) keyword in a derived class.</span></span>

## <a name="two-ways-to-hide-a-variable"></a><span data-ttu-id="984be-109">변수를 숨기는 두 가지 방법</span><span class="sxs-lookup"><span data-stu-id="984be-109">Two Ways to Hide a Variable</span></span>

#### <a name="to-hide-a-variable-by-shadowing-it-through-scope"></a><span data-ttu-id="984be-110">범위를 통해 변수를 숨겨 변수를 숨기려면</span><span class="sxs-lookup"><span data-stu-id="984be-110">To hide a variable by shadowing it through scope</span></span>

1. <span data-ttu-id="984be-111">숨기려는 변수를 정의 하는 영역을 확인 하 고 변수를 사용 하 여이를 다시 정의할 영역을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="984be-111">Determine the region defining the variable you want to hide, and determine a subregion in which to redefine it with your variable.</span></span>

    |<span data-ttu-id="984be-112">변수의 영역</span><span class="sxs-lookup"><span data-stu-id="984be-112">Variable's region</span></span>|<span data-ttu-id="984be-113">재정의할 수 있는 하위 영역</span><span class="sxs-lookup"><span data-stu-id="984be-113">Allowable subregion for redefining it</span></span>|
    |-----------------------|-------------------------------------------|
    |<span data-ttu-id="984be-114">Module</span><span class="sxs-lookup"><span data-stu-id="984be-114">Module</span></span>|<span data-ttu-id="984be-115">모듈 내의 클래스</span><span class="sxs-lookup"><span data-stu-id="984be-115">A class within the module</span></span>|
    |<span data-ttu-id="984be-116">클래스</span><span class="sxs-lookup"><span data-stu-id="984be-116">Class</span></span>|<span data-ttu-id="984be-117">클래스 내의 하위 클래스</span><span class="sxs-lookup"><span data-stu-id="984be-117">A subclass within the class</span></span><br /><br /> <span data-ttu-id="984be-118">클래스 내의 프로시저</span><span class="sxs-lookup"><span data-stu-id="984be-118">A procedure within the class</span></span>|

    <span data-ttu-id="984be-119">해당 프로시저 내에서 프로시저 변수를 다시 정의할 수 없습니다 (예: `If` ... `End If` 생성 또는 `For` 루프).</span><span class="sxs-lookup"><span data-stu-id="984be-119">You cannot redefine a procedure variable in a block within that procedure, for example in an `If`...`End If` construction or a `For` loop.</span></span>

2. <span data-ttu-id="984be-120">아직 없는 경우 영역을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="984be-120">Create the subregion if it does not already exist.</span></span>

3. <span data-ttu-id="984be-121">영역 내에서 숨김 변수를 선언 하는 [Dim 문을](../../../language-reference/statements/dim-statement.md) 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="984be-121">Within the subregion, write a [Dim Statement](../../../language-reference/statements/dim-statement.md) declaring the shadowing variable.</span></span>

    <span data-ttu-id="984be-122">영역 내의 코드가 변수 이름을 참조 하는 경우 컴파일러는 숨기는 변수에 대 한 참조를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="984be-122">When code inside the subregion refers to the variable name, the compiler resolves the reference to the shadowing variable.</span></span>

    <span data-ttu-id="984be-123">다음 예제에서는 범위를 통한 숨김과 숨김을 무시 하는 참조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="984be-123">The following example illustrates shadowing through scope, as well as a reference that bypasses the shadowing.</span></span>

    ```vb
    Module shadowByScope
        ' The following statement declares num as a module-level variable.
        Public num As Integer
        Sub show()
            ' The following statement declares num as a local variable.
            Dim num As Integer
            ' The following statement sets the value of the local variable.
            num = 2
            ' The following statement displays the module-level variable.
            MsgBox(CStr(shadowByScope.num))
        End Sub
        Sub useModuleLevelNum()
            ' The following statement sets the value of the module-level variable.
            num = 1
            show()
        End Sub
    End Module
    ```

    <span data-ttu-id="984be-124">앞의 예제에서는 `num` 모듈 수준 및 프로시저 수준 (프로시저)에서 모두 변수를 선언 합니다 `show` .</span><span class="sxs-lookup"><span data-stu-id="984be-124">The preceding example declares the variable `num` both at module level and at procedure level (in the procedure `show`).</span></span> <span data-ttu-id="984be-125">지역 변수는 `num` 내에서 모듈 수준 변수를 `num` 숨기 `show` 므로 지역 변수는 2로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="984be-125">The local variable `num` shadows the module-level variable `num` within `show`, so the local variable is set to 2.</span></span> <span data-ttu-id="984be-126">그러나 프로시저에서 숨길 지역 변수는 없습니다 `num` `useModuleLevelNum` .</span><span class="sxs-lookup"><span data-stu-id="984be-126">However, there is no local variable to shadow `num` in the `useModuleLevelNum` procedure.</span></span> <span data-ttu-id="984be-127">따라서는 `useModuleLevelNum` 모듈 수준 변수의 값을 1로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="984be-127">Therefore, `useModuleLevelNum` sets the value of the module-level variable to 1.</span></span>

    <span data-ttu-id="984be-128">`MsgBox`내의 호출은 `show` `num` 모듈 이름으로 한정 하 여 숨김 메커니즘을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="984be-128">The `MsgBox` call inside `show` bypasses the shadowing mechanism by qualifying `num` with the module name.</span></span> <span data-ttu-id="984be-129">따라서 지역 변수 대신 모듈 수준 변수를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="984be-129">Therefore, it displays the module-level variable instead of the local variable.</span></span>

#### <a name="to-hide-a-variable-by-shadowing-it-through-inheritance"></a><span data-ttu-id="984be-130">상속을 통해 변수를 숨겨 변수를 숨기려면</span><span class="sxs-lookup"><span data-stu-id="984be-130">To hide a variable by shadowing it through inheritance</span></span>

1. <span data-ttu-id="984be-131">숨기려는 변수가 클래스에서 선언 되 고 클래스 수준 (프로시저 외부)에 선언 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="984be-131">Be sure the variable you want to hide is declared in a class, and at class level (outside any procedure).</span></span> <span data-ttu-id="984be-132">그렇지 않으면 상속을 통해 숨길 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="984be-132">Otherwise you cannot shadow it through inheritance.</span></span>

2. <span data-ttu-id="984be-133">이미 존재 하지 않는 경우 변수의 클래스에서 파생 된 클래스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="984be-133">Define a class derived from the variable's class if one does not already exist.</span></span>

3. <span data-ttu-id="984be-134">파생 클래스 내에서 `Dim` 변수를 선언 하는 문을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="984be-134">Inside the derived class, write a `Dim` statement declaring your variable.</span></span> <span data-ttu-id="984be-135">선언에 [Shadows](../../../language-reference/modifiers/shadows.md) 키워드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="984be-135">Include the [Shadows](../../../language-reference/modifiers/shadows.md) keyword in the declaration.</span></span>

    <span data-ttu-id="984be-136">파생 클래스의 코드가 변수 이름을 참조 하는 경우 컴파일러는 변수에 대 한 참조를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="984be-136">When code in the derived class refers to the variable name, the compiler resolves the reference to your variable.</span></span>

    <span data-ttu-id="984be-137">다음 예제에서는 상속을 통한 숨김을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="984be-137">The following example illustrates shadowing through inheritance.</span></span> <span data-ttu-id="984be-138">두 참조를 만듭니다. 하나는 숨기는 변수에 액세스 하 고 다른 하나는 숨김을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="984be-138">It makes two references, one that accesses the shadowing variable and one that bypasses the shadowing.</span></span>

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

    <span data-ttu-id="984be-139">앞의 예제에서는 `shadowString` 기본 클래스에서 변수를 선언 하 고 파생 클래스에서 해당 변수를 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="984be-139">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="984be-140">`showStrings`파생 클래스의 프로시저는 이름이 한정 되지 않은 경우 문자열의 숨김 버전을 표시 합니다 `shadowString` .</span><span class="sxs-lookup"><span data-stu-id="984be-140">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="984be-141">그런 다음 `shadowString` 키워드를 사용 하 여 정규화 된 버전을 표시 `MyBase` 합니다.</span><span class="sxs-lookup"><span data-stu-id="984be-141">It then displays the shadowed version when `shadowString` is qualified with the `MyBase` keyword.</span></span>

## <a name="robust-programming"></a><span data-ttu-id="984be-142">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="984be-142">Robust Programming</span></span>

<span data-ttu-id="984be-143">섀도잉 시 이름이 같은 변수의 버전이 두 개 이상 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="984be-143">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="984be-144">코드 문이 변수 이름을 참조 하는 경우 컴파일러가 참조를 확인 하는 버전은 코드 문의 위치 및 한정 된 문자열이 있는지 여부와 같은 요소에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="984be-144">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="984be-145">이로 인해 숨겨진 변수의 의도 하지 않은 버전을 참조 하는 위험이 늘어날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="984be-145">This can increase the risk of referring to an unintended version of a shadowed variable.</span></span> <span data-ttu-id="984be-146">숨겨진 변수에 대 한 모든 참조를 정규화 하 여이 위험을 낮출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="984be-146">You can lower that risk by fully qualifying all references to a shadowed variable.</span></span>

## <a name="see-also"></a><span data-ttu-id="984be-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="984be-147">See also</span></span>

- [<span data-ttu-id="984be-148">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="984be-148">References to Declared Elements</span></span>](references-to-declared-elements.md)
- [<span data-ttu-id="984be-149">Visual Basic에서 숨김</span><span class="sxs-lookup"><span data-stu-id="984be-149">Shadowing in Visual Basic</span></span>](shadowing.md)
- [<span data-ttu-id="984be-150">섀도잉과 재정의 간의 차이점</span><span class="sxs-lookup"><span data-stu-id="984be-150">Differences Between Shadowing and Overriding</span></span>](differences-between-shadowing-and-overriding.md)
- [<span data-ttu-id="984be-151">방법: 상속된 변수 숨기기</span><span class="sxs-lookup"><span data-stu-id="984be-151">How to: Hide an Inherited Variable</span></span>](how-to-hide-an-inherited-variable.md)
- [<span data-ttu-id="984be-152">방법: 파생 클래스에 의해 숨겨진 변수에 액세스</span><span class="sxs-lookup"><span data-stu-id="984be-152">How to: Access a Variable Hidden by a Derived Class</span></span>](how-to-access-a-variable-hidden-by-a-derived-class.md)
- [<span data-ttu-id="984be-153">재정의</span><span class="sxs-lookup"><span data-stu-id="984be-153">Overrides</span></span>](../../../language-reference/modifiers/overrides.md)
- [<span data-ttu-id="984be-154">Me, My, MyBase 및 MyClass</span><span class="sxs-lookup"><span data-stu-id="984be-154">Me, My, MyBase, and MyClass</span></span>](../../program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="984be-155">상속 기본 사항</span><span class="sxs-lookup"><span data-stu-id="984be-155">Inheritance Basics</span></span>](../objects-and-classes/inheritance-basics.md)
