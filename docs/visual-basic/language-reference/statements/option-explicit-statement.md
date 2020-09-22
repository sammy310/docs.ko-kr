---
title: Option Explicit 문
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
ms.openlocfilehash: 44bf8205ec071710ee3660968ab3c3e9af33f74d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874943"
---
# <a name="option-explicit-statement-visual-basic"></a><span data-ttu-id="21a2e-102">Option Explicit 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="21a2e-102">Option Explicit Statement (Visual Basic)</span></span>

<span data-ttu-id="21a2e-103">파일의 모든 변수를 명시적으로 선언 하거나 변수의 암시적 선언을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a2e-103">Forces explicit declaration of all variables in a file, or allows implicit declarations of variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21a2e-104">구문</span><span class="sxs-lookup"><span data-stu-id="21a2e-104">Syntax</span></span>  
  
```vb  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="21a2e-105">부분</span><span class="sxs-lookup"><span data-stu-id="21a2e-105">Parts</span></span>  

 `On`  
 <span data-ttu-id="21a2e-106">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="21a2e-106">Optional.</span></span> <span data-ttu-id="21a2e-107">검사를 사용 하도록 설정 `Option Explicit` 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a2e-107">Enables `Option Explicit` checking.</span></span> <span data-ttu-id="21a2e-108">`On`또는 `Off` 를 지정 하지 않으면 기본값은 `On` 입니다.</span><span class="sxs-lookup"><span data-stu-id="21a2e-108">If `On` or `Off` is not specified, the default is `On`.</span></span>  
  
 `Off`  
 <span data-ttu-id="21a2e-109">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="21a2e-109">Optional.</span></span> <span data-ttu-id="21a2e-110">검사를 사용 하지 않습니다 `Option Explicit` .</span><span class="sxs-lookup"><span data-stu-id="21a2e-110">Disables `Option Explicit` checking.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21a2e-111">설명</span><span class="sxs-lookup"><span data-stu-id="21a2e-111">Remarks</span></span>  

 <span data-ttu-id="21a2e-112">`Option Explicit On` `Option Explicit` 파일이 파일에 표시 되 면 또는 문을 사용 하 여 모든 변수를 명시적으로 선언 해야 합니다 `Dim` `ReDim` .</span><span class="sxs-lookup"><span data-stu-id="21a2e-112">When `Option Explicit On` or `Option Explicit` appears in a file, you must explicitly declare all variables by using the `Dim` or `ReDim` statements.</span></span> <span data-ttu-id="21a2e-113">선언 되지 않은 변수 이름을 사용 하려고 하면 컴파일 타임에 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a2e-113">If you try to use an undeclared variable name, an error occurs at compile time.</span></span> <span data-ttu-id="21a2e-114">`Option Explicit Off`문은 변수를 암시적으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21a2e-114">The `Option Explicit Off` statement allows implicit declaration of variables.</span></span>  
  
 <span data-ttu-id="21a2e-115">`Option Explicit` 문은 사용하는 경우 파일에서 다른 소스 코드 문 앞에 나와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a2e-115">If used, the `Option Explicit` statement must appear in a file before any other source code statements.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="21a2e-116">`Option Explicit`일반적으로로 설정 하는 것 `Off` 은 좋은 방법이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="21a2e-116">Setting `Option Explicit` to `Off` is generally not a good practice.</span></span> <span data-ttu-id="21a2e-117">하나 이상의 위치에서 변수 이름을 잘못 입력할 수 있습니다. 그러면 프로그램이 실행될 때 예기치 않은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21a2e-117">You could misspell a variable name in one or more locations, which would cause unexpected results when the program is run.</span></span>  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a><span data-ttu-id="21a2e-118">Option Explicit 문이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="21a2e-118">When an Option Explicit Statement Is Not Present</span></span>  

 <span data-ttu-id="21a2e-119">소스 코드에 문이 포함 되어 있지 않은 경우에는 `Option Explicit` [컴파일 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) 에 대 한 **Option Explicit** 설정이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a2e-119">If the source code does not contain an `Option Explicit` statement, the **Option Explicit** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="21a2e-120">명령줄 컴파일러를 사용 하는 경우 [-옵션 explicit](../../reference/command-line-compiler/optionexplicit.md) 컴파일러 옵션이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a2e-120">If the command-line compiler is used, the [-optionexplicit](../../reference/command-line-compiler/optionexplicit.md) compiler option is used.</span></span>  
  
#### <a name="to-set-option-explicit-in-the-ide"></a><span data-ttu-id="21a2e-121">IDE에서 Option Explicit를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="21a2e-121">To set Option Explicit in the IDE</span></span>  
  
1. <span data-ttu-id="21a2e-122">**솔루션 탐색기**에서 프로젝트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a2e-122">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="21a2e-123">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="21a2e-123">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="21a2e-124">**컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="21a2e-124">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="21a2e-125">**옵션 Explicit** 상자에서 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a2e-125">Set the value in the **Option Explicit** box.</span></span>  
  
 <span data-ttu-id="21a2e-126">새 프로젝트를 만들 때 **컴파일** 탭의 **옵션 Explicit** 설정은 **VB 기본값** 대화 상자의 **옵션 explicit** 설정으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a2e-126">When you create a new project, the **Option Explicit** setting on the **Compile** tab is set to the **Option Explicit** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="21a2e-127">**VB 기본값** 대화 상자에 액세스 하려면 **도구** 메뉴에서 **옵션**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a2e-127">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="21a2e-128">**옵션** 대화 상자에서 **프로젝트 및 솔루션**을 확장하고 **VB 기본값**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="21a2e-128">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="21a2e-129">**VB 기본값** 의 초기 기본 설정은 `On` 입니다.</span><span class="sxs-lookup"><span data-stu-id="21a2e-129">The initial default setting in **VB Defaults** is `On`.</span></span>  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a><span data-ttu-id="21a2e-130">명령줄에서 Option Explicit를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="21a2e-130">To set Option Explicit on the command line</span></span>  
  
- <span data-ttu-id="21a2e-131">**Vbc** 명령에 [-옵션 explicit](../../reference/command-line-compiler/optionexplicit.md) 컴파일러 옵션을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a2e-131">Include the [-optionexplicit](../../reference/command-line-compiler/optionexplicit.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21a2e-132">예제</span><span class="sxs-lookup"><span data-stu-id="21a2e-132">Example</span></span>  

 <span data-ttu-id="21a2e-133">다음 예에서는 문을 사용 `Option Explicit` 하 여 모든 변수를 명시적으로 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a2e-133">The following example uses the `Option Explicit` statement to force explicit declaration of all variables.</span></span> <span data-ttu-id="21a2e-134">선언 되지 않은 변수를 사용 하려고 하면 컴파일 타임에 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a2e-134">Attempting to use an undeclared variable causes an error at compile time.</span></span>  
  
 [!code-vb[VbVbalrStatements#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#47)]  
  
 [!code-vb[VbVbalrStatements#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#48)]  
  
## <a name="see-also"></a><span data-ttu-id="21a2e-135">참조</span><span class="sxs-lookup"><span data-stu-id="21a2e-135">See also</span></span>

- [<span data-ttu-id="21a2e-136">Dim 문</span><span class="sxs-lookup"><span data-stu-id="21a2e-136">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="21a2e-137">ReDim 문</span><span class="sxs-lookup"><span data-stu-id="21a2e-137">ReDim Statement</span></span>](redim-statement.md)
- [<span data-ttu-id="21a2e-138">Option Compare 문</span><span class="sxs-lookup"><span data-stu-id="21a2e-138">Option Compare Statement</span></span>](option-compare-statement.md)
- [<span data-ttu-id="21a2e-139">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="21a2e-139">Option Strict Statement</span></span>](option-strict-statement.md)
- [<span data-ttu-id="21a2e-140">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="21a2e-140">-optioncompare</span></span>](../../reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="21a2e-141">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="21a2e-141">-optionexplicit</span></span>](../../reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="21a2e-142">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="21a2e-142">-optionstrict</span></span>](../../reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="21a2e-143">옵션 대화 상자, 프로젝트, Visual Basic 기본값</span><span class="sxs-lookup"><span data-stu-id="21a2e-143">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
