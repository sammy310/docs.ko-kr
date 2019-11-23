---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: 8c5bc1d2ce331b8fe9461f91d64fbeab5a070b59
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004980"
---
# <a name="-verbose"></a><span data-ttu-id="4cc3f-102">-verbose</span><span class="sxs-lookup"><span data-stu-id="4cc3f-102">-verbose</span></span>
<span data-ttu-id="4cc3f-103">컴파일러가 자세한 상태 및 오류 메시지를 생성 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc3f-103">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cc3f-104">구문</span><span class="sxs-lookup"><span data-stu-id="4cc3f-104">Syntax</span></span>  
  
```console  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="4cc3f-105">인수</span><span class="sxs-lookup"><span data-stu-id="4cc3f-105">Arguments</span></span>  
 <span data-ttu-id="4cc3f-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="4cc3f-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="4cc3f-107">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="4cc3f-107">Optional.</span></span> <span data-ttu-id="4cc3f-108">`-verbose` 지정은 `-verbose+`를 지정 하는 것과 동일 하며,이로 인해 컴파일러가 자세한 정보 메시지를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="4cc3f-108">Specifying `-verbose` is the same as specifying `-verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="4cc3f-109">이 옵션의 기본값은 `-verbose-`입니다.</span><span class="sxs-lookup"><span data-stu-id="4cc3f-109">The default for this option is `-verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4cc3f-110">주의</span><span class="sxs-lookup"><span data-stu-id="4cc3f-110">Remarks</span></span>  
 <span data-ttu-id="4cc3f-111">`-verbose` 옵션은 컴파일러에서 실행 된 총 오류 수에 대 한 정보를 표시 하 고, 모듈에서 로드 되는 어셈블리를 보고 하 고, 현재 컴파일되는 파일을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc3f-111">The `-verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4cc3f-112">`-verbose` 옵션은 Visual Studio 개발 환경에서 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cc3f-112">The `-verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4cc3f-113">예제</span><span class="sxs-lookup"><span data-stu-id="4cc3f-113">Example</span></span>  
 <span data-ttu-id="4cc3f-114">다음 코드는 `In.vb` 컴파일하고 자세한 상태 정보를 표시 하도록 컴파일러에 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cc3f-114">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="4cc3f-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4cc3f-115">See also</span></span>

- [<span data-ttu-id="4cc3f-116">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="4cc3f-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="4cc3f-117">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="4cc3f-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
