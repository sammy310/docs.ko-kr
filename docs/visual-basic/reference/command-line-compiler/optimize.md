---
title: -optimize
ms.date: 07/20/2015
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
ms.openlocfilehash: 337cb794ef9a405a178f1998cbe27b5da7709382
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397443"
---
# <a name="-optimize"></a><span data-ttu-id="fb3a0-102">-optimize</span><span class="sxs-lookup"><span data-stu-id="fb3a0-102">-optimize</span></span>
<span data-ttu-id="fb3a0-103">컴파일러 최적화를 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-103">Enables or disables compiler optimizations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb3a0-104">구문</span><span class="sxs-lookup"><span data-stu-id="fb3a0-104">Syntax</span></span>  
  
```console  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="fb3a0-105">인수</span><span class="sxs-lookup"><span data-stu-id="fb3a0-105">Arguments</span></span>  
  
|<span data-ttu-id="fb3a0-106">용어</span><span class="sxs-lookup"><span data-stu-id="fb3a0-106">Term</span></span>|<span data-ttu-id="fb3a0-107">정의</span><span class="sxs-lookup"><span data-stu-id="fb3a0-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="fb3a0-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="fb3a0-108">`+` &#124; `-`</span></span>|<span data-ttu-id="fb3a0-109">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-109">Optional.</span></span> <span data-ttu-id="fb3a0-110">`-optimize-` 옵션은 컴파일러 최적화를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-110">The `-optimize-` option disables compiler optimizations.</span></span> <span data-ttu-id="fb3a0-111">`-optimize+` 옵션은 최적화를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-111">The `-optimize+` option enables optimizations.</span></span> <span data-ttu-id="fb3a0-112">최적화는 기본적으로 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-112">By default, optimizations are disabled.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fb3a0-113">설명</span><span class="sxs-lookup"><span data-stu-id="fb3a0-113">Remarks</span></span>  
 <span data-ttu-id="fb3a0-114">컴파일러 최적화를 통해 더 작지만 빠르고 효율적인 출력 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-114">Compiler optimizations make your output file smaller, faster, and more efficient.</span></span> <span data-ttu-id="fb3a0-115">그러나 최적화로 인해 출력 파일에서 코드가 재배열되기 때문에 `-optimize+`는 디버깅을 어렵게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-115">However, because optimizations result in code rearrangement in the output file, `-optimize+` can make debugging difficult.</span></span>  
  
 <span data-ttu-id="fb3a0-116">어셈블리에 대해 `-target:module`을 사용하여 생성된 모든 모듈은 어셈블리와 동일한 `-optimize` 설정을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-116">All modules generated with `-target:module` for an assembly must use the same `-optimize` settings as the assembly.</span></span> <span data-ttu-id="fb3a0-117">자세한 내용은 [-target(Visual Basic)](target.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-117">For more information, see [-target (Visual Basic)](target.md).</span></span>  
  
 <span data-ttu-id="fb3a0-118">`-optimize` 및 `-debug` 옵션을 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-118">You can combine the `-optimize` and `-debug` options.</span></span>  
  
|<span data-ttu-id="fb3a0-119">Visual Studio 통합 개발 환경에서 -optimize를 설정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-119">To set -optimize in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="fb3a0-120">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="fb3a0-121">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-121">On the **Project** menu, click **Properties**.</span></span><br />     <br /><span data-ttu-id="fb3a0-122">2.  **컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="fb3a0-123">3.  **고급** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-123">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="fb3a0-124">4.  **최적화 사용** 확인란을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-124">4.  Modify the **Enable optimizations** check box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="fb3a0-125">예제</span><span class="sxs-lookup"><span data-stu-id="fb3a0-125">Example</span></span>  
 <span data-ttu-id="fb3a0-126">다음 코드는 `T2.vb`를 컴파일하고 컴파일러 최적화를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fb3a0-126">The following code compiles `T2.vb` and enables compiler optimizations.</span></span>  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="fb3a0-127">참조</span><span class="sxs-lookup"><span data-stu-id="fb3a0-127">See also</span></span>

- [<span data-ttu-id="fb3a0-128">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="fb3a0-128">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="fb3a0-129">-debug(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb3a0-129">-debug (Visual Basic)</span></span>](debug.md)
- [<span data-ttu-id="fb3a0-130">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="fb3a0-130">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="fb3a0-131">-target(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb3a0-131">-target (Visual Basic)</span></span>](target.md)
