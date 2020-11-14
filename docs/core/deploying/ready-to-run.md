---
title: ReadyToRun 배포 개요
description: ReadyToRun 배포의 정의와 .NET 5 및 .NET Core 3.0 이상 버전을 사용하여 앱을 게시하는 과정에서 사용을 고려해야 하는 이유를 알아봅니다.
author: davidwr
ms.author: davidwr
ms.date: 09/21/2020
ms.openlocfilehash: cd8eaebd05d79b11e90e255e702a52220fffda76
ms.sourcegitcommit: ffd4d5e824db6c5f0c3521c0e802fd9e8f0edcbe
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2020
ms.locfileid: "93342633"
---
# <a name="readytorun-compilation"></a><span data-ttu-id="d38e2-103">ReadyToRun 컴파일</span><span class="sxs-lookup"><span data-stu-id="d38e2-103">ReadyToRun Compilation</span></span>

<span data-ttu-id="d38e2-104">ReadyToRun(R2R) 형식으로 애플리케이션 어셈블리를 컴파일하면 .NET Core 애플리케이션의 시작 시간과 대기 시간을 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-104">.NET application startup time and latency can be improved by compiling your application assemblies as ReadyToRun (R2R) format.</span></span> <span data-ttu-id="d38e2-105">R2R은 AOT(Ahead-Of-Time) 컴파일 양식입니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-105">R2R is a form of ahead-of-time (AOT) compilation.</span></span>

<span data-ttu-id="d38e2-106">R2R 이진 파일은 애플리케이션이 로드될 때 JIT(Just-In-Time) 컴파일러에서 수행해야 하는 작업량을 줄여 시작 성능을 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-106">R2R binaries improve startup performance by reducing the amount of work the just-in-time (JIT) compiler needs to do as your application loads.</span></span> <span data-ttu-id="d38e2-107">이진 파일에는 JIT에서 생성되는 코드와 비슷한 네이티브 코드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-107">The binaries contain similar native code compared to what the JIT would produce.</span></span> <span data-ttu-id="d38e2-108">그러나 R2R 이진 파일은 일부 시나리오에서 필요한 IL(중간 언어) 코드와 동일한 코드의 네이티브 버전을 모두 포함하므로 크기가 더 큽니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-108">However, R2R binaries are larger because they contain both intermediate language (IL) code, which is still needed for some scenarios, and the native version of the same code.</span></span> <span data-ttu-id="d38e2-109">R2R은 Linux x64 또는 Windows x64와 같은 특정 런타임 환경(RID)을 대상으로 하는 앱을 게시하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-109">R2R is only available when you publish an app that targets specific runtime environments (RID) such as Linux x64 or Windows x64.</span></span>

<span data-ttu-id="d38e2-110">프로젝트를 ReadyToRun으로 컴파일하려면 PublishReadyToRun 속성을 true로 설정하여 애플리케이션을 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-110">To compile your project as ReadyToRun, the application must be published with the PublishReadyToRun property set to true.</span></span>

<span data-ttu-id="d38e2-111">앱을 ReadyToRun으로 게시하는 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-111">There are two ways to publish your app as ReadyToRun:</span></span>

01. <span data-ttu-id="d38e2-112">PublishReadyToRun 플래그를 dotnet publish 명령에 직접 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-112">Specify the PublishReadyToRun flag directly to the dotnet publish command.</span></span> <span data-ttu-id="d38e2-113">자세한 내용은 [dotnet publish](../tools/dotnet-publish.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d38e2-113">See [dotnet publish](../tools/dotnet-publish.md) for details.</span></span>

    ```dotnetcli
    dotnet publish -c Release -r win-x64 -p:PublishReadyToRun=true
    ```

02. <span data-ttu-id="d38e2-114">프로젝트에서 속성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-114">Specify the property in the project</span></span>

    - <span data-ttu-id="d38e2-115">프로젝트에 `<PublishReadyToRun>` 설정을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-115">Add the `<PublishReadyToRun>` setting to your project.</span></span>

    ```xml
    <PropertyGroup>
      <PublishReadyToRun>true</PublishReadyToRun>
    </PropertyGroup>
    ```

    - <span data-ttu-id="d38e2-116">특수 매개 변수 없이 애플리케이션을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-116">Publish the application without any special parameters.</span></span>

    ```dotnetcli
    dotnet publish -c Release -r win-x64
    ```

## <a name="impact-of-using-the-readytorun-feature"></a><span data-ttu-id="d38e2-117">ReadyToRun 기능 사용의 영향</span><span class="sxs-lookup"><span data-stu-id="d38e2-117">Impact of using the ReadyToRun feature</span></span>

<span data-ttu-id="d38e2-118">Ahead of Time 컴파일을 수행하면 애플리케이션 성능에 예측하기 어려운 복잡한 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-118">Ahead-of-time compilation has complex performance impact on application performance, which may be difficult to predict.</span></span> <span data-ttu-id="d38e2-119">일반적으로 어셈블리의 크기가 2~3배 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-119">In general, the size of an assembly will grow to between two to three times larger.</span></span> <span data-ttu-id="d38e2-120">파일의 실제 크기가 이렇게 증가하면 디스크에서 어셈블리를 로드하는 성능이 저하되고 프로세스의 작업 집합이 증가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-120">This increase in the physical size of the file may reduce the performance of loading the assembly from disk, and increase working set of the process.</span></span> <span data-ttu-id="d38e2-121">반면 런타임에 컴파일되는 메서드의 수는 일반적으로 크게 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-121">However, in return the number of methods compiled at runtime is typically reduced substantially.</span></span> <span data-ttu-id="d38e2-122">결과적으로 코드의 양이 많은 대부분의 애플리케이션은 ReadyToRun을 사용하여 큰 성능상 이득을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-122">The result is that most applications that have large amounts of code receive large performance benefits from enabling ReadyToRun.</span></span> <span data-ttu-id="d38e2-123">코드의 양이 적은 애플리케이션은 .NET 런타임 라이브러리가 이미 ReadyToRun으로 미리 컴파일되어 있으므로 ReadyToRun 사용으로 성능이 크게 향상될 가능성이 적습니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-123">Applications, which have small amounts of code will likely not experience a significant improvement from enabling ReadyToRun, as the .NET runtime libraries have already been precompiled with ReadyToRun.</span></span>

<span data-ttu-id="d38e2-124">여기서 설명하는 시작 개선은 애플리케이션 시작뿐 아니라 애플리케이션의 코드를 처음 사용할 때도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-124">The startup improvement discussed here applies not only to application startup, but also to the first use of any code in the application.</span></span> <span data-ttu-id="d38e2-125">예를 들어 ReadyToRun을 사용하면 ASP.NET 애플리케이션에서 웹 API를 처음 사용할 때 응답 대기 시간을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-125">For instance, ReadyToRun can be used to reduce the response latency of the first use  of Web API in an ASP.NET application.</span></span>

### <a name="interaction-with-tiered-compilation"></a><span data-ttu-id="d38e2-126">계층화된 컴파일과의 상호 작용</span><span class="sxs-lookup"><span data-stu-id="d38e2-126">Interaction with tiered compilation</span></span>

<span data-ttu-id="d38e2-127">미리 생성된 코드는 JIT에 의해 생성되는 코드만큼 고도로 최적화되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-127">Ahead-of-time generated is not as highly optimized as code produced by the JIT.</span></span> <span data-ttu-id="d38e2-128">이 문제를 해결하기 위해 계층화된 컴파일은 일반적으로 사용되는 ReadyToRun 메서드를 JIT 생성 메서드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-128">To address this issue, tiered compilation will replace commonly used ReadyToRun methods with JIT-generated methods.</span></span>

## <a name="how-is-the-set-of-precompiled-assemblies-chosen"></a><span data-ttu-id="d38e2-129">미리 컴파일되는 어셈블리 집합은 어떻게 선택되나요?</span><span class="sxs-lookup"><span data-stu-id="d38e2-129">How is the set of precompiled assemblies chosen?</span></span>

<span data-ttu-id="d38e2-130">SDK는 애플리케이션과 함께 배포되는 어셈블리를 미리 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-130">The SDK will precompile the assemblies that are distributed with the application.</span></span> <span data-ttu-id="d38e2-131">자체 포함 애플리케이션의 경우 이 어셈블리 집합에 프레임워크가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-131">For self-contained applications, this set of assemblies will include the framework.</span></span> <span data-ttu-id="d38e2-132">C++/CLI 이진 파일은 ReadyToRun 컴파일에 적합하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-132">C++/CLI binaries are not eligible for ReadyToRun compilation.</span></span>

## <a name="how-is-the-set-of-methods-to-precompile-chosen"></a><span data-ttu-id="d38e2-133">미리 컴파일할 메서드 집합은 어떻게 선택되나요?</span><span class="sxs-lookup"><span data-stu-id="d38e2-133">How is the set of methods to precompile chosen?</span></span>

<span data-ttu-id="d38e2-134">컴파일러는 최대한 많은 메서드를 미리 컴파일하려 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-134">The compiler will attempt to pre-compile as many methods as it can.</span></span> <span data-ttu-id="d38e2-135">그러나 예상하지 못한 다양한 이유로 ReadyToRun 기능을 사용하면 JIT가 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-135">However various reasons it is not expected that using the ReadyToRun feature will result in preventing the JIT from executing.</span></span>

<span data-ttu-id="d38e2-136">이러한 이유에는 다음이 포함되지만 이에 국한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-136">Such reasons may include, but are not limited to:</span></span>

- <span data-ttu-id="d38e2-137">별도의 어셈블리에 정의된 제네릭 형식 사용</span><span class="sxs-lookup"><span data-stu-id="d38e2-137">Use of generic types defined in separate assemblies</span></span>
- <span data-ttu-id="d38e2-138">네이티브 코드와의 Interop</span><span class="sxs-lookup"><span data-stu-id="d38e2-138">Interop with native code</span></span>
- <span data-ttu-id="d38e2-139">컴파일러가 입증할 수 없는 하드웨어 내장 함수는 대상 컴퓨터에서 안전하게 사용 가능</span><span class="sxs-lookup"><span data-stu-id="d38e2-139">Use of hardware intrinsics that the compiler cannot prove are safe to use on a target machine</span></span>
- <span data-ttu-id="d38e2-140">일부 비정상적인 IL 패턴</span><span class="sxs-lookup"><span data-stu-id="d38e2-140">Certain unusual IL patterns</span></span>
- <span data-ttu-id="d38e2-141">리플렉션을 통한 동적 메서드 생성 또는 LINQ</span><span class="sxs-lookup"><span data-stu-id="d38e2-141">Dynamic method creation via reflection, or LINQ</span></span>

## <a name="cross-platformarchitecture-restrictions"></a><span data-ttu-id="d38e2-142">교차 플랫폼/아키텍처 제한 사항</span><span class="sxs-lookup"><span data-stu-id="d38e2-142">Cross platform/architecture restrictions</span></span>

<span data-ttu-id="d38e2-143">일부 SDK 플랫폼의 경우 ReadyToRun 컴파일러는 다른 대상 플랫폼에 크로스 컴파일을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-143">For some SDK platforms, the ReadyToRun compiler is capable of cross-compiling for other target platforms.</span></span> <span data-ttu-id="d38e2-144">지원되는 컴파일 대상은 아래 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-144">Supported compilation targets are described in the table below.</span></span>

| <span data-ttu-id="d38e2-145">SDK 플랫폼</span><span class="sxs-lookup"><span data-stu-id="d38e2-145">SDK platform</span></span> | <span data-ttu-id="d38e2-146">지원되는 대상 플랫폼</span><span class="sxs-lookup"><span data-stu-id="d38e2-146">Supported target platforms</span></span> |
| ------------ | --------------------------- |
| <span data-ttu-id="d38e2-147">Windows X64</span><span class="sxs-lookup"><span data-stu-id="d38e2-147">Windows X64</span></span>  | <span data-ttu-id="d38e2-148">Windows X86, Windows X64, Windows ARM32, Windows ARM64</span><span class="sxs-lookup"><span data-stu-id="d38e2-148">Windows X86, Windows X64, Windows ARM32, Windows ARM64</span></span> |
| <span data-ttu-id="d38e2-149">Windows X86</span><span class="sxs-lookup"><span data-stu-id="d38e2-149">Windows X86</span></span>  | <span data-ttu-id="d38e2-150">Windows X86, Windows ARM32</span><span class="sxs-lookup"><span data-stu-id="d38e2-150">Windows X86, Windows ARM32</span></span> |
| <span data-ttu-id="d38e2-151">Linux X64</span><span class="sxs-lookup"><span data-stu-id="d38e2-151">Linux X64</span></span>    | <span data-ttu-id="d38e2-152">Linux X86, Linux X64, Linux ARM32, Linux ARM64</span><span class="sxs-lookup"><span data-stu-id="d38e2-152">Linux X86, Linux X64, Linux ARM32, Linux ARM64</span></span> |
| <span data-ttu-id="d38e2-153">Linux ARM32</span><span class="sxs-lookup"><span data-stu-id="d38e2-153">Linux ARM32</span></span>  | <span data-ttu-id="d38e2-154">Linux ARM32</span><span class="sxs-lookup"><span data-stu-id="d38e2-154">Linux ARM32</span></span> |
| <span data-ttu-id="d38e2-155">Linux ARM64</span><span class="sxs-lookup"><span data-stu-id="d38e2-155">Linux ARM64</span></span>  | <span data-ttu-id="d38e2-156">Linux ARM64</span><span class="sxs-lookup"><span data-stu-id="d38e2-156">Linux ARM64</span></span> |
| <span data-ttu-id="d38e2-157">macOS X64</span><span class="sxs-lookup"><span data-stu-id="d38e2-157">macOS X64</span></span>    | <span data-ttu-id="d38e2-158">macOS X64</span><span class="sxs-lookup"><span data-stu-id="d38e2-158">macOS X64</span></span> |
