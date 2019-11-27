---
title: -warnaserror
ms.date: 03/13/2018
helpviewer_keywords:
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
ms.openlocfilehash: f9ca5575e2a042d68fc490494f2e86991d58b80c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351703"
---
# <a name="-warnaserror-visual-basic"></a><span data-ttu-id="fd257-102">-warnaserror(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fd257-102">-warnaserror (Visual Basic)</span></span>
<span data-ttu-id="fd257-103">컴파일러가 첫 번째 발생하는 경고를 오류로 처리하도록 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fd257-103">Causes the compiler to treat the first occurrence of a warning as an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd257-104">구문</span><span class="sxs-lookup"><span data-stu-id="fd257-104">Syntax</span></span>  
  
```console  
-warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="fd257-105">인수</span><span class="sxs-lookup"><span data-stu-id="fd257-105">Arguments</span></span>  
  
|<span data-ttu-id="fd257-106">용어</span><span class="sxs-lookup"><span data-stu-id="fd257-106">Term</span></span>|<span data-ttu-id="fd257-107">정의</span><span class="sxs-lookup"><span data-stu-id="fd257-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="fd257-108">+ &#124; -</span><span class="sxs-lookup"><span data-stu-id="fd257-108">+ &#124; -</span></span>|<span data-ttu-id="fd257-109">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="fd257-109">Optional.</span></span> <span data-ttu-id="fd257-110">기본적으로 `-warnaserror-`가 적용됩니다. 경고가 발생해도 컴파일러가 출력 파일을 생성하지 못하도록 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd257-110">By default, `-warnaserror-` is in effect; warnings do not prevent the compiler from producing an output file.</span></span> <span data-ttu-id="fd257-111">`-warnaserror`와 동일한 `-warnaserror+` 옵션은 경고가 오류로 처리되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd257-111">The `-warnaserror` option, which is the same as `-warnaserror+`, causes warnings to be treated as errors.</span></span>|  
|`numberList`|<span data-ttu-id="fd257-112">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="fd257-112">Optional.</span></span> <span data-ttu-id="fd257-113">`-warnaserror` 옵션이 적용되는 경고 ID 번호의 쉼표로 구분된 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="fd257-113">Comma-delimited list of the warning ID numbers to which the `-warnaserror` option applies.</span></span> <span data-ttu-id="fd257-114">경고 ID를 지정하지 않으면 `-warnaserror` 옵션이 모든 경고에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd257-114">If no warning ID is specified, the `-warnaserror` option applies to all warnings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd257-115">주의</span><span class="sxs-lookup"><span data-stu-id="fd257-115">Remarks</span></span>  
 <span data-ttu-id="fd257-116">`-warnaserror` 옵션은 모든 경고를 오류로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="fd257-116">The `-warnaserror` option treats all warnings as errors.</span></span> <span data-ttu-id="fd257-117">일반적으로 경고로 보고되는 모든 메시지가 대신 오류로 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd257-117">Any messages that would ordinarily be reported as warnings are instead reported as errors.</span></span> <span data-ttu-id="fd257-118">컴파일러는 이후 발생하는 같은 경고를 경고로 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="fd257-118">The compiler reports subsequent occurrences of the same warning as warnings.</span></span>  
  
 <span data-ttu-id="fd257-119">기본적으로 `-warnaserror-`이 적용되며 경고가 정보 제공용으로만 사용되게 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd257-119">By default, `-warnaserror-` is in effect, which causes the warnings to be informational only.</span></span> <span data-ttu-id="fd257-120">`-warnaserror`와 동일한 `-warnaserror+` 옵션은 경고가 오류로 처리되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd257-120">The `-warnaserror` option, which is the same as `-warnaserror+`, causes warnings to be treated as errors.</span></span>  
  
 <span data-ttu-id="fd257-121">몇 개의 특정 경고만 오류로 처리하려는 경우 오류로 처리할 경고 번호의 쉼표로 구분된 목록을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd257-121">If you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fd257-122">`-warnaserror` 옵션은 경고가 표시되는 방법을 제어하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd257-122">The `-warnaserror` option does not control how warnings are displayed.</span></span> <span data-ttu-id="fd257-123">경고를 사용하지 않도록 설정하려면 [-nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fd257-123">Use the [-nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) option to disable warnings.</span></span>  
  
|<span data-ttu-id="fd257-124">Visual Studio IDE에서 모든 경고를 오류로 처리하도록 -warnaserror을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="fd257-124">To set -warnaserror to treat all warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="fd257-125">1. **솔루션 탐색기**에서 프로젝트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd257-125">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="fd257-126">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fd257-126">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="fd257-127">2. **컴파일** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd257-127">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="fd257-128">3. **모든 경고 사용 안 함** 확인란이 선택 취소 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd257-128">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="fd257-129">4. **모든 경고를 오류로 처리** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd257-129">4.  Check the **Treat all warnings as errors** check box.</span></span>|  
  
|<span data-ttu-id="fd257-130">Visual Studio IDE에서 특정 경고를 오류로 처리하도록 -warnaserror을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="fd257-130">To set -warnaserror to treat specific warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="fd257-131">1. **솔루션 탐색기**에서 프로젝트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd257-131">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="fd257-132">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fd257-132">On the **Project** menu, click **Properties**.</span></span><br /><span data-ttu-id="fd257-133">2. **컴파일** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd257-133">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="fd257-134">3. **모든 경고 사용 안 함** 확인란이 선택 취소 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd257-134">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="fd257-135">4. **모든 경고를 오류로 처리** 확인란이 선택 취소 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd257-135">4.  Make sure the **Treat all warnings as errors** check box is unchecked.</span></span><br /><span data-ttu-id="fd257-136">5. 오류로 처리 해야 하는 경고 옆의 **알림** 열에서 **오류** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd257-136">5.  Select **Error** from the **Notification** column adjacent to the warning that should be treated as an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="fd257-137">예제</span><span class="sxs-lookup"><span data-stu-id="fd257-137">Example</span></span>  
 <span data-ttu-id="fd257-138">다음 코드에서는 `In.vb`를 컴파일하고 컴파일러가 찾는 모든 경고의 첫 번째 발생을 오류로 표시하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd257-138">The following code compiles `In.vb` and directs the compiler to display an error for the first occurrence of every warning it finds.</span></span>  
  
```console
vbc -warnaserror in.vb  
```  
  
## <a name="example"></a><span data-ttu-id="fd257-139">예제</span><span class="sxs-lookup"><span data-stu-id="fd257-139">Example</span></span>  
 <span data-ttu-id="fd257-140">다음 코드에서는 `T2.vb`를 컴파일하고 사용되지 않는 지역 변수(42024)에 대한 경고만 오류로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="fd257-140">The following code compiles `T2.vb` and treats only the warning for unused local variables (42024) as an error.</span></span>  
  
```console
vbc -warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="fd257-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fd257-141">See also</span></span>

- [<span data-ttu-id="fd257-142">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="fd257-142">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="fd257-143">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="fd257-143">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="fd257-144">Visual Basic에서 경고 구성</span><span class="sxs-lookup"><span data-stu-id="fd257-144">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
