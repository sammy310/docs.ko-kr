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
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266731"
---
# <a name="-optionexplicit"></a><span data-ttu-id="fb2cf-102">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="fb2cf-102">-optionexplicit</span></span>
<span data-ttu-id="fb2cf-103">변수를 사용 하기 전에 선언 되지 않은 경우 컴파일러 오류를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb2cf-103">Causes the compiler to report errors if variables are not declared before they are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb2cf-104">구문</span><span class="sxs-lookup"><span data-stu-id="fb2cf-104">Syntax</span></span>  
  
```console  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="fb2cf-105">인수</span><span class="sxs-lookup"><span data-stu-id="fb2cf-105">Arguments</span></span>  
 <span data-ttu-id="fb2cf-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="fb2cf-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="fb2cf-107">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="fb2cf-107">Optional.</span></span> <span data-ttu-id="fb2cf-108">변수의 명시적 선언을 요구하도록 지정합니다. `-optionexplicit+`</span><span class="sxs-lookup"><span data-stu-id="fb2cf-108">Specify `-optionexplicit+` to require explicit declaration of variables.</span></span> <span data-ttu-id="fb2cf-109">이 `-optionexplicit+` 옵션은 기본값이며 `-optionexplicit`.</span><span class="sxs-lookup"><span data-stu-id="fb2cf-109">The `-optionexplicit+` option is the default and is the same as `-optionexplicit`.</span></span> <span data-ttu-id="fb2cf-110">이 `-optionexplicit-` 옵션을 사용하면 변수의 암시적 선언이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="fb2cf-110">The `-optionexplicit-` option enables implicit declaration of variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb2cf-111">설명</span><span class="sxs-lookup"><span data-stu-id="fb2cf-111">Remarks</span></span>  
 <span data-ttu-id="fb2cf-112">소스 코드 파일에 [Option Explicit 문이](../../../visual-basic/language-reference/statements/option-explicit-statement.md)포함된 경우 `-optionexplicit` 문은 명령줄 컴파일러 설정을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fb2cf-112">If the source code file contains an [Option Explicit statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md), the statement overrides the `-optionexplicit` command-line compiler setting.</span></span>  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a><span data-ttu-id="fb2cf-113">비주얼 스튜디오 IDE에서 -optionexplicit를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="fb2cf-113">To set -optionexplicit in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="fb2cf-114">**솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb2cf-114">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="fb2cf-115">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fb2cf-115">On the **Project** menu, click **Properties**.</span></span>
  
2. <span data-ttu-id="fb2cf-116">**컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fb2cf-116">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="fb2cf-117">**옵션 명시적** 상자의 값을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="fb2cf-117">Modify the value in the **Option Explicit** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb2cf-118">예제</span><span class="sxs-lookup"><span data-stu-id="fb2cf-118">Example</span></span>  
 <span data-ttu-id="fb2cf-119">다음 코드는 사용될 `-optionexplicit-` 때 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb2cf-119">The following code compiles when `-optionexplicit-` is used.</span></span>  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="fb2cf-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fb2cf-120">See also</span></span>

- [<span data-ttu-id="fb2cf-121">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="fb2cf-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="fb2cf-122">-옵션 비교</span><span class="sxs-lookup"><span data-stu-id="fb2cf-122">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="fb2cf-123">-옵션 스밀</span><span class="sxs-lookup"><span data-stu-id="fb2cf-123">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="fb2cf-124">- 옵션 인퍼</span><span class="sxs-lookup"><span data-stu-id="fb2cf-124">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="fb2cf-125">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="fb2cf-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="fb2cf-126">Option Explicit 문</span><span class="sxs-lookup"><span data-stu-id="fb2cf-126">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="fb2cf-127">옵션 대화 상자, 프로젝트, VB 기본값</span><span class="sxs-lookup"><span data-stu-id="fb2cf-127">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
