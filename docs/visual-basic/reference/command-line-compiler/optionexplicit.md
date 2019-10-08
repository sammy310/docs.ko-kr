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
ms.openlocfilehash: 5c0946b94bfe02d797d1a484088869375703eb6a
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005314"
---
# <a name="-optionexplicit"></a><span data-ttu-id="9ee50-102">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="9ee50-102">-optionexplicit</span></span>
<span data-ttu-id="9ee50-103">변수가 사용 되기 전에 선언 되지 않은 경우 컴파일러가 오류를 보고 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ee50-103">Causes the compiler to report errors if variables are not declared before they are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ee50-104">구문</span><span class="sxs-lookup"><span data-stu-id="9ee50-104">Syntax</span></span>  
  
```console  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="9ee50-105">인수</span><span class="sxs-lookup"><span data-stu-id="9ee50-105">Arguments</span></span>  
 <span data-ttu-id="9ee50-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="9ee50-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="9ee50-107">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="9ee50-107">Optional.</span></span> <span data-ttu-id="9ee50-108">명시적 변수 선언이 필요 하면 `-optionexplicit+`을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ee50-108">Specify `-optionexplicit+` to require explicit declaration of variables.</span></span> <span data-ttu-id="9ee50-109">@No__t-0 옵션이 기본값이 며 `-optionexplicit`과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ee50-109">The `-optionexplicit+` option is the default and is the same as `-optionexplicit`.</span></span> <span data-ttu-id="9ee50-110">@No__t-0 옵션은 변수의 암시적 선언을 가능 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ee50-110">The `-optionexplicit-` option enables implicit declaration of variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ee50-111">설명</span><span class="sxs-lookup"><span data-stu-id="9ee50-111">Remarks</span></span>  
 <span data-ttu-id="9ee50-112">소스 코드 파일에 [Option Explicit 문이](../../../visual-basic/language-reference/statements/option-explicit-statement.md)포함 되어 있으면 문이 `-optionexplicit` 명령줄 컴파일러 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ee50-112">If the source code file contains an [Option Explicit statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md), the statement overrides the `-optionexplicit` command-line compiler setting.</span></span>  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a><span data-ttu-id="9ee50-113">Visual Studio IDE에서-기능을 명시적으로 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="9ee50-113">To set -optionexplicit in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="9ee50-114">**솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9ee50-114">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="9ee50-115">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9ee50-115">On the **Project** menu, click **Properties**.</span></span>   
  
2. <span data-ttu-id="9ee50-116">**컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9ee50-116">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="9ee50-117">**옵션 Explicit** 상자에서 값을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ee50-117">Modify the value in the **Option Explicit** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ee50-118">예제</span><span class="sxs-lookup"><span data-stu-id="9ee50-118">Example</span></span>  
 <span data-ttu-id="9ee50-119">다음 코드는 `-optionexplicit-`이 사용 될 때 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ee50-119">The following code compiles when `-optionexplicit-` is used.</span></span>  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="9ee50-120">참조</span><span class="sxs-lookup"><span data-stu-id="9ee50-120">See also</span></span>

- [<span data-ttu-id="9ee50-121">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="9ee50-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="9ee50-122">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="9ee50-122">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="9ee50-123">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="9ee50-123">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="9ee50-124">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="9ee50-124">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="9ee50-125">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="9ee50-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="9ee50-126">Option Explicit 문</span><span class="sxs-lookup"><span data-stu-id="9ee50-126">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="9ee50-127">옵션 대화 상자, 프로젝트, Visual Basic 기본값</span><span class="sxs-lookup"><span data-stu-id="9ee50-127">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
