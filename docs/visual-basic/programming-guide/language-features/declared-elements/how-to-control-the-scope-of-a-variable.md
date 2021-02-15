---
description: '자세히 알아보기: 방법: 변수의 범위 제어 (Visual Basic)'
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
ms.openlocfilehash: c6da599f76883cba545efbdf9570aa05770602a2
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100429873"
---
# <a name="how-to-control-the-scope-of-a-variable-visual-basic"></a><span data-ttu-id="35afc-103">방법: 변수의 범위 제어(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="35afc-103">How to: Control the Scope of a Variable (Visual Basic)</span></span>

<span data-ttu-id="35afc-104">일반적으로 변수는 *범위* 내에 있거나 선언 하는 지역 전체에서 참조로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35afc-104">Normally, a variable is in *scope*, or visible for reference, throughout the region in which you declare it.</span></span> <span data-ttu-id="35afc-105">경우에 따라 변수의 *액세스 수준이* 범위에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35afc-105">In some cases, the variable's *access level* can influence its scope.</span></span>  
  
 <span data-ttu-id="35afc-106">자세한 내용은 [Scope in Visual Basic](scope.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="35afc-106">For more information, see [Scope in Visual Basic](scope.md).</span></span>  
  
## <a name="scope-at-block-or-procedure-level"></a><span data-ttu-id="35afc-107">블록 또는 프로시저 수준에서의 범위</span><span class="sxs-lookup"><span data-stu-id="35afc-107">Scope at Block or Procedure Level</span></span>  
  
#### <a name="to-make-a-variable-visible-only-within-a-block"></a><span data-ttu-id="35afc-108">블록 내 에서만 변수를 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="35afc-108">To make a variable visible only within a block</span></span>  
  
- <span data-ttu-id="35afc-109">루프의 및 문 사이에 있는 경우와 같이 해당 블록의 시작 및 종료 선언 문 간에 변수에 [Dim 문을](../../../language-reference/statements/dim-statement.md) 추가 합니다 `For` `Next` `For` .</span><span class="sxs-lookup"><span data-stu-id="35afc-109">Place the [Dim Statement](../../../language-reference/statements/dim-statement.md) for the variable between the initiating and terminating declaration statements of that block, for example between the `For` and `Next` statements of a `For` loop.</span></span>  
  
     <span data-ttu-id="35afc-110">변수는 블록 내 에서만 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35afc-110">You can refer to the variable only from within the block.</span></span>  
  
#### <a name="to-make-a-variable-visible-only-within-a-procedure"></a><span data-ttu-id="35afc-111">프로시저 내 에서만 변수를 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="35afc-111">To make a variable visible only within a procedure</span></span>  
  
- <span data-ttu-id="35afc-112">`Dim`프로시저 내의 변수는 물론 블록 외부 (예: ... `With` `End With` 블록)에 문을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="35afc-112">Place the `Dim` statement for the variable inside the procedure but outside any block (such as a `With`...`End With` block).</span></span>  
  
     <span data-ttu-id="35afc-113">프로시저 내에서 프로시저 내에 포함 된 모든 블록을 포함 하 여 변수만 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35afc-113">You can refer to the variable only from within the procedure, including inside any block contained in the procedure.</span></span>  
  
## <a name="scope-at-module-or-namespace-level"></a><span data-ttu-id="35afc-114">모듈 또는 네임 스페이스 수준에서의 범위</span><span class="sxs-lookup"><span data-stu-id="35afc-114">Scope at Module or Namespace Level</span></span>  

 <span data-ttu-id="35afc-115">편의를 위해 모듈, 클래스 및 구조에는 단일 용어 *모듈 수준이* 동일 하 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35afc-115">For convenience, the single term *module level* applies equally to modules, classes, and structures.</span></span> <span data-ttu-id="35afc-116">모듈 수준 변수의 액세스 수준에 따라 해당 범위가 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35afc-116">The access level of a module level variable determines its scope.</span></span> <span data-ttu-id="35afc-117">모듈, 클래스 또는 구조가 포함 된 네임 스페이스도 범위에 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="35afc-117">The namespace that contains the module, class, or structure also influences the scope.</span></span>  
  
#### <a name="to-make-a-variable-visible-throughout-a-module-class-or-structure"></a><span data-ttu-id="35afc-118">모듈, 클래스 또는 구조 전체에서 변수를 표시 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="35afc-118">To make a variable visible throughout a module, class, or structure</span></span>  
  
1. <span data-ttu-id="35afc-119">`Dim`모듈, 클래스 또는 구조체 내에 있는 변수에 대 한 문을 프로시저 외부에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="35afc-119">Place the `Dim` statement for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="35afc-120">문에 [Private](../../../language-reference/modifiers/private.md) 키워드를 포함 `Dim` 합니다.</span><span class="sxs-lookup"><span data-stu-id="35afc-120">Include the [Private](../../../language-reference/modifiers/private.md) keyword in the `Dim` statement.</span></span>  
  
3. <span data-ttu-id="35afc-121">모듈, 클래스 또는 구조체 내의 어디에서 나 변수를 참조할 수 있지만 외부에서는 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="35afc-121">You can refer to the variable from anywhere within the module, class, or structure, but not from outside it.</span></span>  
  
#### <a name="to-make-a-variable-visible-throughout-a-namespace"></a><span data-ttu-id="35afc-122">네임 스페이스 전체에서 변수를 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="35afc-122">To make a variable visible throughout a namespace</span></span>  
  
1. <span data-ttu-id="35afc-123">`Dim`모듈, 클래스 또는 구조체 내에 있는 변수에 대 한 문을 프로시저 외부에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="35afc-123">Place the `Dim` statement for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="35afc-124">문에 [Friend](../../../language-reference/modifiers/friend.md) 또는 [Public](../../../language-reference/modifiers/public.md) 키워드를 포함 `Dim` 합니다.</span><span class="sxs-lookup"><span data-stu-id="35afc-124">Include the [Friend](../../../language-reference/modifiers/friend.md) or [Public](../../../language-reference/modifiers/public.md) keyword in the `Dim` statement.</span></span>  
  
3. <span data-ttu-id="35afc-125">모듈, 클래스 또는 구조체를 포함 하는 네임 스페이스 내의 어디에서 나 변수를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35afc-125">You can refer to the variable from anywhere within the namespace containing the module, class, or structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35afc-126">예</span><span class="sxs-lookup"><span data-stu-id="35afc-126">Example</span></span>  

 <span data-ttu-id="35afc-127">다음 예제에서는 모듈 수준에서 변수를 선언 하 고 모듈 내의 코드에 대 한 표시 여부를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="35afc-127">The following example declares a variable at module level and limits its visibility to code within the module.</span></span>  
  
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
  
 <span data-ttu-id="35afc-128">위의 예에서는 모듈에 정의 된 모든 프로시저가 `demonstrateScope` 변수를 참조할 수 있습니다 `String` `strMsg` .</span><span class="sxs-lookup"><span data-stu-id="35afc-128">In the preceding example, all the procedures defined in module `demonstrateScope` can refer to the `String` variable `strMsg`.</span></span> <span data-ttu-id="35afc-129">프로시저를 `usePrivateVariable` 호출 하면 대화 상자에 문자열 변수의 내용이 표시 됩니다 `strMsg` .</span><span class="sxs-lookup"><span data-stu-id="35afc-129">When the `usePrivateVariable` procedure is called, it displays the contents of the string variable `strMsg` in a dialog box.</span></span>  
  
 <span data-ttu-id="35afc-130">앞의 예제를 다음과 같이 변경 하 여 문자열 변수를 `strMsg` 선언 네임 스페이스의 모든 위치에서 코드로 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35afc-130">With the following alteration to the preceding example, the string variable `strMsg` can be referred to by code anywhere in the namespace of its declaration.</span></span>  
  
```vb  
Public strMsg As String  
```  
  
## <a name="robust-programming"></a><span data-ttu-id="35afc-131">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="35afc-131">Robust Programming</span></span>  

 <span data-ttu-id="35afc-132">변수의 범위가 작을수록 동일한 이름의 다른 변수 대신 실수로 참조 하는 기회를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35afc-132">The narrower the scope of a variable, the fewer opportunities you have for accidentally referring to it in place of another variable with the same name.</span></span> <span data-ttu-id="35afc-133">참조 일치 문제를 최소화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35afc-133">You can also minimize problems of reference matching.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="35afc-134">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="35afc-134">.NET Framework Security</span></span>  

 <span data-ttu-id="35afc-135">변수의 범위가 작을수록 악의적인 코드가이를 부적절 하 게 사용할 수 있는 기회가 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="35afc-135">The narrower the scope of a variable, the smaller the chances that malicious code can make improper use of it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35afc-136">추가 정보</span><span class="sxs-lookup"><span data-stu-id="35afc-136">See also</span></span>

- [<span data-ttu-id="35afc-137">Visual Basic의 범위</span><span class="sxs-lookup"><span data-stu-id="35afc-137">Scope in Visual Basic</span></span>](scope.md)
- [<span data-ttu-id="35afc-138">Visual Basic의 수명</span><span class="sxs-lookup"><span data-stu-id="35afc-138">Lifetime in Visual Basic</span></span>](lifetime.md)
- [<span data-ttu-id="35afc-139">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="35afc-139">Access levels in Visual Basic</span></span>](access-levels.md)
- [<span data-ttu-id="35afc-140">변수</span><span class="sxs-lookup"><span data-stu-id="35afc-140">Variables</span></span>](../variables/index.md)
- [<span data-ttu-id="35afc-141">변수 선언</span><span class="sxs-lookup"><span data-stu-id="35afc-141">Variable Declaration</span></span>](../variables/variable-declaration.md)
- [<span data-ttu-id="35afc-142">Dim 문</span><span class="sxs-lookup"><span data-stu-id="35afc-142">Dim Statement</span></span>](../../../language-reference/statements/dim-statement.md)
