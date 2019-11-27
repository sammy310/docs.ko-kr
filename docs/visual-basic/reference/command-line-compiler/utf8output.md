---
title: -utf8output
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: 5cdc60888cd872940afc1b03febd879bb6d87c2e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350834"
---
# <a name="-utf8output-visual-basic"></a><span data-ttu-id="2b748-102">-utf8output (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2b748-102">-utf8output (Visual Basic)</span></span>
<span data-ttu-id="2b748-103">UTF-8 인코딩을 사용하여 컴파일러 출력을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2b748-103">Displays compiler output using UTF-8 encoding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b748-104">구문</span><span class="sxs-lookup"><span data-stu-id="2b748-104">Syntax</span></span>  
  
```console  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="2b748-105">인수</span><span class="sxs-lookup"><span data-stu-id="2b748-105">Arguments</span></span>  
 <span data-ttu-id="2b748-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="2b748-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="2b748-107">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="2b748-107">Optional.</span></span> <span data-ttu-id="2b748-108">이 옵션의 기본값은 `-utf8output-`입니다. 즉, 컴파일러 출력에서 UTF-8 인코딩을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b748-108">The default for this option is `-utf8output-`, which means compiler output does not use UTF-8 encoding.</span></span> <span data-ttu-id="2b748-109">`-utf8output`를 지정하는 것은 `-utf8output+`를 지정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2b748-109">Specifying `-utf8output` is the same as specifying `-utf8output+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b748-110">주의</span><span class="sxs-lookup"><span data-stu-id="2b748-110">Remarks</span></span>  
 <span data-ttu-id="2b748-111">일부 국가별 구성에서는 컴파일러 출력이 콘솔에 올바르게 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b748-111">In some international configurations, compiler output cannot be displayed correctly in the console.</span></span> <span data-ttu-id="2b748-112">이러한 경우 `-utf8output`를 사용 하 고 컴파일러 출력을 파일로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="2b748-112">In such situations, use `-utf8output` and redirect compiler output to a file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2b748-113">`-utf8output` 옵션은 Visual Studio 개발 환경에서 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b748-113">The `-utf8output` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b748-114">예제</span><span class="sxs-lookup"><span data-stu-id="2b748-114">Example</span></span>  
 <span data-ttu-id="2b748-115">다음 코드는 `In.vb` 컴파일하고 UTF-8 인코딩을 사용 하 여 출력을 표시 하도록 컴파일러에 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b748-115">The following code compiles `In.vb` and directs the compiler to display output using UTF-8 encoding.</span></span>  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="2b748-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2b748-116">See also</span></span>

- [<span data-ttu-id="2b748-117">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="2b748-117">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="2b748-118">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="2b748-118">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
