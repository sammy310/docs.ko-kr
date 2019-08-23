---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: 5b3899462af7c4aa8e0f77377a8d7485975f9867
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937266"
---
# <a name="-verbose"></a><span data-ttu-id="7dcbc-102">-verbose</span><span class="sxs-lookup"><span data-stu-id="7dcbc-102">-verbose</span></span>
<span data-ttu-id="7dcbc-103">컴파일러가 자세한 상태 및 오류 메시지를 생성 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dcbc-103">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dcbc-104">구문</span><span class="sxs-lookup"><span data-stu-id="7dcbc-104">Syntax</span></span>  
  
```  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="7dcbc-105">인수</span><span class="sxs-lookup"><span data-stu-id="7dcbc-105">Arguments</span></span>  
 <span data-ttu-id="7dcbc-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="7dcbc-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="7dcbc-107">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7dcbc-107">Optional.</span></span> <span data-ttu-id="7dcbc-108">를 지정 하는 것 `-verbose+` 은컴파일러가자세한정보메시지를내보내도록하는을지정하는것과같습니다.`-verbose`</span><span class="sxs-lookup"><span data-stu-id="7dcbc-108">Specifying `-verbose` is the same as specifying `-verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="7dcbc-109">이 옵션 `-verbose-`의 기본값은입니다.</span><span class="sxs-lookup"><span data-stu-id="7dcbc-109">The default for this option is `-verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7dcbc-110">설명</span><span class="sxs-lookup"><span data-stu-id="7dcbc-110">Remarks</span></span>  
 <span data-ttu-id="7dcbc-111">옵션 `-verbose` 은 컴파일러에서 발생 한 총 오류 수에 대 한 정보를 표시 하 고, 모듈에서 로드 되는 어셈블리를 보고 하 고, 현재 컴파일되는 파일을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dcbc-111">The `-verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7dcbc-112">이 `-verbose` 옵션은 Visual Studio 개발 환경에서 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7dcbc-112">The `-verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7dcbc-113">예제</span><span class="sxs-lookup"><span data-stu-id="7dcbc-113">Example</span></span>  
 <span data-ttu-id="7dcbc-114">다음 코드는 자세한 `In.vb` 상태 정보를 표시 하도록 컴파일러를 컴파일하고 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dcbc-114">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="7dcbc-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="7dcbc-115">See also</span></span>

- [<span data-ttu-id="7dcbc-116">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="7dcbc-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="7dcbc-117">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="7dcbc-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
