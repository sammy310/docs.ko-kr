---
title: '방법: 변수 (Visual Basic)의 범위 제어'
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
ms.openlocfilehash: ef7957a991718112fe01c4fa3a85f29b9226abd3
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818725"
---
# <a name="how-to-control-the-scope-of-a-variable-visual-basic"></a><span data-ttu-id="281c4-102">방법: 변수 (Visual Basic)의 범위 제어</span><span class="sxs-lookup"><span data-stu-id="281c4-102">How to: Control the Scope of a Variable (Visual Basic)</span></span>
<span data-ttu-id="281c4-103">일반적으로 변수가 *범위*, 또는 참조를 선언 하는 영역 전체에 대 한 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="281c4-103">Normally, a variable is in *scope*, or visible for reference, throughout the region in which you declare it.</span></span> <span data-ttu-id="281c4-104">경우에 따라 변수의 *액세스 수준* 해당 범위에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="281c4-104">In some cases, the variable's *access level* can influence its scope.</span></span>  
  
 <span data-ttu-id="281c4-105">자세한 내용은 [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="281c4-105">For more information, see [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span></span>  
  
## <a name="scope-at-block-or-procedure-level"></a><span data-ttu-id="281c4-106">블록 또는 프로시저 수준 범위</span><span class="sxs-lookup"><span data-stu-id="281c4-106">Scope at Block or Procedure Level</span></span>  
  
#### <a name="to-make-a-variable-visible-only-within-a-block"></a><span data-ttu-id="281c4-107">변수를 블록 내 에서만 볼 수 있도록 하려면</span><span class="sxs-lookup"><span data-stu-id="281c4-107">To make a variable visible only within a block</span></span>  
  
-   <span data-ttu-id="281c4-108">위치는 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md) 변수는 시작 사이의 선언문 해당 블록의 예를 들어 종료 사이 대 한 합니다 `For` 및 `Next` 문을 `For` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="281c4-108">Place the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) for the variable between the initiating and terminating declaration statements of that block, for example between the `For` and `Next` statements of a `For` loop.</span></span>  
  
     <span data-ttu-id="281c4-109">블록 내에서 변수를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="281c4-109">You can refer to the variable only from within the block.</span></span>  
  
#### <a name="to-make-a-variable-visible-only-within-a-procedure"></a><span data-ttu-id="281c4-110">변수는 프로시저 내 에서만 볼 수 있도록 하려면</span><span class="sxs-lookup"><span data-stu-id="281c4-110">To make a variable visible only within a procedure</span></span>  
  
-   <span data-ttu-id="281c4-111">위치는 `Dim` 문을 프로시저 내에 있지만 모든 블록 외부 변수 (같은 `With`... `End With` 블록).</span><span class="sxs-lookup"><span data-stu-id="281c4-111">Place the `Dim` statement for the variable inside the procedure but outside any block (such as a `With`...`End With` block).</span></span>  
  
     <span data-ttu-id="281c4-112">프로시저에 포함 된 모든 블록을 포함 하 여 프로시저 내에서 변수를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="281c4-112">You can refer to the variable only from within the procedure, including inside any block contained in the procedure.</span></span>  
  
## <a name="scope-at-module-or-namespace-level"></a><span data-ttu-id="281c4-113">모듈 또는 Namespace 수준 범위</span><span class="sxs-lookup"><span data-stu-id="281c4-113">Scope at Module or Namespace Level</span></span>  
 <span data-ttu-id="281c4-114">편의상 라는 단일 용어로 *모듈 수준* 모듈, 클래스 및 구조에도 똑같이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="281c4-114">For convenience, the single term *module level* applies equally to modules, classes, and structures.</span></span> <span data-ttu-id="281c4-115">액세스 수준 모듈 수준 변수의 범위를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="281c4-115">The access level of a module level variable determines its scope.</span></span> <span data-ttu-id="281c4-116">모듈, 클래스 또는 구조체를 포함 하는 네임 스페이스 범위를도 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="281c4-116">The namespace that contains the module, class, or structure also influences the scope.</span></span>  
  
#### <a name="to-make-a-variable-visible-throughout-a-module-class-or-structure"></a><span data-ttu-id="281c4-117">변수를 모듈, 클래스 또는 구조 전체에서 볼 수 있도록 하려면</span><span class="sxs-lookup"><span data-stu-id="281c4-117">To make a variable visible throughout a module, class, or structure</span></span>  
  
1.  <span data-ttu-id="281c4-118">위치는 `Dim` 모듈, 클래스 또는 구조체 내 서 다른 프로시저 외부 변수에 대 한 문입니다.</span><span class="sxs-lookup"><span data-stu-id="281c4-118">Place the `Dim` statement for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2.  <span data-ttu-id="281c4-119">포함 된 [개인](../../../../visual-basic/language-reference/modifiers/private.md) 키워드를 `Dim` 문.</span><span class="sxs-lookup"><span data-stu-id="281c4-119">Include the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword in the `Dim` statement.</span></span>  
  
3.  <span data-ttu-id="281c4-120">모듈, 클래스 또는 구조체 내에서 아무 곳 이나 있지만 아닌에서 변수를 참조할 수 있습니다 외부입니다.</span><span class="sxs-lookup"><span data-stu-id="281c4-120">You can refer to the variable from anywhere within the module, class, or structure, but not from outside it.</span></span>  
  
#### <a name="to-make-a-variable-visible-throughout-a-namespace"></a><span data-ttu-id="281c4-121">변수를 네임 스페이스 전체에서 볼 수 있도록 하려면</span><span class="sxs-lookup"><span data-stu-id="281c4-121">To make a variable visible throughout a namespace</span></span>  
  
1.  <span data-ttu-id="281c4-122">위치는 `Dim` 모듈, 클래스 또는 구조체 내 서 다른 프로시저 외부 변수에 대 한 문입니다.</span><span class="sxs-lookup"><span data-stu-id="281c4-122">Place the `Dim` statement for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2.  <span data-ttu-id="281c4-123">포함 된 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) 또는 [공용](../../../../visual-basic/language-reference/modifiers/public.md) 키워드는 `Dim` 문.</span><span class="sxs-lookup"><span data-stu-id="281c4-123">Include the [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) or [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword in the `Dim` statement.</span></span>  
  
3.  <span data-ttu-id="281c4-124">어디에서 나 변수를 참조할 수는 모듈, 클래스 또는 구조가 포함 된 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="281c4-124">You can refer to the variable from anywhere within the namespace containing the module, class, or structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="281c4-125">예제</span><span class="sxs-lookup"><span data-stu-id="281c4-125">Example</span></span>  
 <span data-ttu-id="281c4-126">다음 예제에서는 모듈 수준 변수를 선언 하 고 모듈 내에서 코드를 참조할 수 있도록 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="281c4-126">The following example declares a variable at module level and limits its visibility to code within the module.</span></span>  
  
```  
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
  
 <span data-ttu-id="281c4-127">앞의 예제에서 모듈에 정의 된 모든 프로시저 `demonstrateScope` 참조할 수는 `String` 변수 `strMsg`합니다.</span><span class="sxs-lookup"><span data-stu-id="281c4-127">In the preceding example, all the procedures defined in module `demonstrateScope` can refer to the `String` variable `strMsg`.</span></span> <span data-ttu-id="281c4-128">경우는 `usePrivateVariable` 프로시저가 호출 되는 문자열 변수의 내용을 표시, `strMsg` 대화 상자에서.</span><span class="sxs-lookup"><span data-stu-id="281c4-128">When the `usePrivateVariable` procedure is called, it displays the contents of the string variable `strMsg` in a dialog box.</span></span>  
  
 <span data-ttu-id="281c4-129">위의 예제에서는 문자열 변수를 다음과 같이 변경 하면 `strMsg` 선언의 네임 스페이스에 있는 모든 코드에서 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="281c4-129">With the following alteration to the preceding example, the string variable `strMsg` can be referred to by code anywhere in the namespace of its declaration.</span></span>  
  
```  
Public strMsg As String  
```  
  
## <a name="robust-programming"></a><span data-ttu-id="281c4-130">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="281c4-130">Robust Programming</span></span>  
 <span data-ttu-id="281c4-131">좁을수록 범위 변수를 실수로 동일한 이름의 다른 변수 대신 참조에 더 적은 수의 기회입니다.</span><span class="sxs-lookup"><span data-stu-id="281c4-131">The narrower the scope of a variable, the fewer opportunities you have for accidentally referring to it in place of another variable with the same name.</span></span> <span data-ttu-id="281c4-132">또한 참조 일치 하는 문제를 최소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="281c4-132">You can also minimize problems of reference matching.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="281c4-133">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="281c4-133">.NET Framework Security</span></span>  
 <span data-ttu-id="281c4-134">변수의 범위는 좁을수록 악성 코드가 부적절 하 게 가능성이 줄어듭니다 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="281c4-134">The narrower the scope of a variable, the smaller the chances that malicious code can make improper use of it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="281c4-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="281c4-135">See also</span></span>

- [<span data-ttu-id="281c4-136">Visual Basic의 범위</span><span class="sxs-lookup"><span data-stu-id="281c4-136">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [<span data-ttu-id="281c4-137">Visual Basic의 수명</span><span class="sxs-lookup"><span data-stu-id="281c4-137">Lifetime in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="281c4-138">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="281c4-138">Access levels in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="281c4-139">변수</span><span class="sxs-lookup"><span data-stu-id="281c4-139">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="281c4-140">변수 선언</span><span class="sxs-lookup"><span data-stu-id="281c4-140">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="281c4-141">Dim 문</span><span class="sxs-lookup"><span data-stu-id="281c4-141">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
