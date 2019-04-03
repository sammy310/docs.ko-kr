---
title: -nowarn
ms.date: 07/20/2015
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
ms.openlocfilehash: 31f7a2b771cfa1bcc6581d720aa0de3505aec826
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58828214"
---
# <a name="-nowarn"></a><span data-ttu-id="62e4d-102">-nowarn</span><span class="sxs-lookup"><span data-stu-id="62e4d-102">-nowarn</span></span>
<span data-ttu-id="62e4d-103">컴파일러에서 경고를 생성하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="62e4d-103">Suppresses the compiler's ability to generate warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62e4d-104">구문</span><span class="sxs-lookup"><span data-stu-id="62e4d-104">Syntax</span></span>  
  
```  
-nowarn[:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="62e4d-105">인수</span><span class="sxs-lookup"><span data-stu-id="62e4d-105">Arguments</span></span>  
  
|<span data-ttu-id="62e4d-106">용어</span><span class="sxs-lookup"><span data-stu-id="62e4d-106">Term</span></span>|<span data-ttu-id="62e4d-107">정의</span><span class="sxs-lookup"><span data-stu-id="62e4d-107">Definition</span></span>|  
|---|---|  
|`numberList`|<span data-ttu-id="62e4d-108">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="62e4d-108">Optional.</span></span> <span data-ttu-id="62e4d-109">컴파일러 억제 해야 하는 경고 ID 번호의 쉼표로 구분 된 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="62e4d-109">Comma-delimited list of the warning ID numbers that the compiler should suppress.</span></span> <span data-ttu-id="62e4d-110">경고 Id를 지정 하지 않은 경우 모든 경고가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="62e4d-110">If the warning IDs are not specified, all warnings are suppressed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62e4d-111">설명</span><span class="sxs-lookup"><span data-stu-id="62e4d-111">Remarks</span></span>  
 <span data-ttu-id="62e4d-112">`-nowarn` 옵션을 사용 하면 경고가 생성 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="62e4d-112">The `-nowarn` option causes the compiler to not generate warnings.</span></span> <span data-ttu-id="62e4d-113">개별 경고를 표시 하지 않으려면 경고의 ID를 제공 합니다 `-nowarn` 콜론 뒤 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="62e4d-113">To suppress an individual warning, supply the warning ID to the `-nowarn` option following the colon.</span></span> <span data-ttu-id="62e4d-114">여러 경고 번호를 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="62e4d-114">Separate multiple warning numbers with commas.</span></span>  
  
 <span data-ttu-id="62e4d-115">경고 식별자의 숫자 부분만 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62e4d-115">You need to specify only the numeric part of the warning identifier.</span></span> <span data-ttu-id="62e4d-116">BC42024, 사용 되지 않는 로컬 변수에 대 한 경고를 표시 하지 않으려는 경우 지정 하는 예를 들어 `-nowarn:42024`합니다.</span><span class="sxs-lookup"><span data-stu-id="62e4d-116">For example, if you want to suppress BC42024, the warning for unused local variables, specify `-nowarn:42024`.</span></span>  
  
 <span data-ttu-id="62e4d-117">경고 ID 번호에 대 한 자세한 내용은 참조 하세요. [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.</span><span class="sxs-lookup"><span data-stu-id="62e4d-117">For more information on the warning ID numbers, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
|<span data-ttu-id="62e4d-118">Visual Studio 통합된 개발 환경에서-nowarn를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="62e4d-118">To set -nowarn in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="62e4d-119">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="62e4d-119">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="62e4d-120">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="62e4d-120">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="62e4d-121">2.  **컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="62e4d-121">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="62e4d-122">3.  선택 된 **모든 경고 사용 안 함** 모든 경고를 사용 하지 않도록 설정 하려면 확인란 합니다.</span><span class="sxs-lookup"><span data-stu-id="62e4d-122">3.  Select the **Disable all warnings** check box to disable all warnings.</span></span><br />     <span data-ttu-id="62e4d-123">또는</span><span class="sxs-lookup"><span data-stu-id="62e4d-123">- or -</span></span><br />     <span data-ttu-id="62e4d-124">특정 경고를 해제 하려면 **None** 경고 옆의 드롭다운 목록에서.</span><span class="sxs-lookup"><span data-stu-id="62e4d-124">To disable a particular warning, click **None** from the drop-down list adjacent to the warning.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="62e4d-125">예제</span><span class="sxs-lookup"><span data-stu-id="62e4d-125">Example</span></span>  
 <span data-ttu-id="62e4d-126">다음 코드에서는 `T2.vb` 모든 경고를 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="62e4d-126">The following code compiles `T2.vb` and does not display any warnings.</span></span>  
  
```console
vbc -nowarn t2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="62e4d-127">예제</span><span class="sxs-lookup"><span data-stu-id="62e4d-127">Example</span></span>  
 <span data-ttu-id="62e4d-128">다음 코드에서는 `T2.vb` 를 사용 하지 않는 로컬 변수 (42024)에 대 한 경고를 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="62e4d-128">The following code compiles `T2.vb` and does not display the warnings for unused local variables (42024).</span></span>  
  
```console
vbc -nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="62e4d-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="62e4d-129">See also</span></span>

- [<span data-ttu-id="62e4d-130">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="62e4d-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="62e4d-131">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="62e4d-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="62e4d-132">Configuring Warnings in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="62e4d-132">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
