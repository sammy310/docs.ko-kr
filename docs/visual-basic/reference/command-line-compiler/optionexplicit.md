---
description: '자세한 정보: -optionexplicit'
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
ms.openlocfilehash: 4d1ab14bbf9de176de17fb5077f4bb919f5472b4
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100433564"
---
# <a name="-optionexplicit"></a><span data-ttu-id="9ff62-103">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="9ff62-103">-optionexplicit</span></span>

<span data-ttu-id="9ff62-104">변수를 사용하기 전에 선언되지 않은 경우 컴파일러에서 오류를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff62-104">Causes the compiler to report errors if variables are not declared before they are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ff62-105">구문</span><span class="sxs-lookup"><span data-stu-id="9ff62-105">Syntax</span></span>  
  
```console  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="9ff62-106">인수</span><span class="sxs-lookup"><span data-stu-id="9ff62-106">Arguments</span></span>  

 <span data-ttu-id="9ff62-107">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="9ff62-107">`+` &#124; `-`</span></span>  
 <span data-ttu-id="9ff62-108">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="9ff62-108">Optional.</span></span> <span data-ttu-id="9ff62-109">명시적 변수 선언이 필요하면 `-optionexplicit+`를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff62-109">Specify `-optionexplicit+` to require explicit declaration of variables.</span></span> <span data-ttu-id="9ff62-110">`-optionexplicit+` 옵션이 기본값이며 `-optionexplicit`와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff62-110">The `-optionexplicit+` option is the default and is the same as `-optionexplicit`.</span></span> <span data-ttu-id="9ff62-111">`-optionexplicit-` 옵션을 사용하면 변수를 암시적으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ff62-111">The `-optionexplicit-` option enables implicit declaration of variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ff62-112">설명</span><span class="sxs-lookup"><span data-stu-id="9ff62-112">Remarks</span></span>  

 <span data-ttu-id="9ff62-113">소스 코드 파일에 [Option Explicit 문](../../language-reference/statements/option-explicit-statement.md)이 포함되어 있으면 해당 명령문이 `-optionexplicit` 명령줄 컴파일러 설정을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff62-113">If the source code file contains an [Option Explicit statement](../../language-reference/statements/option-explicit-statement.md), the statement overrides the `-optionexplicit` command-line compiler setting.</span></span>  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a><span data-ttu-id="9ff62-114">Visual Studio IDE에서 -optionexplicit를 설정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff62-114">To set -optionexplicit in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="9ff62-115">**솔루션 탐색기** 에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff62-115">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="9ff62-116">**프로젝트** 메뉴에서 **속성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff62-116">On the **Project** menu, click **Properties**.</span></span>
  
2. <span data-ttu-id="9ff62-117">**컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff62-117">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="9ff62-118">**Option Explicit** 상자에서 값을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff62-118">Modify the value in the **Option Explicit** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ff62-119">예제</span><span class="sxs-lookup"><span data-stu-id="9ff62-119">Example</span></span>  

 <span data-ttu-id="9ff62-120">다음 코드는 `-optionexplicit-`가 사용될 때 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ff62-120">The following code compiles when `-optionexplicit-` is used.</span></span>  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="9ff62-121">참조</span><span class="sxs-lookup"><span data-stu-id="9ff62-121">See also</span></span>

- [<span data-ttu-id="9ff62-122">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="9ff62-122">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="9ff62-123">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="9ff62-123">-optioncompare</span></span>](optioncompare.md)
- [<span data-ttu-id="9ff62-124">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="9ff62-124">-optionstrict</span></span>](optionstrict.md)
- [<span data-ttu-id="9ff62-125">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="9ff62-125">-optioninfer</span></span>](optioninfer.md)
- [<span data-ttu-id="9ff62-126">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="9ff62-126">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="9ff62-127">Option Explicit 문</span><span class="sxs-lookup"><span data-stu-id="9ff62-127">Option Explicit Statement</span></span>](../../language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="9ff62-128">옵션 대화 상자, 프로젝트, Visual Basic 기본값</span><span class="sxs-lookup"><span data-stu-id="9ff62-128">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
