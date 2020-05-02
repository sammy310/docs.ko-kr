---
title: -nowarn
ms.date: 07/20/2015
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
ms.openlocfilehash: 880fdf4931dadea547d64d0506bd3e978956468e
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005403"
---
# <a name="-nowarn"></a><span data-ttu-id="cab14-102">-nowarn</span><span class="sxs-lookup"><span data-stu-id="cab14-102">-nowarn</span></span>
<span data-ttu-id="cab14-103">컴파일러에서 경고를 생성하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab14-103">Suppresses the compiler's ability to generate warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cab14-104">구문</span><span class="sxs-lookup"><span data-stu-id="cab14-104">Syntax</span></span>  
  
```console  
-nowarn[:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="cab14-105">인수</span><span class="sxs-lookup"><span data-stu-id="cab14-105">Arguments</span></span>  
  
|<span data-ttu-id="cab14-106">용어</span><span class="sxs-lookup"><span data-stu-id="cab14-106">Term</span></span>|<span data-ttu-id="cab14-107">정의</span><span class="sxs-lookup"><span data-stu-id="cab14-107">Definition</span></span>|  
|---|---|  
|`numberList`|<span data-ttu-id="cab14-108">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="cab14-108">Optional.</span></span> <span data-ttu-id="cab14-109">컴파일러가 표시하지 않아야 하는 경고 ID 번호의 쉼표로 구분된 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="cab14-109">Comma-delimited list of the warning ID numbers that the compiler should suppress.</span></span> <span data-ttu-id="cab14-110">경고 ID를 지정하지 않으면 모든 경고가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cab14-110">If the warning IDs are not specified, all warnings are suppressed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cab14-111">설명</span><span class="sxs-lookup"><span data-stu-id="cab14-111">Remarks</span></span>  
 <span data-ttu-id="cab14-112">`-nowarn` 옵션은 컴파일러에서 경고를 생성하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab14-112">The `-nowarn` option causes the compiler to not generate warnings.</span></span> <span data-ttu-id="cab14-113">개별 경고를 표시하지 않으려면 콜론 뒤에 있는 `-nowarn` 옵션에 경고 ID를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cab14-113">To suppress an individual warning, supply the warning ID to the `-nowarn` option following the colon.</span></span> <span data-ttu-id="cab14-114">여러 경고 번호를 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="cab14-114">Separate multiple warning numbers with commas.</span></span>  
  
 <span data-ttu-id="cab14-115">경고 식별자의 숫자 부분만 지정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cab14-115">You need to specify only the numeric part of the warning identifier.</span></span> <span data-ttu-id="cab14-116">예를 들어 사용하지 않은 지역 변수에 대한 경고인 BC42024를 표시하지 않으려면 `-nowarn:42024`를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cab14-116">For example, if you want to suppress BC42024, the warning for unused local variables, specify `-nowarn:42024`.</span></span>  
  
 <span data-ttu-id="cab14-117">경고 ID 번호에 대한 자세한 내용은 [Visual Basic에서 경고 구성](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cab14-117">For more information on the warning ID numbers, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
|<span data-ttu-id="cab14-118">Visual Studio 통합 개발 환경에서 -nowarn을 설정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="cab14-118">To set -nowarn in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="cab14-119">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cab14-119">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="cab14-120">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cab14-120">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="cab14-121">2.  **컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cab14-121">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="cab14-122">3.  **모든 경고 사용 안 함** 확인란을 선택하여 모든 경고를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cab14-122">3.  Select the **Disable all warnings** check box to disable all warnings.</span></span><br />     <span data-ttu-id="cab14-123">또는</span><span class="sxs-lookup"><span data-stu-id="cab14-123">- or -</span></span><br />     <span data-ttu-id="cab14-124">특정 경고를 사용하지 않도록 설정하려면 경고 옆의 드롭다운 목록에서 **없음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cab14-124">To disable a particular warning, click **None** from the drop-down list adjacent to the warning.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="cab14-125">예제</span><span class="sxs-lookup"><span data-stu-id="cab14-125">Example</span></span>  
 <span data-ttu-id="cab14-126">다음 코드에서는 `T2.vb`를 컴파일하고 경고를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cab14-126">The following code compiles `T2.vb` and does not display any warnings.</span></span>  
  
```console
vbc -nowarn t2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="cab14-127">예제</span><span class="sxs-lookup"><span data-stu-id="cab14-127">Example</span></span>  
 <span data-ttu-id="cab14-128">다음 코드에서는 `T2.vb`를 컴파일하고 사용되지 않는 지역 변수(42024)에 대한 경고를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cab14-128">The following code compiles `T2.vb` and does not display the warnings for unused local variables (42024).</span></span>  
  
```console
vbc -nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="cab14-129">참조</span><span class="sxs-lookup"><span data-stu-id="cab14-129">See also</span></span>

- [<span data-ttu-id="cab14-130">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="cab14-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="cab14-131">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="cab14-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="cab14-132">Configuring Warnings in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cab14-132">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
