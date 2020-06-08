---
title: -utf8output
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: 0a16cdc535de5ed0619bf080bb4637449b11cfef
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403059"
---
# <a name="-utf8output-visual-basic"></a><span data-ttu-id="d0191-102">-utf8output(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d0191-102">-utf8output (Visual Basic)</span></span>
<span data-ttu-id="d0191-103">UTF-8 인코딩을 사용하여 컴파일러 출력을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d0191-103">Displays compiler output using UTF-8 encoding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0191-104">구문</span><span class="sxs-lookup"><span data-stu-id="d0191-104">Syntax</span></span>  
  
```console  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="d0191-105">인수</span><span class="sxs-lookup"><span data-stu-id="d0191-105">Arguments</span></span>  
 <span data-ttu-id="d0191-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="d0191-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="d0191-107">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d0191-107">Optional.</span></span> <span data-ttu-id="d0191-108">이 옵션의 기본값은 `-utf8output-`입니다. 즉, 컴파일러 출력에서 UTF-8 인코딩을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0191-108">The default for this option is `-utf8output-`, which means compiler output does not use UTF-8 encoding.</span></span> <span data-ttu-id="d0191-109">`-utf8output`를 지정하는 것은 `-utf8output+`를 지정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d0191-109">Specifying `-utf8output` is the same as specifying `-utf8output+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0191-110">설명</span><span class="sxs-lookup"><span data-stu-id="d0191-110">Remarks</span></span>  
 <span data-ttu-id="d0191-111">일부 국가별 구성에서는 컴파일러 출력이 콘솔에 올바르게 표시되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0191-111">In some international configurations, compiler output cannot be displayed correctly in the console.</span></span> <span data-ttu-id="d0191-112">이러한 경우 `-utf8output`을 사용하여 컴파일러 출력을 파일로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="d0191-112">In such situations, use `-utf8output` and redirect compiler output to a file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d0191-113">Visual Studio 개발 환경 내에서는 `-utf8output` 옵션을 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0191-113">The `-utf8output` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0191-114">예제</span><span class="sxs-lookup"><span data-stu-id="d0191-114">Example</span></span>  
 <span data-ttu-id="d0191-115">다음 코드는 `In.vb`를 컴파일하고 UTF-8 인코딩을 사용하여 출력을 표시하도록 컴파일러에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="d0191-115">The following code compiles `In.vb` and directs the compiler to display output using UTF-8 encoding.</span></span>  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d0191-116">참조</span><span class="sxs-lookup"><span data-stu-id="d0191-116">See also</span></span>

- [<span data-ttu-id="d0191-117">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="d0191-117">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="d0191-118">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="d0191-118">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
