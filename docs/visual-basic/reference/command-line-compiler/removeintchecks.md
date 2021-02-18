---
description: '자세한 정보: -removeintchecks'
title: -removeintchecks
ms.date: 03/13/2018
f1_keywords:
- removeintchecks
- -removeintchecks
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
ms.openlocfilehash: 1dc484e1538718b68fe9f0cc450fa2480dc52412
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100474098"
---
# <a name="-removeintchecks"></a><span data-ttu-id="c6635-103">-removeintchecks</span><span class="sxs-lookup"><span data-stu-id="c6635-103">-removeintchecks</span></span>

<span data-ttu-id="c6635-104">정수 연산에 대해 오버플로 오류 검사를 설정하거나 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="c6635-104">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6635-105">구문</span><span class="sxs-lookup"><span data-stu-id="c6635-105">Syntax</span></span>  
  
```console  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="c6635-106">인수</span><span class="sxs-lookup"><span data-stu-id="c6635-106">Arguments</span></span>  
  
|<span data-ttu-id="c6635-107">용어</span><span class="sxs-lookup"><span data-stu-id="c6635-107">Term</span></span>|<span data-ttu-id="c6635-108">정의</span><span class="sxs-lookup"><span data-stu-id="c6635-108">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="c6635-109">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="c6635-109">`+` &#124; `-`</span></span>|<span data-ttu-id="c6635-110">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c6635-110">Optional.</span></span> <span data-ttu-id="c6635-111">`-removeintchecks-` 옵션을 사용하면 컴파일러에서 오버플로 오류에 대한 모든 정수 계산을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6635-111">The `-removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="c6635-112">기본값은 `-removeintchecks-`입니다.</span><span class="sxs-lookup"><span data-stu-id="c6635-112">The default is `-removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="c6635-113">`-removeintchecks` 또는 `-removeintchecks+`를 지정하면 오류 검사를 방지하고 정수 계산을 더 빠르게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6635-113">Specifying `-removeintchecks` or `-removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="c6635-114">그러나 오류 검사를 수행하지 않고 데이터 형식 용량이 오버플로되는 경우 오류 발생 없이도 잘못된 결과가 저장될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6635-114">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="c6635-115">Visual Studio 통합 개발 환경에서 -removeintchecks를 설정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c6635-115">To set -removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="c6635-116">1.  **솔루션 탐색기** 에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c6635-116">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="c6635-117">**프로젝트** 메뉴에서 **속성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c6635-117">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="c6635-118">2.  **컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c6635-118">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="c6635-119">3.  **고급** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c6635-119">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="c6635-120">4.  **정수 오버플로 검사 해제** 상자의 값을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="c6635-120">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c6635-121">예제</span><span class="sxs-lookup"><span data-stu-id="c6635-121">Example</span></span>  

 <span data-ttu-id="c6635-122">다음 코드는 `Test.vb`를 컴파일하고 정수 오버플로 오류 검사를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="c6635-122">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="c6635-123">참조</span><span class="sxs-lookup"><span data-stu-id="c6635-123">See also</span></span>

- [<span data-ttu-id="c6635-124">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="c6635-124">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="c6635-125">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="c6635-125">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
