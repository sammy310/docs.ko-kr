---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: dd98b45d75ff421dc81666ed47695132a49bfa3a
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524473"
---
# <a name="-addmodule"></a><span data-ttu-id="85c85-102">-addmodule</span><span class="sxs-lookup"><span data-stu-id="85c85-102">-addmodule</span></span>
<span data-ttu-id="85c85-103">컴파일러에서 지정된 파일의 모든 형식 정보를 현재 컴파일하고 있는 프로젝트에 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="85c85-103">Causes the compiler to make all type information from the specified file(s) available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85c85-104">구문</span><span class="sxs-lookup"><span data-stu-id="85c85-104">Syntax</span></span>  
  
```console  
-addmodule:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="85c85-105">인수</span><span class="sxs-lookup"><span data-stu-id="85c85-105">Arguments</span></span>  
 `fileList`  
 <span data-ttu-id="85c85-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="85c85-106">Required.</span></span> <span data-ttu-id="85c85-107">메타 데이터를 포함 하지만 어셈블리 매니페스트를 포함 하지 않는 파일의 쉼표로 구분 된 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="85c85-107">Comma-delimited list of files that contain metadata but do not contain assembly manifests.</span></span> <span data-ttu-id="85c85-108">공백이 포함 된 파일 이름은 큰따옴표 ("")로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85c85-108">File names containing spaces should be surrounded by quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85c85-109">주의</span><span class="sxs-lookup"><span data-stu-id="85c85-109">Remarks</span></span>  
 <span data-ttu-id="85c85-110">@No__t_0 매개 변수를 사용 하 여 나열 되는 파일은 `-target:module` 옵션을 사용 하 여 생성 하거나 다른 컴파일러의 `-target:module`와 동일 하 게 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85c85-110">The files listed by the `fileList` parameter must be created with the `-target:module` option, or with another compiler's equivalent to `-target:module`.</span></span>  
  
 <span data-ttu-id="85c85-111">@No__t_0로 추가 된 모든 모듈은 런타임에 출력 파일과 동일한 디렉터리에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85c85-111">All modules added with `-addmodule` must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="85c85-112">즉, 컴파일 시간에 모든 디렉터리에 모듈을 지정할 수 있지만 런타임에 모듈이 응용 프로그램 디렉터리에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85c85-112">That is, you can specify a module in any directory at compile time, but the module must be in the application directory at run time.</span></span> <span data-ttu-id="85c85-113">그렇지 않으면 <xref:System.TypeLoadException> 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="85c85-113">If it is not, you get a <xref:System.TypeLoadException> error.</span></span>  
  
 <span data-ttu-id="85c85-114">@No__t_2를 사용 하 여 `-target:module` 이외의 임의의[대상 (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) 옵션을 지정 하면 `-addmodule`에 전달 하는 파일이 프로젝트 어셈블리의 일부가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85c85-114">If you specify (implicitly or explicitly) any[-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) option other than `-target:module` with `-addmodule`, the files you pass to `-addmodule` become part of the project's assembly.</span></span> <span data-ttu-id="85c85-115">@No__t_0를 사용 하 여 추가 된 파일이 하나 이상 있는 출력 파일을 실행 하려면 어셈블리가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="85c85-115">An assembly is required to run an output file that has one or more files added with `-addmodule`.</span></span>  
  
 <span data-ttu-id="85c85-116">[-Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) 를 사용 하 여 어셈블리를 포함 하는 파일에서 메타 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="85c85-116">Use [-reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) to import metadata from a file that contains an assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="85c85-117">@No__t_0 옵션은 Visual Studio 개발 환경에서 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85c85-117">The `-addmodule` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85c85-118">예제</span><span class="sxs-lookup"><span data-stu-id="85c85-118">Example</span></span>  
 <span data-ttu-id="85c85-119">다음 코드에서는 모듈을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85c85-119">The following code creates a module.</span></span>  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 <span data-ttu-id="85c85-120">다음 코드에서는 모듈의 형식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="85c85-120">The following code imports the module's types.</span></span>  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 <span data-ttu-id="85c85-121">@No__t_0를 실행 하면 `802` 출력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85c85-121">When you run `t1`, it outputs `802`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85c85-122">참조</span><span class="sxs-lookup"><span data-stu-id="85c85-122">See also</span></span>

- [<span data-ttu-id="85c85-123">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="85c85-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="85c85-124">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85c85-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="85c85-125">-reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85c85-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="85c85-126">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="85c85-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
