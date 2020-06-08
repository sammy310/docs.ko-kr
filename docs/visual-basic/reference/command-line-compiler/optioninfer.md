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
ms.openlocfilehash: 524660fca7c56fa490cc85169898bf2bf6d1a16e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400580"
---
# <a name="-optioninfer"></a><span data-ttu-id="3cfbf-102">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="3cfbf-102">-optioninfer</span></span>
<span data-ttu-id="3cfbf-103">변수 선언에서 지역 형식 유추를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3cfbf-103">Enables the use of local type inference in variable declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cfbf-104">구문</span><span class="sxs-lookup"><span data-stu-id="3cfbf-104">Syntax</span></span>  
  
```console  
-optioninfer[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="3cfbf-105">인수</span><span class="sxs-lookup"><span data-stu-id="3cfbf-105">Arguments</span></span>  
  
|<span data-ttu-id="3cfbf-106">용어</span><span class="sxs-lookup"><span data-stu-id="3cfbf-106">Term</span></span>|<span data-ttu-id="3cfbf-107">정의</span><span class="sxs-lookup"><span data-stu-id="3cfbf-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="3cfbf-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="3cfbf-108">`+` &#124; `-`</span></span>|<span data-ttu-id="3cfbf-109">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="3cfbf-109">Optional.</span></span> <span data-ttu-id="3cfbf-110">지역 형식 유추를 사용하도록 설정하려면 `-optioninfer+`를 지정하고, 차단하려면 `-optioninfer-`를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3cfbf-110">Specify `-optioninfer+` to enable local type inference, or `-optioninfer-` to block it.</span></span> <span data-ttu-id="3cfbf-111">값을 지정하지 않은 `-optioninfer` 옵션은 `-optioninfer+`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3cfbf-111">The `-optioninfer` option, with no value specified, is the same as `-optioninfer+`.</span></span> <span data-ttu-id="3cfbf-112">`-optioninfer` 스위치가 없을 때의 기본값도 `-optioninfer+`입니다.</span><span class="sxs-lookup"><span data-stu-id="3cfbf-112">The default value when the `-optioninfer` switch is not present is also `-optioninfer+`.</span></span> <span data-ttu-id="3cfbf-113">기본값은 vbc.rsp 지시 파일에서 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cfbf-113">The default value is set in the Vbc.rsp response file.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="3cfbf-114">`-noconfig` 옵션을 사용하여 vbc.rsp에 지정된 값 대신 컴파일러의 내부 기본값을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cfbf-114">You can use the `-noconfig` option to retain the compiler's internal defaults instead of those specified in vbc.rsp.</span></span> <span data-ttu-id="3cfbf-115">이 옵션에 대한 컴파일러 기본값은 `-optioninfer-`입니다.</span><span class="sxs-lookup"><span data-stu-id="3cfbf-115">The compiler default for this option is `-optioninfer-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3cfbf-116">설명</span><span class="sxs-lookup"><span data-stu-id="3cfbf-116">Remarks</span></span>  
 <span data-ttu-id="3cfbf-117">소스 코드 파일에 [Option Infer 문](../../language-reference/statements/option-infer-statement.md)이 포함되어 있는 경우 해당 명령문이 `-optioninfer` 명령줄 컴파일러 설정을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3cfbf-117">If the source code file contains an [Option Infer Statement](../../language-reference/statements/option-infer-statement.md), the statement overrides the `-optioninfer` command-line compiler setting.</span></span>  
  
### <a name="to-set--optioninfer-in-the-visual-studio-ide"></a><span data-ttu-id="3cfbf-118">Visual Studio IDE에서 -optioninfer를 설정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3cfbf-118">To set -optioninfer in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="3cfbf-119">**솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3cfbf-119">Select a project in **Solution Explorer**.</span></span> <span data-ttu-id="3cfbf-120">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3cfbf-120">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="3cfbf-121">**컴파일** 탭에서 **Option infer** 상자의 값을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="3cfbf-121">On the **Compile** tab, modify the value in the **Option infer** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cfbf-122">예제</span><span class="sxs-lookup"><span data-stu-id="3cfbf-122">Example</span></span>  
 <span data-ttu-id="3cfbf-123">다음 코드에서는 지역 형식 유추를 사용하도록 설정한 상태로 `test.vb`를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="3cfbf-123">The following code compiles `test.vb` with local type inference enabled.</span></span>  
  
```console
vbc -optioninfer+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="3cfbf-124">참조</span><span class="sxs-lookup"><span data-stu-id="3cfbf-124">See also</span></span>

- [<span data-ttu-id="3cfbf-125">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="3cfbf-125">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="3cfbf-126">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="3cfbf-126">-optioncompare</span></span>](optioncompare.md)
- [<span data-ttu-id="3cfbf-127">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="3cfbf-127">-optionexplicit</span></span>](optionexplicit.md)
- [<span data-ttu-id="3cfbf-128">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="3cfbf-128">-optionstrict</span></span>](optionstrict.md)
- [<span data-ttu-id="3cfbf-129">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="3cfbf-129">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="3cfbf-130">Option Infer 문</span><span class="sxs-lookup"><span data-stu-id="3cfbf-130">Option Infer Statement</span></span>](../../language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="3cfbf-131">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="3cfbf-131">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="3cfbf-132">옵션 대화 상자, 프로젝트, Visual Basic 기본값</span><span class="sxs-lookup"><span data-stu-id="3cfbf-132">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
- [<span data-ttu-id="3cfbf-133">프로젝트 디자이너, 컴파일 페이지(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3cfbf-133">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [<span data-ttu-id="3cfbf-134">-noconfig</span><span class="sxs-lookup"><span data-stu-id="3cfbf-134">-noconfig</span></span>](noconfig.md)
- [<span data-ttu-id="3cfbf-135">명령줄에서 빌드</span><span class="sxs-lookup"><span data-stu-id="3cfbf-135">Building from the Command Line</span></span>](building-from-the-command-line.md)
