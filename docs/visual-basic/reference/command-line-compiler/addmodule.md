---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: 2de5fe82f1969a2fdb305d45951d7d698252c0c8
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816436"
---
# <a name="-addmodule"></a><span data-ttu-id="37040-102">-addmodule</span><span class="sxs-lookup"><span data-stu-id="37040-102">-addmodule</span></span>
<span data-ttu-id="37040-103">컴파일러에서 지정된 파일의 모든 형식 정보를 현재 컴파일하고 있는 프로젝트에 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="37040-103">Causes the compiler to make all type information from the specified file(s) available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37040-104">구문</span><span class="sxs-lookup"><span data-stu-id="37040-104">Syntax</span></span>  
  
```  
-addmodule:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="37040-105">인수</span><span class="sxs-lookup"><span data-stu-id="37040-105">Arguments</span></span>  
 `fileList`  
 <span data-ttu-id="37040-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="37040-106">Required.</span></span> <span data-ttu-id="37040-107">메타 데이터를 포함 하지만 어셈블리 매니페스트를 포함 하지 않은 파일의 쉼표로 구분 된 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="37040-107">Comma-delimited list of files that contain metadata but do not contain assembly manifests.</span></span> <span data-ttu-id="37040-108">공백이 포함 된 파일 이름을 따옴표로 묶어야 ("").</span><span class="sxs-lookup"><span data-stu-id="37040-108">File names containing spaces should be surrounded by quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37040-109">설명</span><span class="sxs-lookup"><span data-stu-id="37040-109">Remarks</span></span>  
 <span data-ttu-id="37040-110">나열 된 파일을 `fileList` 매개 변수를 사용 하 여 만들어야 합니다를 `-target:module` 옵션을 또는 다른 컴파일러의 동일 `-target:module`합니다.</span><span class="sxs-lookup"><span data-stu-id="37040-110">The files listed by the `fileList` parameter must be created with the `-target:module` option, or with another compiler's equivalent to `-target:module`.</span></span>  
  
 <span data-ttu-id="37040-111">사용 하 여 추가 된 모든 모듈 `-addmodule` 런타임에 출력 파일과 동일한 디렉터리에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37040-111">All modules added with `-addmodule` must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="37040-112">즉, 컴파일 타임에 모든 디렉터리의 모듈을 지정할 수 있지만 런타임에 모듈이 응용 프로그램 디렉터리 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37040-112">That is, you can specify a module in any directory at compile time, but the module must be in the application directory at run time.</span></span> <span data-ttu-id="37040-113">그렇지 않은 경우 표시는 <xref:System.TypeLoadException> 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="37040-113">If it is not, you get a <xref:System.TypeLoadException> error.</span></span>  
  
 <span data-ttu-id="37040-114">(암시적 또는 명시적)을 지정 하면 모든[-대상 (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) 이외의 옵션 `-target:module` 사용 하 여 `-addmodule`에 전달 되는 파일이 `-addmodule` 프로젝트의 어셈블리의 일부가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37040-114">If you specify (implicitly or explicitly) any[-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) option other than `-target:module` with `-addmodule`, the files you pass to `-addmodule` become part of the project's assembly.</span></span> <span data-ttu-id="37040-115">어셈블리에 있는 출력 파일을 실행 해야 합니다. 또는 더 많은 파일 추가 `-addmodule`합니다.</span><span class="sxs-lookup"><span data-stu-id="37040-115">An assembly is required to run an output file that has one or more files added with `-addmodule`.</span></span>  
  
 <span data-ttu-id="37040-116">사용 하 여 [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) 어셈블리가 포함 된 파일에서 메타 데이터를 가져오려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="37040-116">Use [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) to import metadata from a file that contains an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="37040-117">`-addmodule` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 있는 명령줄에서 컴파일할 경우에 사용할 수 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="37040-117">The `-addmodule` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37040-118">예제</span><span class="sxs-lookup"><span data-stu-id="37040-118">Example</span></span>  
 <span data-ttu-id="37040-119">다음 코드는 모듈을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="37040-119">The following code creates a module.</span></span>  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 <span data-ttu-id="37040-120">다음 코드는 모듈의 형식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="37040-120">The following code imports the module's types.</span></span>  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 <span data-ttu-id="37040-121">실행할 때 `t1`, 출력 `802`합니다.</span><span class="sxs-lookup"><span data-stu-id="37040-121">When you run `t1`, it outputs `802`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37040-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="37040-122">See also</span></span>

- [<span data-ttu-id="37040-123">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="37040-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="37040-124">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37040-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="37040-125">-참조 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37040-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="37040-126">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="37040-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
