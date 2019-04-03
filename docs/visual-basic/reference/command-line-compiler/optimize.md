---
title: -optimize
ms.date: 07/20/2015
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
ms.openlocfilehash: eb84e0a7038e7ff8cb399ac7222b6ac1661b5bc1
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842163"
---
# <a name="-optimize"></a><span data-ttu-id="97229-102">-optimize</span><span class="sxs-lookup"><span data-stu-id="97229-102">-optimize</span></span>
<span data-ttu-id="97229-103">사용 하거나 컴파일러 최적화를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="97229-103">Enables or disables compiler optimizations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97229-104">구문</span><span class="sxs-lookup"><span data-stu-id="97229-104">Syntax</span></span>  
  
```  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="97229-105">인수</span><span class="sxs-lookup"><span data-stu-id="97229-105">Arguments</span></span>  
  
|<span data-ttu-id="97229-106">용어</span><span class="sxs-lookup"><span data-stu-id="97229-106">Term</span></span>|<span data-ttu-id="97229-107">정의</span><span class="sxs-lookup"><span data-stu-id="97229-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="97229-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="97229-108">`+` &#124; `-`</span></span>|<span data-ttu-id="97229-109">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="97229-109">Optional.</span></span> <span data-ttu-id="97229-110">`-optimize-` 옵션 컴파일러 최적화를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="97229-110">The `-optimize-` option disables compiler optimizations.</span></span> <span data-ttu-id="97229-111">`-optimize+` 옵션 최적화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97229-111">The `-optimize+` option enables optimizations.</span></span> <span data-ttu-id="97229-112">최적화는 기본적으로 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97229-112">By default, optimizations are disabled.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97229-113">설명</span><span class="sxs-lookup"><span data-stu-id="97229-113">Remarks</span></span>  
 <span data-ttu-id="97229-114">컴파일러 최적화를 통해 더 작지만 빠르고 효율적인 출력 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="97229-114">Compiler optimizations make your output file smaller, faster, and more efficient.</span></span> <span data-ttu-id="97229-115">그러나 최적화로 인해 출력 파일에서 코드가 다시 정렬 되기 때문에, `-optimize+` 디버깅이 어려워질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97229-115">However, because optimizations result in code rearrangement in the output file, `-optimize+` can make debugging difficult.</span></span>  
  
 <span data-ttu-id="97229-116">사용 하 여 생성 된 모든 모듈 `-target:module` 어셈블리는 동일한 사용 해야 합니다 `-optimize` 어셈블리로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="97229-116">All modules generated with `-target:module` for an assembly must use the same `-optimize` settings as the assembly.</span></span> <span data-ttu-id="97229-117">자세한 내용은 [-대상 (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="97229-117">For more information, see [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span>  
  
 <span data-ttu-id="97229-118">결합할 수 있습니다 합니다 `-optimize` 고 `-debug` 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="97229-118">You can combine the `-optimize` and `-debug` options.</span></span>  
  
|<span data-ttu-id="97229-119">Visual Studio 통합된 개발 환경 설정-최적화</span><span class="sxs-lookup"><span data-stu-id="97229-119">To set -optimize in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="97229-120">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="97229-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="97229-121">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="97229-121">On the **Project** menu, click **Properties**.</span></span><br />     <br /><span data-ttu-id="97229-122">2.  **컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="97229-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="97229-123">3.  **고급** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="97229-123">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="97229-124">4.  수정 된 **최적화를 사용 하도록 설정** 확인란 합니다.</span><span class="sxs-lookup"><span data-stu-id="97229-124">4.  Modify the **Enable optimizations** check box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="97229-125">예제</span><span class="sxs-lookup"><span data-stu-id="97229-125">Example</span></span>  
 <span data-ttu-id="97229-126">다음 코드에서는 `T2.vb` 컴파일러 최적화를 사용 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97229-126">The following code compiles `T2.vb` and enables compiler optimizations.</span></span>  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="97229-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="97229-127">See also</span></span>

- [<span data-ttu-id="97229-128">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="97229-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="97229-129">-디버그 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="97229-129">-debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)
- [<span data-ttu-id="97229-130">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="97229-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="97229-131">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="97229-131">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
