---
title: .NET 용어
description: .NET 설명서에서 사용되는 선택한 용어의 의미를 알아봅니다.
ms.date: 11/16/2020
ms.openlocfilehash: 77ed506fb1c5bd4018b5fe0c14cc0bf37cb08113
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96438189"
---
# <a name="net-glossary"></a><span data-ttu-id="80130-103">.NET 용어</span><span class="sxs-lookup"><span data-stu-id="80130-103">.NET Glossary</span></span>

<span data-ttu-id="80130-104">이 용어집의 주 용도는 .NET 설명서에서 정의 없이 자주 나타나는 선택한 용어 및 머리글자어의 의미를 명확히 나타내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-104">The primary goal of this glossary is to clarify meanings of selected terms and acronyms that appear frequently in the .NET documentation without definitions.</span></span>

## <a name="aot"></a><span data-ttu-id="80130-105">AOT</span><span class="sxs-lookup"><span data-stu-id="80130-105">AOT</span></span>

<span data-ttu-id="80130-106">Ahead-Of-Time 컴파일러입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-106">Ahead-of-time compiler.</span></span>

<span data-ttu-id="80130-107">[JIT](#jit)와 비슷하게 이 컴파일러도 [IL](#il)을 기계어 코드로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-107">Similar to [JIT](#jit), this compiler also translates [IL](#il) to machine code.</span></span> <span data-ttu-id="80130-108">JIT 컴파일과는 달리 AOT 컴파일은 애플리케이션이 실행되기 전에 수행되며 일반적으로 다른 컴퓨터에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="80130-108">In contrast to JIT compilation, AOT compilation happens before the application is executed and is usually performed on a different machine.</span></span> <span data-ttu-id="80130-109">AOT 툴 체인은 런타임에 컴파일되지 않으므로 컴파일 시간을 최소화할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-109">Because AOT tool chains don't compile at run time, they don't have to minimize time spent compiling.</span></span> <span data-ttu-id="80130-110">즉, 더 많은 시간을 최적화하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-110">That means they can spend more time optimizing.</span></span> <span data-ttu-id="80130-111">AOT의 컨텍스트는 전체 애플리케이션이므로 AOT 컴파일러는 모듈 간 연결 및 전체 프로그램 분석도 수행합니다. 즉, 모든 참조가 수행되고 단일 실행 파일이 생성된다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-111">Since the context of AOT is the entire application, the AOT compiler also performs cross-module linking and whole-program analysis, which means that all references are followed and a single executable is produced.</span></span>

<span data-ttu-id="80130-112">[CoreRT](#corert)와 [.NET 네이티브](#net-native)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80130-112">See [CoreRT](#corert) and [.NET Native](#net-native).</span></span>

## <a name="app-model"></a><span data-ttu-id="80130-113">앱 모델</span><span class="sxs-lookup"><span data-stu-id="80130-113">app model</span></span>

<span data-ttu-id="80130-114">[워크로드](#workload)별 API.</span><span class="sxs-lookup"><span data-stu-id="80130-114">A [workload](#workload)-specific API.</span></span> <span data-ttu-id="80130-115">몇 가지 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-115">Here are some examples:</span></span>

* <span data-ttu-id="80130-116">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="80130-116">ASP.NET</span></span>
* <span data-ttu-id="80130-117">ASP.NET Web API</span><span class="sxs-lookup"><span data-stu-id="80130-117">ASP.NET Web API</span></span>
* <span data-ttu-id="80130-118">EF(Entity Framework)</span><span class="sxs-lookup"><span data-stu-id="80130-118">Entity Framework (EF)</span></span>
* <span data-ttu-id="80130-119">WPF(Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="80130-119">Windows Presentation Foundation (WPF)</span></span>
* <span data-ttu-id="80130-120">WCF(Windows Communication Foundation)</span><span class="sxs-lookup"><span data-stu-id="80130-120">Windows Communication Foundation (WCF)</span></span>
* <span data-ttu-id="80130-121">Windows WF(Workflow Foundation)</span><span class="sxs-lookup"><span data-stu-id="80130-121">Windows Workflow Foundation (WF)</span></span>
* <span data-ttu-id="80130-122">Windows Forms(WinForms)</span><span class="sxs-lookup"><span data-stu-id="80130-122">Windows Forms (WinForms)</span></span>

## <a name="aspnet"></a><span data-ttu-id="80130-123">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="80130-123">ASP.NET</span></span>

<span data-ttu-id="80130-124">.NET Framework와 함께 제공되는 원래 ASP.NET 구현체입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-124">The original ASP.NET implementation that ships with the .NET Framework.</span></span>

<span data-ttu-id="80130-125">경우에 따라 ASP.NET은 ASP.NET Core를 포함한 두가지 ASP.NET 구현체를 나타내는 포괄적인 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-125">Sometimes ASP.NET is an umbrella term that refers to both ASP.NET implementations including ASP.NET Core.</span></span> <span data-ttu-id="80130-126">지정된 인스턴스에서 이 용어가 전달하는 의미는 컨텍스트에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="80130-126">The meaning that the term carries in any given instance is determined by context.</span></span> <span data-ttu-id="80130-127">ASP.NET을 사용하여 두 구현체를 모두 의미하는 것이 아님을 분명히 하려는 경우 ASP.NET 4.x를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80130-127">Refer to ASP.NET 4.x when you want to make it clear that you're not using ASP.NET to mean both implementations.</span></span>

<span data-ttu-id="80130-128">[ASP.NET 설명서](/aspnet/#pivot=aspnet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80130-128">See [ASP.NET documentation](/aspnet/#pivot=aspnet).</span></span>

## <a name="aspnet-core"></a><span data-ttu-id="80130-129">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="80130-129">ASP.NET Core</span></span>

<span data-ttu-id="80130-130">다양한 ASP.NET 플랫폼에서 사용할 수 있는 고성능 오픈 소스 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-130">A cross-platform, high-performance, open-source implementation of ASP.NET.</span></span>

<span data-ttu-id="80130-131">[ASP.NET Core 설명서](/aspnet/#pivot=core)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80130-131">See [ASP.NET Core documentation](/aspnet/#pivot=core).</span></span>

## <a name="assembly"></a><span data-ttu-id="80130-132">어셈블리</span><span class="sxs-lookup"><span data-stu-id="80130-132">assembly</span></span>

<span data-ttu-id="80130-133">애플리케이션이나 다른 어셈블리에서 호출할 수 있는 API 컬렉션을 포함할 수 있는 *.dll*/ *.exe* 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-133">A *.dll*/*.exe* file that can contain a collection of APIs that can be called by applications or other assemblies.</span></span>

<span data-ttu-id="80130-134">어셈블리에는 인터페이스와 클래스, 구조체, 열거형, 대리자와 같은 형식이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-134">An assembly may include types such as interfaces, classes, structures, enumerations, and delegates.</span></span> <span data-ttu-id="80130-135">프로젝트의 *bin* 폴더에 있는 어셈블리를 *바이너리* 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-135">Assemblies in a project's *bin* folder are sometimes referred to as *binaries*.</span></span> <span data-ttu-id="80130-136">[라이브러리](#library)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80130-136">See also [library](#library).</span></span>

## <a name="bcl"></a><span data-ttu-id="80130-137">BCL</span><span class="sxs-lookup"><span data-stu-id="80130-137">BCL</span></span>

<span data-ttu-id="80130-138">기본 클래스 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-138">Base Class Library.</span></span>

<span data-ttu-id="80130-139">System.\*(및 제한된 범위의 Microsoft.\*) 네임스페이스를 구성하는 라이브러리 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-139">A set of libraries that comprise the System.\* (and to a limited extent Microsoft.\*) namespaces.</span></span> <span data-ttu-id="80130-140">BCL은 ASP.NET Core 같은 상위 수준 애플리케이션 프레임워크의 기반이 되는 하위 수준의 범용 프레임워크입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-140">The BCL is a general purpose, lower-level framework that higher-level application frameworks, such as ASP.NET Core, build on.</span></span>

<span data-ttu-id="80130-141">[.NET 5(및 .NET Core) 이상 버전](#net-5-and-later-versions)의 BCL 소스 코드는 [.NET 런타임 리포지토리](https://github.com/dotnet/runtime)에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="80130-141">The source code of the BCL for [.NET 5 (and .NET Core) and later versions](#net-5-and-later-versions) is contained in the [.NET runtime repository](https://github.com/dotnet/runtime).</span></span> <span data-ttu-id="80130-142">대다수 BCL API는 .NET Framework에서도 사용할 수 있으므로 이 소스 코드를 .NET Framework BCL 소스 코드의 포크로 간주할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-142">The majority of these BCL APIs are also available in .NET Framework, so you can think of this source code as a fork of the .NET Framework BCL source code.</span></span>

<span data-ttu-id="80130-143">다음 용어는 종종 BCL에서 참조하는 것과 동일한 API 컬렉션을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-143">The following terms often refer to the same collection of APIs that BCL refers to:</span></span>

- [<span data-ttu-id="80130-144">핵심 .NET 라이브러리</span><span class="sxs-lookup"><span data-stu-id="80130-144">core .NET libraries</span></span>](../core/compatibility/corefx.md)
- [<span data-ttu-id="80130-145">프레임워크 라이브러리</span><span class="sxs-lookup"><span data-stu-id="80130-145">framework libraries</span></span>](#framework-libraries)
- [<span data-ttu-id="80130-146">런타임 라이브러리</span><span class="sxs-lookup"><span data-stu-id="80130-146">runtime libraries</span></span>](#runtime)
- [<span data-ttu-id="80130-147">공유 프레임워크</span><span class="sxs-lookup"><span data-stu-id="80130-147">shared framework</span></span>](#shared-framework)

## <a name="clr"></a><span data-ttu-id="80130-148">CLR</span><span class="sxs-lookup"><span data-stu-id="80130-148">CLR</span></span>

<span data-ttu-id="80130-149">공용 언어 런타임입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-149">Common Language Runtime.</span></span>

<span data-ttu-id="80130-150">정확한 의미는 컨텍스트에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="80130-150">The exact meaning depends on the context.</span></span> <span data-ttu-id="80130-151">공용 언어 런타임은 일반적으로 [.NET Framework](#net-framework) 또는 [.NET 5(및 .NET Core) 이상 버전](#net-5-and-later-versions)의 런타임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="80130-151">Common Language Runtime usually refers to the runtime of [.NET Framework](#net-framework) or the runtime of [.NET 5 (and .NET Core) and later versions](#net-5-and-later-versions).</span></span>

<span data-ttu-id="80130-152">CLR은 메모리 할당 및 관리를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-152">A CLR handles memory allocation and management.</span></span> <span data-ttu-id="80130-153">또한 CLR은 앱을 실행할 뿐만 아니라 [JIT](#jit) 컴파일러를 사용하여 즉시 코드를 생성하고 컴파일하는 가상 머신입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-153">A CLR is also a virtual machine that not only executes apps but also generates and compiles code on-the-fly using a [JIT](#jit) compiler.</span></span>

<span data-ttu-id="80130-154">.NET Framework의 CLR 구현은 Windows 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-154">The CLR implementation for .NET Framework is Windows only.</span></span>

<span data-ttu-id="80130-155">.NET 5 이상 버전의 CLR 구현(Core CLR이라고도 함)은 .NET Framework CLR과 동일한 코드베이스에서 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="80130-155">The CLR implementation for .NET 5 and later versions (also known as the Core CLR) is built from the same code base as the .NET Framework CLR.</span></span> <span data-ttu-id="80130-156">원래 Core CLR은 Silverlight의 런타임이고 여러 플랫폼, 특히 Windows 및 OS X에서 실행되도록 디자인되었습니다. 지금도 많은 Linux 배포 지원을 포함하는 [플랫폼 간](#cross-platform) 런타임입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-156">Originally, the Core CLR was the runtime of Silverlight and was designed to run on multiple platforms, specifically Windows and OS X. It's still a [cross-platform](#cross-platform) runtime, now including support for many Linux distributions.</span></span>

<span data-ttu-id="80130-157">[런타임](#runtime)도 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80130-157">See also [runtime](#runtime).</span></span>

## <a name="core-clr"></a><span data-ttu-id="80130-158">Core CLR</span><span class="sxs-lookup"><span data-stu-id="80130-158">Core CLR</span></span>

<span data-ttu-id="80130-159">[.NET 5(및 .NET Core) 이상 버전](#net-5-and-later-versions)의 공용 언어 런타임입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-159">The Common Language Runtime for [.NET 5 (and .NET Core) and later versions](#net-5-and-later-versions).</span></span>

<span data-ttu-id="80130-160">[CLR](#clr)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80130-160">See [CLR](#clr)</span></span>

## <a name="corert"></a><span data-ttu-id="80130-161">CoreRT</span><span class="sxs-lookup"><span data-stu-id="80130-161">CoreRT</span></span>

<span data-ttu-id="80130-162">[CLR](#clr)과 달리 CoreRT는 가상 머신이 아닙니다. 즉, [JIT](#jit)를 포함하지 않으므로 즉시 코드를 생성하고 실행하는 기능을 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-162">In contrast to the [CLR](#clr), CoreRT is not a virtual machine, which means it doesn't include the facilities to generate and run code on-the-fly because it doesn't include a [JIT](#jit).</span></span> <span data-ttu-id="80130-163">그러나 [GC](#gc)와 RTTI(런타임 형식 식별) 및 리플렉션에 대한 기능은 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-163">It does, however, include the [GC](#gc) and the ability for run-time type identification (RTTI) and reflection.</span></span> <span data-ttu-id="80130-164">그러나 해당 형식 시스템은 리플렉션에 대한 메타데이터가 필요하지 않도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-164">However, its type system is designed so that metadata for reflection isn't required.</span></span> <span data-ttu-id="80130-165">메타데이터가 필요하지 않으면 불필요한 메타데이터를 분리하고 더 중요하게는 앱이 사용하지 않는 코드를 식별할 수 있는 [AOT](#aot) 도구 체인을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-165">Not requiring metadata enables having an [AOT](#aot) tool chain that can link away superfluous metadata and (more importantly) identify code that the app doesn't use.</span></span> <span data-ttu-id="80130-166">CoreRT는 개발 중입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-166">CoreRT is in development.</span></span>

<span data-ttu-id="80130-167">[.NET 네이티브와 CoreRT 소개](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80130-167">See [Intro to .NET Native and CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md).</span></span>

## <a name="cross-platform"></a><span data-ttu-id="80130-168">크로스 플랫폼</span><span class="sxs-lookup"><span data-stu-id="80130-168">cross-platform</span></span>

<span data-ttu-id="80130-169">각 운영 체제에 맞게 다시 작성할 필요 없이 Linux, Windows 및 iOS와 같은 다양한 운영 체제에서 사용할 수 있는 애플리케이션을 개발하고 실행하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-169">The ability to develop and execute an application that can be used on multiple different operating systems, such as Linux, Windows, and iOS, without having to rewrite specifically for each one.</span></span> <span data-ttu-id="80130-170">이를 통해 다양한 플랫폼에서 애플리케이션 간에 코드를 다시 사용하고 일관성을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-170">This enables code reuse and consistency between applications on different platforms.</span></span>

## <a name="ecosystem"></a><span data-ttu-id="80130-171">에코시스템</span><span class="sxs-lookup"><span data-stu-id="80130-171">ecosystem</span></span>

<span data-ttu-id="80130-172">특정 기술에 대한 애플리케이션을 빌드하고 실행하는 데 사용되는 모든 런타임 소프트웨어, 개발 도구 및 커뮤니티 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-172">All of the runtime software, development tools, and community resources that are used to build and run applications for a given technology.</span></span>

<span data-ttu-id="80130-173">“.NET 에코시스템”이라는 용어는 타사 앱 및 라이브러리를 포함한다는 점에서 “.NET 스택”과 같은 유사한 용어와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="80130-173">The term ".NET ecosystem" differs from similar terms such as ".NET stack" in its inclusion of third-party apps and libraries.</span></span> <span data-ttu-id="80130-174">다음은 문장에서의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-174">Here's an example in a sentence:</span></span>

- <span data-ttu-id="80130-175">“[.NET Standard](#net-standard)는 .NET 에코시스템의 통일성을 높이기 위한 것입니다.”</span><span class="sxs-lookup"><span data-stu-id="80130-175">"The motivation behind [.NET Standard](#net-standard) is to establish greater uniformity in the .NET ecosystem."</span></span>

## <a name="framework"></a><span data-ttu-id="80130-176">프레임워크</span><span class="sxs-lookup"><span data-stu-id="80130-176">framework</span></span>

<span data-ttu-id="80130-177">일반적으로 특정 기술을 기반으로 하는 애플리케이션의 개발 및 배포를 용이하게 하는 포괄적인 API 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-177">In general, a comprehensive collection of APIs that facilitates development and deployment of applications that are based on a particular technology.</span></span> <span data-ttu-id="80130-178">이 일반적인 의미에서 ASP.NET Core 및 Windows Forms는 애플리케이션 프레임워크의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-178">In this general sense, ASP.NET Core and Windows Forms are examples of application frameworks.</span></span> <span data-ttu-id="80130-179">[라이브러리](#library)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80130-179">See also [library](#library).</span></span>

<span data-ttu-id="80130-180">“프레임워크”라는 단어는 다음 용어에서 다른 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-180">The word "framework" has a different meaning in the following terms:</span></span>

- [<span data-ttu-id="80130-181">프레임워크 라이브러리</span><span class="sxs-lookup"><span data-stu-id="80130-181">framework libraries</span></span>](#framework-libraries)
- [<span data-ttu-id="80130-182">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="80130-182">.NET Framework</span></span>](#net-framework)
- [<span data-ttu-id="80130-183">공유 프레임워크</span><span class="sxs-lookup"><span data-stu-id="80130-183">shared framework</span></span>](#shared-framework)
- [<span data-ttu-id="80130-184">대상 프레임워크</span><span class="sxs-lookup"><span data-stu-id="80130-184">target framework</span></span>](#target-framework)
- [<span data-ttu-id="80130-185">TFM(대상 프레임워크 모니커)</span><span class="sxs-lookup"><span data-stu-id="80130-185">TFM (target framework moniker)</span></span>](#tfm)
- [<span data-ttu-id="80130-186">프레임워크 종속 앱</span><span class="sxs-lookup"><span data-stu-id="80130-186">framework-dependent app</span></span>](../core/deploying/index.md#publish-framework-dependent)

<span data-ttu-id="80130-187">경우에 따라 “프레임워크”는 [.NET 구현](#implementation-of-net)을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="80130-187">Sometimes "framework" refers to an [implementation of .NET](#implementation-of-net).</span></span> <span data-ttu-id="80130-188">예를 들어 문서에서는 .NET 5를 프레임워크라고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-188">For example, an article may call .NET 5 a framework.</span></span>

## <a name="framework-libraries"></a><span data-ttu-id="80130-189">프레임워크 라이브러리</span><span class="sxs-lookup"><span data-stu-id="80130-189">framework libraries</span></span>

<span data-ttu-id="80130-190">의미는 컨텍스트에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="80130-190">Meaning depends on context.</span></span> <span data-ttu-id="80130-191">[.NET 5(및 .NET Core) 이상 버전](#net-5-and-later-versions)의 프레임워크 라이브러리를 나타낼 수 있습니다. 이 경우 [BCL](#bcl)이 참조하는 것과 동일한 라이브러리를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-191">May refer to the framework libraries for [.NET 5 (and .NET Core) and later versions](#net-5-and-later-versions), in which case it refers to the same libraries that [BCL](#bcl) refers to.</span></span> <span data-ttu-id="80130-192">BCL을 기반으로 하고 웹앱에 대한 추가 API를 제공하는 ASP.NET Core 프레임워크 라이브러리를 참조할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-192">It may also refer to the ASP.NET Core framework libraries, which build on the BCL and provide additional APIs for web apps.</span></span>

## <a name="gc"></a><span data-ttu-id="80130-193">GC</span><span class="sxs-lookup"><span data-stu-id="80130-193">GC</span></span>

<span data-ttu-id="80130-194">가비지 수집기입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-194">Garbage collector.</span></span>

<span data-ttu-id="80130-195">가비지 수집기는 자동 메모리 관리의 구현체입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-195">The garbage collector is an implementation of automatic memory management.</span></span>  <span data-ttu-id="80130-196">GC는 개체가 사용한 메모리에서 더 이상 사용되지 않는 메모리를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-196">The GC frees memory occupied by objects that are no longer in use.</span></span>

<span data-ttu-id="80130-197">[가비지 수집](garbage-collection/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80130-197">See [Garbage Collection](garbage-collection/index.md).</span></span>

## <a name="il"></a><span data-ttu-id="80130-198">IL</span><span class="sxs-lookup"><span data-stu-id="80130-198">IL</span></span>

<span data-ttu-id="80130-199">중간 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-199">Intermediate language.</span></span>

<span data-ttu-id="80130-200">C#과 같은 상위 수준 .NET 언어가 IL(중간 언어)이라는 하드웨어 독립 명령 집합으로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="80130-200">Higher-level .NET languages, such as C#, compile down to a hardware-agnostic instruction set, which is called Intermediate Language (IL).</span></span> <span data-ttu-id="80130-201">IL은 MSIL(Microsoft IL) 또는 CIL(공통 IL)이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-201">IL is sometimes referred to as MSIL (Microsoft IL) or CIL (Common IL).</span></span>

## <a name="jit"></a><span data-ttu-id="80130-202">JIT</span><span class="sxs-lookup"><span data-stu-id="80130-202">JIT</span></span>

<span data-ttu-id="80130-203">Just-In-Time 컴파일러입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-203">Just-in-time compiler.</span></span>

<span data-ttu-id="80130-204">[AOT](#aot)와 유사한 이 컴파일러는 [IL](#il)을 프로세서에서 이해하는 기계어 코드로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-204">Similar to [AOT](#aot), this compiler translates [IL](#il) to machine code that the processor understands.</span></span> <span data-ttu-id="80130-205">AOT와 달리 JIT 컴파일은 요청 시 수행되며 코드가 실행되어야 하는 것과 동일한 컴퓨터에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="80130-205">Unlike AOT, JIT compilation happens on demand and is performed on the same machine that the code needs to run on.</span></span> <span data-ttu-id="80130-206">JIT 컴파일은 애플리케이션이 실행되는 동안 수행되므로 컴파일 시간이 실행 시간의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-206">Since JIT compilation occurs during execution of the application, compile time is part of the run time.</span></span> <span data-ttu-id="80130-207">따라서 JIT 컴파일러는 결과 코드가 생성할 수 있는 시간 단축과 코드 최적화에 소요된 시간의 균형을 맞춰야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-207">Thus, JIT compilers have to balance time spent optimizing code against the savings that the resulting code can produce.</span></span> <span data-ttu-id="80130-208">그러나 JIT는 실제 하드웨어를 인식하므로 개발자가 다른 구현을 제공할 필요가 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-208">But a JIT knows the actual hardware and can free developers from having to ship different implementations.</span></span>

## <a name="implementation-of-net"></a><span data-ttu-id="80130-209">.NET의 구현체</span><span class="sxs-lookup"><span data-stu-id="80130-209">implementation of .NET</span></span>

<span data-ttu-id="80130-210">.NET의 구현체에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="80130-210">An implementation of .NET includes:</span></span>

- <span data-ttu-id="80130-211">하나 이상의 런타임.</span><span class="sxs-lookup"><span data-stu-id="80130-211">One or more runtimes.</span></span> <span data-ttu-id="80130-212">예: [CLR](#clr), [CoreRT](#corert).</span><span class="sxs-lookup"><span data-stu-id="80130-212">Examples: [CLR](#clr), [CoreRT](#corert).</span></span>
- <span data-ttu-id="80130-213">.NET Standard의 버전을 구현하고 추가 API를 포함할 수 있는 클래스 라이브러리.</span><span class="sxs-lookup"><span data-stu-id="80130-213">A class library that implements a version of .NET Standard and may include additional APIs.</span></span> <span data-ttu-id="80130-214">예: [.NET Framework](#net-framework) 및 [.NET 5(및 .NET Core) 이상 버전](#net-5-and-later-versions)의 [BCL](#bcl).</span><span class="sxs-lookup"><span data-stu-id="80130-214">Examples: the [BCLs](#bcl) for [.NET Framework](#net-framework) and [.NET 5 (and .NET Core) and later versions](#net-5-and-later-versions).</span></span>
- <span data-ttu-id="80130-215">필요에 따라 하나 이상의 애플리케이션 프레임워크.</span><span class="sxs-lookup"><span data-stu-id="80130-215">Optionally, one or more application frameworks.</span></span> <span data-ttu-id="80130-216">예: [ASP.NET](#aspnet), Windows Forms 및 WPF는 .NET Framework 및 .NET 5에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="80130-216">Examples: [ASP.NET](#aspnet), Windows Forms, and WPF are included in the .NET Framework and .NET 5.</span></span>
- <span data-ttu-id="80130-217">필요에 따라 개발 도구.</span><span class="sxs-lookup"><span data-stu-id="80130-217">Optionally, development tools.</span></span> <span data-ttu-id="80130-218">일부 개발 도구는 여러 구현체에서 공통적으로 사용할 수 있음.</span><span class="sxs-lookup"><span data-stu-id="80130-218">Some development tools are shared among multiple implementations.</span></span>

<span data-ttu-id="80130-219">.NET 구현체의 예:</span><span class="sxs-lookup"><span data-stu-id="80130-219">Examples of .NET implementations:</span></span>

- [<span data-ttu-id="80130-220">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="80130-220">.NET Framework</span></span>](#net-framework)
- [<span data-ttu-id="80130-221">.NET 5 이상 버전(.NET Core 2.1~3.1 포함)</span><span class="sxs-lookup"><span data-stu-id="80130-221">.NET 5 and later versions (including .NET Core 2.1-3.1)</span></span>](#net-5-and-later-versions)
- [<span data-ttu-id="80130-222">UWP(유니버설 Windows 플랫폼)</span><span class="sxs-lookup"><span data-stu-id="80130-222">Universal Windows Platform (UWP)</span></span>](#uwp)
- [<span data-ttu-id="80130-223">Mono</span><span class="sxs-lookup"><span data-stu-id="80130-223">Mono</span></span>](#mono)

## <a name="library"></a><span data-ttu-id="80130-224">라이브러리</span><span class="sxs-lookup"><span data-stu-id="80130-224">library</span></span>

<span data-ttu-id="80130-225">앱이나 다른 라이브러리에서 호출할 수 있는 API 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-225">A collection of APIs that can be called by apps or other libraries.</span></span> <span data-ttu-id="80130-226">.NET 라이브러리는 하나 이상의 [어셈블리](#assembly)로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="80130-226">A .NET library is composed of one or more [assemblies](#assembly).</span></span>

<span data-ttu-id="80130-227">라이브러리 및 [프레임워크](#framework)라는 단어는 종종 같은 뜻으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="80130-227">The words library and [framework](#framework) are often used synonymously.</span></span>

## <a name="mono"></a><span data-ttu-id="80130-228">Mono</span><span class="sxs-lookup"><span data-stu-id="80130-228">Mono</span></span>

<span data-ttu-id="80130-229">Mono는 작은 런타임이 필요할 때 주로 사용되는 오픈 소스 [크로스 플랫폼](#cross-platform) .NET 구현체입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-229">Mono is an open source, [cross-platform](#cross-platform) .NET implementation that is mainly used when a small runtime is required.</span></span> <span data-ttu-id="80130-230">이는 Android, Mac, iOS, tvOS 및 watchOS에서 Xamarin 애플리케이션의 성능을 향상하는 런타임으로, 주로 작은 사용 공간이 필요한 앱에 초점을 맞춥니다.</span><span class="sxs-lookup"><span data-stu-id="80130-230">It is the runtime that powers Xamarin applications on Android, Mac, iOS, tvOS, and watchOS and is focused primarily on apps that require a small footprint.</span></span>

<span data-ttu-id="80130-231">Mono는 현재 게시된 .NET Standard 버전을 모두 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-231">It supports all of the currently published .NET Standard versions.</span></span>

<span data-ttu-id="80130-232">지금까지 Mono는 .NET Framework의 방대한 API를 구현하고 Unix에서 가장 인기 있는 기능의 일부를 따라서 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-232">Historically, Mono implemented the larger API of the .NET Framework and emulated some of the most popular capabilities on Unix.</span></span> <span data-ttu-id="80130-233">경우에 따라 Unix에서 해당 기능을 사용하는 .NET 애플리케이션을 실행하는 데도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="80130-233">It is sometimes used to run .NET applications that rely on those capabilities on Unix.</span></span>

<span data-ttu-id="80130-234">일반적으로 Mono는 [Just-In-Time 컴파일러](#jit)에서 사용되지만 iOS 같은 플랫폼에 사용되는 전체 [정적 컴파일러(Ahead-Of-Time 컴파일)](#aot) 기능도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-234">Mono is typically used with a [just-in-time compiler](#jit), but it also features a full [static compiler (ahead-of-time compilation)](#aot) that is used on platforms like iOS.</span></span>

<span data-ttu-id="80130-235">[Mono 설명서](https://www.mono-project.com/docs/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80130-235">See the [Mono documentation](https://www.mono-project.com/docs/).</span></span>

## <a name="net"></a><span data-ttu-id="80130-236">.NET</span><span class="sxs-lookup"><span data-stu-id="80130-236">.NET</span></span>

<span data-ttu-id="80130-237">[.NET Standard](#net-standard) 및 모든 [.NET 구현체](#implementation-of-net)와 워크로드에 대한 포괄적인 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-237">The umbrella term for [.NET Standard](#net-standard) and all [.NET implementations](#implementation-of-net) and workloads.</span></span> <span data-ttu-id="80130-238">항상 전체를 대문자로 표기하며 절대로 ".Net"을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-238">Always fully capitalized, never ".Net".</span></span>

<span data-ttu-id="80130-239">[.NET 5](#net-5-and-later-versions)(현재 미리 보기 상태)가 릴리스되면 모든 새로운 .NET 개발에 권장되는 .NET 구현이 되므로 일부 컨텍스트에서 “.NET”은 “.NET 5 이상 버전”을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-239">When [.NET 5](#net-5-and-later-versions) (currently in preview) is released, it will be the recommended .NET implementation for all new .NET development, and so in some contexts ".NET" will imply ".NET 5 and later versions."</span></span>

<span data-ttu-id="80130-240">[.NET 기본 사항](../fundamentals/index.yml)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80130-240">See [.NET fundamentals](../fundamentals/index.yml)</span></span>

## <a name="net-5-and-later-versions"></a><span data-ttu-id="80130-241">.NET 5 이상 버전</span><span class="sxs-lookup"><span data-stu-id="80130-241">.NET 5 and later versions</span></span>

<span data-ttu-id="80130-242">다양한 .NET 플랫폼에서 사용할 수 있는 고성능 오픈 소스 구현체입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-242">A cross-platform, high-performance, open-source implementation of .NET.</span></span> <span data-ttu-id="80130-243">[CLR](#clr)(공용 언어 런타임), [AOT](#aot) 런타임(개발 시 [CoreRT](#corert)), [BCL](#bcl)(기본 클래스 라이브러리) 및 [.NET SDK](#net-sdk)를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-243">Includes a Common Language Runtime ([CLR](#clr)), an [AOT](#aot) runtime ([CoreRT](#corert), in development), a Base Class Library ([BCL](#bcl)), and the [.NET SDK](#net-sdk).</span></span>

<span data-ttu-id="80130-244">이 .NET 구현의 초기 버전을 .NET Core라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-244">Earlier versions of this .NET implementation are known as .NET Core.</span></span> <span data-ttu-id="80130-245">.Net 5.0은 .NET Core 3.1 다음 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-245">.NET 5.0 is the next version following .NET Core 3.1.</span></span> <span data-ttu-id="80130-246">[.NET Framework](#net-framework)라고 알려진 이전 구현과 최신 .NET 구현을 혼동하지 않도록 버전 4를 건너뛰었습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-246">Version 4 was skipped to avoid confusing this newer implementation of .NET with the older implementation that is known as [.NET Framework](#net-framework).</span></span> <span data-ttu-id="80130-247">현재 버전의 .NET Framework는 4.8입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-247">The current version of .NET Framework is 4.8.</span></span>

<span data-ttu-id="80130-248">[.NET 기본 사항](../fundamentals/index.yml)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80130-248">See [.NET fundamentals](../fundamentals/index.yml).</span></span>

## <a name="net-cli"></a><span data-ttu-id="80130-249">.NET CLI</span><span class="sxs-lookup"><span data-stu-id="80130-249">.NET CLI</span></span>

<span data-ttu-id="80130-250">[.NET 5(및 .NET Core) 이상 버전](#net-5-and-later-versions)용 애플리케이션 및 라이브러리를 개발하기 위한 플랫폼 간 도구 체인입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-250">A cross-platform toolchain for developing applications and libraries for [.NET 5 (and .NET Core) and later versions](#net-5-and-later-versions).</span></span> <span data-ttu-id="80130-251">.NET Core CLI라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-251">Also known as the .NET Core CLI.</span></span>

<span data-ttu-id="80130-252">[.NET CLI](../core/tools/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80130-252">See [.NET CLI](../core/tools/index.md).</span></span>

## <a name="net-core"></a><span data-ttu-id="80130-253">.NET Core</span><span class="sxs-lookup"><span data-stu-id="80130-253">.NET Core</span></span>

<span data-ttu-id="80130-254">[.NET 5 이상 버전](#net-5-and-later-versions)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80130-254">See [.NET 5 and later versions](#net-5-and-later-versions).</span></span>

## <a name="net-framework"></a><span data-ttu-id="80130-255">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="80130-255">.NET Framework</span></span>

<span data-ttu-id="80130-256">Windows에서만 실행되는 .NET의 구현체입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-256">An implementation of .NET that runs only on Windows.</span></span> <span data-ttu-id="80130-257">[CLR](#clr)(공용 언어 런타임), [BCL](#bcl)(기본 클래스 라이브러리) 및 [ASP.NET](#aspnet), Windows Forms, WPF 등의 애플리케이션 프레임워크 라이브러리를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-257">Includes the Common Language Runtime ([CLR](#clr)), the Base Class Library ([BCL](#bcl)), and application framework libraries such as [ASP.NET](#aspnet), Windows Forms, and WPF.</span></span>

<span data-ttu-id="80130-258">[.NET Framework 가이드](../framework/index.yml)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80130-258">See [.NET Framework Guide](../framework/index.yml).</span></span>

## <a name="net-native"></a><span data-ttu-id="80130-259">.NET 네이티브</span><span class="sxs-lookup"><span data-stu-id="80130-259">.NET Native</span></span>

<span data-ttu-id="80130-260">[JIT](#jit)(Just-In-Time)와 반대로 네이티브 코드 [AOT](#aot)(Ahead-Of-Time)를 생성하는 컴파일러 툴 체인입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-260">A compiler tool chain that produces native code ahead-of-time ([AOT](#aot)), as opposed to just-in-time ([JIT](#jit)).</span></span>

<span data-ttu-id="80130-261">컴파일은 C++ 컴파일러 및 링커가 작동하는 방식과 유사하게 개발자의 컴퓨터에서 수행되며,</span><span class="sxs-lookup"><span data-stu-id="80130-261">Compilation happens on the developer's machine similar to the way a C++ compiler and linker works.</span></span> <span data-ttu-id="80130-262">사용되지 않는 코드를 제거하고 더 많은 시간을 최적화에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-262">It removes unused code and spends more time optimizing it.</span></span> <span data-ttu-id="80130-263">라이브러리에서 코드를 추출하여 실행 파일에 병합합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-263">It extracts code from libraries and merges them into the executable.</span></span> <span data-ttu-id="80130-264">결과는 전체 앱을 나타내는 단일 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-264">The result is a single module that represents the entire app.</span></span>

<span data-ttu-id="80130-265">UWP는 .NET 네이티브에서 지원하는 첫 번째 애플리케이션 프레임워크였습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-265">UWP was the first application framework supported by .NET Native.</span></span> <span data-ttu-id="80130-266">이제 Windows와 macOS, Linux용 네이티브 콘솔 앱 작성을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-266">Now, we support building native console apps for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="80130-267">[.NET 네이티브와 CoreRT 소개](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80130-267">See [Intro to .NET Native and CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)</span></span>

## <a name="net-sdk"></a><span data-ttu-id="80130-268">.NET SDK</span><span class="sxs-lookup"><span data-stu-id="80130-268">.NET SDK</span></span>

<span data-ttu-id="80130-269">개발자가 [.NET 5(및 .NET Core) 이상 버전](#net-5-and-later-versions)용 .NET 애플리케이션과 라이브러리를 만드는 데 사용할 수 있는 라이브러리 및 도구 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-269">A set of libraries and tools that allow developers to create .NET applications and libraries for [.NET 5 (and .NET Core) and later versions](#net-5-and-later-versions).</span></span> <span data-ttu-id="80130-270">.NET Core SDK라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-270">Also known as the .NET Core SDK.</span></span>

<span data-ttu-id="80130-271">앱을 빌드하기 위한 [.NET CLI](#net-cli), 앱을 빌드하고 실행하기 위한 .NET 라이브러리 및 런타임, CLI 명령을 실행하고 애플리케이션을 실행하는 dotnet 실행 파일(*dotnet.exe*)을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-271">Includes the [.NET CLI](#net-cli) for building apps, .NET libraries and runtime for building and running apps, and the dotnet executable (*dotnet.exe*) that runs CLI commands and runs applications.</span></span>

<span data-ttu-id="80130-272">[.NET SDK 개요](../core/sdk.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80130-272">See [.NET SDK Overview](../core/sdk.md).</span></span>

## <a name="net-standard"></a><span data-ttu-id="80130-273">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="80130-273">.NET Standard</span></span>

<span data-ttu-id="80130-274">모든 .NET 구현체에서 사용할 수 있는 .NET API의 공식 규격입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-274">A formal specification of .NET APIs that are available in each .NET implementation.</span></span>

<span data-ttu-id="80130-275">.NET Standard 규격은 설명서에서 라이브러리라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-275">The .NET Standard specification is sometimes called a library in the documentation.</span></span> <span data-ttu-id="80130-276">라이브러리는 API 구현체를 포함하므로 규격(인터페이스)뿐만 아니라 .NET Standard를 “라이브러리”라고 잘못 부르기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-276">Because a library includes API implementations, not only specifications (interfaces), it's misleading to call .NET Standard a "library."</span></span>

<span data-ttu-id="80130-277">[.NET Standard](net-standard.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80130-277">See [.NET Standard](net-standard.md).</span></span>

## <a name="ngen"></a><span data-ttu-id="80130-278">NGEN</span><span class="sxs-lookup"><span data-stu-id="80130-278">NGEN</span></span>

<span data-ttu-id="80130-279">네이티브(이미지) 생성입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-279">Native (image) generation.</span></span>

<span data-ttu-id="80130-280">해당 기술을 영구 [JIT](#jit) 컴파일러로 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-280">You can think of this technology as a persistent [JIT](#jit) compiler.</span></span> <span data-ttu-id="80130-281">일반적으로 코드가 실행되는 컴퓨터에서 코드를 컴파일하지만 컴파일은 대개 설치 시에 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="80130-281">It usually compiles code on the machine where the code is executed, but compilation typically occurs at install time.</span></span>

## <a name="package"></a><span data-ttu-id="80130-282">패키지</span><span class="sxs-lookup"><span data-stu-id="80130-282">package</span></span>

<span data-ttu-id="80130-283">NuGet 패키지(또는 줄여서 패키지)는 작성자 이름과 같은 추가 메타데이터와 함께 동일한 이름의 어셈블리가 하나 이상 있는 .zip 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-283">A NuGet package &mdash; or just a package &mdash; is a *.zip* file with one or more assemblies of the same name along with additional metadata such as the author name.</span></span>

<span data-ttu-id="80130-284">*.zip* 파일은 *.nupkg* 확장명을 사용하며 *.dll* 파일 및 *.xml* 파일과 같이 여러 대상 프레임워크 및 버전에서 사용할 자산을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-284">The *.zip* file has a *.nupkg* extension and may contain assets, such as *.dll* files and *.xml* files, for use with multiple target frameworks and versions.</span></span> <span data-ttu-id="80130-285">앱 또는 라이브러리에 설치된 경우 앱 또는 라이브러리에서 지정한 대상 프레임워크에 따라 적절한 자산이 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="80130-285">When installed in an app or library, the appropriate assets are selected based on the target framework specified by the app or library.</span></span> <span data-ttu-id="80130-286">인터페이스를 정의하는 자산은 *ref* 폴더에 있으며 구현을 정의하는 자산은 *lib* 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-286">The assets that define the interface are in the *ref* folder, and the assets that define the implementation are in the *lib* folder.</span></span>

## <a name="platform"></a><span data-ttu-id="80130-287">platform</span><span class="sxs-lookup"><span data-stu-id="80130-287">platform</span></span>

<span data-ttu-id="80130-288">Windows와 macOS, Linux, iOS, Android 같은 운영 체제와 해당 운영 체제가 실행되는 하드웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-288">An operating system and the hardware it runs on, such as Windows, macOS, Linux, iOS, and Android.</span></span>

<span data-ttu-id="80130-289">다음은 문장에서의 사용 예입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-289">Here are examples of usage in sentences:</span></span>

- <span data-ttu-id="80130-290">“.NET Core는 다양한 플랫폼에서 사용할 수 있는 .NET의 구현체입니다.”</span><span class="sxs-lookup"><span data-stu-id="80130-290">".NET Core is a cross-platform implementation of .NET."</span></span>
- <span data-ttu-id="80130-291">“PCL 프로필은 Microsoft 플랫폼을 나타내지만 .NET Standard는 플랫폼에 독립적입니다.”</span><span class="sxs-lookup"><span data-stu-id="80130-291">"PCL profiles represent Microsoft platforms, while .NET Standard is agnostic to platform."</span></span>

<span data-ttu-id="80130-292">레거시 .NET 설명서에서는 [.NET 구현](#implementation-of-net) 또는 모든 구현을 포함하는 .NET [스택](#stack)을 의미하는 용어로 “.NET 플랫폼”을 사용하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-292">Legacy .NET documentation sometimes uses ".NET platform" to mean either an [implementation of .NET](#implementation-of-net) or the .NET [stack](#stack) including all implementations.</span></span> <span data-ttu-id="80130-293">해당 용어는 둘 다 기본적인(OS/하드웨어) 의미와 혼동되므로 여기서는 해당 용어를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-293">Both of these usages tend to get confused with the primary (OS/hardware) meaning, so we try to avoid these usages.</span></span>

<span data-ttu-id="80130-294">“플랫폼”은 앱 빌드 및 실행을 위한 도구 및 라이브러리를 제공하는 소프트웨어를 나타내는 “개발자 플랫폼”이라는 관용구에서 다른 의미를 가집니다.</span><span class="sxs-lookup"><span data-stu-id="80130-294">"Platform" has a different meaning in the phrase "developer platform," which refers to software that provides tools and libraries for building and running apps.</span></span> <span data-ttu-id="80130-295">.NET은 다양한 유형의 애플리케이션을 빌드하기 위한 플랫폼 간 오픈 소스 개발자 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-295">.NET is a cross-platform, open source developer platform for building many different types of applications.</span></span>

## <a name="runtime"></a><span data-ttu-id="80130-296">런타임</span><span class="sxs-lookup"><span data-stu-id="80130-296">runtime</span></span>

<span data-ttu-id="80130-297">일반적으로 관리형 프로그램의 실행 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-297">In general, the execution environment for a managed program.</span></span> <span data-ttu-id="80130-298">OS는 런타임 환경의 일부이지만 .NET 런타임의 일부는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="80130-298">The OS is part of the runtime environment but is not part of the .NET runtime.</span></span> <span data-ttu-id="80130-299">해당 단어의 뜻 그대로 .NET 런타임의 몇 가지 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-299">Here are some examples of .NET runtimes in this sense of the word:</span></span>

- <span data-ttu-id="80130-300">[CLR](#clr)(공용 언어 런타임)</span><span class="sxs-lookup"><span data-stu-id="80130-300">Common Language Runtime ([CLR](#clr))</span></span>
- <span data-ttu-id="80130-301">.NET 네이티브(UWP)</span><span class="sxs-lookup"><span data-stu-id="80130-301">.NET Native (for UWP)</span></span>
- <span data-ttu-id="80130-302">Mono 런타임</span><span class="sxs-lookup"><span data-stu-id="80130-302">Mono runtime</span></span>

<span data-ttu-id="80130-303">“런타임”이라는 단어는 컨텍스트에 따라 여러 가지 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-303">The word "runtime" has a different meaning in some contexts:</span></span>

* <span data-ttu-id="80130-304">[.NET 5.0 다운로드 페이지](https://dotnet.microsoft.com/download/dotnet/5.0)의 ‘.NET 런타임’.</span><span class="sxs-lookup"><span data-stu-id="80130-304">*.NET runtime* on the [.NET 5.0 download page](https://dotnet.microsoft.com/download/dotnet/5.0).</span></span>

  <span data-ttu-id="80130-305">‘.NET 런타임’이나 다른 런타임(예: ‘ASP.NET Core 런타임’)을 다운로드할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="80130-305">You can download the *.NET runtime* or other runtimes, such as the *ASP.NET Core runtime*.</span></span> <span data-ttu-id="80130-306">이러한 사용에 대한 ‘런타임’은 머신에서 [프레임워크 종속](../core/deploying/index.md#publish-framework-dependent) 앱을 실행하기 위해 머신에 설치해야 하는 구성 요소 세트입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-306">A *runtime* in this usage is the set of components that must be installed on a machine to run a [framework-dependent](../core/deploying/index.md#publish-framework-dependent) app on the machine.</span></span> <span data-ttu-id="80130-307">.NET 런타임에는 [BCL](#bcl)을 제공하는 [CLR](#clr) 및 .NET [공유 프레임워크](#shared-framework)가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="80130-307">The .NET runtime includes the [CLR](#clr) and the .NET [shared framework](#shared-framework), which provides the [BCL](#bcl).</span></span>

* <span data-ttu-id="80130-308">‘.NET 런타임 라이브러리’</span><span class="sxs-lookup"><span data-stu-id="80130-308">*.NET runtime libraries*</span></span>

  <span data-ttu-id="80130-309">[BCL](#bcl)이 참조하는 것과 동일한 라이브러리를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-309">Refers to the same libraries that [BCL](#bcl) refers to.</span></span> <span data-ttu-id="80130-310">그러나 ASP.NET Core 런타임과 같은 다른 런타임에는 BCL을 기반으로 하는 추가 라이브러리와 함께 다른 [공유 프레임워크](#shared-framework)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-310">However, other runtimes, such as the ASP.NET Core runtime, have different [shared frameworks](#shared-framework), with additional libraries that build on the BCL.</span></span>

* <span data-ttu-id="80130-311">[RID(런타임 식별자)](../core/rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="80130-311">[Runtime Identifier (RID)](../core/rid-catalog.md).</span></span>

  <span data-ttu-id="80130-312">여기에서 ‘런타임’은 .NET 앱이 실행되는 OS 플랫폼 및 CPU 아키텍처를 의미합니다(예: `linux-x64`).</span><span class="sxs-lookup"><span data-stu-id="80130-312">*Runtime* here means the OS platform and CPU architecture that a .NET app runs on, for example: `linux-x64`.</span></span>

* <span data-ttu-id="80130-313">경우에 따라 “런타임”은 다음 예제와 같이 [.NET 구현](#implementation-of-net)의 의미로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="80130-313">Sometimes "runtime" is used in the sense of an [implementation of .NET](#implementation-of-net), as in the following examples:</span></span>

  - <span data-ttu-id="80130-314">“다양한 .NET 런타임에서 특정 버전의 .NET Standard를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-314">"The various .NET runtimes implement specific versions of .NET Standard.</span></span> <span data-ttu-id="80130-315">…</span><span class="sxs-lookup"><span data-stu-id="80130-315">…</span></span> <span data-ttu-id="80130-316">각 .NET 런타임 버전은 지원하는 최신 .NET Standard 버전을 보급합니다.”</span><span class="sxs-lookup"><span data-stu-id="80130-316">Each .NET runtime version advertises the highest .NET Standard version it supports …"</span></span>
  - <span data-ttu-id="80130-317">“여러 런타임에서 실행되도록 만들어진 라이브러리는 이 프레임워크를 대상으로 해야 합니다.”</span><span class="sxs-lookup"><span data-stu-id="80130-317">"Libraries that are intended to run on multiple runtimes should target this framework."</span></span> <span data-ttu-id="80130-318">(.NET Standard를 참조)</span><span class="sxs-lookup"><span data-stu-id="80130-318">(referring to .NET Standard)</span></span>

## <a name="shared-framework"></a><span data-ttu-id="80130-319">공유 프레임워크</span><span class="sxs-lookup"><span data-stu-id="80130-319">shared framework</span></span>

<span data-ttu-id="80130-320">의미는 컨텍스트에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="80130-320">Meaning depends on context.</span></span> <span data-ttu-id="80130-321">‘.NET 공유 프레임워크’는 [.NET 런타임](#runtime)에 포함된 라이브러리를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-321">The *.NET shared framework* refers to the libraries included in the [.NET runtime](#runtime).</span></span> <span data-ttu-id="80130-322">이 경우 [.NET 5(및 .NET Core) 이상 버전](#net-5-and-later-versions)의 ‘공유 프레임워크’는 [BCL](#bcl)이 참조하는 것과 동일한 라이브러리를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-322">In this case, the *shared framework* for [.NET 5 (and .NET Core) and later versions](#net-5-and-later-versions) refers to the same libraries that [BCL](#bcl) refers to.</span></span>

<span data-ttu-id="80130-323">다른 공유 프레임워크도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-323">There are other shared frameworks.</span></span> <span data-ttu-id="80130-324">‘ASP.NET Core 공유 프레임워크’는 BCL과 웹앱에서 사용할 추가 API를 포함하는 [ASP.NET Core 런타임](#runtime)에 포함된 라이브러리를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-324">The *ASP.NET Core shared framework* refers to the libraries included in the [ASP.NET Core runtime](#runtime), which includes the BCL plus additional APIs for use by web apps.</span></span>

<span data-ttu-id="80130-325">[프레임워크 종속 앱](../core/deploying/index.md#publish-framework-dependent)의 공유 프레임워크는 앱을 실행하는 머신의 폴더에 설치된 어셈블리에 포함되는 라이브러리로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="80130-325">For [framework-dependent apps](../core/deploying/index.md#publish-framework-dependent), the shared framework consists of libraries that are contained in assemblies installed in a folder on the machine that runs the app.</span></span> <span data-ttu-id="80130-326">[자체 포함 앱](../core/deploying/index.md#publish-self-contained)의 공유 프레임워크 어셈블리는 앱에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="80130-326">For [self-contained apps](../core/deploying/index.md#publish-self-contained), the shared framework assemblies are included with the app.</span></span>

<span data-ttu-id="80130-327">자세한 내용은 [Deep-dive into .NET Core primitives, part 2: the shared framework](https://natemcmaster.com/blog/2018/08/29/netcore-primitives-2/)(.NET Core 기본 형식 심층 분석, 2부: 공유 프레임워크)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80130-327">For more information, see [Deep-dive into .NET Core primitives, part 2: the shared framework](https://natemcmaster.com/blog/2018/08/29/netcore-primitives-2/).</span></span>

## <a name="stack"></a><span data-ttu-id="80130-328">스택</span><span class="sxs-lookup"><span data-stu-id="80130-328">stack</span></span>

<span data-ttu-id="80130-329">애플리케이션을 만들고 실행하는 데 사용되는 프로그래밍 기술 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-329">A set of programming technologies that are used together to build and run applications.</span></span>

<span data-ttu-id="80130-330">“.NET 스택”은 .NET Standard 및 모든 .NET 구현을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="80130-330">"The .NET stack" refers to .NET Standard and all .NET implementations.</span></span> <span data-ttu-id="80130-331">“.NET 스택”이라는 문구는 하나의 .NET 구현체를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="80130-331">The phrase "a .NET stack" may refer to one implementation of .NET.</span></span>

## <a name="target-framework"></a><span data-ttu-id="80130-332">대상 프레임워크(target framework)</span><span class="sxs-lookup"><span data-stu-id="80130-332">target framework</span></span>

<span data-ttu-id="80130-333">.NET 앱이나 라이브러리에서 사용하는 API 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-333">The collection of APIs that a .NET app or library relies on.</span></span>

<span data-ttu-id="80130-334">앱이나 라이브러리는 모든.NET 구현에서 표준화된 API 세트의 사양인 .NET Standard의 버전(예: .NET Standard 2.0)을 대상으로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-334">An app or library can target a version of .NET Standard (for example, .NET Standard 2.0), which is a specification for a standardized set of APIs across all .NET implementations.</span></span> <span data-ttu-id="80130-335">또한 앱이나는 라이브러리는 특정 .NET 구현체의 버전을 대상으로 할 수 있으며, 이 경우 구현체 관련 API에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-335">An app or library can also target a version of a specific .NET implementation, in which case it gets access to implementation-specific APIs.</span></span> <span data-ttu-id="80130-336">예를 들어 Xamarin.iOS를 대상으로 하는 앱은 Xamarin 제공 iOS API 래퍼에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-336">For example, an app that targets Xamarin.iOS gets access to Xamarin-provided iOS API wrappers.</span></span>

<span data-ttu-id="80130-337">일부 대상 프레임워크(예: .NET Framework)에서 사용 가능한 API는 .NET 구현체에서 시스템에 설치하는 어셈블리에 의해 정의되고 애플리케이션 프레임워크 API(예: ASP.NET, WinForms)를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-337">For some target frameworks (for example, the .NET Framework) the available APIs are defined by the assemblies that a .NET implementation installs on a system, which may include application framework APIs (for example, ASP.NET, WinForms).</span></span> <span data-ttu-id="80130-338">패키지 기반 대상 프레임워크(예: .NET Standard 및 .NET Core)에서 프레임워크 API는 앱이나 라이브러리에 설치된 패키지에 의해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="80130-338">For package-based target frameworks (such as .NET Standard and .NET Core), the framework APIs are defined by the packages installed in the app or library.</span></span> <span data-ttu-id="80130-339">이 경우 대상 프레임워크는 프레임워크를 구성하는 모든 패키지를 참조하는 패키지를 암시적으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-339">In that case, the target framework implicitly specifies a package that references all the packages that together make up the framework.</span></span>

<span data-ttu-id="80130-340">[대상 프레임워크](frameworks.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80130-340">See [Target Frameworks](frameworks.md).</span></span>

## <a name="tfm"></a><span data-ttu-id="80130-341">TFM</span><span class="sxs-lookup"><span data-stu-id="80130-341">TFM</span></span>

<span data-ttu-id="80130-342">대상 프레임워크 모니커입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-342">Target framework moniker.</span></span>

<span data-ttu-id="80130-343">.NET 앱이나 라이브러리의 대상 프레임워크를 지정하기 위한 표준화된 토큰 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-343">A standardized token format for specifying the target framework of a .NET app or library.</span></span> <span data-ttu-id="80130-344">대상 프레임워크는 일반적으로 `net462` 같은 짧은 이름으로 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-344">Target frameworks are typically referenced by a short name, such as `net462`.</span></span> <span data-ttu-id="80130-345">긴 형식의 TFM(예: .NETFramework,Version=4.6.2)이 있지만 일반적으로 대상 프레임워크를 지정하는 데 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-345">Long-form TFMs (such as .NETFramework,Version=4.6.2) exist but are not generally used to specify a target framework.</span></span>

<span data-ttu-id="80130-346">[대상 프레임워크](frameworks.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80130-346">See [Target Frameworks](frameworks.md).</span></span>

## <a name="uwp"></a><span data-ttu-id="80130-347">UWP</span><span class="sxs-lookup"><span data-stu-id="80130-347">UWP</span></span>

<span data-ttu-id="80130-348">유니버설 Windows 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-348">Universal Windows Platform.</span></span>

<span data-ttu-id="80130-349">IoT(사물 인터넷)에 대한 최신의 터치 가능 Windows 애플리케이션 및 소프트웨어를 작성하는 데 사용되는 .NET의 구현체입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-349">An implementation of .NET that is used for building modern, touch-enabled Windows applications and software for the Internet of Things (IoT).</span></span> <span data-ttu-id="80130-350">PC, 태블릿, 휴대폰, Xbox와 같은 대상으로 지정할 수 있는 다양한 종류의 디바이스를 통합하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-350">It's designed to unify the different types of devices that you may want to target, including PCs, tablets, phones, and even the Xbox.</span></span> <span data-ttu-id="80130-351">UWP는 중앙 집중식 앱 스토어, 실행 환경(AppContainer), Win32를 대체할 Windows API(WinRT) 등 많은 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-351">UWP provides many services, such as a centralized app store, an execution environment (AppContainer), and a set of Windows APIs to use instead of Win32 (WinRT).</span></span> <span data-ttu-id="80130-352">앱은 C++과 C#, Visual Basic, JavaScript로 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-352">Apps can be written in C++, C#, Visual Basic, and JavaScript.</span></span> <span data-ttu-id="80130-353">C#과 Visual Basic을 사용할 경우 .NET API는 .NET 5(및 .NET Core) 이상 버전에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="80130-353">When using C# and Visual Basic, the .NET APIs are provided by .NET 5 (and .NET Core) and later versions.</span></span>

## <a name="workload"></a><span data-ttu-id="80130-354">workload</span><span class="sxs-lookup"><span data-stu-id="80130-354">workload</span></span>

<span data-ttu-id="80130-355">다른 사람이 빌드 중인 앱의 유형.</span><span class="sxs-lookup"><span data-stu-id="80130-355">A type of app someone is building.</span></span> <span data-ttu-id="80130-356">[앱 모델](#app-model)보다 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-356">More generic than [app model](#app-model).</span></span> <span data-ttu-id="80130-357">예를 들어 이 문서를 포함하여 모든 .NET 문서 페이지의 맨 위에는 **워크로드** 에 대한 드롭다운 목록이 있습니다. 이를 통해 **웹**, **모바일**, **클라우드**, **데스크톱**, **기계 학습 \& 데이터** 에 대한 문서로 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-357">For example, at the top of every .NET documentation page, including this one, is a drop-down list for **Workloads**, which lets you switch to documentation for **Web**, **Mobile**, **Cloud**, **Desktop**, and **Machine Learning \& Data**.</span></span>

<span data-ttu-id="80130-358">일부 컨텍스트에서 *워크로드* 는 특정 유형의 앱을 지원하기 위해 설치할 수 있는 Visual Studio 기능 컬렉션을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-358">In some contexts, *workload* refers to a collection of Visual Studio features that you can choose to install to support a particular type of app.</span></span> <span data-ttu-id="80130-359">예를 들어 [워크로드 선택](../core/install/windows.md#select-a-workload)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80130-359">For an example, see [Select a workload](../core/install/windows.md#select-a-workload).</span></span>

## <a name="see-also"></a><span data-ttu-id="80130-360">참조</span><span class="sxs-lookup"><span data-stu-id="80130-360">See also</span></span>

- [<span data-ttu-id="80130-361">.NET 기본 사항</span><span class="sxs-lookup"><span data-stu-id="80130-361">.NET fundamentals</span></span>](../fundamentals/index.yml)
- [<span data-ttu-id="80130-362">.NET Framework 가이드</span><span class="sxs-lookup"><span data-stu-id="80130-362">.NET Framework Guide</span></span>](../framework/index.yml)
- [<span data-ttu-id="80130-363">ASP.NET 개요</span><span class="sxs-lookup"><span data-stu-id="80130-363">ASP.NET Overview</span></span>](/aspnet/index#pivot=aspnet)
- [<span data-ttu-id="80130-364">ASP.NET Core 개요</span><span class="sxs-lookup"><span data-stu-id="80130-364">ASP.NET Core Overview</span></span>](/aspnet/index#pivot=core)
