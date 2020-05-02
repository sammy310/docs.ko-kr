---
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
ms.openlocfilehash: bea6ca24ea6da9000267e754d52fe0ca152f7d7f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005232"
---
# <a name="-removeintchecks"></a><span data-ttu-id="7e2a2-102">-removeintchecks</span><span class="sxs-lookup"><span data-stu-id="7e2a2-102">-removeintchecks</span></span>
<span data-ttu-id="7e2a2-103">정수 연산에 대해 오버플로 오류 검사를 설정하거나 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2a2-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e2a2-104">구문</span><span class="sxs-lookup"><span data-stu-id="7e2a2-104">Syntax</span></span>  
  
```console  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="7e2a2-105">인수</span><span class="sxs-lookup"><span data-stu-id="7e2a2-105">Arguments</span></span>  
  
|<span data-ttu-id="7e2a2-106">용어</span><span class="sxs-lookup"><span data-stu-id="7e2a2-106">Term</span></span>|<span data-ttu-id="7e2a2-107">정의</span><span class="sxs-lookup"><span data-stu-id="7e2a2-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="7e2a2-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="7e2a2-108">`+` &#124; `-`</span></span>|<span data-ttu-id="7e2a2-109">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7e2a2-109">Optional.</span></span> <span data-ttu-id="7e2a2-110">`-removeintchecks-` 옵션을 사용하면 컴파일러에서 오버플로 오류에 대한 모든 정수 계산을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e2a2-110">The `-removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="7e2a2-111">기본값은 `-removeintchecks-`입니다.</span><span class="sxs-lookup"><span data-stu-id="7e2a2-111">The default is `-removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="7e2a2-112">`-removeintchecks` 또는 `-removeintchecks+`를 지정하면 오류 검사를 방지하고 정수 계산을 더 빠르게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e2a2-112">Specifying `-removeintchecks` or `-removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="7e2a2-113">그러나 오류 검사를 수행하지 않고 데이터 형식 용량이 오버플로되는 경우 오류 발생 없이도 잘못된 결과가 저장될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e2a2-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="7e2a2-114">Visual Studio 통합 개발 환경에서 -removeintchecks를 설정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2a2-114">To set -removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="7e2a2-115">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2a2-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="7e2a2-116">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2a2-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="7e2a2-117">2.  **컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2a2-117">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="7e2a2-118">3.  **고급** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2a2-118">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="7e2a2-119">4.  **정수 오버플로 검사 해제** 상자의 값을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2a2-119">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7e2a2-120">예제</span><span class="sxs-lookup"><span data-stu-id="7e2a2-120">Example</span></span>  
 <span data-ttu-id="7e2a2-121">다음 코드는 `Test.vb`를 컴파일하고 정수 오버플로 오류 검사를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2a2-121">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="7e2a2-122">참조</span><span class="sxs-lookup"><span data-stu-id="7e2a2-122">See also</span></span>

- [<span data-ttu-id="7e2a2-123">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="7e2a2-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="7e2a2-124">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="7e2a2-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
