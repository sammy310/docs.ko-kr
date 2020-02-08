---
title: .NET 용어
description: .NET 설명서에서 사용되는 선택한 용어의 의미를 알아봅니다.
ms.date: 01/22/2019
ms.technology: dotnet-standard
ms.openlocfilehash: 822d6c9513d49dcc6bc57421003441d9bcc7c281
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2020
ms.locfileid: "76921119"
---
# <a name="net-glossary"></a><span data-ttu-id="0eb4c-103">.NET 용어</span><span class="sxs-lookup"><span data-stu-id="0eb4c-103">.NET Glossary</span></span>

<span data-ttu-id="0eb4c-104">이 용어집의 주 용도는 .NET 설명서에서 정의 없이 자주 나타나는 선택한 용어 및 머리글자어의 의미를 명확히 나타내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-104">The primary goal of this glossary is to clarify meanings of selected terms and acronyms that appear frequently in the .NET documentation without definitions.</span></span>

## <a name="aot"></a><span data-ttu-id="0eb4c-105">AOT</span><span class="sxs-lookup"><span data-stu-id="0eb4c-105">AOT</span></span>

<span data-ttu-id="0eb4c-106">Ahead-Of-Time 컴파일러입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-106">Ahead-of-time compiler.</span></span>

<span data-ttu-id="0eb4c-107">[JIT](#jit)와 비슷하게 이 컴파일러도 [IL](#il)을 기계어 코드로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-107">Similar to [JIT](#jit), this compiler also translates [IL](#il) to machine code.</span></span> <span data-ttu-id="0eb4c-108">JIT 컴파일과는 달리 AOT 컴파일은 애플리케이션이 실행되기 전에 수행되며 일반적으로 다른 컴퓨터에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-108">In contrast to JIT compilation, AOT compilation happens before the application is executed and is usually performed on a different machine.</span></span> <span data-ttu-id="0eb4c-109">AOT 툴 체인은 런타임에 컴파일되지 않으므로 컴파일 시간을 최소화할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-109">Because AOT tool chains don't compile at runtime, they don't have to minimize time spent compiling.</span></span> <span data-ttu-id="0eb4c-110">즉, 더 많은 시간을 최적화하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-110">That means they can spend more time optimizing.</span></span> <span data-ttu-id="0eb4c-111">AOT의 컨텍스트는 전체 애플리케이션이므로 AOT 컴파일러는 모듈 간 연결 및 전체 프로그램 분석도 수행합니다. 즉, 모든 참조가 수행되고 단일 실행 파일이 생성된다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-111">Since the context of AOT is the entire application, the AOT compiler also performs cross-module linking and whole-program analysis, which means that all references are followed and a single executable is produced.</span></span>

<span data-ttu-id="0eb4c-112">[CoreRT](#corert)와 [.NET 네이티브](#net-native)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-112">See [CoreRT](#corert) and [.NET Native](#net-native).</span></span>

## <a name="aspnet"></a><span data-ttu-id="0eb4c-113">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="0eb4c-113">ASP.NET</span></span> 

<span data-ttu-id="0eb4c-114">.NET Framework와 함께 제공되는 원래 ASP.NET 구현체입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-114">The original ASP.NET implementation that ships with the .NET Framework.</span></span>

<span data-ttu-id="0eb4c-115">경우에 따라 ASP.NET은 ASP.NET Core를 포함한 두가지 ASP.NET 구현체를 나타내는 포괄적인 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-115">Sometimes ASP.NET is an umbrella term that refers to both ASP.NET implementations including ASP.NET Core.</span></span> <span data-ttu-id="0eb4c-116">지정된 인스턴스에서 이 용어가 전달하는 의미는 컨텍스트에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-116">The meaning that the term carries in any given instance is determined by context.</span></span> <span data-ttu-id="0eb4c-117">두 구현체을 모두 의미하는 데 ASP.NET을 사용하지 않는 것을 분명히 하려는 경우 ASP.NET 4.x를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-117">Refer to ASP.NET 4.x when you want to make it clear that you’re not using ASP.NET to mean both implementations.</span></span> 

<span data-ttu-id="0eb4c-118">[ASP.NET 설명서](/aspnet/#pivot=aspnet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-118">See [ASP.NET documentation](/aspnet/#pivot=aspnet).</span></span>

## <a name="aspnet-core"></a><span data-ttu-id="0eb4c-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0eb4c-119">ASP.NET Core</span></span>

<span data-ttu-id="0eb4c-120">다양한 플랫폼에서 사용할 수 있는 고성능의, .NET Core를 기반으로 하는 ASP.NET의 오픈 소스 구현체입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-120">A cross-platform, high-performance, open source implementation of ASP.NET built on .NET Core.</span></span>

<span data-ttu-id="0eb4c-121">[ASP.NET Core 설명서](/aspnet/#pivot=core)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-121">See [ASP.NET Core documentation](/aspnet/#pivot=core).</span></span>

## <a name="assembly"></a><span data-ttu-id="0eb4c-122">어셈블리</span><span class="sxs-lookup"><span data-stu-id="0eb4c-122">assembly</span></span>

<span data-ttu-id="0eb4c-123">애플리케이션이나 다른 어셈블리에서 호출할 수 있는 API 컬렉션을 포함할 수 있는 *.dll*/ *.exe* 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-123">A *.dll*/*.exe* file that can contain a collection of APIs that can be called by applications or other assemblies.</span></span>

<span data-ttu-id="0eb4c-124">어셈블리에는 인터페이스와 클래스, 구조체, 열거형, 대리자와 같은 형식이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-124">An assembly may include types such as interfaces, classes, structures, enumerations, and delegates.</span></span> <span data-ttu-id="0eb4c-125">프로젝트의 *bin* 폴더에 있는 어셈블리를 *바이너리*라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-125">Assemblies in a project's *bin* folder are sometimes referred to as *binaries*.</span></span> <span data-ttu-id="0eb4c-126">[라이브러리](#library)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-126">See also [library](#library).</span></span>

## <a name="clr"></a><span data-ttu-id="0eb4c-127">CLR</span><span class="sxs-lookup"><span data-stu-id="0eb4c-127">CLR</span></span>

<span data-ttu-id="0eb4c-128">공용 언어 런타임입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-128">Common Language Runtime.</span></span>

<span data-ttu-id="0eb4c-129">정확한 의미는 컨텍스트에 따라 달라지지만 일반적으로 .NET Framework의 런타임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-129">The exact meaning depends on the context, but this usually refers to the runtime of the .NET Framework.</span></span> <span data-ttu-id="0eb4c-130">CLR은 메모리 할당 및 관리를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-130">The CLR handles memory allocation and management.</span></span> <span data-ttu-id="0eb4c-131">또한 CLR은 앱을 실행할 뿐만 아니라 [JIT](#jit) 컴파일러를 사용하여 즉시 코드를 생성하고 컴파일하는 가상 머신입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-131">The CLR is also a virtual machine that not only executes apps but also generates and compiles code on-the-fly using a [JIT](#jit) compiler.</span></span> <span data-ttu-id="0eb4c-132">현재 Microsoft CLR 구현체는 Windows 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-132">The current Microsoft CLR implementation is Windows only.</span></span>

## <a name="coreclr"></a><span data-ttu-id="0eb4c-133">CoreCLR</span><span class="sxs-lookup"><span data-stu-id="0eb4c-133">CoreCLR</span></span>

<span data-ttu-id="0eb4c-134">.NET Core 공용 언어 런타임입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-134">.NET Core Common Language Runtime.</span></span>

<span data-ttu-id="0eb4c-135">이 CLR은 CLR과 동일한 코드베이스에서 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-135">This CLR is built from the same code base as the CLR.</span></span> <span data-ttu-id="0eb4c-136">원래 CoreCLR은 Silverlight의 런타임이었으며 여러 플랫폼, 특히 Windows 및 OS X에서 실행되도록 설계되었습니다. 이제 CoreCLR은 .NET Core의 일부이며 CLR의 단순화된 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-136">Originally, CoreCLR was the runtime of Silverlight and was designed to run on multiple platforms, specifically Windows and OS X. CoreCLR is now part of .NET Core and represents a simplified version of the CLR.</span></span> <span data-ttu-id="0eb4c-137">이제 많은 Linux 배포에 대한 지원을 포함하는 [플랫폼 간](#cross-platform) 런타임이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-137">It's still a [cross-platform](#cross-platform) runtime, now including support for many Linux distributions.</span></span> <span data-ttu-id="0eb4c-138">CoreCLR은 JIT 및 코드 실행 기능이 있는 가상 머신이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-138">CoreCLR is also a virtual machine with JIT and code execution capabilities.</span></span>

## <a name="corefx"></a><span data-ttu-id="0eb4c-139">CoreFX</span><span class="sxs-lookup"><span data-stu-id="0eb4c-139">CoreFX</span></span>

<span data-ttu-id="0eb4c-140">.NET Core BCL(기본 클래스 라이브러리)</span><span class="sxs-lookup"><span data-stu-id="0eb4c-140">.NET Core Base Class Library (BCL)</span></span>

<span data-ttu-id="0eb4c-141">System.\*(및 제한된 범위의 Microsoft.\*) 네임스페이스를 구성하는 라이브러리 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-141">A set of libraries that comprise the System.\* (and to a limited extent Microsoft.\*) namespaces.</span></span> <span data-ttu-id="0eb4c-142">BCL은 ASP.NET Core 같은 상위 수준 애플리케이션 프레임워크의 기반이 되는 하위 수준의 범용 프레임워크입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-142">The BCL is a general purpose, lower-level framework that higher-level application frameworks, such as ASP.NET Core, build on.</span></span> <span data-ttu-id="0eb4c-143">.NET Core BCL의 소스 코드는 [.NET Core 런타임 리포지토리](https://github.com/dotnet/runtime)에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-143">The source code of the .NET Core BCL is contained in the [.NET Core runtime repository](https://github.com/dotnet/runtime).</span></span> <span data-ttu-id="0eb4c-144">그러나 대부분의 .NET Core API는 .NET Framework에서 사용할 수도 있으므로 CoreFX를 .NET Framework BCL의 포크로 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-144">However, the majority of the .NET Core APIs are also available in the .NET Framework, so you can think of CoreFX as a fork of the .NET Framework BCL.</span></span>

## <a name="corert"></a><span data-ttu-id="0eb4c-145">CoreRT</span><span class="sxs-lookup"><span data-stu-id="0eb4c-145">CoreRT</span></span>

<span data-ttu-id="0eb4c-146">.NET Core 런타임입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-146">.NET Core runtime.</span></span>

<span data-ttu-id="0eb4c-147">CLR/CoreCLR과 달리 CoreRT는 가상 머신이 아닙니다. 즉, [JIT](#jit)를 포함하지 않으므로 즉시 코드를 생성하고 실행하는 기능을 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-147">In contrast to the CLR/CoreCLR, CoreRT is not a virtual machine, which means it doesn't include the facilities to generate and run code on-the-fly because it doesn't include a [JIT](#jit).</span></span> <span data-ttu-id="0eb4c-148">그러나 [GC](#gc)와 RTTI(런타임 형식 식별) 및 리플렉션에 대한 기능은 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-148">It does, however, include the [GC](#gc) and the ability for runtime type identification (RTTI) and reflection.</span></span> <span data-ttu-id="0eb4c-149">그러나 해당 형식 시스템은 리플렉션에 대한 메타데이터가 필요하지 않도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-149">However, its type system is designed so that metadata for reflection isn't required.</span></span> <span data-ttu-id="0eb4c-150">따라서 불필요한 메타데이터를 분리하고 더 중요하게는 앱이 사용하지 않는 코드를 식별할 수 있는 [AOT](#aot) 도구 체인을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-150">This enables having an [AOT](#aot) tool chain that can link away superfluous metadata and (more importantly) identify code that the app doesn't use.</span></span> <span data-ttu-id="0eb4c-151">CoreRT는 개발 중입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-151">CoreRT is in development.</span></span>

<span data-ttu-id="0eb4c-152">[.NET 네이티브와 CoreRT 소개](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-152">See [Intro to .NET Native and CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md).</span></span>

## <a name="cross-platform"></a><span data-ttu-id="0eb4c-153">크로스 플랫폼</span><span class="sxs-lookup"><span data-stu-id="0eb4c-153">cross-platform</span></span>

<span data-ttu-id="0eb4c-154">각 운영 체제에 맞게 다시 작성할 필요 없이 Linux와 Windows, iOS와 같은 다양한 운영 체제에서 사용할 수 있는 애플리케이션을 개발하고 실행하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-154">The ability to develop and execute an application that can be used on multiple different operating systems, such as Linux, Windows and iOS, without having to re-write specifically for each one.</span></span> <span data-ttu-id="0eb4c-155">이를 통해 다양한 플랫폼에서 애플리케이션 간에 코드를 다시 사용하고 일관성을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-155">This enables code re-use and consistency between applications on different platforms.</span></span>

## <a name="ecosystem"></a><span data-ttu-id="0eb4c-156">에코시스템</span><span class="sxs-lookup"><span data-stu-id="0eb4c-156">ecosystem</span></span>

<span data-ttu-id="0eb4c-157">특정 기술에 대한 애플리케이션을 빌드하고 실행하는 데 사용되는 모든 런타임 소프트웨어, 개발 도구 및 커뮤니티 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-157">All of the runtime software, development tools, and community resources that are used to build and run applications for a given technology.</span></span>

<span data-ttu-id="0eb4c-158">“.NET 에코시스템”이라는 용어는 타사 앱 및 라이브러리를 포함한다는 점에서 “.NET 스택”과 같은 유사한 용어와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-158">The term ".NET ecosystem" differs from similar terms such as ".NET stack" in its inclusion of third-party apps and libraries.</span></span> <span data-ttu-id="0eb4c-159">다음은 문장에서의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-159">Here's an example in a sentence:</span></span>

- <span data-ttu-id="0eb4c-160">“[.NET Standard](#net-standard)는 .NET 에코시스템의 통일성을 높이기 위한 것입니다.”</span><span class="sxs-lookup"><span data-stu-id="0eb4c-160">"The motivation behind the [.NET Standard](#net-standard) is to establish greater uniformity in the .NET ecosystem."</span></span> 

## <a name="framework"></a><span data-ttu-id="0eb4c-161">프레임워크</span><span class="sxs-lookup"><span data-stu-id="0eb4c-161">framework</span></span>

<span data-ttu-id="0eb4c-162">일반적으로 특정 기술을 기반으로 하는 애플리케이션의 개발 및 배포를 용이하게 하는 포괄적인 API 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-162">In general, a comprehensive collection of APIs that facilitates development and deployment of applications that are based on a particular technology.</span></span> <span data-ttu-id="0eb4c-163">이 일반적인 의미에서 ASP.NET Core 및 Windows Forms는 애플리케이션 프레임워크의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-163">In this general sense, ASP.NET Core and Windows Forms are examples of application frameworks.</span></span> <span data-ttu-id="0eb4c-164">[라이브러리](#library)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-164">See also [library](#library).</span></span>

<span data-ttu-id="0eb4c-165">“프레임 워크”라는 단어는 다음과 같은 용어에서 좀 더 구체적인 기술적 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-165">The word "framework" has a more specific technical meaning in the following terms:</span></span>

- [<span data-ttu-id="0eb4c-166">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="0eb4c-166">.NET Framework</span></span>](#net-framework)
- [<span data-ttu-id="0eb4c-167">대상 프레임워크</span><span class="sxs-lookup"><span data-stu-id="0eb4c-167">target framework</span></span>](#target-framework)
- [<span data-ttu-id="0eb4c-168">TFM(대상 프레임워크 모니커)</span><span class="sxs-lookup"><span data-stu-id="0eb4c-168">TFM (target framework moniker)</span></span>](#tfm)

<span data-ttu-id="0eb4c-169">기존 설명서에서 “프레임워크”는 경우에 따라 [.NET의 구현체](#implementation-of-net)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-169">In the existing documentation, "framework" sometimes refers to an [implementation of .NET](#implementation-of-net).</span></span> <span data-ttu-id="0eb4c-170">예를 들어 문서에서 .NET Core를 프레임워크라고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-170">For example, an article may call .NET Core a framework.</span></span> <span data-ttu-id="0eb4c-171">설명서에서 혼동을 주는 이러한 사용 예를 제거할 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-171">We plan to eliminate this confusing usage from the documentation.</span></span>

## <a name="gc"></a><span data-ttu-id="0eb4c-172">GC</span><span class="sxs-lookup"><span data-stu-id="0eb4c-172">GC</span></span>

<span data-ttu-id="0eb4c-173">가비지 수집기입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-173">Garbage collector.</span></span>

<span data-ttu-id="0eb4c-174">가비지 수집기는 자동 메모리 관리의 구현체입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-174">The garbage collector is an implementation of automatic memory management.</span></span>  <span data-ttu-id="0eb4c-175">GC는 개체가 사용한 메모리에서 더 이상 사용되지 않는 메모리를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-175">The GC frees memory occupied by objects that are no longer in use.</span></span> 

<span data-ttu-id="0eb4c-176">[가비지 수집](garbage-collection/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-176">See [Garbage Collection](garbage-collection/index.md).</span></span>

## <a name="il"></a><span data-ttu-id="0eb4c-177">IL</span><span class="sxs-lookup"><span data-stu-id="0eb4c-177">IL</span></span>

<span data-ttu-id="0eb4c-178">중간 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-178">Intermediate language.</span></span>

<span data-ttu-id="0eb4c-179">C#과 같은 상위 수준 .NET 언어가 IL(중간 언어)이라는 하드웨어 독립 명령 집합으로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-179">Higher-level .NET languages, such as C#, compile down to a hardware-agnostic instruction set, which is called Intermediate Language (IL).</span></span> <span data-ttu-id="0eb4c-180">IL은 MSIL(Microsoft IL) 또는 CIL(공통 IL)이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-180">IL is sometimes referred to as MSIL (Microsoft IL) or CIL (Common IL).</span></span>

## <a name="jit"></a><span data-ttu-id="0eb4c-181">JIT</span><span class="sxs-lookup"><span data-stu-id="0eb4c-181">JIT</span></span>

<span data-ttu-id="0eb4c-182">Just-In-Time 컴파일러입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-182">Just-in-time compiler.</span></span>

<span data-ttu-id="0eb4c-183">[AOT](#aot)와 유사한 이 컴파일러는 [IL](#il)을 프로세서에서 이해하는 기계어 코드로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-183">Similar to [AOT](#aot), this compiler translates [IL](#il) to machine code that the processor understands.</span></span> <span data-ttu-id="0eb4c-184">AOT와 달리 JIT 컴파일은 요청 시 수행되며 코드가 실행되어야 하는 것과 동일한 컴퓨터에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-184">Unlike AOT, JIT compilation happens on demand and is performed on the same machine that the code needs to run on.</span></span> <span data-ttu-id="0eb4c-185">JIT 컴파일은 애플리케이션이 실행되는 동안 수행되므로 컴파일 시간이 실행 시간의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-185">Since JIT compilation occurs during execution of the application, compile time is part of the run time.</span></span> <span data-ttu-id="0eb4c-186">따라서 JIT 컴파일러는 결과 코드가 생성할 수 있는 시간 단축과 코드 최적화에 소요된 시간의 균형을 맞춰야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-186">Thus, JIT compilers have to balance time spent optimizing code against the savings that the resulting code can produce.</span></span> <span data-ttu-id="0eb4c-187">그러나 JIT는 실제 하드웨어를 인식하므로 개발자가 다른 구현을 제공할 필요가 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-187">But a JIT knows the actual hardware and can free developers from having to ship different implementations.</span></span>

## <a name="implementation-of-net"></a><span data-ttu-id="0eb4c-188">.NET의 구현체</span><span class="sxs-lookup"><span data-stu-id="0eb4c-188">implementation of .NET</span></span>

<span data-ttu-id="0eb4c-189">.NET의 구현체에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-189">An implementation of .NET includes the following:</span></span>

- <span data-ttu-id="0eb4c-190">하나 이상의 런타임.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-190">One or more runtimes.</span></span> <span data-ttu-id="0eb4c-191">예: CLR, CoreCLR, CoreRT.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-191">Examples: CLR, CoreCLR, CoreRT.</span></span>
- <span data-ttu-id="0eb4c-192">.NET Standard의 버전을 구현하고 추가 API를 포함할 수 있는 클래스 라이브러리.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-192">A class library that implements a version of the .NET Standard and may include additional APIs.</span></span> <span data-ttu-id="0eb4c-193">예: .NET Framework 기본 클래스 라이브러리, .NET Core 기본 클래스 라이브러리.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-193">Examples: .NET Framework Base Class Library, .NET Core Base Class Library.</span></span>
- <span data-ttu-id="0eb4c-194">필요에 따라 하나 이상의 애플리케이션 프레임워크.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-194">Optionally, one or more application frameworks.</span></span> <span data-ttu-id="0eb4c-195">예: ASP.NET과 Windows Forms, WPF가 .NET Framework에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-195">Examples: ASP.NET, Windows Forms, and WPF are included in the .NET Framework.</span></span>
- <span data-ttu-id="0eb4c-196">필요에 따라 개발 도구.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-196">Optionally, development tools.</span></span> <span data-ttu-id="0eb4c-197">일부 개발 도구는 여러 구현체에서 공통적으로 사용할 수 있음.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-197">Some development tools are shared among multiple implementations.</span></span>

<span data-ttu-id="0eb4c-198">.NET 구현체의 예:</span><span class="sxs-lookup"><span data-stu-id="0eb4c-198">Examples of .NET implementations:</span></span>

- [<span data-ttu-id="0eb4c-199">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="0eb4c-199">.NET Framework</span></span>](#net-framework)
- [<span data-ttu-id="0eb4c-200">.NET Core</span><span class="sxs-lookup"><span data-stu-id="0eb4c-200">.NET Core</span></span>](#net-core)
- [<span data-ttu-id="0eb4c-201">UWP(유니버설 Windows 플랫폼)</span><span class="sxs-lookup"><span data-stu-id="0eb4c-201">Universal Windows Platform (UWP)</span></span>](#uwp)

## <a name="library"></a><span data-ttu-id="0eb4c-202">라이브러리</span><span class="sxs-lookup"><span data-stu-id="0eb4c-202">library</span></span>

<span data-ttu-id="0eb4c-203">앱이나 다른 라이브러리에서 호출할 수 있는 API 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-203">A collection of APIs that can be called by apps or other libraries.</span></span> <span data-ttu-id="0eb4c-204">.NET 라이브러리는 하나 이상의 [어셈블리](#assembly)로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-204">A .NET library is composed of one or more [assemblies](#assembly).</span></span>

<span data-ttu-id="0eb4c-205">라이브러리 및 [프레임워크](#framework)라는 단어는 종종 같은 뜻으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-205">The words library and [framework](#framework) are often used synonymously.</span></span>

## <a name="metapackage"></a><span data-ttu-id="0eb4c-206">메타패키지</span><span class="sxs-lookup"><span data-stu-id="0eb4c-206">metapackage</span></span>

<span data-ttu-id="0eb4c-207">고유한 라이브러리는 없고 종속성 목록만 갖는 NuGet 패키지입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-207">A NuGet package that has no library of its own but is only a list of dependencies.</span></span> <span data-ttu-id="0eb4c-208">포함된 패키지는 필요에 따라 대상 프레임워크에 대한 API를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-208">The included packages can optionally establish the API for a target framework.</span></span>

<span data-ttu-id="0eb4c-209">[패키지와 메타패키지, 프레임워크](../core/packages.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-209">See [Packages, Metapackages and Frameworks](../core/packages.md)</span></span>

## <a name="mono"></a><span data-ttu-id="0eb4c-210">Mono</span><span class="sxs-lookup"><span data-stu-id="0eb4c-210">Mono</span></span>

<span data-ttu-id="0eb4c-211">Mono는 작은 런타임이 필요할 때 주로 사용되는 오픈 소스 [크로스 플랫폼](#cross-platform) .NET 구현체입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-211">Mono is an open source, [cross-platform](#cross-platform) .NET implementation that is mainly used when a small runtime is required.</span></span> <span data-ttu-id="0eb4c-212">이는 Android와 Mac, iOS, tvOS, watchOS에서 Xamarin 애플리케이션의 성능을 향상시키는 런타임으로, 주로 작은 사용 공간이 필요한 앱에 초점을 맞춥니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-212">It is the runtime that powers Xamarin applications on Android, Mac, iOS, tvOS and watchOS and is focused primarily on apps that require a small footprint.</span></span>

<span data-ttu-id="0eb4c-213">Mono는 현재 게시된 .NET Standard 버전을 모두 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-213">It supports all of the currently published .NET Standard versions.</span></span>

<span data-ttu-id="0eb4c-214">지금까지 Mono는 .NET Framework의 방대한 API를 구현하고 Unix에서 가장 인기 있는 기능의 일부를 따라서 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-214">Historically, Mono implemented the larger API of the .NET Framework and emulated some of the most popular capabilities on Unix.</span></span> <span data-ttu-id="0eb4c-215">경우에 따라 Unix에서 해당 기능을 사용하는 .NET 애플리케이션을 실행하는 데도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-215">It is sometimes used to run .NET applications that rely on those capabilities on Unix.</span></span>

<span data-ttu-id="0eb4c-216">일반적으로 Mono는 Just-In-Time 컴파일러에서 사용되지만 iOS 같은 플랫폼에 사용되는 전체 정적 컴파일러(Ahead-Of-Time 컴파일) 기능도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-216">Mono is typically used with a just-in-time compiler, but it also features a full static compiler (ahead-of-time compilation) that is used on platforms like iOS.</span></span>

<span data-ttu-id="0eb4c-217">Mono의 자세한 내용은 [Mono 설명서](https://www.mono-project.com/docs/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-217">To learn more about Mono, see the [Mono documentation](https://www.mono-project.com/docs/).</span></span>

## <a name="net"></a><span data-ttu-id="0eb4c-218">.NET</span><span class="sxs-lookup"><span data-stu-id="0eb4c-218">.NET</span></span>

<span data-ttu-id="0eb4c-219">[.NET Standard](#net-standard) 및 모든 [.NET 구현체](#implementation-of-net)와 워크로드에 대한 포괄적인 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-219">The umbrella term for [.NET Standard](#net-standard) and all [.NET implementations](#implementation-of-net) and workloads.</span></span> <span data-ttu-id="0eb4c-220">항상 대문자로 표기하며, “.Net”이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-220">Always capitalized, never ".Net".</span></span>

<span data-ttu-id="0eb4c-221">[.NET 가이드](index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-221">See the [.NET Guide](index.md)</span></span>

## <a name="net-core"></a><span data-ttu-id="0eb4c-222">.NET Core</span><span class="sxs-lookup"><span data-stu-id="0eb4c-222">.NET Core</span></span> 

<span data-ttu-id="0eb4c-223">다양한 .NET 플랫폼에서 사용할 수 있는 고성능 오픈 소스 구현체입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-223">A cross-platform, high-performance, open source implementation of .NET.</span></span> <span data-ttu-id="0eb4c-224">CoreCLR(Core 공용 언어 런타임)과 Core AOT 런타임(CoreRT, 개발 중), Core 기본 클래스 라이브러리, Core SDK를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-224">Includes the Core Common Language Runtime (CoreCLR), the Core AOT Runtime (CoreRT, in development), the Core Base Class Library, and the Core SDK.</span></span>

<span data-ttu-id="0eb4c-225">[.NET Core](../core/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-225">See [.NET Core](../core/index.md).</span></span>

## <a name="net-core-cli"></a><span data-ttu-id="0eb4c-226">.NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="0eb4c-226">.NET Core CLI</span></span>

<span data-ttu-id="0eb4c-227">다양한 플랫폼에서 사용할 수 있는 .NET Core 애플리케이션 개발용 툴 체인입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-227">A cross-platform toolchain for developing .NET Core applications.</span></span>

<span data-ttu-id="0eb4c-228">[.NET Core CLI](../core/tools/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-228">See [.NET Core CLI](../core/tools/index.md).</span></span>

## <a name="net-core-sdk"></a><span data-ttu-id="0eb4c-229">.NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="0eb4c-229">.NET Core SDK</span></span>

<span data-ttu-id="0eb4c-230">개발자가 .NET Core 애플리케이션과 라이브러리를 만드는 데 사용할 수 있는 라이브러리 및 도구 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-230">A set of libraries and tools that allow developers to create .NET Core applications and libraries.</span></span> <span data-ttu-id="0eb4c-231">앱을 빌드하기 위한 [.NET Core CLI](#net-core-cli), 앱을 빌드하고 실행하기 위한 .NET Core 라이브러리 및 런타임, CLI 명령을 실행하고 애플리케이션을 실행하는 dotnet 실행 파일(*dotnet.exe*)을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-231">Includes the [.NET Core CLI](#net-core-cli) for building apps, .NET Core libraries and runtime for building and running apps, and the dotnet executable (*dotnet.exe*) that runs CLI commands and runs applications.</span></span>

<span data-ttu-id="0eb4c-232">[.NET Core SDK 개요](../core/sdk.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-232">See [.NET Core SDK Overview](../core/sdk.md).</span></span>

## <a name="net-framework"></a><span data-ttu-id="0eb4c-233">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="0eb4c-233">.NET Framework</span></span>

<span data-ttu-id="0eb4c-234">Windows에서만 실행되는 .NET의 구현체입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-234">An implementation of .NET that runs only on Windows.</span></span> <span data-ttu-id="0eb4c-235">CLR(공용 언어 런타임), 기본 클래스 라이브러리 및 ASP.NET, Windows Forms, WPF 등의 애플리케이션 프레임워크 라이브러리를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-235">Includes the Common Language Runtime (CLR), the Base Class Library, and application framework libraries such as ASP.NET, Windows Forms, and WPF.</span></span>

<span data-ttu-id="0eb4c-236">[.NET Framework 가이드](../framework/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-236">See [.NET Framework Guide](../framework/index.md).</span></span>

## <a name="net-native"></a><span data-ttu-id="0eb4c-237">.NET 네이티브</span><span class="sxs-lookup"><span data-stu-id="0eb4c-237">.NET Native</span></span>

<span data-ttu-id="0eb4c-238">JIT(Just-In-Time)와 반대로 네이티브 코드 AOT(Ahead-Of-Time)를 생성하는 컴파일러 툴 체인입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-238">A compiler tool chain that produces native code ahead-of-time (AOT), as opposed to just-in-time (JIT).</span></span>

<span data-ttu-id="0eb4c-239">컴파일은 C++ 컴파일러 및 링커가 작동하는 방식과 유사하게 개발자의 컴퓨터에서 수행되며,</span><span class="sxs-lookup"><span data-stu-id="0eb4c-239">Compilation happens on the developer's machine similar to the way a C++ compiler and linker works.</span></span> <span data-ttu-id="0eb4c-240">사용되지 않는 코드를 제거하고 더 많은 시간을 최적화에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-240">It removes unused code and spends more time optimizing it.</span></span> <span data-ttu-id="0eb4c-241">라이브러리에서 코드를 추출하여 실행 파일에 병합합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-241">It extracts code from libraries and merges them into the executable.</span></span> <span data-ttu-id="0eb4c-242">결과는 전체 앱을 나타내는 단일 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-242">The result is a single module that represents the entire app.</span></span>

<span data-ttu-id="0eb4c-243">UWP는 .NET 네이티브에서 지원하는 첫 번째 애플리케이션 프레임워크였습니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-243">UWP was the first application framework supported by .NET Native.</span></span> <span data-ttu-id="0eb4c-244">이제 Windows와 macOS, Linux용 네이티브 콘솔 앱 작성을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-244">Now, we support building native console apps for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="0eb4c-245">[.NET 네이티브와 CoreRT 소개](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-245">See [Intro to .NET Native and CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)</span></span>

## <a name="net-standard"></a><span data-ttu-id="0eb4c-246">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="0eb4c-246">.NET Standard</span></span>

<span data-ttu-id="0eb4c-247">모든 .NET 구현체에서 사용할 수 있는 .NET API의 공식 규격입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-247">A formal specification of .NET APIs that are available in each .NET implementation.</span></span>

<span data-ttu-id="0eb4c-248">.NET Standard 규격은 설명서에서 라이브러리라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-248">The .NET Standard specification is sometimes called a library in the documentation.</span></span> <span data-ttu-id="0eb4c-249">라이브러리는 API 구현체를 포함하므로 규격(인터페이스)뿐만 아니라 .NET Standard를 “라이브러리”라고 잘못 부르기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-249">Because a library includes API implementations, not only specifications (interfaces), it's misleading to call .NET Standard a "library."</span></span> <span data-ttu-id="0eb4c-250">.NET Standard 메타패키지(`NETStandard.Library`)의 이름을 참조할 때를 제외하고 설명서에서 이렇게 사용한 부분을 제거할 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-250">We plan to eliminate that usage from the documentation, except in reference to the name of the .NET Standard metapackage (`NETStandard.Library`).</span></span>

<span data-ttu-id="0eb4c-251">[.NET Standard](net-standard.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-251">See [.NET Standard](net-standard.md).</span></span>

## <a name="ngen"></a><span data-ttu-id="0eb4c-252">NGEN</span><span class="sxs-lookup"><span data-stu-id="0eb4c-252">NGEN</span></span>

<span data-ttu-id="0eb4c-253">네이티브(이미지) 생성입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-253">Native (image) generation.</span></span>

<span data-ttu-id="0eb4c-254">이 기술을 영구 JIT 컴파일러로 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-254">You can think of this technology as a persistent JIT compiler.</span></span> <span data-ttu-id="0eb4c-255">일반적으로 코드가 실행되는 컴퓨터에서 코드를 컴파일하지만 컴파일은 대개 설치 시에 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-255">It usually compiles code on the machine where the code is executed, but compilation typically occurs at install time.</span></span>

## <a name="package"></a><span data-ttu-id="0eb4c-256">패키지</span><span class="sxs-lookup"><span data-stu-id="0eb4c-256">package</span></span>

<span data-ttu-id="0eb4c-257">NuGet 패키지(또는 줄여서 패키지)는 작성자 이름과 같은 추가 메타데이터와 함께 동일한 이름의 어셈블리가 하나 이상 있는 .zip 파일입니다. </span><span class="sxs-lookup"><span data-stu-id="0eb4c-257">A NuGet package &mdash; or just a package &mdash; is a *.zip* file with one or more assemblies of the same name along with additional metadata such as the author name.</span></span>

<span data-ttu-id="0eb4c-258">*.zip* 파일은 *.nupkg* 확장명을 사용하며 *.dll* 파일 및 *.xml* 파일과 같이 여러 대상 프레임워크 및 버전에서 사용할 자산을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-258">The *.zip* file has a *.nupkg* extension and may contain assets, such as *.dll* files and *.xml* files, for use with multiple target frameworks and versions.</span></span> <span data-ttu-id="0eb4c-259">앱 또는 라이브러리에 설치된 경우 앱 또는 라이브러리에서 지정한 대상 프레임워크에 따라 적절한 자산이 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-259">When installed in an app or library, the appropriate assets are selected based on the target framework specified by the app or library.</span></span> <span data-ttu-id="0eb4c-260">인터페이스를 정의하는 자산은 *ref* 폴더에 있으며 구현을 정의하는 자산은 *lib* 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-260">The assets that define the interface are in the *ref* folder, and the assets that define the implementation are in the *lib* folder.</span></span>

## <a name="platform"></a><span data-ttu-id="0eb4c-261">platform</span><span class="sxs-lookup"><span data-stu-id="0eb4c-261">platform</span></span>

<span data-ttu-id="0eb4c-262">Windows와 macOS, Linux, iOS, Android 같은 운영 체제와 해당 운영 체제가 실행되는 하드웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-262">An operating system and the hardware it runs on, such as Windows, macOS, Linux, iOS, and Android.</span></span>

<span data-ttu-id="0eb4c-263">다음은 문장에서의 사용 예입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-263">Here are examples of usage in sentences:</span></span>

- <span data-ttu-id="0eb4c-264">“.NET Core는 다양한 플랫폼에서 사용할 수 있는 .NET의 구현체입니다.”</span><span class="sxs-lookup"><span data-stu-id="0eb4c-264">".NET Core is a cross-platform implementation of .NET."</span></span> 
- <span data-ttu-id="0eb4c-265">“PCL 프로필은 Microsoft 플랫폼을 나타내지만 .NET Standard는 플랫폼에 독립적입니다.”</span><span class="sxs-lookup"><span data-stu-id="0eb4c-265">"PCL profiles represent Microsoft platforms, while the .NET Standard is agnostic to platform."</span></span>

<span data-ttu-id="0eb4c-266">.NET 설명서에서는 .NET의 구현체나 모든 구현체를 포함하는 .NET 스택을 의미하는 용어로 “.NET 플랫폼”을 자주 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-266">The .NET documentation frequently uses ".NET platform" to mean either an implementation of .NET or the .NET stack including all implementations.</span></span> <span data-ttu-id="0eb4c-267">이렇게 사용한 부분은 모두 기본적인(OS/하드웨어) 의미와 혼동되므로 설명서에서 이러한 사용을 제거할 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-267">Both of these usages tend to get confused with the primary (OS/hardware) meaning, so we plan to eliminate these usages from the documentation.</span></span>

## <a name="runtime"></a><span data-ttu-id="0eb4c-268">런타임</span><span class="sxs-lookup"><span data-stu-id="0eb4c-268">runtime</span></span>

<span data-ttu-id="0eb4c-269">관리되는 프로그램의 실행 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-269">The execution environment for a managed program.</span></span>

<span data-ttu-id="0eb4c-270">OS는 런타임 환경의 일부이지만 .NET 런타임의 일부는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-270">The OS is part of the runtime environment but is not part of the .NET runtime.</span></span> <span data-ttu-id="0eb4c-271">다음은 .NET 런타임의 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-271">Here are some examples of .NET runtimes:</span></span>

- <span data-ttu-id="0eb4c-272">CLR(공용 언어 런타임)</span><span class="sxs-lookup"><span data-stu-id="0eb4c-272">Common Language Runtime (CLR)</span></span>
- <span data-ttu-id="0eb4c-273">CoreCLR(Core 공용 언어 런타임)</span><span class="sxs-lookup"><span data-stu-id="0eb4c-273">Core Common Language Runtime (CoreCLR)</span></span>
- <span data-ttu-id="0eb4c-274">.NET 네이티브(UWP)</span><span class="sxs-lookup"><span data-stu-id="0eb4c-274">.NET Native (for UWP)</span></span>
- <span data-ttu-id="0eb4c-275">Mono 런타임</span><span class="sxs-lookup"><span data-stu-id="0eb4c-275">Mono runtime</span></span>

<span data-ttu-id="0eb4c-276">.NET 설명서에서는 경우에 따라 “런타임”을 사용하여 .NET의 구현체를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-276">The .NET documentation sometimes uses "runtime" to mean an implementation of .NET.</span></span> <span data-ttu-id="0eb4c-277">예를 들어 다음 문장에서 “런타임”은 “구현체”로 대체되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-277">For example, in the following sentences "runtime" should be replaced with "implementation":</span></span>

- <span data-ttu-id="0eb4c-278">“다양한 .NET 런타임에서 특정 버전의 .NET Standard를 구현합니다.”</span><span class="sxs-lookup"><span data-stu-id="0eb4c-278">"The various .NET runtimes implement specific versions of .NET Standard."</span></span>
- <span data-ttu-id="0eb4c-279">“여러 런타임에서 실행되도록 만들어진 라이브러리는 이 프레임워크를 대상으로 해야 합니다.”</span><span class="sxs-lookup"><span data-stu-id="0eb4c-279">"Libraries that are intended to run on multiple runtimes should target this framework."</span></span> <span data-ttu-id="0eb4c-280">(.NET Standard를 참조)</span><span class="sxs-lookup"><span data-stu-id="0eb4c-280">(referring to .NET Standard)</span></span>
- <span data-ttu-id="0eb4c-281">“다양한 .NET 런타임에서 특정 버전의 .NET Standard를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-281">"The various .NET runtimes implement specific versions of .NET Standard.</span></span> <span data-ttu-id="0eb4c-282">…</span><span class="sxs-lookup"><span data-stu-id="0eb4c-282">…</span></span> <span data-ttu-id="0eb4c-283">각 .NET 런타임 버전은 지원하는 최신 .NET Standard 버전을 보급합니다.”</span><span class="sxs-lookup"><span data-stu-id="0eb4c-283">Each .NET runtime version advertises the highest .NET Standard version it supports …"</span></span>

<span data-ttu-id="0eb4c-284">이와 같이 일관성 없이 사용한 부분을 제거할 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-284">We plan to eliminate this inconsistent usage.</span></span> 

## <a name="stack"></a><span data-ttu-id="0eb4c-285">스택</span><span class="sxs-lookup"><span data-stu-id="0eb4c-285">stack</span></span>

<span data-ttu-id="0eb4c-286">애플리케이션을 만들고 실행하는 데 사용되는 프로그래밍 기술 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-286">A set of programming technologies that are used together to build and run applications.</span></span>

<span data-ttu-id="0eb4c-287">“.NET 스택”은 .NET Standard 및 모든 .NET 구현체를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-287">"The .NET stack" refers to the .NET Standard and all .NET implementations.</span></span> <span data-ttu-id="0eb4c-288">“.NET 스택”이라는 문구는 하나의 .NET 구현체를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-288">The phrase "a .NET stack" may refer to one implementation of .NET.</span></span> 

## <a name="target-framework"></a><span data-ttu-id="0eb4c-289">대상 프레임워크(target framework)</span><span class="sxs-lookup"><span data-stu-id="0eb4c-289">target framework</span></span>

<span data-ttu-id="0eb4c-290">.NET 앱이나 라이브러리에서 사용하는 API 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-290">The collection of APIs that a .NET app or library relies on.</span></span>

<span data-ttu-id="0eb4c-291">앱이나 라이브러리는 모든.NET 구현체에서 표준화된 API 집합에 대한 규격인 .NET Standard의 버전(예: .NET Standard 2.0)을 대상으로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-291">An app or library can target a version of .NET Standard (for example, .NET Standard 2.0), which is specification for a standardized set of APIs across all .NET implementations.</span></span> <span data-ttu-id="0eb4c-292">또한 앱이나는 라이브러리는 특정 .NET 구현체의 버전을 대상으로 할 수 있으며, 이 경우 구현체 관련 API에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-292">An app or library can also target a version of a specific .NET implementation, in which case it gets access to implementation-specific APIs.</span></span> <span data-ttu-id="0eb4c-293">예를 들어 Xamarin.iOS를 대상으로 하는 앱은 Xamarin 제공 iOS API 래퍼에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-293">For example, an app that targets Xamarin.iOS gets access to Xamarin-provided iOS API wrappers.</span></span>

<span data-ttu-id="0eb4c-294">일부 대상 프레임워크(예: .NET Framework)에서 사용 가능한 API는 .NET 구현체에서 시스템에 설치하는 어셈블리에 의해 정의되고 애플리케이션 프레임워크 API(예: ASP.NET, WinForms)를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-294">For some target frameworks (for example, the .NET Framework) the available APIs are defined by the assemblies that a .NET implementation installs on a system, which may include application framework APIs (for example, ASP.NET, WinForms).</span></span> <span data-ttu-id="0eb4c-295">패키지 기반 대상 프레임워크(예: .NET Standard 및 .NET Core)에서 프레임워크 API는 앱이나 라이브러리에 설치된 패키지에 의해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-295">For package-based target frameworks (such as .NET Standard and .NET Core), the framework APIs are defined by the packages installed in the app or library.</span></span> <span data-ttu-id="0eb4c-296">이 경우 대상 프레임워크는 프레임워크를 구성하는 모든 패키지를 참조하는 메타패키지를 암시적으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-296">In that case, the target framework implicitly specifies a metapackage that references all the packages that together make up the framework.</span></span>

<span data-ttu-id="0eb4c-297">[대상 프레임워크](frameworks.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-297">See [Target Frameworks](frameworks.md).</span></span>

## <a name="tfm"></a><span data-ttu-id="0eb4c-298">TFM</span><span class="sxs-lookup"><span data-stu-id="0eb4c-298">TFM</span></span>

<span data-ttu-id="0eb4c-299">대상 프레임워크 모니커입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-299">Target framework moniker.</span></span>

<span data-ttu-id="0eb4c-300">.NET 앱이나 라이브러리의 대상 프레임워크를 지정하기 위한 표준화된 토큰 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-300">A standardized token format for specifying the target framework of a .NET app or library.</span></span> <span data-ttu-id="0eb4c-301">대상 프레임워크는 일반적으로 `net462` 같은 짧은 이름으로 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-301">Target frameworks are typically referenced by a short name, such as `net462`.</span></span> <span data-ttu-id="0eb4c-302">긴 형식의 TFM(예: .NETFramework,Version=4.6.2)이 있지만 일반적으로 대상 프레임워크를 지정하는 데 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-302">Long-form TFMs (such as .NETFramework,Version=4.6.2) exist but are not generally used to specify a target framework.</span></span>

<span data-ttu-id="0eb4c-303">[대상 프레임워크](frameworks.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-303">See [Target Frameworks](frameworks.md).</span></span>

## <a name="uwp"></a><span data-ttu-id="0eb4c-304">UWP</span><span class="sxs-lookup"><span data-stu-id="0eb4c-304">UWP</span></span>

<span data-ttu-id="0eb4c-305">유니버설 Windows 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-305">Universal Windows Platform.</span></span>

<span data-ttu-id="0eb4c-306">IoT(사물 인터넷)에 대한 최신의 터치 가능 Windows 애플리케이션 및 소프트웨어를 작성하는 데 사용되는 .NET의 구현체입니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-306">An implementation of .NET that is used for building modern, touch-enabled Windows applications and software for the Internet of Things (IoT).</span></span> <span data-ttu-id="0eb4c-307">PC, 태블릿, 패블릿, 휴대폰, Xbox와 같은 대상으로 지정할 수 있는 다양한 종류의 디바이스를 통합하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-307">It's designed to unify the different types of devices that you may want to target, including PCs, tablets, phablets, phones, and even the Xbox.</span></span> <span data-ttu-id="0eb4c-308">UWP는 중앙 집중식 앱 스토어, 실행 환경(AppContainer), Win32를 대체할 Windows API(WinRT) 등 많은 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-308">UWP provides many services, such as a centralized app store, an execution environment (AppContainer), and a set of Windows APIs to use instead of Win32 (WinRT).</span></span> <span data-ttu-id="0eb4c-309">앱은 C++과 C#, Visual Basic, JavaScript로 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-309">Apps can be written in C++, C#, Visual Basic, and JavaScript.</span></span> <span data-ttu-id="0eb4c-310">C#과 Visual Basic을 사용할 경우 .NET API는 .NET Core에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="0eb4c-310">When using C# and Visual Basic, the .NET APIs are provided by .NET Core.</span></span>

## <a name="see-also"></a><span data-ttu-id="0eb4c-311">참조</span><span class="sxs-lookup"><span data-stu-id="0eb4c-311">See also</span></span>

- [<span data-ttu-id="0eb4c-312">.NET 가이드</span><span class="sxs-lookup"><span data-stu-id="0eb4c-312">.NET Guide</span></span>](index.md)
- [<span data-ttu-id="0eb4c-313">.NET Framework 가이드</span><span class="sxs-lookup"><span data-stu-id="0eb4c-313">.NET Framework Guide</span></span>](../framework/index.md)
- [<span data-ttu-id="0eb4c-314">.NET Core</span><span class="sxs-lookup"><span data-stu-id="0eb4c-314">.NET Core</span></span>](../core/index.md)
- [<span data-ttu-id="0eb4c-315">ASP.NET 개요</span><span class="sxs-lookup"><span data-stu-id="0eb4c-315">ASP.NET Overview</span></span>](/aspnet/index#pivot=aspnet)
- [<span data-ttu-id="0eb4c-316">ASP.NET Core 개요</span><span class="sxs-lookup"><span data-stu-id="0eb4c-316">ASP.NET Core Overview</span></span>](/aspnet/index#pivot=core)
