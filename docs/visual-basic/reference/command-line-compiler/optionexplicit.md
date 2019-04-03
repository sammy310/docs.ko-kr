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
ms.openlocfilehash: 4aca6e9c20dbce7aa8a94067c96fcf44329a6fe4
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814876"
---
# <a name="-optionexplicit"></a><span data-ttu-id="94800-102">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="94800-102">-optionexplicit</span></span>
<span data-ttu-id="94800-103">컴파일러에서 오류를 보고 사용 하기 전에 선언 되지 않은 경우.</span><span class="sxs-lookup"><span data-stu-id="94800-103">Causes the compiler to report errors if variables are not declared before they are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94800-104">구문</span><span class="sxs-lookup"><span data-stu-id="94800-104">Syntax</span></span>  
  
```  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="94800-105">인수</span><span class="sxs-lookup"><span data-stu-id="94800-105">Arguments</span></span>  
 <span data-ttu-id="94800-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="94800-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="94800-107">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="94800-107">Optional.</span></span> <span data-ttu-id="94800-108">지정 `-optionexplicit+` 변수의 명시적 선언이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="94800-108">Specify `-optionexplicit+` to require explicit declaration of variables.</span></span> <span data-ttu-id="94800-109">합니다 `-optionexplicit+` 옵션은 기본값 이므로 같습니다 `-optionexplicit`합니다.</span><span class="sxs-lookup"><span data-stu-id="94800-109">The `-optionexplicit+` option is the default and is the same as `-optionexplicit`.</span></span> <span data-ttu-id="94800-110">`-optionexplicit-` 암시적 변수 선언을 수 있도록 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="94800-110">The `-optionexplicit-` option enables implicit declaration of variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94800-111">설명</span><span class="sxs-lookup"><span data-stu-id="94800-111">Remarks</span></span>  
 <span data-ttu-id="94800-112">소스 코드 파일을 포함 하는 경우는 [Option Explicit 문](../../../visual-basic/language-reference/statements/option-explicit-statement.md), 문이 재정의 `-optionexplicit` 명령줄 컴파일러 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="94800-112">If the source code file contains an [Option Explicit statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md), the statement overrides the `-optionexplicit` command-line compiler setting.</span></span>  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a><span data-ttu-id="94800-113">-Optionexplicit Visual Studio IDE에서 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="94800-113">To set -optionexplicit in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="94800-114">**솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="94800-114">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="94800-115">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="94800-115">On the **Project** menu, click **Properties**.</span></span>   
  
2.  <span data-ttu-id="94800-116">**컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="94800-116">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="94800-117">값을 수정 합니다 **Option Explicit** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="94800-117">Modify the value in the **Option Explicit** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94800-118">예제</span><span class="sxs-lookup"><span data-stu-id="94800-118">Example</span></span>  
 <span data-ttu-id="94800-119">다음 코드는 경우 `-optionexplicit-` 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="94800-119">The following code compiles when `-optionexplicit-` is used.</span></span>  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="94800-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="94800-120">See also</span></span>

- [<span data-ttu-id="94800-121">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="94800-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="94800-122">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="94800-122">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="94800-123">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="94800-123">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="94800-124">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="94800-124">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="94800-125">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="94800-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="94800-126">Option Explicit 문</span><span class="sxs-lookup"><span data-stu-id="94800-126">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="94800-127">옵션 대화 상자, 프로젝트, Visual Basic 기본값</span><span class="sxs-lookup"><span data-stu-id="94800-127">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
