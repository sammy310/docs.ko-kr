---
title: Visual Basic 프로그램의 구조
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], Visual Basic
- program structure [Visual Basic], Visual Basic
- procedures [Visual Basic], structure
- Visual Basic code, program structure
ms.assetid: ad0c6531-d762-4c77-a700-de16b07b6119
ms.openlocfilehash: dc6b38d78f02a42c8e7cc2aa964e9f3f74996f44
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408766"
---
# <a name="structure-of-a-visual-basic-program"></a><span data-ttu-id="06ea9-102">Visual Basic 프로그램의 구조</span><span class="sxs-lookup"><span data-stu-id="06ea9-102">Structure of a Visual Basic Program</span></span>
<span data-ttu-id="06ea9-103">Visual Basic 프로그램은 표준 구성 요소에서 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="06ea9-103">A Visual Basic program is built up from standard building blocks.</span></span> <span data-ttu-id="06ea9-104">*솔루션* 은 하나 이상의 프로젝트로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06ea9-104">A *solution* comprises one or more projects.</span></span> <span data-ttu-id="06ea9-105">그러면 *프로젝트* 에 하나 이상의 어셈블리가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06ea9-105">A *project* in turn can contain one or more assemblies.</span></span> <span data-ttu-id="06ea9-106">각 *어셈블리* 는 하나 이상의 소스 파일에서 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="06ea9-106">Each *assembly* is compiled from one or more source files.</span></span> <span data-ttu-id="06ea9-107">*소스 파일* 은 궁극적으로 모든 코드를 포함 하는 클래스, 구조체, 모듈 및 인터페이스의 정의와 구현을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="06ea9-107">A *source file* provides the definition and implementation of classes, structures, modules, and interfaces, which ultimately contain all your code.</span></span>  
  
 <span data-ttu-id="06ea9-108">Visual Basic 프로그램의 이러한 구성 요소에 대 한 자세한 내용은 .NET의 [솔루션 및 프로젝트](/visualstudio/ide/solutions-and-projects-in-visual-studio) 및 [어셈블리](../../../standard/assembly/index.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="06ea9-108">For more information about these building blocks of a Visual Basic program, see [Solutions and Projects](/visualstudio/ide/solutions-and-projects-in-visual-studio) and [Assemblies in .NET](../../../standard/assembly/index.md).</span></span>  
  
## <a name="file-level-programming-elements"></a><span data-ttu-id="06ea9-109">파일 수준 프로그래밍 요소</span><span class="sxs-lookup"><span data-stu-id="06ea9-109">File-Level Programming Elements</span></span>  
 <span data-ttu-id="06ea9-110">프로젝트 또는 파일을 시작 하 고 코드 편집기를 열면 일부 코드가 이미 있고 올바른 순서로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06ea9-110">When you start a project or file and open the code editor, you see some code already in place and in the correct order.</span></span> <span data-ttu-id="06ea9-111">작성 하는 모든 코드는 다음 순서를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06ea9-111">Any code that you write should follow the following sequence:</span></span>  
  
1. <span data-ttu-id="06ea9-112">`Option`할당문</span><span class="sxs-lookup"><span data-stu-id="06ea9-112">`Option` statements</span></span>  
  
2. <span data-ttu-id="06ea9-113">`Imports`할당문</span><span class="sxs-lookup"><span data-stu-id="06ea9-113">`Imports` statements</span></span>  
  
3. <span data-ttu-id="06ea9-114">`Namespace`문 및 네임 스페이스 수준 요소</span><span class="sxs-lookup"><span data-stu-id="06ea9-114">`Namespace` statements and namespace-level elements</span></span>  
  
 <span data-ttu-id="06ea9-115">문을 다른 순서로 입력 하면 컴파일 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06ea9-115">If you enter statements in a different order, compilation errors can result.</span></span>  
  
 <span data-ttu-id="06ea9-116">프로그램에는 조건부 컴파일 문도 포함 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06ea9-116">A program can also contain conditional compilation statements.</span></span> <span data-ttu-id="06ea9-117">이러한 파일을 원본 파일에서 이전 시퀀스의 문 사이에 섞어서 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06ea9-117">You can intersperse these in the source file among the statements of the preceding sequence.</span></span>  
  
### <a name="option-statements"></a><span data-ttu-id="06ea9-118">Option 문</span><span class="sxs-lookup"><span data-stu-id="06ea9-118">Option Statements</span></span>  
 <span data-ttu-id="06ea9-119">`Option`문은 후속 코드에 대 한 접지 규칙을 설정 하 여 구문 및 논리 오류를 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="06ea9-119">`Option` statements establish ground rules for subsequent code, helping prevent syntax and logic errors.</span></span> <span data-ttu-id="06ea9-120">[Option Explicit 문은](../../language-reference/statements/option-explicit-statement.md) 모든 변수가 올바르게 선언 되 고 철자가 올바른지 확인 하므로 디버깅 시간이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="06ea9-120">The [Option Explicit Statement](../../language-reference/statements/option-explicit-statement.md) ensures that all variables are declared and spelled correctly, which reduces debugging time.</span></span> <span data-ttu-id="06ea9-121">[Option Strict 문은](../../language-reference/statements/option-strict-statement.md) 다른 데이터 형식의 변수 사이에서 작업할 때 발생할 수 있는 논리 오류 및 데이터 손실을 최소화 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06ea9-121">The [Option Strict Statement](../../language-reference/statements/option-strict-statement.md) helps to minimize logic errors and data loss that can occur when you work between variables of different data types.</span></span> <span data-ttu-id="06ea9-122">[Option Compare 문은](../../language-reference/statements/option-compare-statement.md) 또는 값을 기준으로 문자열이 서로 비교 되는 방식을 지정 합니다 `Binary` `Text` .</span><span class="sxs-lookup"><span data-stu-id="06ea9-122">The [Option Compare Statement](../../language-reference/statements/option-compare-statement.md) specifies the way strings are compared to each other, based on either their `Binary` or `Text` values.</span></span>  
  
### <a name="imports-statements"></a><span data-ttu-id="06ea9-123">Imports 문</span><span class="sxs-lookup"><span data-stu-id="06ea9-123">Imports Statements</span></span>  
 <span data-ttu-id="06ea9-124">[Imports 문 (.Net 네임 스페이스 및 형식)](../../language-reference/statements/imports-statement-net-namespace-and-type.md) 을 포함 하 여 프로젝트 외부에 정의 된 이름을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06ea9-124">You can include an [Imports Statement (.NET Namespace and Type)](../../language-reference/statements/imports-statement-net-namespace-and-type.md) to import names defined outside your project.</span></span> <span data-ttu-id="06ea9-125">`Imports`문을 사용 하면 코드에서 가져온 네임 스페이스 내에 정의 된 클래스 및 기타 형식을 한정할 필요 없이 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06ea9-125">An `Imports` statement allows your code to refer to classes and other types defined within the imported namespace, without having to qualify them.</span></span> <span data-ttu-id="06ea9-126">필요한 만큼 문을 사용할 수 있습니다 `Imports` .</span><span class="sxs-lookup"><span data-stu-id="06ea9-126">You can use as many `Imports` statements as appropriate.</span></span> <span data-ttu-id="06ea9-127">자세한 내용은 [참조 및 Imports 문](references-and-the-imports-statement.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="06ea9-127">For more information, see [References and the Imports Statement](references-and-the-imports-statement.md).</span></span>  
  
### <a name="namespace-statements"></a><span data-ttu-id="06ea9-128">Namespace 문</span><span class="sxs-lookup"><span data-stu-id="06ea9-128">Namespace Statements</span></span>  
 <span data-ttu-id="06ea9-129">네임 스페이스는 그룹화 및 액세스 용이성을 위해 프로그래밍 요소를 구성 하 고 분류 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06ea9-129">Namespaces help you organize and classify your programming elements for ease of grouping and accessing.</span></span> <span data-ttu-id="06ea9-130">[Namespace 문을](../../language-reference/statements/namespace-statement.md) 사용 하 여 특정 네임 스페이스 내에서 다음 문을 분류 합니다.</span><span class="sxs-lookup"><span data-stu-id="06ea9-130">You use the [Namespace Statement](../../language-reference/statements/namespace-statement.md) to classify the following statements within a particular namespace.</span></span> <span data-ttu-id="06ea9-131">자세한 내용은 [Visual Basic의 네임스페이스](namespaces.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06ea9-131">For more information, see [Namespaces in Visual Basic](namespaces.md).</span></span>  
  
### <a name="conditional-compilation-statements"></a><span data-ttu-id="06ea9-132">조건부 컴파일 문</span><span class="sxs-lookup"><span data-stu-id="06ea9-132">Conditional Compilation Statements</span></span>  
 <span data-ttu-id="06ea9-133">조건부 컴파일 문은 소스 파일의 거의 모든 위치에 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06ea9-133">Conditional compilation statements can appear almost anywhere in your source file.</span></span> <span data-ttu-id="06ea9-134">특정 조건에 따라 코드의 일부를 컴파일 시간에 포함 하거나 제외 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="06ea9-134">They cause parts of your code to be included or excluded at compile time depending on certain conditions.</span></span> <span data-ttu-id="06ea9-135">조건부 코드는 디버깅 모드 에서만 실행 되므로 응용 프로그램을 디버깅 하는 데 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06ea9-135">You can also use them for debugging your application, because conditional code runs in debugging mode only.</span></span> <span data-ttu-id="06ea9-136">자세한 내용은 [조건부 컴파일](conditional-compilation.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="06ea9-136">For more information, see [Conditional Compilation](conditional-compilation.md).</span></span>  
  
## <a name="namespace-level-programming-elements"></a><span data-ttu-id="06ea9-137">네임 스페이스 수준 프로그래밍 요소</span><span class="sxs-lookup"><span data-stu-id="06ea9-137">Namespace-Level Programming Elements</span></span>  
 <span data-ttu-id="06ea9-138">클래스, 구조체 및 모듈은 소스 파일의 모든 코드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="06ea9-138">Classes, structures, and modules contain all the code in your source file.</span></span> <span data-ttu-id="06ea9-139">네임 스페이스는 네임 스페이스 또는 소스 파일 수준에서 나타날 수 있는 *네임 스페이스 수준* 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="06ea9-139">They are *namespace-level* elements, which can appear within a namespace or at the source file level.</span></span> <span data-ttu-id="06ea9-140">다른 모든 프로그래밍 요소의 선언을 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="06ea9-140">They hold the declarations of all other programming elements.</span></span> <span data-ttu-id="06ea9-141">요소 시그니처를 정의 하지만 구현을 제공 하지 않는 인터페이스는 모듈 수준에도 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06ea9-141">Interfaces, which define element signatures but provide no implementation, also appear at module level.</span></span> <span data-ttu-id="06ea9-142">모듈 수준 요소에 대 한 자세한 내용은 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="06ea9-142">For more information on the module-level elements, see the following:</span></span>  
  
- [<span data-ttu-id="06ea9-143">Class 문</span><span class="sxs-lookup"><span data-stu-id="06ea9-143">Class Statement</span></span>](../../language-reference/statements/class-statement.md)  
  
- [<span data-ttu-id="06ea9-144">Structure 문</span><span class="sxs-lookup"><span data-stu-id="06ea9-144">Structure Statement</span></span>](../../language-reference/statements/structure-statement.md)  
  
- [<span data-ttu-id="06ea9-145">Module 문</span><span class="sxs-lookup"><span data-stu-id="06ea9-145">Module Statement</span></span>](../../language-reference/statements/module-statement.md)  
  
- [<span data-ttu-id="06ea9-146">Interface 문</span><span class="sxs-lookup"><span data-stu-id="06ea9-146">Interface Statement</span></span>](../../language-reference/statements/interface-statement.md)  
  
 <span data-ttu-id="06ea9-147">네임 스페이스 수준에서 데이터 요소는 열거형 및 대리자입니다.</span><span class="sxs-lookup"><span data-stu-id="06ea9-147">Data elements at namespace level are enumerations and delegates.</span></span>  
  
## <a name="module-level-programming-elements"></a><span data-ttu-id="06ea9-148">모듈 수준 프로그래밍 요소</span><span class="sxs-lookup"><span data-stu-id="06ea9-148">Module-Level Programming Elements</span></span>  
 <span data-ttu-id="06ea9-149">프로시저, 연산자, 속성 및 이벤트는 실행 코드 (런타임에 동작을 수행 하는 문)를 보유할 수 있는 유일한 프로그래밍 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="06ea9-149">Procedures, operators, properties, and events are the only programming elements that can hold executable code (statements that perform actions at run time).</span></span> <span data-ttu-id="06ea9-150">프로그램의 *모듈 수준* 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="06ea9-150">They are the *module-level* elements of your program.</span></span> <span data-ttu-id="06ea9-151">프로시저 수준 요소에 대 한 자세한 내용은 다음을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="06ea9-151">For more information on the procedure-level elements, see the following:</span></span>  
  
- [<span data-ttu-id="06ea9-152">Function 문</span><span class="sxs-lookup"><span data-stu-id="06ea9-152">Function Statement</span></span>](../../language-reference/statements/function-statement.md)  
  
- [<span data-ttu-id="06ea9-153">Sub 문</span><span class="sxs-lookup"><span data-stu-id="06ea9-153">Sub Statement</span></span>](../../language-reference/statements/sub-statement.md)  
  
- [<span data-ttu-id="06ea9-154">Declare 문</span><span class="sxs-lookup"><span data-stu-id="06ea9-154">Declare Statement</span></span>](../../language-reference/statements/declare-statement.md)  
  
- [<span data-ttu-id="06ea9-155">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="06ea9-155">Operator Statement</span></span>](../../language-reference/statements/operator-statement.md)  
  
- [<span data-ttu-id="06ea9-156">Property Statement</span><span class="sxs-lookup"><span data-stu-id="06ea9-156">Property Statement</span></span>](../../language-reference/statements/property-statement.md)  
  
- [<span data-ttu-id="06ea9-157">Event 문</span><span class="sxs-lookup"><span data-stu-id="06ea9-157">Event Statement</span></span>](../../language-reference/statements/event-statement.md)  
  
 <span data-ttu-id="06ea9-158">모듈 수준에서 데이터 요소는 변수, 상수, 열거형 및 대리자입니다.</span><span class="sxs-lookup"><span data-stu-id="06ea9-158">Data elements at module level are variables, constants, enumerations, and delegates.</span></span>  
  
## <a name="procedure-level-programming-elements"></a><span data-ttu-id="06ea9-159">프로시저 수준 프로그래밍 요소</span><span class="sxs-lookup"><span data-stu-id="06ea9-159">Procedure-Level Programming Elements</span></span>  
 <span data-ttu-id="06ea9-160">*프로시저 수준* 요소의 내용 대부분은 프로그램의 런타임 코드를 구성 하는 실행 가능한 문입니다.</span><span class="sxs-lookup"><span data-stu-id="06ea9-160">Most of the contents of *procedure-level* elements are executable statements, which constitute the run-time code of your program.</span></span> <span data-ttu-id="06ea9-161">모든 실행 코드는 일부 프로시저 ( `Function` ,,,,,,,)에 있어야 합니다 `Sub` `Operator` `Get` `Set` `AddHandler` `RemoveHandler` `RaiseEvent` .</span><span class="sxs-lookup"><span data-stu-id="06ea9-161">All executable code must be in some procedure (`Function`, `Sub`, `Operator`, `Get`, `Set`, `AddHandler`, `RemoveHandler`, `RaiseEvent`).</span></span> <span data-ttu-id="06ea9-162">자세한 내용은 [문](../language-features/statements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="06ea9-162">For more information, see [Statements](../language-features/statements.md).</span></span>  
  
 <span data-ttu-id="06ea9-163">프로시저 수준에서 데이터 요소는 지역 변수 및 상수로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06ea9-163">Data elements at procedure level are limited to local variables and constants.</span></span>  
  
## <a name="the-main-procedure"></a><span data-ttu-id="06ea9-164">주 프로시저</span><span class="sxs-lookup"><span data-stu-id="06ea9-164">The Main Procedure</span></span>  
 <span data-ttu-id="06ea9-165">`Main`프로시저는 응용 프로그램이 로드 될 때 실행 되는 첫 번째 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="06ea9-165">The `Main` procedure is the first code to run when your application has been loaded.</span></span> <span data-ttu-id="06ea9-166">`Main`응용 프로그램에 대 한 시작 지점 및 전반적인 제어 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="06ea9-166">`Main` serves as the starting point and overall control for your application.</span></span> <span data-ttu-id="06ea9-167">다음과 같은 네 가지 종류의이 있습니다 `Main` .</span><span class="sxs-lookup"><span data-stu-id="06ea9-167">There are four varieties of `Main`:</span></span>  
  
- `Sub Main()`  
  
- `Sub Main(ByVal cmdArgs() As String)`  
  
- `Function Main() As Integer`  
  
- `Function Main(ByVal cmdArgs() As String) As Integer`  
  
 <span data-ttu-id="06ea9-168">이 절차의 가장 일반적인 방법은 `Sub Main()` 입니다.</span><span class="sxs-lookup"><span data-stu-id="06ea9-168">The most common variety of this procedure is `Sub Main()`.</span></span> <span data-ttu-id="06ea9-169">자세한 내용은 [Visual Basic 주 절차](main-procedure.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="06ea9-169">For more information, see [Main Procedure in Visual Basic](main-procedure.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06ea9-170">참고 항목</span><span class="sxs-lookup"><span data-stu-id="06ea9-170">See also</span></span>

- [<span data-ttu-id="06ea9-171">Visual Basic의 Main 프로시저</span><span class="sxs-lookup"><span data-stu-id="06ea9-171">Main Procedure in Visual Basic</span></span>](main-procedure.md)
- [<span data-ttu-id="06ea9-172">Visual Basic 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="06ea9-172">Visual Basic Naming Conventions</span></span>](naming-conventions.md)
- [<span data-ttu-id="06ea9-173">Visual Basic 제한 사항</span><span class="sxs-lookup"><span data-stu-id="06ea9-173">Visual Basic Limitations</span></span>](limitations.md)
