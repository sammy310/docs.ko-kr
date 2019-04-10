---
title: Visual Basic 프로그램의 구조
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], Visual Basic
- program structure [Visual Basic], Visual Basic
- procedures [Visual Basic], structure
- Visual Basic code, program structure
ms.assetid: ad0c6531-d762-4c77-a700-de16b07b6119
ms.openlocfilehash: 42e366a844f9c5e80a8f617bf73dfd869608540d
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59295772"
---
# <a name="structure-of-a-visual-basic-program"></a><span data-ttu-id="b36ac-102">Visual Basic 프로그램의 구조</span><span class="sxs-lookup"><span data-stu-id="b36ac-102">Structure of a Visual Basic Program</span></span>
<span data-ttu-id="b36ac-103">Visual Basic 프로그램은 표준 구성 요소에서 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-103">A Visual Basic program is built up from standard building blocks.</span></span> <span data-ttu-id="b36ac-104">A *솔루션* 하나 이상의 프로젝트를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-104">A *solution* comprises one or more projects.</span></span> <span data-ttu-id="b36ac-105">A *프로젝트* 에 하나 이상의 어셈블리를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-105">A *project* in turn can contain one or more assemblies.</span></span> <span data-ttu-id="b36ac-106">각 *어셈블리* 하나 이상의 소스 파일에서 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-106">Each *assembly* is compiled from one or more source files.</span></span> <span data-ttu-id="b36ac-107">A *소스 파일* 정의와 클래스, 구조체, 모듈 및 궁극적으로 모든 코드를 포함 하는 인터페이스의 구현을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-107">A *source file* provides the definition and implementation of classes, structures, modules, and interfaces, which ultimately contain all your code.</span></span>  
  
 <span data-ttu-id="b36ac-108">Visual Basic 프로그램의 이러한 구성 요소에 대 한 자세한 내용은 참조 하세요 [솔루션 및 프로젝트](/visualstudio/ide/solutions-and-projects-in-visual-studio) 하 고 [.net에서 어셈블리](../../../standard/assembly/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-108">For more information about these building blocks of a Visual Basic program, see [Solutions and Projects](/visualstudio/ide/solutions-and-projects-in-visual-studio) and [Assemblies in .NET](../../../standard/assembly/index.md).</span></span>  
  
## <a name="file-level-programming-elements"></a><span data-ttu-id="b36ac-109">파일-수준 프로그래밍 요소</span><span class="sxs-lookup"><span data-stu-id="b36ac-109">File-Level Programming Elements</span></span>  
 <span data-ttu-id="b36ac-110">프로젝트 또는 파일을 시작 하 고 코드 편집기를 열고 올바른 순서에 이미 있는 코드가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-110">When you start a project or file and open the code editor, you see some code already in place and in the correct order.</span></span> <span data-ttu-id="b36ac-111">모든 코드를 작성할 때는 다음 순서 대로 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-111">Any code that you write should follow the following sequence:</span></span>  
  
1. `Option` <span data-ttu-id="b36ac-112">문</span><span class="sxs-lookup"><span data-stu-id="b36ac-112">statements</span></span>  
  
2. `Imports` <span data-ttu-id="b36ac-113">문</span><span class="sxs-lookup"><span data-stu-id="b36ac-113">statements</span></span>  
  
3. `Namespace` <span data-ttu-id="b36ac-114">문 및 네임 스페이스 수준 요소</span><span class="sxs-lookup"><span data-stu-id="b36ac-114">statements and namespace-level elements</span></span>  
  
 <span data-ttu-id="b36ac-115">문을 다른 순서로 입력 하면 컴파일 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-115">If you enter statements in a different order, compilation errors can result.</span></span>  
  
 <span data-ttu-id="b36ac-116">프로그램에 조건부 컴파일 문에 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-116">A program can also contain conditional compilation statements.</span></span> <span data-ttu-id="b36ac-117">이전 시퀀스의 문 함께 소스 파일에서 이러한 중간에 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-117">You can intersperse these in the source file among the statements of the preceding sequence.</span></span>  
  
### <a name="option-statements"></a><span data-ttu-id="b36ac-118">문 옵션</span><span class="sxs-lookup"><span data-stu-id="b36ac-118">Option Statements</span></span>  
 `Option` <span data-ttu-id="b36ac-119">문은 후속 코드, 구문 및 논리 오류를 방지 하기 위해 노력에 대 한 기본 규칙을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-119">statements establish ground rules for subsequent code, helping prevent syntax and logic errors.</span></span> <span data-ttu-id="b36ac-120">합니다 [Option Explicit 문](../../../visual-basic/language-reference/statements/option-explicit-statement.md) 모든 변수 선언 하면 되며 확인 철자가 디버깅 시간을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-120">The [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md) ensures that all variables are declared and spelled correctly, which reduces debugging time.</span></span> <span data-ttu-id="b36ac-121">합니다 [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md) 서로 다른 데이터 형식의 변수 사이 작업할 때 발생할 수 있는 논리 오류 및 데이터 손실을 최소화 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-121">The [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) helps to minimize logic errors and data loss that can occur when you work between variables of different data types.</span></span> <span data-ttu-id="b36ac-122">합니다 [Option Compare 문](../../../visual-basic/language-reference/statements/option-compare-statement.md) 서로 기준 방식으로 문자열 비교 지정 해당 `Binary` 또는 `Text` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-122">The [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md) specifies the way strings are compared to each other, based on either their `Binary` or `Text` values.</span></span>  
  
### <a name="imports-statements"></a><span data-ttu-id="b36ac-123">Imports 문</span><span class="sxs-lookup"><span data-stu-id="b36ac-123">Imports Statements</span></span>  
 <span data-ttu-id="b36ac-124">포함할 수 있습니다는 [Imports 문 (.NET Namespace 및 형식)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) 프로젝트 외부에 정의 된 이름을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-124">You can include an [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to import names defined outside your project.</span></span> <span data-ttu-id="b36ac-125">`Imports` 문 클래스를 한정 하지 않고는 가져온된 네임 스페이스 내에서 정의 된 다른 형식을 참조 하도록 코드를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-125">An `Imports` statement allows your code to refer to classes and other types defined within the imported namespace, without having to qualify them.</span></span> <span data-ttu-id="b36ac-126">만큼 사용할 수 있습니다 `Imports` 문을 적절 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-126">You can use as many `Imports` statements as appropriate.</span></span> <span data-ttu-id="b36ac-127">자세한 내용은 [참조 및 Imports 문](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-127">For more information, see [References and the Imports Statement](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md).</span></span>  
  
### <a name="namespace-statements"></a><span data-ttu-id="b36ac-128">Namespace 문</span><span class="sxs-lookup"><span data-stu-id="b36ac-128">Namespace Statements</span></span>  
 <span data-ttu-id="b36ac-129">네임 스페이스 도움말 구성 하 고 그룹화 하 고 액세스 하는 편의 위해 프로그래밍 요소를 분류 합니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-129">Namespaces help you organize and classify your programming elements for ease of grouping and accessing.</span></span> <span data-ttu-id="b36ac-130">사용할 합니다 [Namespace 문](../../../visual-basic/language-reference/statements/namespace-statement.md) 특정 네임 스페이스 내에서 다음 명령문을 분류 합니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-130">You use the [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md) to classify the following statements within a particular namespace.</span></span> <span data-ttu-id="b36ac-131">자세한 내용은 [Visual Basic의 네임스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b36ac-131">For more information, see [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).</span></span>  
  
### <a name="conditional-compilation-statements"></a><span data-ttu-id="b36ac-132">조건부 컴파일 문은</span><span class="sxs-lookup"><span data-stu-id="b36ac-132">Conditional Compilation Statements</span></span>  
 <span data-ttu-id="b36ac-133">조건부 컴파일 문을 소스 파일의 거의 모든 곳에 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-133">Conditional compilation statements can appear almost anywhere in your source file.</span></span> <span data-ttu-id="b36ac-134">특정 조건에 따라 컴파일 시 제외 되거나 포함 된 코드의 일부 문제를 일으킬 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-134">They cause parts of your code to be included or excluded at compile time depending on certain conditions.</span></span> <span data-ttu-id="b36ac-135">이용할 수 있습니다 이러한 응용 프로그램 디버깅에 대 한 조건부 코드 디버깅 모드 에서만 실행 되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-135">You can also use them for debugging your application, because conditional code runs in debugging mode only.</span></span> <span data-ttu-id="b36ac-136">자세한 내용은 [조건부 컴파일](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-136">For more information, see [Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md).</span></span>  
  
## <a name="namespace-level-programming-elements"></a><span data-ttu-id="b36ac-137">Namespace 수준 프로그래밍 요소</span><span class="sxs-lookup"><span data-stu-id="b36ac-137">Namespace-Level Programming Elements</span></span>  
 <span data-ttu-id="b36ac-138">클래스, 구조체 및 모듈 원본 파일의 모든 코드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-138">Classes, structures, and modules contain all the code in your source file.</span></span> <span data-ttu-id="b36ac-139">이들은 *네임 스페이스 수준* 요소 네임 스페이스 내에서 또는 소스 파일 수준에서 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-139">They are *namespace-level* elements, which can appear within a namespace or at the source file level.</span></span> <span data-ttu-id="b36ac-140">다른 모든 프로그래밍 요소 선언을 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-140">They hold the declarations of all other programming elements.</span></span> <span data-ttu-id="b36ac-141">인터페이스 요소 서명을 정의 하지만 구현이 제공 하는 모듈 수준에서도 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-141">Interfaces, which define element signatures but provide no implementation, also appear at module level.</span></span> <span data-ttu-id="b36ac-142">모듈 수준 요소에 대 한 자세한 내용은 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b36ac-142">For more information on the module-level elements, see the following:</span></span>  
  
-   [<span data-ttu-id="b36ac-143">Class 문</span><span class="sxs-lookup"><span data-stu-id="b36ac-143">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
-   [<span data-ttu-id="b36ac-144">Structure 문</span><span class="sxs-lookup"><span data-stu-id="b36ac-144">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
-   [<span data-ttu-id="b36ac-145">Module 문</span><span class="sxs-lookup"><span data-stu-id="b36ac-145">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
-   [<span data-ttu-id="b36ac-146">Interface 문</span><span class="sxs-lookup"><span data-stu-id="b36ac-146">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 <span data-ttu-id="b36ac-147">네임 스페이스 수준에서 데이터 요소는 열거형 및 대리자입니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-147">Data elements at namespace level are enumerations and delegates.</span></span>  
  
## <a name="module-level-programming-elements"></a><span data-ttu-id="b36ac-148">모듈 수준 프로그래밍 요소</span><span class="sxs-lookup"><span data-stu-id="b36ac-148">Module-Level Programming Elements</span></span>  
 <span data-ttu-id="b36ac-149">프로시저, 연산자, 속성 및 이벤트는 실행 코드 (런타임 시 작업을 수행 하는 문)을 보유할 수 있는 유일한 프로그래밍 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-149">Procedures, operators, properties, and events are the only programming elements that can hold executable code (statements that perform actions at run time).</span></span> <span data-ttu-id="b36ac-150">이들은 합니다 *모듈 수준* 프로그램의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-150">They are the *module-level* elements of your program.</span></span> <span data-ttu-id="b36ac-151">프로시저 수준 요소에 대 한 자세한 내용은 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b36ac-151">For more information on the procedure-level elements, see the following:</span></span>  
  
-   [<span data-ttu-id="b36ac-152">Function 문</span><span class="sxs-lookup"><span data-stu-id="b36ac-152">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [<span data-ttu-id="b36ac-153">Sub 문</span><span class="sxs-lookup"><span data-stu-id="b36ac-153">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
-   [<span data-ttu-id="b36ac-154">Declare 문</span><span class="sxs-lookup"><span data-stu-id="b36ac-154">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [<span data-ttu-id="b36ac-155">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="b36ac-155">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
-   [<span data-ttu-id="b36ac-156">Property Statement</span><span class="sxs-lookup"><span data-stu-id="b36ac-156">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [<span data-ttu-id="b36ac-157">Event 문</span><span class="sxs-lookup"><span data-stu-id="b36ac-157">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 <span data-ttu-id="b36ac-158">모듈 수준에서 데이터 요소에는 변수, 상수, 열거형 및 대리자는입니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-158">Data elements at module level are variables, constants, enumerations, and delegates.</span></span>  
  
## <a name="procedure-level-programming-elements"></a><span data-ttu-id="b36ac-159">프로시저 수준 프로그래밍 요소</span><span class="sxs-lookup"><span data-stu-id="b36ac-159">Procedure-Level Programming Elements</span></span>  
 <span data-ttu-id="b36ac-160">내용의 대부분 *프로시저 수준* 요소는 프로그램의 런타임 코드를 구성 하는 문을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-160">Most of the contents of *procedure-level* elements are executable statements, which constitute the run-time code of your program.</span></span> <span data-ttu-id="b36ac-161">모든 실행 코드는 몇 가지 절차에 있어야 합니다. (`Function`, `Sub`, `Operator`, `Get`를 `Set`를 `AddHandler`를 `RemoveHandler`, `RaiseEvent`).</span><span class="sxs-lookup"><span data-stu-id="b36ac-161">All executable code must be in some procedure (`Function`, `Sub`, `Operator`, `Get`, `Set`, `AddHandler`, `RemoveHandler`, `RaiseEvent`).</span></span> <span data-ttu-id="b36ac-162">자세한 내용은 [문](../../../visual-basic/programming-guide/language-features/statements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b36ac-162">For more information, see [Statements](../../../visual-basic/programming-guide/language-features/statements.md).</span></span>  
  
 <span data-ttu-id="b36ac-163">프로시저 수준에서 데이터 요소는 로컬 변수 및 상수에 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-163">Data elements at procedure level are limited to local variables and constants.</span></span>  
  
## <a name="the-main-procedure"></a><span data-ttu-id="b36ac-164">Main 프로시저</span><span class="sxs-lookup"><span data-stu-id="b36ac-164">The Main Procedure</span></span>  
 <span data-ttu-id="b36ac-165">`Main` 프로시저는 응용 프로그램 로드 되었을 때 실행할 첫 번째 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-165">The `Main` procedure is the first code to run when your application has been loaded.</span></span> `Main` <span data-ttu-id="b36ac-166">시작 지점 및 응용 프로그램에 대 한 전체 제어 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-166">serves as the starting point and overall control for your application.</span></span> <span data-ttu-id="b36ac-167">네 가지가 있습니다 `Main`:</span><span class="sxs-lookup"><span data-stu-id="b36ac-167">There are four varieties of `Main`:</span></span>  
  
-   `Sub Main()`  
  
-   `Sub Main(ByVal cmdArgs() As String)`  
  
-   `Function Main() As Integer`  
  
-   `Function Main(ByVal cmdArgs() As String) As Integer`  
  
 <span data-ttu-id="b36ac-168">이 절차의 가장 일반적인 것은 `Sub Main()`합니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-168">The most common variety of this procedure is `Sub Main()`.</span></span> <span data-ttu-id="b36ac-169">자세한 내용은 [Visual Basic의 Main 프로시저](../../../visual-basic/programming-guide/program-structure/main-procedure.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b36ac-169">For more information, see [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b36ac-170">참고자료</span><span class="sxs-lookup"><span data-stu-id="b36ac-170">See also</span></span>

- [<span data-ttu-id="b36ac-171">Visual Basic의 Main 프로시저</span><span class="sxs-lookup"><span data-stu-id="b36ac-171">Main Procedure in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/main-procedure.md)
- [<span data-ttu-id="b36ac-172">Visual Basic 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="b36ac-172">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
- [<span data-ttu-id="b36ac-173">Visual Basic 제한 사항</span><span class="sxs-lookup"><span data-stu-id="b36ac-173">Visual Basic Limitations</span></span>](../../../visual-basic/programming-guide/program-structure/limitations.md)
