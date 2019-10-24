---
title: -highentropyva (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
ms.openlocfilehash: 203380bbe2b2828e159ee36d795b6cd4a24e2917
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775651"
---
# <a name="-highentropyva-visual-basic"></a><span data-ttu-id="53d63-102">-highentropyva (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="53d63-102">-highentropyva (Visual Basic)</span></span>
<span data-ttu-id="53d63-103">[-Platform: anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) 컴파일러 옵션으로 표시 된 실행 파일이 나 64 비트 실행 파일이 높은 엔트로피의 ASLR (주소 공간 레이아웃 임의 지정)을 지원 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="53d63-103">Indicates whether a 64-bit executable or an executable that's marked by the [-platform:anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) compiler option supports high entropy Address Space Layout Randomization (ASLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53d63-104">구문</span><span class="sxs-lookup"><span data-stu-id="53d63-104">Syntax</span></span>  
  
```console  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="53d63-105">인수</span><span class="sxs-lookup"><span data-stu-id="53d63-105">Arguments</span></span>  
 <span data-ttu-id="53d63-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="53d63-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="53d63-107">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="53d63-107">Optional.</span></span> <span data-ttu-id="53d63-108">옵션은 기본적으로 off 이거나 `-highentropyva-` 지정 하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="53d63-108">The option is off by default or if you specify `-highentropyva-`.</span></span> <span data-ttu-id="53d63-109">@No__t_0 또는 `-highentropyva+`를 지정 하는 경우 옵션은 on입니다.</span><span class="sxs-lookup"><span data-stu-id="53d63-109">The option is on if you specify `-highentropyva` or `-highentropyva+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53d63-110">주의</span><span class="sxs-lookup"><span data-stu-id="53d63-110">Remarks</span></span>  
 <span data-ttu-id="53d63-111">이 옵션을 지정 하는 경우 커널에서 ASLR의 일부로 프로세스의 주소 공간 레이아웃을 임의화 하는 경우 호환 되는 버전의 Windows 커널에서 더 높은 수준의 엔트로피를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53d63-111">If you specify this option, compatible versions of the Windows kernel can use higher degrees of entropy when the kernel randomizes the address space layout of a process as part of ASLR.</span></span> <span data-ttu-id="53d63-112">커널이 높은 수준의 엔트로피를 사용 하는 경우 스택 및 힙과 같은 메모리 영역에 더 많은 주소를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53d63-112">If the kernel uses higher degrees of entropy, a larger number of addresses can be allocated to memory regions such as stacks and heaps.</span></span> <span data-ttu-id="53d63-113">따라서 특정 메모리 영역의 위치를 추측하기 어려워집니다.</span><span class="sxs-lookup"><span data-stu-id="53d63-113">As a result, it is more difficult to guess the location of a particular memory region.</span></span>  
  
 <span data-ttu-id="53d63-114">옵션을 on으로 설정 하면 대상 실행 파일과이 실행 파일이 종속 된 모든 모듈이 64 비트 프로세스로 실행 될 때 4gb 보다 큰 포인터 값을 처리할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53d63-114">When the option is on, the target executable and any modules on which it depends must be able to handle pointer values that are larger than 4 gigabytes (GB) when those modules are running as 64-bit processes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53d63-115">참조</span><span class="sxs-lookup"><span data-stu-id="53d63-115">See also</span></span>

- [<span data-ttu-id="53d63-116">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="53d63-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="53d63-117">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="53d63-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
