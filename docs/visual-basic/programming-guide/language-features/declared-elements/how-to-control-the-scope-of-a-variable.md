---
title: '방법: 변수의 범위 제어'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], scope
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- variables [Visual Basic], visibility
- scope [Visual Basic], declared elements
- scope [Visual Basic], variables
- scope [Visual Basic], Visual Basic
- declared elements [Visual Basic], visibility
- visibility [Visual Basic], variables
ms.assetid: 44b7f62a-cb5c-4d50-bce9-60ae68f87072
ms.openlocfilehash: 0ee6ce183310aa836ecdbbc0bc819e0e83d1872d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345371"
---
# <a name="how-to-control-the-scope-of-a-variable-visual-basic"></a><span data-ttu-id="1399c-102">방법: 변수의 범위 제어(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1399c-102">How to: Control the Scope of a Variable (Visual Basic)</span></span>
<span data-ttu-id="1399c-103">일반적으로 변수는 *범위*내에 있거나 선언 하는 지역 전체에서 참조로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1399c-103">Normally, a variable is in *scope*, or visible for reference, throughout the region in which you declare it.</span></span> <span data-ttu-id="1399c-104">경우에 따라 변수의 *액세스 수준이* 범위에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1399c-104">In some cases, the variable's *access level* can influence its scope.</span></span>  
  
 <span data-ttu-id="1399c-105">자세한 내용은 [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1399c-105">For more information, see [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span></span>  
  
## <a name="scope-at-block-or-procedure-level"></a><span data-ttu-id="1399c-106">블록 또는 프로시저 수준에서의 범위</span><span class="sxs-lookup"><span data-stu-id="1399c-106">Scope at Block or Procedure Level</span></span>  
  
#### <a name="to-make-a-variable-visible-only-within-a-block"></a><span data-ttu-id="1399c-107">블록 내 에서만 변수를 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="1399c-107">To make a variable visible only within a block</span></span>  
  
- <span data-ttu-id="1399c-108">해당 블록의 시작 및 종료 선언문 사이에 있는 변수에 대 한 [Dim 문을](../../../../visual-basic/language-reference/statements/dim-statement.md) 저장 합니다 (예: `For` 루프의 `For` 문과 `Next` 문 사이).</span><span class="sxs-lookup"><span data-stu-id="1399c-108">Place the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) for the variable between the initiating and terminating declaration statements of that block, for example between the `For` and `Next` statements of a `For` loop.</span></span>  
  
     <span data-ttu-id="1399c-109">변수는 블록 내 에서만 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1399c-109">You can refer to the variable only from within the block.</span></span>  
  
#### <a name="to-make-a-variable-visible-only-within-a-procedure"></a><span data-ttu-id="1399c-110">프로시저 내 에서만 변수를 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="1399c-110">To make a variable visible only within a procedure</span></span>  
  
- <span data-ttu-id="1399c-111">프로시저 내의 변수에 대 한 `Dim` 문을 저장 합니다 (예: `With`...`End With` 블록).</span><span class="sxs-lookup"><span data-stu-id="1399c-111">Place the `Dim` statement for the variable inside the procedure but outside any block (such as a `With`...`End With` block).</span></span>  
  
     <span data-ttu-id="1399c-112">프로시저 내에서 프로시저 내에 포함 된 모든 블록을 포함 하 여 변수만 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1399c-112">You can refer to the variable only from within the procedure, including inside any block contained in the procedure.</span></span>  
  
## <a name="scope-at-module-or-namespace-level"></a><span data-ttu-id="1399c-113">모듈 또는 네임 스페이스 수준에서의 범위</span><span class="sxs-lookup"><span data-stu-id="1399c-113">Scope at Module or Namespace Level</span></span>  
 <span data-ttu-id="1399c-114">편의를 위해 모듈, 클래스 및 구조에는 단일 용어 *모듈 수준이* 동일 하 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1399c-114">For convenience, the single term *module level* applies equally to modules, classes, and structures.</span></span> <span data-ttu-id="1399c-115">모듈 수준 변수의 액세스 수준에 따라 해당 범위가 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1399c-115">The access level of a module level variable determines its scope.</span></span> <span data-ttu-id="1399c-116">모듈, 클래스 또는 구조가 포함 된 네임 스페이스도 범위에 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="1399c-116">The namespace that contains the module, class, or structure also influences the scope.</span></span>  
  
#### <a name="to-make-a-variable-visible-throughout-a-module-class-or-structure"></a><span data-ttu-id="1399c-117">모듈, 클래스 또는 구조 전체에서 변수를 표시 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="1399c-117">To make a variable visible throughout a module, class, or structure</span></span>  
  
1. <span data-ttu-id="1399c-118">모듈, 클래스 또는 구조체 내의 변수에 대 한 `Dim` 문을 프로시저 외부에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="1399c-118">Place the `Dim` statement for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="1399c-119">[Private](../../../../visual-basic/language-reference/modifiers/private.md) 키워드를 `Dim` 문에 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="1399c-119">Include the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword in the `Dim` statement.</span></span>  
  
3. <span data-ttu-id="1399c-120">모듈, 클래스 또는 구조체 내의 어디에서 나 변수를 참조할 수 있지만 외부에서는 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1399c-120">You can refer to the variable from anywhere within the module, class, or structure, but not from outside it.</span></span>  
  
#### <a name="to-make-a-variable-visible-throughout-a-namespace"></a><span data-ttu-id="1399c-121">네임 스페이스 전체에서 변수를 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="1399c-121">To make a variable visible throughout a namespace</span></span>  
  
1. <span data-ttu-id="1399c-122">모듈, 클래스 또는 구조체 내의 변수에 대 한 `Dim` 문을 프로시저 외부에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="1399c-122">Place the `Dim` statement for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="1399c-123">[Friend](../../../../visual-basic/language-reference/modifiers/friend.md) 또는 [Public](../../../../visual-basic/language-reference/modifiers/public.md) 키워드를 `Dim` 문에 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="1399c-123">Include the [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) or [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword in the `Dim` statement.</span></span>  
  
3. <span data-ttu-id="1399c-124">모듈, 클래스 또는 구조체를 포함 하는 네임 스페이스 내의 어디에서 나 변수를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1399c-124">You can refer to the variable from anywhere within the namespace containing the module, class, or structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1399c-125">예제</span><span class="sxs-lookup"><span data-stu-id="1399c-125">Example</span></span>  
 <span data-ttu-id="1399c-126">다음 예제에서는 모듈 수준에서 변수를 선언 하 고 모듈 내의 코드에 대 한 표시 여부를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="1399c-126">The following example declares a variable at module level and limits its visibility to code within the module.</span></span>  
  
```vb  
Module demonstrateScope  
    Private strMsg As String  
    Sub initializePrivateVariable()  
        strMsg = "This variable cannot be used outside this module."  
    End Sub  
    Sub usePrivateVariable()  
        MsgBox(strMsg)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="1399c-127">위의 예제에서 모듈 `demonstrateScope`에 정의 된 모든 프로시저는 `strMsg``String` 변수를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1399c-127">In the preceding example, all the procedures defined in module `demonstrateScope` can refer to the `String` variable `strMsg`.</span></span> <span data-ttu-id="1399c-128">`usePrivateVariable` 프로시저가 호출 되 면 대화 상자에 `strMsg` 문자열 변수의 내용이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1399c-128">When the `usePrivateVariable` procedure is called, it displays the contents of the string variable `strMsg` in a dialog box.</span></span>  
  
 <span data-ttu-id="1399c-129">앞의 예제를 다음과 같이 변경 하 여 문자열 변수 `strMsg` 선언 네임 스페이스의 모든 위치에서 코드로 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1399c-129">With the following alteration to the preceding example, the string variable `strMsg` can be referred to by code anywhere in the namespace of its declaration.</span></span>  
  
```vb  
Public strMsg As String  
```  
  
## <a name="robust-programming"></a><span data-ttu-id="1399c-130">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="1399c-130">Robust Programming</span></span>  
 <span data-ttu-id="1399c-131">변수의 범위가 작을수록 동일한 이름의 다른 변수 대신 실수로 참조 하는 기회를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1399c-131">The narrower the scope of a variable, the fewer opportunities you have for accidentally referring to it in place of another variable with the same name.</span></span> <span data-ttu-id="1399c-132">참조 일치 문제를 최소화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1399c-132">You can also minimize problems of reference matching.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="1399c-133">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="1399c-133">.NET Framework Security</span></span>  
 <span data-ttu-id="1399c-134">변수의 범위가 작을수록 악의적인 코드가이를 부적절 하 게 사용할 수 있는 기회가 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="1399c-134">The narrower the scope of a variable, the smaller the chances that malicious code can make improper use of it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1399c-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1399c-135">See also</span></span>

- [<span data-ttu-id="1399c-136">Visual Basic 범위</span><span class="sxs-lookup"><span data-stu-id="1399c-136">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [<span data-ttu-id="1399c-137">Visual Basic 수명</span><span class="sxs-lookup"><span data-stu-id="1399c-137">Lifetime in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="1399c-138">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="1399c-138">Access levels in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="1399c-139">변수</span><span class="sxs-lookup"><span data-stu-id="1399c-139">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="1399c-140">변수 선언</span><span class="sxs-lookup"><span data-stu-id="1399c-140">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="1399c-141">Dim 문</span><span class="sxs-lookup"><span data-stu-id="1399c-141">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
