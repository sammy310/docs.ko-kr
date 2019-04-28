---
title: '방법: 추적 및 디버그를 사용하여 조건부 컴파일'
ms.date: 03/30/2017
helpviewer_keywords:
- trace compiler options
- trace statements
- compiling source code, trace statements
- tracing [.NET Framework], enabling or disabling
- tracing [.NET Framework], compiling conditionally
- TRACE directive
- conditional compilation, tracing code
ms.assetid: 56d051c3-012c-42c1-9a58-7270edc624aa
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a010b2ee1de17741b2d0bdd6e7c50d5f602256ac
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61754559"
---
# <a name="how-to-compile-conditionally-with-trace-and-debug"></a><span data-ttu-id="013fa-102">방법: 추적 및 디버그를 사용하여 조건부 컴파일</span><span class="sxs-lookup"><span data-stu-id="013fa-102">How to: Compile Conditionally with Trace and Debug</span></span>
<span data-ttu-id="013fa-103">개발 중에 응용 프로그램을 디버그하는 동안 추적 및 디버깅 출력은 둘 다 Visual Studio의 출력 창으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="013fa-103">While you are debugging an application during development, both your tracing and debugging output go to the Output window in Visual Studio.</span></span> <span data-ttu-id="013fa-104">그러나 배포된 애플리케이션에 추적 기능을 포함하려면 **TRACE** 컴파일러 지시문을 사용하도록 설정하여 계측된 애플리케이션을 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="013fa-104">However, to include tracing features in a deployed application, you must compile your instrumented applications with the **TRACE** compiler directive enabled.</span></span> <span data-ttu-id="013fa-105">이렇게 하면 추적 코드를 응용 프로그램의 릴리스 버전으로 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="013fa-105">This allows tracing code to be compiled into the release version of your application.</span></span> <span data-ttu-id="013fa-106">**TRACE** 지시문을 사용하지 않으면 모든 추적 코드가 컴파일 중에 무시되고 배포할 실행 코드에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="013fa-106">If you do not enable the **TRACE** directive, all tracing code is ignored during compilation and is not included in the executable code that you will deploy.</span></span>  
  
 <span data-ttu-id="013fa-107">추적 및 디버깅 메서드에는 연결된 조건부 특성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="013fa-107">Both the tracing and debugging methods have associated conditional attributes.</span></span> <span data-ttu-id="013fa-108">예를 들어 추적에 대한 조건부 특성이 **true**이면 모든 trace 문이 어셈블리(컴파일된 .exe 파일 또는 .dll) 내에 포함되고, **Trace** 조건부 특성이 **false**이면 trace 문이 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="013fa-108">For example, if the conditional attribute for tracing is **true**, all trace statements are included within an assembly (a compiled .exe file or .dll); if the **Trace** conditional attribute is **false**, the trace statements are not included.</span></span>  
  
 <span data-ttu-id="013fa-109">빌드에 대해 **Trace** 또는 **Debug** 조건부 특성의 하나를 설정하거나, 둘 다 설정하거나, 아무것도 설정하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="013fa-109">You can have either the **Trace** or **Debug** conditional attribute turned on for a build, or both, or neither.</span></span> <span data-ttu-id="013fa-110">따라서 네 가지 유형의 빌드는 **디버그**하십시오 **추적**, 둘 다 또는 둘입니다.</span><span class="sxs-lookup"><span data-stu-id="013fa-110">Thus, there are four types of build: **Debug**, **Trace**, both, or neither.</span></span> <span data-ttu-id="013fa-111">프로덕션 배포의 일부 릴리스 빌드에는 아무것도 포함되지 않을 수 있습니다. 대부분 디버깅 빌드에는 둘 다 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="013fa-111">Some release builds for production deployment might contain neither; most debugging builds contain both.</span></span>  
  
 <span data-ttu-id="013fa-112">여러 가지 방법으로 응용 프로그램에 대한 컴파일러 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="013fa-112">You can specify the compiler settings for your application in several ways:</span></span>  
  
- <span data-ttu-id="013fa-113">속성 페이지</span><span class="sxs-lookup"><span data-stu-id="013fa-113">The property pages</span></span>  
  
- <span data-ttu-id="013fa-114">명령줄</span><span class="sxs-lookup"><span data-stu-id="013fa-114">The command line</span></span>  
  
- <span data-ttu-id="013fa-115">**#CONST**(Visual Basic의 경우) 및 **#define**(C#의 경우)</span><span class="sxs-lookup"><span data-stu-id="013fa-115">**#CONST** (for Visual Basic) and **#define** (for C#)</span></span>  
  
### <a name="to-change-compile-settings-from-the-property-pages-dialog-box"></a><span data-ttu-id="013fa-116">속성 페이지 대화 상자에서 컴파일 설정을 변경하려면</span><span class="sxs-lookup"><span data-stu-id="013fa-116">To change compile settings from the property pages dialog box</span></span>  
  
1. <span data-ttu-id="013fa-117">**솔루션 탐색기**에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="013fa-117">Right-click the project node in **Solution Explorer**.</span></span>  
  
2. <span data-ttu-id="013fa-118">바로 가기 메뉴에서 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="013fa-118">Choose **Properties** from the shortcut menu.</span></span>  
  
    - <span data-ttu-id="013fa-119">Visual Basic에서 속성 페이지의 왼쪽 창에 있는 **컴파일** 탭을 클릭하고 **고급 컴파일 옵션** 단추를 클릭하여 **고급 컴파일러 설정** 대화 상자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="013fa-119">In Visual Basic, click the **Compile** tab in the left pane of the property page, then click the **Advanced Compile Options** button to display the **Advanced Compiler Settings** dialog box.</span></span> <span data-ttu-id="013fa-120">사용하도록 설정할 컴파일러 설정의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="013fa-120">Select the check boxes for the compiler settings you want to enable.</span></span> <span data-ttu-id="013fa-121">사용하지 않도록 설정할 설정의 확인란을 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="013fa-121">Clear the check boxes for settings you want to disable.</span></span>  
  
    - <span data-ttu-id="013fa-122">C#에서 속성 페이지의 왼쪽 창에 있는 **빌드** 탭을 클릭하고 사용하도록 설정할 컴파일러 설정의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="013fa-122">In C#, click the **Build** tab in the left pane of the property page, then select the check boxes for the compiler settings you want to enable.</span></span> <span data-ttu-id="013fa-123">사용하지 않도록 설정할 설정의 확인란을 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="013fa-123">Clear the check boxes for settings you want to disable.</span></span>  
  
### <a name="to-compile-instrumented-code-using-the-command-line"></a><span data-ttu-id="013fa-124">명령줄을 사용하여 계측된 코드를 컴파일하려면</span><span class="sxs-lookup"><span data-stu-id="013fa-124">To compile instrumented code using the command line</span></span>  
  
1. <span data-ttu-id="013fa-125">명령줄에서 조건부 컴파일러 스위치를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="013fa-125">Set a conditional compiler switch on the command line.</span></span> <span data-ttu-id="013fa-126">컴파일러는 실행 파일에 추적 및 디버그 코드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="013fa-126">The compiler will include trace or debug code in the executable.</span></span>  
  
     <span data-ttu-id="013fa-127">예를 들어 명령줄에 입력된 다음 컴파일러 명령은 컴파일된 실행 파일에 추적 코드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="013fa-127">For example, the following compiler instruction entered on the command line would include your tracing code in a compiled executable:</span></span>  
  
     <span data-ttu-id="013fa-128">Visual basic: **vbc-r:System.dll-d: TRACE = TRUE-d: DEBUG = FALSE MyApplication.vb**</span><span class="sxs-lookup"><span data-stu-id="013fa-128">For Visual Basic: **vbc -r:System.dll -d:TRACE=TRUE -d:DEBUG=FALSE MyApplication.vb**</span></span>  
  
     <span data-ttu-id="013fa-129">에 대 한 C#: **csc-r:System.dll-d: 추적-d: DEBUG = FALSE MyApplication.cs**</span><span class="sxs-lookup"><span data-stu-id="013fa-129">For C#: **csc -r:System.dll -d:TRACE -d:DEBUG=FALSE MyApplication.cs**</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="013fa-130">애플리케이션 파일을 두 개 이상 컴파일하려면 파일 이름 사이에 공백을 남깁니다(예: **MyApplication1.vb MyApplication2.vb MyApplication3.vb** 또는 **MyApplication1.cs MyApplication2.cs MyApplication3.cs**).</span><span class="sxs-lookup"><span data-stu-id="013fa-130">To compile more than one application file, leave a blank space between the file names, for example, **MyApplication1.vb MyApplication2.vb MyApplication3.vb** or **MyApplication1.cs MyApplication2.cs MyApplication3.cs**.</span></span>  
  
     <span data-ttu-id="013fa-131">위 예제에서 사용된 조건부 컴파일 지시문의 의미는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="013fa-131">The meaning of the conditional-compilation directives used in the above examples is as follows:</span></span>  
  
    |<span data-ttu-id="013fa-132">지시문</span><span class="sxs-lookup"><span data-stu-id="013fa-132">Directive</span></span>|<span data-ttu-id="013fa-133">의미</span><span class="sxs-lookup"><span data-stu-id="013fa-133">Meaning</span></span>|  
    |---------------|-------------|  
    |`vbc`|<span data-ttu-id="013fa-134">Visual Basic 컴파일러</span><span class="sxs-lookup"><span data-stu-id="013fa-134">Visual Basic compiler</span></span>|  
    |`csc`|<span data-ttu-id="013fa-135">C# 컴파일러</span><span class="sxs-lookup"><span data-stu-id="013fa-135">C# compiler</span></span>|  
    |`-r:`|<span data-ttu-id="013fa-136">외부 어셈블리(EXE 또는 DLL)를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="013fa-136">References an external assembly (EXE or DLL)</span></span>|  
    |`-d:`|<span data-ttu-id="013fa-137">조건부 컴파일 기호를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="013fa-137">Defines a conditional compilation symbol</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="013fa-138">TRACE 또는 DEBUG를 대문자로 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="013fa-138">You must spell TRACE or DEBUG with uppercase letters.</span></span> <span data-ttu-id="013fa-139">조건부 컴파일 명령에 대한 자세한 내용을 보려면 명령 프롬프트에 `vbc /?`(Visual Basic의 경우) 또는 `csc /?`(C#의 경우)를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="013fa-139">For more information about the conditional compilation commands, enter `vbc /?` (for Visual Basic) or `csc /?` (for C#) at the command prompt.</span></span> <span data-ttu-id="013fa-140">자세한 내용은 [명령줄에서 빌드](~/docs/csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)(C#) 또는 [명령줄 컴파일러 호출](~/docs/visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)(Visual Basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="013fa-140">For more information, see [Building from the Command Line](~/docs/csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md) (C#) or [Invoking the Command-Line Compiler](~/docs/visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md) (Visual Basic).</span></span>  
  
### <a name="to-perform-conditional-compilation-using-const-or-define"></a><span data-ttu-id="013fa-141">#CONST 또는 #define을 사용하여 조건부 컴파일을 수행하려면</span><span class="sxs-lookup"><span data-stu-id="013fa-141">To perform conditional compilation using #CONST or #define</span></span>  
  
1. <span data-ttu-id="013fa-142">소스 코드 파일의 위쪽에서 프로그래밍 언어에 대한 적절한 문을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="013fa-142">Type the appropriate statement for your programming language at the top of the source code file.</span></span>  
  
    |<span data-ttu-id="013fa-143">언어</span><span class="sxs-lookup"><span data-stu-id="013fa-143">Language</span></span>|<span data-ttu-id="013fa-144">문</span><span class="sxs-lookup"><span data-stu-id="013fa-144">Statement</span></span>|<span data-ttu-id="013fa-145">결과</span><span class="sxs-lookup"><span data-stu-id="013fa-145">Result</span></span>|  
    |--------------|---------------|------------|  
    |<span data-ttu-id="013fa-146">**Visual Basic**</span><span class="sxs-lookup"><span data-stu-id="013fa-146">**Visual Basic**</span></span>|<span data-ttu-id="013fa-147">**#CONST TRACE = true**</span><span class="sxs-lookup"><span data-stu-id="013fa-147">**#CONST TRACE = true**</span></span>|<span data-ttu-id="013fa-148">추적 사용</span><span class="sxs-lookup"><span data-stu-id="013fa-148">Enables tracing</span></span>|  
    ||<span data-ttu-id="013fa-149">**#CONST TRACE = false**</span><span class="sxs-lookup"><span data-stu-id="013fa-149">**#CONST TRACE = false**</span></span>|<span data-ttu-id="013fa-150">추적 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="013fa-150">Disables tracing</span></span>|  
    ||<span data-ttu-id="013fa-151">**#CONST DEBUG = true**</span><span class="sxs-lookup"><span data-stu-id="013fa-151">**#CONST DEBUG = true**</span></span>|<span data-ttu-id="013fa-152">디버깅 사용</span><span class="sxs-lookup"><span data-stu-id="013fa-152">Enables debugging</span></span>|  
    ||<span data-ttu-id="013fa-153">**#CONST DEBUG = false**</span><span class="sxs-lookup"><span data-stu-id="013fa-153">**#CONST DEBUG = false**</span></span>|<span data-ttu-id="013fa-154">디버깅 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="013fa-154">Disables debugging</span></span>|  
    |<span data-ttu-id="013fa-155">**C#**</span><span class="sxs-lookup"><span data-stu-id="013fa-155">**C#**</span></span>|<span data-ttu-id="013fa-156">**#define TRACE**</span><span class="sxs-lookup"><span data-stu-id="013fa-156">**#define TRACE**</span></span>|<span data-ttu-id="013fa-157">추적 사용</span><span class="sxs-lookup"><span data-stu-id="013fa-157">Enables tracing</span></span>|  
    ||<span data-ttu-id="013fa-158">**#undef TRACE**</span><span class="sxs-lookup"><span data-stu-id="013fa-158">**#undef TRACE**</span></span>|<span data-ttu-id="013fa-159">추적 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="013fa-159">Disables tracing</span></span>|  
    ||<span data-ttu-id="013fa-160">**#define DEBUG**</span><span class="sxs-lookup"><span data-stu-id="013fa-160">**#define DEBUG**</span></span>|<span data-ttu-id="013fa-161">디버깅 사용</span><span class="sxs-lookup"><span data-stu-id="013fa-161">Enables debugging</span></span>|  
    ||<span data-ttu-id="013fa-162">**#undef DEBUG**</span><span class="sxs-lookup"><span data-stu-id="013fa-162">**#undef DEBUG**</span></span>|<span data-ttu-id="013fa-163">디버깅 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="013fa-163">Disables debugging</span></span>|  
  
### <a name="to-disable-tracing-or-debugging"></a><span data-ttu-id="013fa-164">추적 또는 디버깅을 사용하지 않으려면</span><span class="sxs-lookup"><span data-stu-id="013fa-164">To disable tracing or debugging</span></span>  
  
<span data-ttu-id="013fa-165">소스 코드에서 컴파일러 지시문을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="013fa-165">Delete the compiler directive from your source code.</span></span>  
  
<span data-ttu-id="013fa-166">\- 또는 -</span><span class="sxs-lookup"><span data-stu-id="013fa-166">\- or -</span></span>  
  
<span data-ttu-id="013fa-167">컴파일러 지시문을 주석으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="013fa-167">Comment out the compiler directive.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="013fa-168">컴파일할 준비가 되면 **빌드** 메뉴에서 **빌드**를 선택하거나, **d:** 을 입력하지 않고 명령줄 메서드를 사용하여 조건부 컴파일 기호를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="013fa-168">When you are ready to compile, you can either choose **Build** from the **Build** menu, or use the command line method but without typing the **d:** to define conditional compilation symbols.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="013fa-169">참고자료</span><span class="sxs-lookup"><span data-stu-id="013fa-169">See also</span></span>

- [<span data-ttu-id="013fa-170">응용 프로그램 추적 및 조율</span><span class="sxs-lookup"><span data-stu-id="013fa-170">Tracing and Instrumenting Applications</span></span>](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)
- [<span data-ttu-id="013fa-171">방법: 만들기, 초기화 및 추적 스위치 구성</span><span class="sxs-lookup"><span data-stu-id="013fa-171">How to: Create, Initialize and Configure Trace Switches</span></span>](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md)
- [<span data-ttu-id="013fa-172">추적 스위치</span><span class="sxs-lookup"><span data-stu-id="013fa-172">Trace Switches</span></span>](../../../docs/framework/debug-trace-profile/trace-switches.md)
- [<span data-ttu-id="013fa-173">추적 수신기</span><span class="sxs-lookup"><span data-stu-id="013fa-173">Trace Listeners</span></span>](../../../docs/framework/debug-trace-profile/trace-listeners.md)
- [<span data-ttu-id="013fa-174">방법: 응용 프로그램 코드에 Trace 문 추가</span><span class="sxs-lookup"><span data-stu-id="013fa-174">How to: Add Trace Statements to Application Code</span></span>](../../../docs/framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md)
- [<span data-ttu-id="013fa-175">방법: Visual Studio 명령줄에 필요한 환경 변수 설정</span><span class="sxs-lookup"><span data-stu-id="013fa-175">How to: Set Environment Variables for the Visual Studio Command Line</span></span>](~/docs/csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)
- [<span data-ttu-id="013fa-176">방법: 명령줄 컴파일러 호출</span><span class="sxs-lookup"><span data-stu-id="013fa-176">How to: Invoke the Command-Line Compiler</span></span>](~/docs/visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)
