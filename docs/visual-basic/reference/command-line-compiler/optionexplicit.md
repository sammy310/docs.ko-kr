---
title: -optionexplicit
ms.date: 07/20/2015
f1_keywords:
- /optionexplicit
- -optionexplicit
helpviewer_keywords:
- /optionexplicit compiler option [Visual Basic]
- optionexplicit compiler option [Visual Basic]
- -optionexplicit compiler option [Visual Basic]
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
ms.openlocfilehash: 37ccd14dae0ebba2535185f2646e312d9bb70390
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266731"
---
# <a name="-optionexplicit"></a><span data-ttu-id="23184-102">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="23184-102">-optionexplicit</span></span>
<span data-ttu-id="23184-103">변수를 사용하기 전에 선언되지 않은 경우 컴파일러에서 오류를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="23184-103">Causes the compiler to report errors if variables are not declared before they are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23184-104">구문</span><span class="sxs-lookup"><span data-stu-id="23184-104">Syntax</span></span>  
  
```console  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="23184-105">인수</span><span class="sxs-lookup"><span data-stu-id="23184-105">Arguments</span></span>  
 <span data-ttu-id="23184-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="23184-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="23184-107">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="23184-107">Optional.</span></span> <span data-ttu-id="23184-108">명시적 변수 선언이 필요하면 `-optionexplicit+`를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="23184-108">Specify `-optionexplicit+` to require explicit declaration of variables.</span></span> <span data-ttu-id="23184-109">`-optionexplicit+` 옵션이 기본값이며 `-optionexplicit`와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="23184-109">The `-optionexplicit+` option is the default and is the same as `-optionexplicit`.</span></span> <span data-ttu-id="23184-110">`-optionexplicit-` 옵션을 사용하면 변수를 암시적으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23184-110">The `-optionexplicit-` option enables implicit declaration of variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23184-111">설명</span><span class="sxs-lookup"><span data-stu-id="23184-111">Remarks</span></span>  
 <span data-ttu-id="23184-112">소스 코드 파일에 [Option Explicit 문](../../../visual-basic/language-reference/statements/option-explicit-statement.md)이 포함되어 있으면 해당 명령문이 `-optionexplicit` 명령줄 컴파일러 설정을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="23184-112">If the source code file contains an [Option Explicit statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md), the statement overrides the `-optionexplicit` command-line compiler setting.</span></span>  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a><span data-ttu-id="23184-113">Visual Studio IDE에서 -optionexplicit를 설정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="23184-113">To set -optionexplicit in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="23184-114">**솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="23184-114">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="23184-115">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="23184-115">On the **Project** menu, click **Properties**.</span></span>
  
2. <span data-ttu-id="23184-116">**컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="23184-116">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="23184-117">**Option Explicit** 상자에서 값을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="23184-117">Modify the value in the **Option Explicit** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23184-118">예제</span><span class="sxs-lookup"><span data-stu-id="23184-118">Example</span></span>  
 <span data-ttu-id="23184-119">다음 코드는 `-optionexplicit-`가 사용될 때 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="23184-119">The following code compiles when `-optionexplicit-` is used.</span></span>  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="23184-120">참조</span><span class="sxs-lookup"><span data-stu-id="23184-120">See also</span></span>

- [<span data-ttu-id="23184-121">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="23184-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="23184-122">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="23184-122">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="23184-123">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="23184-123">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="23184-124">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="23184-124">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="23184-125">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="23184-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="23184-126">Option Explicit 문</span><span class="sxs-lookup"><span data-stu-id="23184-126">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="23184-127">옵션 대화 상자, 프로젝트, Visual Basic 기본값</span><span class="sxs-lookup"><span data-stu-id="23184-127">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
