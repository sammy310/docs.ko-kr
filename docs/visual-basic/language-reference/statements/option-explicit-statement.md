---
title: Option Explicit 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Explicit
- vb.OptionExplicit
helpviewer_keywords:
- declaring variables [Visual Basic], explicit
- forced variable declaration in Option Explicit statement [Visual Basic]
- Explicit keyword
- explicit variable declaration
- Option Explicit statement [Visual Basic]
ms.assetid: e82ac1ad-2cd3-49b2-b985-8bcf016f3fcc
ms.openlocfilehash: 0a319ba4259e66ed9a37aa2de9e97d2335b78663
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59308616"
---
# <a name="option-explicit-statement-visual-basic"></a><span data-ttu-id="6fada-102">Option Explicit 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6fada-102">Option Explicit Statement (Visual Basic)</span></span>
<span data-ttu-id="6fada-103">파일에서 모든 변수에 명시적으로 강제 또는 암시적 변수 선언을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fada-103">Forces explicit declaration of all variables in a file, or allows implicit declarations of variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fada-104">구문</span><span class="sxs-lookup"><span data-stu-id="6fada-104">Syntax</span></span>  
  
```  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="6fada-105">요소</span><span class="sxs-lookup"><span data-stu-id="6fada-105">Parts</span></span>  
 `On`  
 <span data-ttu-id="6fada-106">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6fada-106">Optional.</span></span> <span data-ttu-id="6fada-107">사용 하도록 설정 `Option Explicit` 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fada-107">Enables `Option Explicit` checking.</span></span> <span data-ttu-id="6fada-108">하는 경우 `On` 나 `Off` 지정 하지 않으면 기본값은 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="6fada-108">If `On` or `Off` is not specified, the default is `On`.</span></span>  
  
 `Off`  
 <span data-ttu-id="6fada-109">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6fada-109">Optional.</span></span> <span data-ttu-id="6fada-110">사용 하지 않도록 설정 `Option Explicit` 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fada-110">Disables `Option Explicit` checking.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6fada-111">설명</span><span class="sxs-lookup"><span data-stu-id="6fada-111">Remarks</span></span>  
 <span data-ttu-id="6fada-112">때 `Option Explicit On` 또는 `Option Explicit` 파일에서 사용 하 여 모든 변수를 명시적으로 선언 해야 표시 되는 `Dim` 또는 `ReDim` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="6fada-112">When `Option Explicit On` or `Option Explicit` appears in a file, you must explicitly declare all variables by using the `Dim` or `ReDim` statements.</span></span> <span data-ttu-id="6fada-113">선언 되지 않은 변수 이름을 사용 하려고 하면 컴파일 타임 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fada-113">If you try to use an undeclared variable name, an error occurs at compile time.</span></span> <span data-ttu-id="6fada-114">`Option Explicit Off` 문은 암시적 변수 선언을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fada-114">The `Option Explicit Off` statement allows implicit declaration of variables.</span></span>  
  
 <span data-ttu-id="6fada-115">`Option Explicit` 문은 사용하는 경우 파일에서 다른 소스 코드 문 앞에 나와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fada-115">If used, the `Option Explicit` statement must appear in a file before any other source code statements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6fada-116">설정 `Option Explicit` 에 `Off` 일반적으로 좋은 방법은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="6fada-116">Setting `Option Explicit` to `Off` is generally not a good practice.</span></span> <span data-ttu-id="6fada-117">하나 이상의 위치에서 변수 이름을 잘못 입력할 수 있습니다. 그러면 프로그램이 실행될 때 예기치 않은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fada-117">You could misspell a variable name in one or more locations, which would cause unexpected results when the program is run.</span></span>  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a><span data-ttu-id="6fada-118">Option Explicit 문은 현재 없는 경우</span><span class="sxs-lookup"><span data-stu-id="6fada-118">When an Option Explicit Statement Is Not Present</span></span>  
 <span data-ttu-id="6fada-119">소스 코드에 없는 경우는 `Option Explicit` 문을 **Option Explicit** 에 설정 합니다 [컴파일 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fada-119">If the source code does not contain an `Option Explicit` statement, the **Option Explicit** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="6fada-120">명령줄 컴파일러를 사용 하는 경우는 [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) 컴파일러 옵션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fada-120">If the command-line compiler is used, the [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option is used.</span></span>  
  
#### <a name="to-set-option-explicit-in-the-ide"></a><span data-ttu-id="6fada-121">IDE에서 Option Explicit을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="6fada-121">To set Option Explicit in the IDE</span></span>  
  
1. <span data-ttu-id="6fada-122">**솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6fada-122">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="6fada-123">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6fada-123">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="6fada-124">**컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6fada-124">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="6fada-125">값을 설정 합니다 **Option Explicit** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="6fada-125">Set the value in the **Option Explicit** box.</span></span>  
  
 <span data-ttu-id="6fada-126">새 프로젝트를 만들 때를 **Option Explicit** 에 설정 합니다 **컴파일** 탭으로 설정 됩니다는 **Option Explicit** 에서 설정는 **VB 기본값**대화 상자.</span><span class="sxs-lookup"><span data-stu-id="6fada-126">When you create a new project, the **Option Explicit** setting on the **Compile** tab is set to the **Option Explicit** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="6fada-127">액세스 하는 **VB 기본값** 대화 상자의 합니다 **도구** 메뉴에서 클릭 **옵션**.</span><span class="sxs-lookup"><span data-stu-id="6fada-127">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="6fada-128">**옵션** 대화 상자에서 **프로젝트 및 솔루션**을 확장하고 **VB 기본값**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6fada-128">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="6fada-129">초기 기본 설정은 **VB 기본값** 는 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="6fada-129">The initial default setting in **VB Defaults** is `On`.</span></span>  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a><span data-ttu-id="6fada-130">명령줄에서 Option Explicit을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="6fada-130">To set Option Explicit on the command line</span></span>  
  
-   <span data-ttu-id="6fada-131">포함 된 [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) 컴파일러 옵션을 **vbc** 명령.</span><span class="sxs-lookup"><span data-stu-id="6fada-131">Include the [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6fada-132">예제</span><span class="sxs-lookup"><span data-stu-id="6fada-132">Example</span></span>  
 <span data-ttu-id="6fada-133">다음 예제에서는 `Option Explicit` 문을 모든 변수의 명시적 선언을 강제 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fada-133">The following example uses the `Option Explicit` statement to force explicit declaration of all variables.</span></span> <span data-ttu-id="6fada-134">선언 되지 않은 변수를 사용 하려고 하면 컴파일 타임에 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fada-134">Attempting to use an undeclared variable causes an error at compile time.</span></span>  
  
 [!code-vb[VbVbalrStatements#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#47)]  
  
 [!code-vb[VbVbalrStatements#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#48)]  
  
## <a name="see-also"></a><span data-ttu-id="6fada-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="6fada-135">See also</span></span>

- [<span data-ttu-id="6fada-136">Dim 문</span><span class="sxs-lookup"><span data-stu-id="6fada-136">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="6fada-137">ReDim 문</span><span class="sxs-lookup"><span data-stu-id="6fada-137">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="6fada-138">Option Compare 문</span><span class="sxs-lookup"><span data-stu-id="6fada-138">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="6fada-139">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="6fada-139">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="6fada-140">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="6fada-140">/optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="6fada-141">/optionexplicit</span><span class="sxs-lookup"><span data-stu-id="6fada-141">/optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="6fada-142">/optionstrict</span><span class="sxs-lookup"><span data-stu-id="6fada-142">/optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="6fada-143">옵션 대화 상자, 프로젝트, VB 기본값</span><span class="sxs-lookup"><span data-stu-id="6fada-143">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
