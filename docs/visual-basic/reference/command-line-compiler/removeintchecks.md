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
ms.openlocfilehash: c086a031d5cef4563a6769e7683dcb1110b8fe49
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788767"
---
# <a name="-removeintchecks"></a><span data-ttu-id="b017c-102">-removeintchecks</span><span class="sxs-lookup"><span data-stu-id="b017c-102">-removeintchecks</span></span>
<span data-ttu-id="b017c-103">오버플로 오류 또는 해제 하는 정수 연산에 대 한 검사를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b017c-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b017c-104">구문</span><span class="sxs-lookup"><span data-stu-id="b017c-104">Syntax</span></span>  
  
```  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="b017c-105">인수</span><span class="sxs-lookup"><span data-stu-id="b017c-105">Arguments</span></span>  
  
|<span data-ttu-id="b017c-106">용어</span><span class="sxs-lookup"><span data-stu-id="b017c-106">Term</span></span>|<span data-ttu-id="b017c-107">정의</span><span class="sxs-lookup"><span data-stu-id="b017c-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="b017c-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="b017c-108">`+` &#124; `-`</span></span>|<span data-ttu-id="b017c-109">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b017c-109">Optional.</span></span> <span data-ttu-id="b017c-110">`-removeintchecks-` 옵션을 사용 하면 모든 정수 연산 오버플로 오류를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b017c-110">The `-removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="b017c-111">기본값은 `-removeintchecks-`입니다.</span><span class="sxs-lookup"><span data-stu-id="b017c-111">The default is `-removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="b017c-112">지정 `-removeintchecks` 또는 `-removeintchecks+` 오류 검사를 차단 하 고 정수 계산을 더욱 빠르게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b017c-112">Specifying `-removeintchecks` or `-removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="b017c-113">오류를 검사 하지 않는 반면 및 잘못 된 결과 데이터 형식 용량 오버플로 경우 오류를 일으키지 않고 저장 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b017c-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="b017c-114">Visual Studio 통합된 개발 환경에서-removeintchecks를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="b017c-114">To set -removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="b017c-115">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b017c-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="b017c-116">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b017c-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="b017c-117">2.  **컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b017c-117">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="b017c-118">3.  **고급** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b017c-118">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="b017c-119">4.  값을 수정 합니다 **정수 오버플로 검사 해제** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="b017c-119">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b017c-120">예제</span><span class="sxs-lookup"><span data-stu-id="b017c-120">Example</span></span>  
 <span data-ttu-id="b017c-121">다음 코드에서는 `Test.vb` 정수 오버플로 오류 검사를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="b017c-121">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="b017c-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="b017c-122">See also</span></span>

- [<span data-ttu-id="b017c-123">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="b017c-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="b017c-124">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="b017c-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
