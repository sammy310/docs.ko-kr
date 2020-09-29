---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: c5bf988d819a8df8aed99588abbb30e19d14b1ac
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91084985"
---
# <a name="-verbose"></a><span data-ttu-id="ecc2f-102">-verbose</span><span class="sxs-lookup"><span data-stu-id="ecc2f-102">-verbose</span></span>

<span data-ttu-id="ecc2f-103">컴파일러가 자세한 상태 및 오류 메시지를 생성하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecc2f-103">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecc2f-104">구문</span><span class="sxs-lookup"><span data-stu-id="ecc2f-104">Syntax</span></span>  
  
```console  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="ecc2f-105">인수</span><span class="sxs-lookup"><span data-stu-id="ecc2f-105">Arguments</span></span>  

 <span data-ttu-id="ecc2f-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="ecc2f-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="ecc2f-107">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="ecc2f-107">Optional.</span></span> <span data-ttu-id="ecc2f-108">`-verbose`를 지정하는 것은 `-verbose+`를 지정하는 것과 동일하며, 이로 인해 컴파일러가 자세한 정보 메시지를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="ecc2f-108">Specifying `-verbose` is the same as specifying `-verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="ecc2f-109">이 옵션의 기본값은 `-verbose-`입니다.</span><span class="sxs-lookup"><span data-stu-id="ecc2f-109">The default for this option is `-verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ecc2f-110">설명</span><span class="sxs-lookup"><span data-stu-id="ecc2f-110">Remarks</span></span>  

 <span data-ttu-id="ecc2f-111">`-verbose` 옵션은 컴파일러에서 발생한 총 오류 수에 대한 정보를 표시하고, 모듈에서 로드되는 어셈블리를 보고하고, 현재 컴파일되는 파일을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ecc2f-111">The `-verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ecc2f-112">Visual Studio 개발 환경 내에서는 `-verbose` 옵션을 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecc2f-112">The `-verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ecc2f-113">예제</span><span class="sxs-lookup"><span data-stu-id="ecc2f-113">Example</span></span>  

 <span data-ttu-id="ecc2f-114">다음 코드는 `In.vb`를 컴파일하고 자세한 상태 정보를 표시하도록 컴파일러에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="ecc2f-114">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="ecc2f-115">참조</span><span class="sxs-lookup"><span data-stu-id="ecc2f-115">See also</span></span>

- [<span data-ttu-id="ecc2f-116">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="ecc2f-116">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="ecc2f-117">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="ecc2f-117">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
