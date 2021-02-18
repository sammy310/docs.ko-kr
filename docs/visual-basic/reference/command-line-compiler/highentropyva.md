---
description: '자세한 정보: -highentropyva(Visual Basic)'
title: -highentropyva
ms.date: 03/10/2018
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
ms.openlocfilehash: 90fc3713ae4f9a073a63a57c5b35114548e26cbb
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100470267"
---
# <a name="-highentropyva-visual-basic"></a><span data-ttu-id="a6207-103">-highentropyva(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a6207-103">-highentropyva (Visual Basic)</span></span>

<span data-ttu-id="a6207-104">[-platform:anycpu](platform.md) 컴파일러 옵션으로 표시된 실행 파일 또는 64비트 실행 파일이 높은 엔트로피의 ASLR(주소 공간 레이아웃 불규칙화)을 지원하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a6207-104">Indicates whether a 64-bit executable or an executable that's marked by the [-platform:anycpu](platform.md) compiler option supports high entropy Address Space Layout Randomization (ASLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6207-105">구문</span><span class="sxs-lookup"><span data-stu-id="a6207-105">Syntax</span></span>  
  
```console  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="a6207-106">인수</span><span class="sxs-lookup"><span data-stu-id="a6207-106">Arguments</span></span>  

 <span data-ttu-id="a6207-107">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="a6207-107">`+` &#124; `-`</span></span>  
 <span data-ttu-id="a6207-108">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a6207-108">Optional.</span></span> <span data-ttu-id="a6207-109">이 옵션은 기본적으로 또는 `-highentropyva-`를 지정하는 경우 off입니다.</span><span class="sxs-lookup"><span data-stu-id="a6207-109">The option is off by default or if you specify `-highentropyva-`.</span></span> <span data-ttu-id="a6207-110">`-highentropyva` 또는 `-highentropyva+`를 지정하는 경우에는 이 옵션이 on입니다.</span><span class="sxs-lookup"><span data-stu-id="a6207-110">The option is on if you specify `-highentropyva` or `-highentropyva+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6207-111">설명</span><span class="sxs-lookup"><span data-stu-id="a6207-111">Remarks</span></span>  

 <span data-ttu-id="a6207-112">이 옵션을 지정할 경우 Windows 커널의 호환되는 버전이 ASLR의 일부로 프로세스의 주소 공간 레이아웃을 임의로 선택할 때 보다 높은 수준의 엔트로피를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6207-112">If you specify this option, compatible versions of the Windows kernel can use higher degrees of entropy when the kernel randomizes the address space layout of a process as part of ASLR.</span></span> <span data-ttu-id="a6207-113">커널이 더 높은 수준의 엔트로피를 사용하면 스택 및 힙과 같은 메모리 영역에 더 많은 주소를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6207-113">If the kernel uses higher degrees of entropy, a larger number of addresses can be allocated to memory regions such as stacks and heaps.</span></span> <span data-ttu-id="a6207-114">따라서 특정 메모리 영역의 위치를 추측하기 어려워집니다.</span><span class="sxs-lookup"><span data-stu-id="a6207-114">As a result, it is more difficult to guess the location of a particular memory region.</span></span>  
  
 <span data-ttu-id="a6207-115">이 옵션이 on이면 대상 실행 파일과 이 실행 파일이 종속된 모든 모듈이 64비트 프로세스로 실행될 때 4GB보다 큰 포인터 값을 처리할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6207-115">When the option is on, the target executable and any modules on which it depends must be able to handle pointer values that are larger than 4 gigabytes (GB) when those modules are running as 64-bit processes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6207-116">참조</span><span class="sxs-lookup"><span data-stu-id="a6207-116">See also</span></span>

- [<span data-ttu-id="a6207-117">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="a6207-117">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="a6207-118">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="a6207-118">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
