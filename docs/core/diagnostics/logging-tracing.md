---
title: 로깅 및 추적 - .NET Core
description: .NET Core 로깅 및 추적에 대해 간략히 설명합니다.
ms.date: 08/05/2019
ms.openlocfilehash: 392b88c9ea3c31c919a605ac0a5c886f7d63f79a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75714419"
---
# <a name="net-core-logging-and-tracing"></a><span data-ttu-id="f36b6-103">.NET Core 로깅 및 추적</span><span class="sxs-lookup"><span data-stu-id="f36b6-103">.NET Core logging and tracing</span></span>

<span data-ttu-id="f36b6-104">로깅과 추적은 실제로 동일한 기술에 대한 두 가지 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-104">Logging and tracing are really two names for the same technique.</span></span> <span data-ttu-id="f36b6-105">간단한 기술은 컴퓨터 초기부터 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-105">The simple technique has been used since the early days of computers.</span></span> <span data-ttu-id="f36b6-106">단지 나중에 사용할 쓰기 출력을 작성하기 위해 애플리케이션을 계측하는 것과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-106">It simply involves instrumenting an application to write output to be consumed later.</span></span>

## <a name="reasons-to-use-logging-and-tracing"></a><span data-ttu-id="f36b6-107">로깅 및 추적을 사용하는 이유</span><span class="sxs-lookup"><span data-stu-id="f36b6-107">Reasons to use logging and tracing</span></span>

<span data-ttu-id="f36b6-108">이 간단한 기술은 놀라울 정도로 강력합니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-108">This simple technique is surprisingly powerful.</span></span> <span data-ttu-id="f36b6-109">디버거가 실패하는 경우 다음과 같이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-109">It can be used in situations where a debugger fails:</span></span>

- <span data-ttu-id="f36b6-110">오랜 기간 동안 발생하는 문제는 기존 디버거로 디버그하기가 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-110">Issues occurring over long periods of time, can be difficult to debug with a traditional debugger.</span></span> <span data-ttu-id="f36b6-111">로그를 사용하면 오랜 기간에 걸친 사후 검토를 자세히 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-111">Logs allow for detailed post-mortem review spanning long periods of time.</span></span> <span data-ttu-id="f36b6-112">이와 대조적으로 디버거는 실시간 분석으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-112">In contrast, debuggers are constrained to real-time analysis.</span></span>
- <span data-ttu-id="f36b6-113">다중 스레드 애플리케이션과 분산 애플리케이션은 디버그하기 어려운 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-113">Multi-threaded applications and distributed applications are often difficult to debug.</span></span>  <span data-ttu-id="f36b6-114">디버거를 연결하면 동작이 수정되는 경향이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-114">Attaching a debugger tends to modify behaviors.</span></span> <span data-ttu-id="f36b6-115">복잡한 시스템을 이해하기 위해 필요에 따라 자세한 로그를 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-115">Detailed logs can be analyzed as needed to understand complex systems.</span></span>
- <span data-ttu-id="f36b6-116">분산 애플리케이션의 문제는 여러 구성 요소 간의 복잡한 상호 작용으로 인해 발생할 수 있으며, 디버거를 시스템의 모든 부분에 연결하는 것이 적절하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-116">Issues in distributed applications may arise from a complex interaction between many components and it may not be reasonable to connect a debugger to every part of the system.</span></span>
- <span data-ttu-id="f36b6-117">많은 서비스가 중단되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-117">Many services shouldn't be stalled.</span></span> <span data-ttu-id="f36b6-118">디버거를 연결하면 시간 제한 오류가 발생하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-118">Attaching a debugger often causes timeout failures.</span></span>
- <span data-ttu-id="f36b6-119">문제는 항상 예측되는 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-119">Issues aren't always foreseen.</span></span> <span data-ttu-id="f36b6-120">로깅 및 추적은 문제가 발생하는 경우 프로그램에서 항상 기록할 수 있도록 낮은 오버헤드로 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-120">Logging and tracing are designed for low overhead so that programs can always be recording in case an issue occurs.</span></span>

## <a name="net-core-apis"></a><span data-ttu-id="f36b6-121">.NET Core API</span><span class="sxs-lookup"><span data-stu-id="f36b6-121">.NET Core APIs</span></span>

### <a name="print-style-apis"></a><span data-ttu-id="f36b6-122">인쇄 스타일 API</span><span class="sxs-lookup"><span data-stu-id="f36b6-122">Print style APIs</span></span>

<span data-ttu-id="f36b6-123"><xref:System.Console?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace?displayProperty=nameWithType> 및 <xref:System.Diagnostics.Debug?displayProperty=nameWithType> 클래스는 각각 로깅에 편리한 비슷한 인쇄 스타일 API를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-123">The <xref:System.Console?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace?displayProperty=nameWithType>, and <xref:System.Diagnostics.Debug?displayProperty=nameWithType> classes each provide similar print style APIs convenient for logging.</span></span>

<span data-ttu-id="f36b6-124">사용할 인쇄 스타일 API를 선택하는 것은 사용자에게 달려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-124">The choice of which print style API to use is up to you.</span></span> <span data-ttu-id="f36b6-125">주요 차이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-125">The key differences are:</span></span>

- <xref:System.Console?displayProperty=nameWithType>
  - <span data-ttu-id="f36b6-126">항상 사용하도록 설정되어 있으며 항상 콘솔에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-126">Always enabled and always writes to the console.</span></span>
  - <span data-ttu-id="f36b6-127">고객이 릴리스에서 확인해야 하는 정보에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-127">Useful for information that your customer may need to see in the release.</span></span>
  - <span data-ttu-id="f36b6-128">가장 간단한 방법이므로 임시 디버깅에 자주 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-128">Because it's the simplest approach, it's often used for ad-hoc temporary debugging.</span></span> <span data-ttu-id="f36b6-129">이 디버그 코드는 소스 제어에 체크인되지 않는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-129">This debug code is often never checked in to source control.</span></span>
- <xref:System.Diagnostics.Trace?displayProperty=nameWithType>
  - <span data-ttu-id="f36b6-130">`TRACE`가 정의된 경우에만 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-130">Only enabled when `TRACE` is defined.</span></span>
  - <span data-ttu-id="f36b6-131">연결된 <xref:System.Diagnostics.Trace.Listeners>(기본적으로 <xref:System.Diagnostics.DefaultTraceListener>)에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-131">Writes to attached <xref:System.Diagnostics.Trace.Listeners>, by default the <xref:System.Diagnostics.DefaultTraceListener>.</span></span>
  - <span data-ttu-id="f36b6-132">대부분의 빌드에서 사용하도록 설정될 로그를 만드는 경우 이 API를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-132">Use this API when creating logs that will be enabled in most builds.</span></span>
- <xref:System.Diagnostics.Debug?displayProperty=nameWithType>
  - <span data-ttu-id="f36b6-133">`DEBUG`가 정의된 경우에만 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-133">Only enabled when `DEBUG` is defined.</span></span>
  - <span data-ttu-id="f36b6-134">연결된 디버거에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-134">Writes to an attached debugger.</span></span>
  - <span data-ttu-id="f36b6-135">`COMPlus_DebugWriteToStdErr`가 설정된 경우 `*nix`에서 stderr에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-135">On `*nix` writes to stderr if `COMPlus_DebugWriteToStdErr` is set.</span></span>
  - <span data-ttu-id="f36b6-136">디버그 빌드에서만 사용하도록 설정될 로그를 만드는 경우 이 API를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-136">Use this API when creating logs that will be enabled only in debug builds.</span></span>

### <a name="logging-events"></a><span data-ttu-id="f36b6-137">이벤트 로깅</span><span class="sxs-lookup"><span data-stu-id="f36b6-137">Logging events</span></span>

<span data-ttu-id="f36b6-138">다음 API는 더 이벤트 지향적입니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-138">The following APIs are more event oriented.</span></span> <span data-ttu-id="f36b6-139">단순 문자열을 기록하는 대신 이벤트 개체를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-139">Rather than logging simple strings they log event objects.</span></span>

- <xref:System.Diagnostics.Tracing.EventSource?displayProperty=nameWithType>
  - <span data-ttu-id="f36b6-140">EventSource는 기본 루트 .NET Core 추적 API입니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-140">EventSource is the primary root .NET Core tracing API.</span></span>
  - <span data-ttu-id="f36b6-141">모든 .NET Standard 버전에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-141">Available in all .NET Standard versions.</span></span>
  - <span data-ttu-id="f36b6-142">직렬화할 수 있는 개체만 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-142">Only allows tracing serializable objects.</span></span>
  - <span data-ttu-id="f36b6-143">연결된 [이벤트 수신기](xref:System.Diagnostics.Tracing.EventListener)에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-143">Writes to the attached [event listeners](xref:System.Diagnostics.Tracing.EventListener).</span></span>
  - <span data-ttu-id="f36b6-144">.NET Core에서 제공하는 수신기는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-144">.NET Core provides listeners for:</span></span>
    - <span data-ttu-id="f36b6-145">모든 플랫폼에서 .NET Core의 EventPipe</span><span class="sxs-lookup"><span data-stu-id="f36b6-145">.NET Core's EventPipe on all platforms</span></span>
    - [<span data-ttu-id="f36b6-146">ETW(Windows용 이벤트 추적)</span><span class="sxs-lookup"><span data-stu-id="f36b6-146">Event Tracing for Windows (ETW)</span></span>](/windows/win32/etw/event-tracing-portal)
    - [<span data-ttu-id="f36b6-147">Linux용 LTTng 추적 프레임워크</span><span class="sxs-lookup"><span data-stu-id="f36b6-147">LTTng tracing framework for Linux</span></span>](https://lttng.org/)

- <xref:System.Diagnostics.DiagnosticSource?displayProperty=nameWithType>
  - <span data-ttu-id="f36b6-148">.NET Core 및 .NET Framework용 [NuGet 패키지](https://www.nuget.org/packages/System.Diagnostics.DiagnosticSource)에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-148">Included in .NET Core and as a [NuGet package](https://www.nuget.org/packages/System.Diagnostics.DiagnosticSource) for .NET Framework.</span></span>
  - <span data-ttu-id="f36b6-149">프로세스 내에서 직렬화할 수 없는 개체를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-149">Allows in-process tracing of non-serializable objects.</span></span>
  - <span data-ttu-id="f36b6-150">로깅된 개체의 선택한 필드를 <xref:System.Diagnostics.Tracing.EventSource>에 쓸 수 있게 하는 브리지가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-150">Includes a bridge to allow selected fields of logged objects to be written to an <xref:System.Diagnostics.Tracing.EventSource>.</span></span>

- <xref:System.Diagnostics.Activity?displayProperty=nameWithType>
  - <span data-ttu-id="f36b6-151">특정 활동 또는 트랜잭션으로 인해 발생하는 로그 메시지를 식별할 수 있는 명확한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-151">Provides a definitive way to identify log messages resulting from a specific activity or transaction.</span></span> <span data-ttu-id="f36b6-152">이 개체를 사용하여 여러 서비스에서 로그를 상호 연결시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-152">This object can be used to correlate logs across different services.</span></span>

- <xref:System.Diagnostics.EventLog?displayProperty=nameWithType>
  - <span data-ttu-id="f36b6-153">Windows만 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-153">Windows only.</span></span>
  - <span data-ttu-id="f36b6-154">메시지를 Windows 이벤트 로그에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-154">Writes messages to the Windows Event Log.</span></span>
  - <span data-ttu-id="f36b6-155">시스템 관리자는 Windows 이벤트 로그에 심각한 애플리케이션 오류 메시지가 표시될 것으로 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-155">System administrators expect fatal application error messages to appear in the Windows Event Log.</span></span>

## <a name="ilogger-and-logging-frameworks"></a><span data-ttu-id="f36b6-156">ILogger 및 로깅 프레임워크</span><span class="sxs-lookup"><span data-stu-id="f36b6-156">ILogger and logging frameworks</span></span>

<span data-ttu-id="f36b6-157">하위 수준 API는 로깅 요구 사항에 적합하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-157">The low-level APIs may not be the right choice for your logging needs.</span></span> <span data-ttu-id="f36b6-158">로깅 프레임워크를 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-158">You may want to consider a logging framework.</span></span>

<span data-ttu-id="f36b6-159"><xref:Microsoft.Extensions.Logging.ILogger> 인터페이스는 종속성 주입을 통해 로거를 삽입할 수 있는 공용 로깅 인터페이스를 만드는 데 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-159">The <xref:Microsoft.Extensions.Logging.ILogger> interface has been used to create a common logging interface where the loggers can be inserted through dependency injection.</span></span>

<span data-ttu-id="f36b6-160">예를 들어 애플리케이션에 가장 적합한 것을 선택할 수 있도록 `ASP.NET`에서 기본 제공 및 타사 프레임워크를 선택할 수 있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-160">For instance, to allow you to make the best choice for your application `ASP.NET` offers support for a selection of built-in and third-party frameworks:</span></span>

- [<span data-ttu-id="f36b6-161">ASP.NET 기본 제공 로깅 공급자</span><span class="sxs-lookup"><span data-stu-id="f36b6-161">ASP.NET built in logging providers</span></span>](/aspnet/core/fundamentals/logging/#built-in-logging-providers)
- [<span data-ttu-id="f36b6-162">ASP.NET 타사 로깅 공급자</span><span class="sxs-lookup"><span data-stu-id="f36b6-162">ASP.NET Third-party logging providers</span></span>](/aspnet/core/fundamentals/logging/#third-party-logging-providers)

## <a name="logging-related-references"></a><span data-ttu-id="f36b6-163">로깅 관련 참고 자료</span><span class="sxs-lookup"><span data-stu-id="f36b6-163">Logging related references</span></span>

- [<span data-ttu-id="f36b6-164">방법: 추적 및 디버그를 사용한 조건부 컴파일</span><span class="sxs-lookup"><span data-stu-id="f36b6-164">How to: Compile Conditionally with Trace and Debug</span></span>](../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)

- [<span data-ttu-id="f36b6-165">방법: 애플리케이션 코드에 Trace 문 추가</span><span class="sxs-lookup"><span data-stu-id="f36b6-165">How to: Add Trace Statements to Application Code</span></span>](../../framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md)

- <span data-ttu-id="f36b6-166">[ASP.NET 로깅](/aspnet/core/fundamentals/logging)은 지원하는 로깅 기술에 대해 간략히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-166">[ASP.NET Logging](/aspnet/core/fundamentals/logging) provides an overview of the logging techniques it supports.</span></span>

- <span data-ttu-id="f36b6-167">[C# 문자열 보간](../../csharp/language-reference/tokens/interpolated.md)은 로깅 코드 작성을 간소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-167">[C# String Interpolation](../../csharp/language-reference/tokens/interpolated.md) can simplify writing logging code.</span></span>

- <span data-ttu-id="f36b6-168"><xref:System.Exception.Message?displayProperty=nameWithType> 속성은 예외를 기록하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-168">The <xref:System.Exception.Message?displayProperty=nameWithType> property is useful for logging exceptions.</span></span>

- <span data-ttu-id="f36b6-169"><xref:System.Diagnostics.StackTrace?displayProperty=nameWithType> 클래스는 로그에 스택 정보를 제공하는 데 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-169">The <xref:System.Diagnostics.StackTrace?displayProperty=nameWithType> class can be useful to provide stack info in your logs.</span></span>

## <a name="performance-considerations"></a><span data-ttu-id="f36b6-170">성능 고려 사항</span><span class="sxs-lookup"><span data-stu-id="f36b6-170">Performance considerations</span></span>

<span data-ttu-id="f36b6-171">문자열 형식을 지정하면 CPU 처리 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-171">String formatting can take noticeable CPU processing time.</span></span>

<span data-ttu-id="f36b6-172">성능이 중요한 애플리케이션에 추천되는 고려 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-172">In performance critical applications, it's recommended that you:</span></span>

- <span data-ttu-id="f36b6-173">수신 대기하지 않을 때는 로깅을 많이 수행하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-173">Avoid lots of logging when no one is listening.</span></span> <span data-ttu-id="f36b6-174">로깅을 먼저 사용하도록 설정되어 있는지 확인하여 비용이 많이 드는 로깅 메시지를 생성하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-174">Avoid constructing costly logging messages by checking if logging is enabled first.</span></span>
- <span data-ttu-id="f36b6-175">유용한 것만 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-175">Only log what's useful.</span></span>
- <span data-ttu-id="f36b6-176">고급 서식 지정을 분석 단계까지 연기합니다.</span><span class="sxs-lookup"><span data-stu-id="f36b6-176">Defer fancy formatting to the analysis stage.</span></span>
