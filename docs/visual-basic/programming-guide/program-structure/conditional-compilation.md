---
description: '자세한 정보: Visual Basic의 조건부 컴파일'
title: 조건부 컴파일
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], about conditional compilation
- compilation [Visual Basic], conditional
ms.assetid: 9c35e55e-7eee-44fb-a586-dad1f1884848
ms.openlocfilehash: e9cb8a5af4dfbf2ffadef8edd8f6583614188391
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100476139"
---
# <a name="conditional-compilation-in-visual-basic"></a><span data-ttu-id="0d29c-103">Visual Basic의 조건부 컴파일</span><span class="sxs-lookup"><span data-stu-id="0d29c-103">Conditional Compilation in Visual Basic</span></span>

<span data-ttu-id="0d29c-104">*조건부 컴파일에서* 프로그램의 특정 코드 블록은 선택적으로 컴파일되고 다른 항목은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d29c-104">In *conditional compilation*, particular blocks of code in a program are compiled selectively while others are ignored.</span></span>  
  
 <span data-ttu-id="0d29c-105">예를 들어 서로 다른 방법의 속도와 동일한 프로그래밍 작업을 비교 하는 디버깅 문을 작성 하거나 응용 프로그램에서 여러 언어를 지역화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d29c-105">For example, you may want to write debugging statements that compare the speed of different approaches to the same programming task, or you may want to localize an application for multiple languages.</span></span> <span data-ttu-id="0d29c-106">조건부 컴파일 문은 런타임에 실행 되지 않고 컴파일 시간에 실행 되도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d29c-106">Conditional compilation statements are designed to run during compile time, not at run time.</span></span>  
  
 <span data-ttu-id="0d29c-107">지시문을 사용 하 여 조건부로 컴파일되는 코드 블록을 나타냅니다 `#If...Then...#Else` .</span><span class="sxs-lookup"><span data-stu-id="0d29c-107">You denote blocks of code to be conditionally compiled with the `#If...Then...#Else` directive.</span></span> <span data-ttu-id="0d29c-108">예를 들어 동일한 소스 코드에서 프랑스어 및 독일어 버전의 동일한 응용 프로그램을 만들려면 `#If...Then` 미리 정의 된 상수 및를 사용 하 여 문에 플랫폼별 코드 세그먼트를 포함 `FrenchVersion` `GermanVersion` 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d29c-108">For example, to create French- and German-language versions of the same application from the same source code, you embed platform-specific code segments in `#If...Then` statements using the predefined constants `FrenchVersion` and `GermanVersion`.</span></span> <span data-ttu-id="0d29c-109">다음 예에서는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0d29c-109">The following example demonstrates how:</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#5)]  
  
 <span data-ttu-id="0d29c-110">`FrenchVersion`컴파일 시간에 조건부 컴파일 상수 값을로 설정 하면 `True` 프랑스어 버전의 조건부 코드가 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d29c-110">If you set the value of the `FrenchVersion` conditional compilation constant to `True` at compile time, the conditional code for the French version is compiled.</span></span> <span data-ttu-id="0d29c-111">상수 값을로 설정 하는 경우 `GermanVersion` `True` 컴파일러는 독일어 버전을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d29c-111">If you set the value of the `GermanVersion` constant to `True`, the compiler uses the German version.</span></span> <span data-ttu-id="0d29c-112">둘 다로 설정 하지 않으면 `True` 마지막 블록의 코드가 `Else` 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d29c-112">If neither is set to `True`, the code in the last `Else` block runs.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0d29c-113">코드를 편집 하 고 코드를 현재 분기에 포함 하지 않는 경우 조건부 컴파일 지시문을 사용 하면 자동 완성이 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d29c-113">Autocompletion will not function when editing code and using conditional compilation directives if the code is not part of the current branch.</span></span>  
  
## <a name="declaring-conditional-compilation-constants"></a><span data-ttu-id="0d29c-114">조건부 컴파일 상수 선언</span><span class="sxs-lookup"><span data-stu-id="0d29c-114">Declaring Conditional Compilation Constants</span></span>  

 <span data-ttu-id="0d29c-115">다음 세 가지 방법 중 하나로 조건부 컴파일 상수를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d29c-115">You can set conditional compilation constants in one of three ways:</span></span>  
  
- <span data-ttu-id="0d29c-116">**프로젝트 디자이너** 에서</span><span class="sxs-lookup"><span data-stu-id="0d29c-116">In the **Project Designer**</span></span>  
  
- <span data-ttu-id="0d29c-117">명령줄 컴파일러를 사용 하는 경우 명령줄에서</span><span class="sxs-lookup"><span data-stu-id="0d29c-117">At the command line when using the command-line compiler</span></span>  
  
- <span data-ttu-id="0d29c-118">코드에서</span><span class="sxs-lookup"><span data-stu-id="0d29c-118">In your code</span></span>  
  
 <span data-ttu-id="0d29c-119">조건부 컴파일 상수는 특수 한 범위를 가지 며 표준 코드에서 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d29c-119">Conditional compilation constants have a special scope and cannot be accessed from standard code.</span></span> <span data-ttu-id="0d29c-120">조건부 컴파일 상수의 범위는 설정 된 방식에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="0d29c-120">The scope of a conditional compilation constant is dependent on the way it is set.</span></span> <span data-ttu-id="0d29c-121">다음 표에서는 위에 설명 된 세 가지 방법을 사용 하 여 선언 된 상수 범위를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d29c-121">The following table lists the scope of constants declared using each of the three ways mentioned above.</span></span>  
  
|<span data-ttu-id="0d29c-122">상수 설정 방법</span><span class="sxs-lookup"><span data-stu-id="0d29c-122">How constant is set</span></span>|<span data-ttu-id="0d29c-123">상수 범위</span><span class="sxs-lookup"><span data-stu-id="0d29c-123">Scope of constant</span></span>|  
|---|---|  
|<span data-ttu-id="0d29c-124">**프로젝트 디자이너**</span><span class="sxs-lookup"><span data-stu-id="0d29c-124">**Project Designer**</span></span>|<span data-ttu-id="0d29c-125">프로젝트의 모든 파일에 공개</span><span class="sxs-lookup"><span data-stu-id="0d29c-125">Public to all files in the project</span></span>|  
|<span data-ttu-id="0d29c-126">명령 줄</span><span class="sxs-lookup"><span data-stu-id="0d29c-126">Command line</span></span>|<span data-ttu-id="0d29c-127">명령줄 컴파일러에 전달 된 모든 파일에 공용</span><span class="sxs-lookup"><span data-stu-id="0d29c-127">Public to all files passed to the command-line compiler</span></span>|  
|<span data-ttu-id="0d29c-128">`#Const` 코드의 문</span><span class="sxs-lookup"><span data-stu-id="0d29c-128">`#Const` statement in code</span></span>|<span data-ttu-id="0d29c-129">선언 된 파일 전용</span><span class="sxs-lookup"><span data-stu-id="0d29c-129">Private to the file in which it is declared</span></span>|  
  
|<span data-ttu-id="0d29c-130">프로젝트 디자이너에서 상수를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="0d29c-130">To set constants in the Project Designer</span></span>|  
|---|  
|<span data-ttu-id="0d29c-131">-실행 파일을 만들기 전에 프로젝트 **디자이너** 에서 [프로젝트 및 솔루션 속성 관리](/visualstudio/ide/managing-project-and-solution-properties)에 제공 된 단계에 따라 상수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d29c-131">-   Before creating your executable file, set constants in the **Project Designer** by following the steps provided in [Managing Project and Solution Properties](/visualstudio/ide/managing-project-and-solution-properties).</span></span>|  
  
|<span data-ttu-id="0d29c-132">명령줄에서 상수를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="0d29c-132">To set constants at the command line</span></span>|  
|---|  
|<span data-ttu-id="0d29c-133">-다음 예제와 같이- **d** 스위치를 사용 하 여 조건부 컴파일 상수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d29c-133">-   Use the **-d** switch to enter conditional compilation constants, as in the following example:</span></span><br />     `vbc MyProj.vb /d:conFrenchVersion=–1:conANSI=0`<br />     <span data-ttu-id="0d29c-134">**-D** 스위치와 첫 번째 상수 사이에는 공간이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d29c-134">No space is required between the **-d** switch and the first constant.</span></span> <span data-ttu-id="0d29c-135">자세한 내용은 [-define (Visual Basic)](../../reference/command-line-compiler/define.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0d29c-135">For more information, see [-define (Visual Basic)](../../reference/command-line-compiler/define.md).</span></span><br />     <span data-ttu-id="0d29c-136">명령줄 선언은 **프로젝트 디자이너** 에 입력 된 선언을 재정의 하지만이를 지우지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d29c-136">Command-line declarations override declarations entered in the **Project Designer**, but do not erase them.</span></span> <span data-ttu-id="0d29c-137">**프로젝트 디자이너** 에 설정 되는 인수는 후속 컴파일에서 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d29c-137">Arguments set in **Project Designer** remain in effect for subsequent compilations.</span></span><br />     <span data-ttu-id="0d29c-138">코드 자체에서 상수를 작성 하는 경우 해당 범위는 선언 된 전체 모듈 이므로 배치에 대 한 엄격한 규칙이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d29c-138">When writing constants in the code itself, there are no strict rules as to their placement, since their scope is the entire module in which they are declared.</span></span>|  
  
|<span data-ttu-id="0d29c-139">코드에서 상수를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="0d29c-139">To set constants in your code</span></span>|  
|---|  
|<span data-ttu-id="0d29c-140">-상수를 사용 되는 모듈의 선언 블록에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d29c-140">-   Place the constants in the declaration block of the module in which they are used.</span></span> <span data-ttu-id="0d29c-141">이렇게 하면 코드를 구성 하 고 읽기 쉽게 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d29c-141">This helps keep your code organized and easier to read.</span></span>|  
  
## <a name="related-topics"></a><span data-ttu-id="0d29c-142">관련 항목</span><span class="sxs-lookup"><span data-stu-id="0d29c-142">Related Topics</span></span>  
  
|<span data-ttu-id="0d29c-143">제목</span><span class="sxs-lookup"><span data-stu-id="0d29c-143">Title</span></span>|<span data-ttu-id="0d29c-144">설명</span><span class="sxs-lookup"><span data-stu-id="0d29c-144">Description</span></span>|  
|---|---|  
|[<span data-ttu-id="0d29c-145">프로그램 구조 및 코드 규칙</span><span class="sxs-lookup"><span data-stu-id="0d29c-145">Program Structure and Code Conventions</span></span>](program-structure-and-code-conventions.md)|<span data-ttu-id="0d29c-146">코드를 쉽게 읽고 유지 관리할 수 있는 제안 사항을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d29c-146">Provides suggestions for making your code easy to read and maintain.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="0d29c-147">참조</span><span class="sxs-lookup"><span data-stu-id="0d29c-147">Reference</span></span>  

 [<span data-ttu-id="0d29c-148">#Const 지시문</span><span class="sxs-lookup"><span data-stu-id="0d29c-148">#Const Directive</span></span>](../../language-reference/directives/const-directive.md)  
  
 [<span data-ttu-id="0d29c-149">#If...Then...#Else 지시문</span><span class="sxs-lookup"><span data-stu-id="0d29c-149">#If...Then...#Else Directives</span></span>](../../language-reference/directives/if-then-else-directives.md)  
  
 [<span data-ttu-id="0d29c-150">-define(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0d29c-150">-define (Visual Basic)</span></span>](../../reference/command-line-compiler/define.md)
