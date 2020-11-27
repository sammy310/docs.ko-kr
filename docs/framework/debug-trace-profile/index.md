---
title: 디버깅, 추적 및 프로파일링
description: .NET의 디버깅, 추적 및 프로 파일링에 대해 읽어 보십시오. JIT (just-in-time) 디버깅, 응용 프로그램 추적 및 계측 등을 다루는 문서를 참조 하세요.
ms.date: 03/30/2017
helpviewer_keywords:
- debugging [.NET Framework]
- .NET Framework application configuration, debugging
- debugging [.NET Framework], .NET Framework application debugging
- troubleshooting applications [.NET Framework], profiling
- application development [.NET Framework], debugging
- .NET Framework application configuration, profiling
- profiling applications
- troubleshooting applications [.NET Framework], debugging
- troubleshooting applications [.NET Framework]
- application development [.NET Framework], profiling
ms.assetid: 4a04863e-2475-46f4-bc3f-3c11510c2a4b
ms.openlocfilehash: 33dd840f4c1421bbff54499af56ab3e147cc694b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272776"
---
# <a name="debugging-tracing-and-profiling"></a><span data-ttu-id="a74c9-104">디버깅, 추적 및 프로파일링</span><span class="sxs-lookup"><span data-stu-id="a74c9-104">Debugging, Tracing, and Profiling</span></span>

<span data-ttu-id="a74c9-105">.NET Framework 애플리케이션을 디버그하려면 디버거가 애플리케이션에 연결하고 가능한 경우 애플리케이션 및 해당 MSIL(Microsoft intermediate language)에 대한 기호 및 라인 맵을 둘 다 생성할 수 있도록 컴파일러 및 런타임 환경을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a74c9-105">To debug a .NET Framework application, the compiler and runtime environment must be configured to enable a debugger to attach to the application and to produce both symbols and line maps, if possible, for the application and its corresponding Microsoft intermediate language (MSIL).</span></span> <span data-ttu-id="a74c9-106">관리되는 애플리케이션이 디버그된 후 성능을 향상시키기 위해 프로파일링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a74c9-106">After a managed application has been debugged, it can be profiled to boost performance.</span></span> <span data-ttu-id="a74c9-107">프로파일링은 가장 자주 실행된 코드를 생성하는 소스 코드 줄과 실행하는 데 소요된 시간을 평가 및 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a74c9-107">Profiling evaluates and describes the lines of source code that generate the most frequently executed code, and how much time it takes to execute them.</span></span>  
  
 <span data-ttu-id="a74c9-108">.NET framework 애플리케이션은 다양한 구성 세부 정보를 처리하는 Visual Studio를 사용하여 쉽게 디버그됩니다.</span><span class="sxs-lookup"><span data-stu-id="a74c9-108">.NET Framework applications are easily debugged by using Visual Studio, which handles many of the configuration details.</span></span> <span data-ttu-id="a74c9-109">Visual Studio가 설치되어 있지 않으면 .NET Framework <xref:System.Diagnostics> 네임스페이스의 디버깅 클래스를 사용하여 .NET Framework 애플리케이션의 성능을 검사 및 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a74c9-109">If Visual Studio is not installed, you can examine and improve the performance of .NET Framework applications by using the debugging classes in the .NET Framework <xref:System.Diagnostics> namespace.</span></span> <span data-ttu-id="a74c9-110">이 네임스페이스에는 실행 흐름 추적을 위한 <xref:System.Diagnostics.Trace>, <xref:System.Diagnostics.Debug> 및 <xref:System.Diagnostics.TraceSource> 클래스 및 코드 프로파일링을 위한 <xref:System.Diagnostics.Process>, <xref:System.Diagnostics.EventLog> 및 <xref:System.Diagnostics.PerformanceCounter> 클래스가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a74c9-110">This namespace includes the <xref:System.Diagnostics.Trace>, <xref:System.Diagnostics.Debug>, and <xref:System.Diagnostics.TraceSource> classes for tracing execution flow, and the <xref:System.Diagnostics.Process>, <xref:System.Diagnostics.EventLog>, and <xref:System.Diagnostics.PerformanceCounter> classes for profiling code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a74c9-111">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="a74c9-111">In This Section</span></span>  

 [<span data-ttu-id="a74c9-112">JIT 연결 디버깅 설정</span><span class="sxs-lookup"><span data-stu-id="a74c9-112">Enabling JIT-Attach Debugging</span></span>](enabling-jit-attach-debugging.md)  
 <span data-ttu-id="a74c9-113">.NET Framework 애플리케이션에 디버그 엔진을 JIT 연결하도록 레지스트리를 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a74c9-113">Shows how to configure the registry to JIT-attach a debug engine to a .NET Framework application.</span></span>  
  
 [<span data-ttu-id="a74c9-114">쉽게 디버깅할 수 있도록 이미지 만들기</span><span class="sxs-lookup"><span data-stu-id="a74c9-114">Making an Image Easier to Debug</span></span>](making-an-image-easier-to-debug.md)  
 <span data-ttu-id="a74c9-115">어셈블리를 디버그하기 쉽도록 JIT 추적을 설정하고 최적화를 해제하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a74c9-115">Shows how to turn JIT tracking on and optimization off to make an assembly easier to debug.</span></span>  
  
 [<span data-ttu-id="a74c9-116">애플리케이션 추적 및 조율</span><span class="sxs-lookup"><span data-stu-id="a74c9-116">Tracing and Instrumenting Applications</span></span>](tracing-and-instrumenting-applications.md)  
 <span data-ttu-id="a74c9-117">실행되는 동안 애플리케이션 실행을 모니터링하는 방법 및 성능이나 오류가 발생했는지 여부를 표시하도록 계측하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a74c9-117">Describes how to monitor the execution of your application while it is running, and how to instrument it to display how well it is performing or whether something has gone wrong.</span></span>  
  
 [<span data-ttu-id="a74c9-118">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="a74c9-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)  
 <span data-ttu-id="a74c9-119">런타임 상태에 대한 정보를 제공하기 위해 CLR(공용 언어 런타임)과 함께 작동하는 디버깅 도우미인 MDA(관리 디버깅 도우미)를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a74c9-119">Describes managed debugging assistants (MDAs), which are debugging aids that work in conjunction with the common language runtime (CLR) to provide information on runtime state.</span></span>  
  
 [<span data-ttu-id="a74c9-120">디버거 표시 특성을 사용하여 디버깅 향상</span><span class="sxs-lookup"><span data-stu-id="a74c9-120">Enhancing Debugging with the Debugger Display Attributes</span></span>](enhancing-debugging-with-the-debugger-display-attributes.md)  
 <span data-ttu-id="a74c9-121">형식 개발자가 디버거에 표시될 때 형식의 모양을 지정할 수 있는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a74c9-121">Describes how the developer of a type can specify what that type will look like when it is displayed in a debugger.</span></span>  
  
 [<span data-ttu-id="a74c9-122">성능 카운터</span><span class="sxs-lookup"><span data-stu-id="a74c9-122">Performance Counters</span></span>](performance-counters.md)  
 <span data-ttu-id="a74c9-123">애플리케이션의 성능을 추적하는 데 사용할 수 있는 카운터를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a74c9-123">Describes the counters that you can use to track the performance of an application.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a74c9-124">관련 단원</span><span class="sxs-lookup"><span data-stu-id="a74c9-124">Related Sections</span></span>  

 [<span data-ttu-id="a74c9-125">Visual Studio에서 ASP.NET 또는 ASP.NET Core 앱 디버그</span><span class="sxs-lookup"><span data-stu-id="a74c9-125">Debug ASP.NET or ASP.NET Core apps in Visual Studio</span></span>](/visualstudio/debugger/how-to-enable-debugging-for-aspnet-applications)  
 <span data-ttu-id="a74c9-126">개발 중이나 개발 후에 ASP.NET 애플리케이션을 디버그하는 방법에 대한 지침과 필수 전제 조건을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a74c9-126">Provides prerequisites and instructions for how to debug an ASP.NET application during development or after deployment.</span></span>  
  
 [<span data-ttu-id="a74c9-127">개발 가이드</span><span class="sxs-lookup"><span data-stu-id="a74c9-127">Development Guide</span></span>](../development-guide.md)  
 <span data-ttu-id="a74c9-128">만들기, 구성, 디버깅, 보안, 애플리케이션 배포, 동적 프로그래밍에 대한 정보, 상호 운용성, 확장성, 메모리 관리 및 스레딩을 포함하여 애플리케이션 개발에 대한 모든 주요 기술 분야 및 작업에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a74c9-128">Provides a guide to all key technology areas and tasks for application development, including creating, configuring, debugging, securing, and deploying your application, and information about dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>
