---
title: '방법: 추적 및 디버그를 사용하여 조건부 컴파일'
description: .NET 응용 프로그램을 컴파일할 때 추적 및 디버그 조건부 특성을 사용 하 여 조건부로 컴파일하는 방법에 대해 알아봅니다.
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
ms.openlocfilehash: 90c989bcf21e24cf7ccf410c9a18a44cde81233e
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103478208"
---
# <a name="how-to-compile-conditionally-with-trace-and-debug"></a><span data-ttu-id="613c6-103">방법: 추적 및 디버그를 사용하여 조건부 컴파일</span><span class="sxs-lookup"><span data-stu-id="613c6-103">How to: Compile Conditionally with Trace and Debug</span></span>

<span data-ttu-id="613c6-104">개발 중에 애플리케이션을 디버그하는 동안 추적 및 디버깅 출력은 둘 다 Visual Studio의 출력 창으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="613c6-104">While you are debugging an application during development, both your tracing and debugging output go to the Output window in Visual Studio.</span></span> <span data-ttu-id="613c6-105">그러나 배포된 애플리케이션에 추적 기능을 포함하려면 **TRACE** 컴파일러 지시문을 사용하도록 설정하여 계측된 애플리케이션을 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="613c6-105">However, to include tracing features in a deployed application, you must compile your instrumented applications with the **TRACE** compiler directive enabled.</span></span> <span data-ttu-id="613c6-106">이렇게 하면 추적 코드를 애플리케이션의 릴리스 버전으로 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="613c6-106">This allows tracing code to be compiled into the release version of your application.</span></span> <span data-ttu-id="613c6-107">**TRACE** 지시문을 사용하지 않으면 모든 추적 코드가 컴파일 중에 무시되고 배포할 실행 코드에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="613c6-107">If you do not enable the **TRACE** directive, all tracing code is ignored during compilation and is not included in the executable code that you will deploy.</span></span>  
  
 <span data-ttu-id="613c6-108">추적 및 디버깅 메서드에는 연결된 조건부 특성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="613c6-108">Both the tracing and debugging methods have associated conditional attributes.</span></span> <span data-ttu-id="613c6-109">예를 들어 추적에 대한 조건부 특성이 **true** 이면 모든 trace 문이 어셈블리(컴파일된 .exe 파일 또는 .dll) 내에 포함되고, **Trace** 조건부 특성이 **false** 이면 trace 문이 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="613c6-109">For example, if the conditional attribute for tracing is **true**, all trace statements are included within an assembly (a compiled .exe file or .dll); if the **Trace** conditional attribute is **false**, the trace statements are not included.</span></span>  
  
 <span data-ttu-id="613c6-110">빌드에 대해 **Trace** 또는 **Debug** 조건부 특성의 하나를 설정하거나, 둘 다 설정하거나, 아무것도 설정하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="613c6-110">You can have either the **Trace** or **Debug** conditional attribute turned on for a build, or both, or neither.</span></span> <span data-ttu-id="613c6-111">따라서 **디버그**, **추적**, 둘 다 또는 아무것도 설정하지 않는 네 가지 빌드 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="613c6-111">Thus, there are four types of build: **Debug**, **Trace**, both, or neither.</span></span> <span data-ttu-id="613c6-112">프로덕션 배포의 일부 릴리스 빌드에는 아무것도 포함되지 않을 수 있습니다. 대부분 디버깅 빌드에는 둘 다 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="613c6-112">Some release builds for production deployment might contain neither; most debugging builds contain both.</span></span>  
  
 <span data-ttu-id="613c6-113">여러 가지 방법으로 애플리케이션에 대한 컴파일러 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="613c6-113">You can specify the compiler settings for your application in several ways:</span></span>  
  
- <span data-ttu-id="613c6-114">속성 페이지</span><span class="sxs-lookup"><span data-stu-id="613c6-114">The property pages</span></span>  
  
- <span data-ttu-id="613c6-115">명령줄</span><span class="sxs-lookup"><span data-stu-id="613c6-115">The command line</span></span>  
  
- <span data-ttu-id="613c6-116">**#CONST**(Visual Basic의 경우) 및 **#define**(C#의 경우)</span><span class="sxs-lookup"><span data-stu-id="613c6-116">**#CONST** (for Visual Basic) and **#define** (for C#)</span></span>  
  
### <a name="to-change-compile-settings-from-the-property-pages-dialog-box"></a><span data-ttu-id="613c6-117">속성 페이지 대화 상자에서 컴파일 설정을 변경하려면</span><span class="sxs-lookup"><span data-stu-id="613c6-117">To change compile settings from the property pages dialog box</span></span>  
  
1. <span data-ttu-id="613c6-118">**솔루션 탐색기** 에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="613c6-118">Right-click the project node in **Solution Explorer**.</span></span>  
  
2. <span data-ttu-id="613c6-119">바로 가기 메뉴에서 **속성** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="613c6-119">Choose **Properties** from the shortcut menu.</span></span>  
  
    - <span data-ttu-id="613c6-120">Visual Basic에서 속성 페이지의 왼쪽 창에 있는 **컴파일** 탭을 클릭하고 **고급 컴파일 옵션** 단추를 클릭하여 **고급 컴파일러 설정** 대화 상자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="613c6-120">In Visual Basic, click the **Compile** tab in the left pane of the property page, then click the **Advanced Compile Options** button to display the **Advanced Compiler Settings** dialog box.</span></span> <span data-ttu-id="613c6-121">사용하도록 설정할 컴파일러 설정의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="613c6-121">Select the check boxes for the compiler settings you want to enable.</span></span> <span data-ttu-id="613c6-122">사용하지 않도록 설정할 설정의 확인란을 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="613c6-122">Clear the check boxes for settings you want to disable.</span></span>  
  
    - <span data-ttu-id="613c6-123">C#에서 속성 페이지의 왼쪽 창에 있는 **빌드** 탭을 클릭하고 사용하도록 설정할 컴파일러 설정의 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="613c6-123">In C#, click the **Build** tab in the left pane of the property page, then select the check boxes for the compiler settings you want to enable.</span></span> <span data-ttu-id="613c6-124">사용하지 않도록 설정할 설정의 확인란을 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="613c6-124">Clear the check boxes for settings you want to disable.</span></span>  
  
### <a name="to-compile-instrumented-code-using-the-command-line"></a><span data-ttu-id="613c6-125">명령줄을 사용하여 계측된 코드를 컴파일하려면</span><span class="sxs-lookup"><span data-stu-id="613c6-125">To compile instrumented code using the command line</span></span>  
  
1. <span data-ttu-id="613c6-126">명령줄에서 조건부 컴파일러 스위치를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="613c6-126">Set a conditional compiler switch on the command line.</span></span> <span data-ttu-id="613c6-127">컴파일러는 실행 파일에 추적 및 디버그 코드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="613c6-127">The compiler will include trace or debug code in the executable.</span></span>  
  
     <span data-ttu-id="613c6-128">예를 들어 명령줄에 입력된 다음 컴파일러 명령은 컴파일된 실행 파일에 추적 코드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="613c6-128">For example, the following compiler instruction entered on the command line would include your tracing code in a compiled executable:</span></span>  
  
     <span data-ttu-id="613c6-129">Visual Basic: **vbc -r:System.dll-d:TRACE = TRUE-d:DEBUG = FALSE MyApplication .vb**</span><span class="sxs-lookup"><span data-stu-id="613c6-129">For Visual Basic: **vbc -r:System.dll -d:TRACE=TRUE -d:DEBUG=FALSE MyApplication.vb**</span></span>  
  
     <span data-ttu-id="613c6-130">C #: **csc -r:System.dll-d:TRACE-d:DEBUG = FALSE MyApplication.cs**</span><span class="sxs-lookup"><span data-stu-id="613c6-130">For C#: **csc -r:System.dll -d:TRACE -d:DEBUG=FALSE MyApplication.cs**</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="613c6-131">애플리케이션 파일을 두 개 이상 컴파일하려면 파일 이름 사이에 공백을 남깁니다(예: **MyApplication1.vb MyApplication2.vb MyApplication3.vb** 또는 **MyApplication1.cs MyApplication2.cs MyApplication3.cs**).</span><span class="sxs-lookup"><span data-stu-id="613c6-131">To compile more than one application file, leave a blank space between the file names, for example, **MyApplication1.vb MyApplication2.vb MyApplication3.vb** or **MyApplication1.cs MyApplication2.cs MyApplication3.cs**.</span></span>  
  
     <span data-ttu-id="613c6-132">위 예제에서 사용된 조건부 컴파일 지시문의 의미는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="613c6-132">The meaning of the conditional-compilation directives used in the above examples is as follows:</span></span>  
  
    |<span data-ttu-id="613c6-133">지시문</span><span class="sxs-lookup"><span data-stu-id="613c6-133">Directive</span></span>|<span data-ttu-id="613c6-134">의미</span><span class="sxs-lookup"><span data-stu-id="613c6-134">Meaning</span></span>|  
    |---------------|-------------|  
    |`vbc`|<span data-ttu-id="613c6-135">Visual Basic 컴파일러</span><span class="sxs-lookup"><span data-stu-id="613c6-135">Visual Basic compiler</span></span>|  
    |`csc`|<span data-ttu-id="613c6-136">C# 컴파일러</span><span class="sxs-lookup"><span data-stu-id="613c6-136">C# compiler</span></span>|  
    |`-r:`|<span data-ttu-id="613c6-137">외부 어셈블리(EXE 또는 DLL)를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="613c6-137">References an external assembly (EXE or DLL)</span></span>|  
    |`-d:`|<span data-ttu-id="613c6-138">조건부 컴파일 기호를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="613c6-138">Defines a conditional compilation symbol</span></span>|  
  
    > [!NOTE]
    > <span data-ttu-id="613c6-139">TRACE 또는 DEBUG를 대문자로 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="613c6-139">You must spell TRACE or DEBUG with uppercase letters.</span></span> <span data-ttu-id="613c6-140">조건부 컴파일 명령에 대한 자세한 내용을 보려면 명령 프롬프트에 `vbc /?`(Visual Basic의 경우) 또는 `csc /?`(C#의 경우)를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="613c6-140">For more information about the conditional compilation commands, enter `vbc /?` (for Visual Basic) or `csc /?` (for C#) at the command prompt.</span></span> <span data-ttu-id="613c6-141">자세한 내용은 [명령줄에서 빌드](../../csharp/language-reference/compiler-options/index.md)(C#) 또는 [명령줄 컴파일러 호출](../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)(Visual Basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="613c6-141">For more information, see [Building from the Command Line](../../csharp/language-reference/compiler-options/index.md) (C#) or [Invoking the Command-Line Compiler](../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md) (Visual Basic).</span></span>  
  
### <a name="to-perform-conditional-compilation-using-const-or-define"></a><span data-ttu-id="613c6-142">#CONST 또는 #define을 사용하여 조건부 컴파일을 수행하려면</span><span class="sxs-lookup"><span data-stu-id="613c6-142">To perform conditional compilation using #CONST or #define</span></span>  
  
1. <span data-ttu-id="613c6-143">소스 코드 파일의 위쪽에서 프로그래밍 언어에 대한 적절한 문을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="613c6-143">Type the appropriate statement for your programming language at the top of the source code file.</span></span>  
  
    |<span data-ttu-id="613c6-144">언어</span><span class="sxs-lookup"><span data-stu-id="613c6-144">Language</span></span>|<span data-ttu-id="613c6-145">문</span><span class="sxs-lookup"><span data-stu-id="613c6-145">Statement</span></span>|<span data-ttu-id="613c6-146">결과</span><span class="sxs-lookup"><span data-stu-id="613c6-146">Result</span></span>|  
    |--------------|---------------|------------|  
    |<span data-ttu-id="613c6-147">**Visual Basic**</span><span class="sxs-lookup"><span data-stu-id="613c6-147">**Visual Basic**</span></span>|<span data-ttu-id="613c6-148">**#CONST TRACE = true**</span><span class="sxs-lookup"><span data-stu-id="613c6-148">**#CONST TRACE = true**</span></span>|<span data-ttu-id="613c6-149">추적 사용</span><span class="sxs-lookup"><span data-stu-id="613c6-149">Enables tracing</span></span>|  
    ||<span data-ttu-id="613c6-150">**#CONST TRACE = false**</span><span class="sxs-lookup"><span data-stu-id="613c6-150">**#CONST TRACE = false**</span></span>|<span data-ttu-id="613c6-151">추적 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="613c6-151">Disables tracing</span></span>|  
    ||<span data-ttu-id="613c6-152">**#CONST DEBUG = true**</span><span class="sxs-lookup"><span data-stu-id="613c6-152">**#CONST DEBUG = true**</span></span>|<span data-ttu-id="613c6-153">디버깅 사용</span><span class="sxs-lookup"><span data-stu-id="613c6-153">Enables debugging</span></span>|  
    ||<span data-ttu-id="613c6-154">**#CONST DEBUG = false**</span><span class="sxs-lookup"><span data-stu-id="613c6-154">**#CONST DEBUG = false**</span></span>|<span data-ttu-id="613c6-155">디버깅 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="613c6-155">Disables debugging</span></span>|  
    |<span data-ttu-id="613c6-156">**C#**</span><span class="sxs-lookup"><span data-stu-id="613c6-156">**C#**</span></span>|<span data-ttu-id="613c6-157">**#define TRACE**</span><span class="sxs-lookup"><span data-stu-id="613c6-157">**#define TRACE**</span></span>|<span data-ttu-id="613c6-158">추적 사용</span><span class="sxs-lookup"><span data-stu-id="613c6-158">Enables tracing</span></span>|  
    ||<span data-ttu-id="613c6-159">**#undef TRACE**</span><span class="sxs-lookup"><span data-stu-id="613c6-159">**#undef TRACE**</span></span>|<span data-ttu-id="613c6-160">추적 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="613c6-160">Disables tracing</span></span>|  
    ||<span data-ttu-id="613c6-161">**#define DEBUG**</span><span class="sxs-lookup"><span data-stu-id="613c6-161">**#define DEBUG**</span></span>|<span data-ttu-id="613c6-162">디버깅 사용</span><span class="sxs-lookup"><span data-stu-id="613c6-162">Enables debugging</span></span>|  
    ||<span data-ttu-id="613c6-163">**#undef DEBUG**</span><span class="sxs-lookup"><span data-stu-id="613c6-163">**#undef DEBUG**</span></span>|<span data-ttu-id="613c6-164">디버깅 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="613c6-164">Disables debugging</span></span>|  
  
### <a name="to-disable-tracing-or-debugging"></a><span data-ttu-id="613c6-165">추적 또는 디버깅을 사용하지 않으려면</span><span class="sxs-lookup"><span data-stu-id="613c6-165">To disable tracing or debugging</span></span>  
  
<span data-ttu-id="613c6-166">소스 코드에서 컴파일러 지시문을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="613c6-166">Delete the compiler directive from your source code.</span></span>  
  
<span data-ttu-id="613c6-167">\- 또는 -</span><span class="sxs-lookup"><span data-stu-id="613c6-167">\- or -</span></span>  
  
<span data-ttu-id="613c6-168">컴파일러 지시문을 주석으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="613c6-168">Comment out the compiler directive.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="613c6-169">컴파일할 준비가 되면 **빌드** 메뉴에서 **빌드** 를 선택하거나, **d:** 을 입력하지 않고 명령줄 메서드를 사용하여 조건부 컴파일 기호를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="613c6-169">When you are ready to compile, you can either choose **Build** from the **Build** menu, or use the command line method but without typing the **d:** to define conditional compilation symbols.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="613c6-170">참고 항목</span><span class="sxs-lookup"><span data-stu-id="613c6-170">See also</span></span>

- [<span data-ttu-id="613c6-171">애플리케이션 추적 및 조율</span><span class="sxs-lookup"><span data-stu-id="613c6-171">Tracing and Instrumenting Applications</span></span>](tracing-and-instrumenting-applications.md)
- [<span data-ttu-id="613c6-172">방법: 추적 스위치 만들기, 초기화 및 구성</span><span class="sxs-lookup"><span data-stu-id="613c6-172">How to: Create, Initialize and Configure Trace Switches</span></span>](how-to-create-initialize-and-configure-trace-switches.md)
- [<span data-ttu-id="613c6-173">추적 스위치</span><span class="sxs-lookup"><span data-stu-id="613c6-173">Trace Switches</span></span>](trace-switches.md)
- [<span data-ttu-id="613c6-174">추적 수신기</span><span class="sxs-lookup"><span data-stu-id="613c6-174">Trace Listeners</span></span>](trace-listeners.md)
- [<span data-ttu-id="613c6-175">방법: 애플리케이션 코드에 Trace 문 추가</span><span class="sxs-lookup"><span data-stu-id="613c6-175">How to: Add Trace Statements to Application Code</span></span>](how-to-add-trace-statements-to-application-code.md)
- [<span data-ttu-id="613c6-176">Visual Studio 명령줄에 필요한 환경 변수를 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="613c6-176">How to set environment variables for the Visual Studio Command Line</span></span>](../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="613c6-177">방법: 명령줄 컴파일러 호출</span><span class="sxs-lookup"><span data-stu-id="613c6-177">How to: Invoke the Command-Line Compiler</span></span>](../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)
