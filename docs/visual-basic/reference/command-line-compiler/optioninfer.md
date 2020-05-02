---
title: -optioninfer
ms.date: 07/20/2015
f1_keywords:
- -optioninfer
helpviewer_keywords:
- -optioninfer compiler option [Visual Basic]
- /optioninfer compiler option [Visual Basic]
- optioninfer compiler option [Visual Basic]
ms.assetid: f6c09db1-0553-464a-abe3-d4510c61d6ed
ms.openlocfilehash: d7209e431b84e52e487bccbf73bd633a346efde0
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775614"
---
# <a name="-optioninfer"></a><span data-ttu-id="46ecd-102">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="46ecd-102">-optioninfer</span></span>
<span data-ttu-id="46ecd-103">변수 선언에서 지역 형식 유추를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="46ecd-103">Enables the use of local type inference in variable declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46ecd-104">구문</span><span class="sxs-lookup"><span data-stu-id="46ecd-104">Syntax</span></span>  
  
```console  
-optioninfer[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="46ecd-105">인수</span><span class="sxs-lookup"><span data-stu-id="46ecd-105">Arguments</span></span>  
  
|<span data-ttu-id="46ecd-106">용어</span><span class="sxs-lookup"><span data-stu-id="46ecd-106">Term</span></span>|<span data-ttu-id="46ecd-107">정의</span><span class="sxs-lookup"><span data-stu-id="46ecd-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="46ecd-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="46ecd-108">`+` &#124; `-`</span></span>|<span data-ttu-id="46ecd-109">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="46ecd-109">Optional.</span></span> <span data-ttu-id="46ecd-110">지역 형식 유추를 사용하도록 설정하려면 `-optioninfer+`를 지정하고, 차단하려면 `-optioninfer-`를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="46ecd-110">Specify `-optioninfer+` to enable local type inference, or `-optioninfer-` to block it.</span></span> <span data-ttu-id="46ecd-111">값을 지정하지 않은 `-optioninfer` 옵션은 `-optioninfer+`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="46ecd-111">The `-optioninfer` option, with no value specified, is the same as `-optioninfer+`.</span></span> <span data-ttu-id="46ecd-112">`-optioninfer` 스위치가 없을 때의 기본값도 `-optioninfer+`입니다.</span><span class="sxs-lookup"><span data-stu-id="46ecd-112">The default value when the `-optioninfer` switch is not present is also `-optioninfer+`.</span></span> <span data-ttu-id="46ecd-113">기본값은 vbc.rsp 지시 파일에서 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="46ecd-113">The default value is set in the Vbc.rsp response file.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="46ecd-114">`-noconfig` 옵션을 사용하여 vbc.rsp에 지정된 값 대신 컴파일러의 내부 기본값을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46ecd-114">You can use the `-noconfig` option to retain the compiler's internal defaults instead of those specified in vbc.rsp.</span></span> <span data-ttu-id="46ecd-115">이 옵션에 대한 컴파일러 기본값은 `-optioninfer-`입니다.</span><span class="sxs-lookup"><span data-stu-id="46ecd-115">The compiler default for this option is `-optioninfer-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46ecd-116">설명</span><span class="sxs-lookup"><span data-stu-id="46ecd-116">Remarks</span></span>  
 <span data-ttu-id="46ecd-117">소스 코드 파일에 [Option Infer 문](../../../visual-basic/language-reference/statements/option-infer-statement.md)이 포함되어 있는 경우 해당 명령문이 `-optioninfer` 명령줄 컴파일러 설정을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="46ecd-117">If the source code file contains an [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md), the statement overrides the `-optioninfer` command-line compiler setting.</span></span>  
  
### <a name="to-set--optioninfer-in-the-visual-studio-ide"></a><span data-ttu-id="46ecd-118">Visual Studio IDE에서 -optioninfer를 설정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="46ecd-118">To set -optioninfer in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="46ecd-119">**솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="46ecd-119">Select a project in **Solution Explorer**.</span></span> <span data-ttu-id="46ecd-120">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="46ecd-120">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="46ecd-121">**컴파일** 탭에서 **Option infer** 상자의 값을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="46ecd-121">On the **Compile** tab, modify the value in the **Option infer** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46ecd-122">예제</span><span class="sxs-lookup"><span data-stu-id="46ecd-122">Example</span></span>  
 <span data-ttu-id="46ecd-123">다음 코드에서는 지역 형식 유추를 사용하도록 설정한 상태로 `test.vb`를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="46ecd-123">The following code compiles `test.vb` with local type inference enabled.</span></span>  
  
```console
vbc -optioninfer+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="46ecd-124">참조</span><span class="sxs-lookup"><span data-stu-id="46ecd-124">See also</span></span>

- [<span data-ttu-id="46ecd-125">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="46ecd-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="46ecd-126">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="46ecd-126">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="46ecd-127">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="46ecd-127">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="46ecd-128">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="46ecd-128">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="46ecd-129">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="46ecd-129">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="46ecd-130">Option Infer 문</span><span class="sxs-lookup"><span data-stu-id="46ecd-130">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="46ecd-131">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="46ecd-131">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="46ecd-132">옵션 대화 상자, 프로젝트, Visual Basic 기본값</span><span class="sxs-lookup"><span data-stu-id="46ecd-132">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
- [<span data-ttu-id="46ecd-133">프로젝트 디자이너, 컴파일 페이지(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="46ecd-133">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [<span data-ttu-id="46ecd-134">-noconfig</span><span class="sxs-lookup"><span data-stu-id="46ecd-134">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="46ecd-135">명령줄에서 빌드</span><span class="sxs-lookup"><span data-stu-id="46ecd-135">Building from the Command Line</span></span>](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)
