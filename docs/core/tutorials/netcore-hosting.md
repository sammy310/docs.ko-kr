---
title: 사용자 지정 .NET Core 런타임 호스트 작성
description: .NET Core 런타임의 작동 방식을 제어해야 하는 고급 시나리오를 지원하기 위해 네이티브 코드에서 .NET Core 런타임을 호스트하는 방법을 알아봅니다.
author: mjrousos
ms.topic: how-to
ms.date: 12/21/2018
ms.openlocfilehash: 4b6b0d9765d78aac5f267dfac4a907f920230feb
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102258223"
---
# <a name="write-a-custom-net-core-host-to-control-the-net-runtime-from-your-native-code"></a><span data-ttu-id="dbd30-103">사용자 지정 .NET Core 호스트를 작성하여 네이티브 코드에서 .NET 런타임 제어</span><span class="sxs-lookup"><span data-stu-id="dbd30-103">Write a custom .NET Core host to control the .NET runtime from your native code</span></span>

<span data-ttu-id="dbd30-104">모든 관리 코드와 같이 .NET Core 애플리케이션은 호스트에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-104">Like all managed code, .NET Core applications are executed by a host.</span></span> <span data-ttu-id="dbd30-105">호스트는 런타임(가비지 수집기 및 JIT와 같은 구성 요소 포함)을 시작하고 관리 진입점을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-105">The host is responsible for starting the runtime (including components like the JIT and garbage collector) and invoking managed entry points.</span></span>

<span data-ttu-id="dbd30-106">.NET Core 런타임 호스트는 고급 시나리오이며, .NET Core 빌드 프로세스는 .NET Core 애플리케이션을 실행하는 기본 호스트를 제공하므로 대부분의 경우 .NET Core 개발자는 호스트에 대해 걱정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-106">Hosting the .NET Core runtime is an advanced scenario and, in most cases, .NET Core developers don't need to worry about hosting because .NET Core build processes provide a default host to run .NET Core applications.</span></span> <span data-ttu-id="dbd30-107">그러나 일부 특수한 경우, 네이티브 프로세스에서 관리 코드를 호출하는 수단으로나 런타임 작동 방식에 대해 더 많은 제어 권한을 얻기 위해 .NET Core 런타임을 명시적으로 호스트한 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-107">In some specialized circumstances, though, it can be useful to explicitly host the .NET Core runtime, either as a means of invoking managed code in a native process or in order to gain more control over how the runtime works.</span></span>

<span data-ttu-id="dbd30-108">이 문서에서는 네이티브 코드에서 .NET Core 런타임을 시작하고 관리 코드를 실행하는 데 필요한 단계에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-108">This article gives an overview of the steps necessary to start the .NET Core runtime from native code and execute managed code in it.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dbd30-109">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="dbd30-109">Prerequisites</span></span>

<span data-ttu-id="dbd30-110">호스트는 네이티브 애플리케이션이기 때문에 이 자습서에서는 .NET Core를 호스트하는 C++ 애플리케이션을 생성을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-110">Because hosts are native applications, this tutorial covers constructing a C++ application to host .NET Core.</span></span> <span data-ttu-id="dbd30-111">[Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)에서 제공하는 C++ 개발 환경 같은 C++ 개발 환경이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-111">You will need a C++ development environment (such as that provided by [Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)).</span></span>

<span data-ttu-id="dbd30-112">또한 호스트를 테스트할 간단한 .NET Core 애플리케이션이 필요하므로 [.NET Core SDK](https://dotnet.microsoft.com/download)를 설치하고 [소규모 .NET Core 테스트 앱](with-visual-studio.md)(예: 'Hello World' 앱)을 빌드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-112">You will also want a simple .NET Core application to test the host with, so you should install the [.NET Core SDK](https://dotnet.microsoft.com/download) and [build a small .NET Core test app](with-visual-studio.md) (such as a 'Hello World' app).</span></span> <span data-ttu-id="dbd30-113">새로운 .NET Core 콘솔 프로젝트 템플릿으로 만든 'Hello World' 앱으로 충분합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-113">The 'Hello World' app created by the new .NET Core console project template is sufficient.</span></span>

## <a name="hosting-apis"></a><span data-ttu-id="dbd30-114">호스팅 API</span><span class="sxs-lookup"><span data-stu-id="dbd30-114">Hosting APIs</span></span>

<span data-ttu-id="dbd30-115">.NET Core를 호스트하는 데 사용할 수 있는 두 가지 API가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-115">There are two different APIs that can be used to host .NET Core.</span></span> <span data-ttu-id="dbd30-116">이 문서(및 관련 [샘플](https://github.com/dotnet/samples/tree/master/core/hosting))에서는 이 두 가지 옵션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-116">This article (and its associated [samples](https://github.com/dotnet/samples/tree/master/core/hosting)) covers these 2 options.</span></span>

* <span data-ttu-id="dbd30-117">.NET Core 3.0 이상에서 .NET Core 런타임을 호스트하는 기본 방법은 `nethost` 및 `hostfxr` 라이브러리 API를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-117">The preferred method of hosting the .NET Core runtime in .NET Core 3.0 and above is with the `nethost` and `hostfxr` libraries' APIs.</span></span> <span data-ttu-id="dbd30-118">이러한 진입점은 런타임을 찾아 초기화에 대해 설정하는 복잡성을 처리하고, 관리형 애플리케이션 시작과 정적 관리형 메서드 호출을 모두 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-118">These entry points handle the complexity of finding and setting up the runtime for initialization and allow both launching a managed application and calling into a static managed method.</span></span>
* <span data-ttu-id="dbd30-119">.NET Core 3.0보다 이전 버전에서 .NET Core 런타임을 호스트하는 기본 방법은 [`coreclrhost.h`](https://github.com/dotnet/runtime/blob/master/src/coreclr/hosts/inc/coreclrhost.h) API를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-119">The preferred method of hosting the .NET Core runtime prior to .NET Core 3.0 is with the [`coreclrhost.h`](https://github.com/dotnet/runtime/blob/master/src/coreclr/hosts/inc/coreclrhost.h) API.</span></span> <span data-ttu-id="dbd30-120">이 API는 런타임을 쉽게 시작 및 중지하고, 관리 코드를 호출하는 데 사용할 수 있는 함수를 제공합니다(관리 exe를 실행하거나 정적 관리 메서드를 호출하는 방식).</span><span class="sxs-lookup"><span data-stu-id="dbd30-120">This API exposes functions for easily starting and stopping the runtime and invoking managed code (either by launching a managed exe or by calling static managed methods).</span></span>

## <a name="sample-hosts"></a><span data-ttu-id="dbd30-121">샘플 호스트</span><span class="sxs-lookup"><span data-stu-id="dbd30-121">Sample Hosts</span></span>

<span data-ttu-id="dbd30-122">자습서에 설명된 단계를 보여주는 [샘플 호스트](https://github.com/dotnet/samples/tree/master/core/hosting)는 GitHub의 dotnet/samples 리포지토리에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-122">[Sample hosts](https://github.com/dotnet/samples/tree/master/core/hosting) demonstrating the steps outlined in the tutorials below are available in the dotnet/samples GitHub repository.</span></span> <span data-ttu-id="dbd30-123">샘플에 있는 주석은 이 자습서에서 번호가 매겨진 단계를 샘플에서 수행되는 위치와 명확하게 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-123">Comments in the samples clearly associate the numbered steps from these tutorials with where they're performed in the sample.</span></span> <span data-ttu-id="dbd30-124">다운로드 지침은 [샘플 및 자습서](../../samples-and-tutorials/index.md#view-and-download-samples)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dbd30-124">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#view-and-download-samples).</span></span>

<span data-ttu-id="dbd30-125">샘플 호스트는 학습 목적으로 사용되므로 오류 검사가 부족하며 효율성보다 가독성을 강조하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-125">Keep in mind that the sample hosts are meant to be used for learning purposes, so they are light on error checking and are designed to emphasize readability over efficiency.</span></span>

## <a name="create-a-host-using-nethosth-and-hostfxrh"></a><span data-ttu-id="dbd30-126">`nethost.h` 및 `hostfxr.h`를 사용하여 호스트 만들기</span><span class="sxs-lookup"><span data-stu-id="dbd30-126">Create a host using `nethost.h` and `hostfxr.h`</span></span>

<span data-ttu-id="dbd30-127">다음 단계에서는 `nethost` 및 `hostfxr` 라이브러리를 사용하여 네이티브 애플리케이션에서 .NET Core 런타임을 시작하고 관리형 정적 메서드를 호출하는 방법을 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-127">The following steps detail how to use the `nethost` and `hostfxr` libraries to start the .NET Core runtime in a native application and call into a managed static method.</span></span> <span data-ttu-id="dbd30-128">[샘플](https://github.com/dotnet/samples/tree/master/core/hosting/HostWithHostFxr)은 .NET SDK와 함께 설치된 `nethost` 헤더 및 라이브러리와 [dotnet/runtime](https://github.com/dotnet/runtime) 리포지토리의 [`coreclr_delegates.h`](https://github.com/dotnet/runtime/blob/master/src/installer/corehost/cli/coreclr_delegates.h) 및 [`hostfxr.h`](https://github.com/dotnet/runtime/blob/master/src/native/corehost/hostfxr.h) 파일 복사본을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-128">The [sample](https://github.com/dotnet/samples/tree/master/core/hosting/HostWithHostFxr) uses the `nethost` header and library installed with the .NET SDK and copies of the [`coreclr_delegates.h`](https://github.com/dotnet/runtime/blob/master/src/installer/corehost/cli/coreclr_delegates.h) and [`hostfxr.h`](https://github.com/dotnet/runtime/blob/master/src/native/corehost/hostfxr.h) files from the [dotnet/runtime](https://github.com/dotnet/runtime) repository.</span></span>

### <a name="step-1---load-hostfxr-and-get-exported-hosting-functions"></a><span data-ttu-id="dbd30-129">1단계 - `hostfxr`을 로드하고 내보낸 호스팅 함수 가져오기</span><span class="sxs-lookup"><span data-stu-id="dbd30-129">Step 1 - Load `hostfxr` and get exported hosting functions</span></span>

<span data-ttu-id="dbd30-130">`nethost` 라이브러리는 `hostfxr` 라이브러리를 찾기 위한 `get_hostfxr_path` 함수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-130">The `nethost` library provides the `get_hostfxr_path` function for locating the `hostfxr` library.</span></span> <span data-ttu-id="dbd30-131">`hostfxr` 라이브러리는 .NET Core 런타임을 호스트하기 위한 함수를 공개합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-131">The `hostfxr` library exposes functions for hosting the .NET Core runtime.</span></span> <span data-ttu-id="dbd30-132">함수의 전체 목록은 [`hostfxr.h`](https://github.com/dotnet/runtime/blob/master/src/native/corehost/hostfxr.h) 및 [기본 호스팅 디자인 문서](https://github.com/dotnet/runtime/blob/master/docs/design/features/native-hosting.md)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-132">The full list of functions can be found in [`hostfxr.h`](https://github.com/dotnet/runtime/blob/master/src/native/corehost/hostfxr.h) and the [native hosting design document](https://github.com/dotnet/runtime/blob/master/docs/design/features/native-hosting.md).</span></span> <span data-ttu-id="dbd30-133">샘플 및 이 자습서는 다음을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-133">The sample and this tutorial use the following:</span></span>

* <span data-ttu-id="dbd30-134">`hostfxr_initialize_for_runtime_config`: 호스트 컨텍스트를 초기화하고, 지정된 런타임 구성을 사용하여 .NET Core 런타임 초기화를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-134">`hostfxr_initialize_for_runtime_config`: Initializes a host context and prepares for initialization of the .NET Core runtime using the specified runtime configuration.</span></span>
* <span data-ttu-id="dbd30-135">`hostfxr_get_runtime_delegate`: 런타임 기능의 대리자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-135">`hostfxr_get_runtime_delegate`: Gets a delegate for runtime functionality.</span></span>
* <span data-ttu-id="dbd30-136">`hostfxr_close`: 호스트 컨텍스트를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-136">`hostfxr_close`: Closes a host context.</span></span>

<span data-ttu-id="dbd30-137">`get_hostfxr_path`를 사용하여 `hostfxr` 라이브러리를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-137">The `hostfxr` library is found using `get_hostfxr_path`.</span></span> <span data-ttu-id="dbd30-138">라이브러리가 로드되고, 해당 내보내기가 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-138">It is then loaded and its exports are retrieved.</span></span>

[!code-cpp[HostFxrHost#LoadHostFxr](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithHostFxr/src/NativeHost/nativehost.cpp#LoadHostFxr)]

### <a name="step-2---initialize-and-start-the-net-core-runtime"></a><span data-ttu-id="dbd30-139">2단계 - .NET Core 런타임 초기화 및 시작</span><span class="sxs-lookup"><span data-stu-id="dbd30-139">Step 2 - Initialize and start the .NET Core runtime</span></span>

<span data-ttu-id="dbd30-140">`hostfxr_initialize_for_runtime_config` 및 `hostfxr_get_runtime_delegate` 함수는 로드되는 관리형 구성 요소에 대한 런타임 구성을 사용하여 .NET Core 런타임을 초기화하고 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-140">The `hostfxr_initialize_for_runtime_config` and `hostfxr_get_runtime_delegate` functions initialize and start the .NET Core runtime using the runtime configuration for the managed component that will be loaded.</span></span> <span data-ttu-id="dbd30-141">`hostfxr_get_runtime_delegate` 함수는 관리형 어셈블리를 로드하고 해당 어셈블리의 정적 메서드에 대한 함수 포인터를 가져올 수 있도록 런타임 대리자를 가져오는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-141">The `hostfxr_get_runtime_delegate` function is used to get a runtime delegate that allows loading a managed assembly and getting a function pointer to a static method in that assembly.</span></span>

[!code-cpp[HostFxrHost#Initialize](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithHostFxr/src/NativeHost/nativehost.cpp#Initialize)]

### <a name="step-3---load-managed-assembly-and-get-function-pointer-to-a-managed-method"></a><span data-ttu-id="dbd30-142">3단계 - 관리형 어셈블리 로드 및 관리형 메서드에 대한 함수 포인터 가져오기</span><span class="sxs-lookup"><span data-stu-id="dbd30-142">Step 3 - Load managed assembly and get function pointer to a managed method</span></span>

<span data-ttu-id="dbd30-143">관리형 어셈블리를 로드하고 관리형 메서드에 대한 함수 포인터를 가져오기 위해 런타임 대리자가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-143">The runtime delegate is called to load the managed assembly and get a function pointer to a managed method.</span></span> <span data-ttu-id="dbd30-144">대리자는 어셈블리 경로, 형식 이름 및 메서드 이름을 입력으로 사용하고, 관리형 메서드를 호출하는 데 사용할 수 있는 함수 포인터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-144">The delegate requires the assembly path, type name, and method name as inputs and returns a function pointer that can be used to invoke the managed method.</span></span>

[!code-cpp[HostFxrHost#LoadAndGet](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithHostFxr/src/NativeHost/nativehost.cpp#LoadAndGet)]

<span data-ttu-id="dbd30-145">샘플에서는 런타임 대리자를 호출할 때 `nullptr`을 대리자 형식 이름으로 전달하여 기본 시그니처를 관리형 메서드에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-145">By passing `nullptr` as the delegate type name when calling the runtime delegate, the sample uses a default signature for the managed method:</span></span>

```csharp
public delegate int ComponentEntryPoint(IntPtr args, int sizeBytes);
```

<span data-ttu-id="dbd30-146">런타임 대리자를 호출할 때 대리자 형식 이름을 지정하면 다른 시그니처를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-146">A different signature can be used by specifying the delegate type name when calling the runtime delegate.</span></span>

### <a name="step-4---run-managed-code"></a><span data-ttu-id="dbd30-147">4단계 - 관리 코드 실행!</span><span class="sxs-lookup"><span data-stu-id="dbd30-147">Step 4 - Run managed code!</span></span>

<span data-ttu-id="dbd30-148">이제 기본 호스트가 관리형 메서드를 호출하고 원하는 매개 변수를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-148">The native host can now call the managed method and pass it the desired parameters.</span></span>

[!code-cpp[HostFxrHost#CallManaged](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithHostFxr/src/NativeHost/nativehost.cpp#CallManaged)]

## <a name="create-a-host-using-coreclrhosth"></a><span data-ttu-id="dbd30-149">`coreclrhost.h`를 사용하여 호스트 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="dbd30-149">Create a host using `coreclrhost.h`</span></span>

<span data-ttu-id="dbd30-150">다음 단계에서는 `coreclrhost.h` API를 사용하여 네이티브 애플리케이션에서 .NET Core 런타임을 시작하고 관리형 정적 메서드를 호출하는 방법을 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-150">The following steps detail how to use the `coreclrhost.h` API to start the .NET Core runtime in a native application and call into a managed static method.</span></span> <span data-ttu-id="dbd30-151">이 문서의 코드 조각은 Windows 관련 API를 사용하지만 [전체 샘플 호스트](https://github.com/dotnet/samples/tree/master/core/hosting/HostWithCoreClrHost)는 Windows 및 Linux 코드 경로를 모두 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-151">The code snippets in this document use some Windows-specific APIs, but the [full sample host](https://github.com/dotnet/samples/tree/master/core/hosting/HostWithCoreClrHost) shows both Windows and Linux code paths.</span></span>

<span data-ttu-id="dbd30-152">[Unix CoreRun 호스트](https://github.com/dotnet/runtime/tree/master/src/coreclr/hosts/unixcorerun)는 `coreclrhost.h`를 사용하여 더욱 복잡하고 현실적인 호스팅 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-152">The [Unix CoreRun host](https://github.com/dotnet/runtime/tree/master/src/coreclr/hosts/unixcorerun) shows a more complex, real-world example of hosting using `coreclrhost.h`.</span></span>

### <a name="step-1---find-and-load-coreclr"></a><span data-ttu-id="dbd30-153">1단계 - CoreCLR 찾기 및 로드</span><span class="sxs-lookup"><span data-stu-id="dbd30-153">Step 1 - Find and load CoreCLR</span></span>

<span data-ttu-id="dbd30-154">.NET Core 런타임 API는 *coreclr.dll*(Windows), *libcoreclr.so*(Linux) 또는 *libcoreclr.dylib*(macOS)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-154">The .NET Core runtime APIs are in *coreclr.dll* (on Windows), in *libcoreclr.so* (on Linux), or in *libcoreclr.dylib* (on macOS).</span></span> <span data-ttu-id="dbd30-155">.NET Core를 호스트하는 첫 번째 단계는 CoreCLR 라이브러리를 로드하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-155">The first step to hosting .NET Core is to load the CoreCLR library.</span></span> <span data-ttu-id="dbd30-156">여러 경로를 검색하거나 입력 매개 변수를 사용하여 라이브러리를 찾는 호스트가 있는 반면, 특정 경로에서 로드하는 것을 아는 호스트도 있습니다(예: 호스트 옆 또는 머신 수준의 위치에서).</span><span class="sxs-lookup"><span data-stu-id="dbd30-156">Some hosts probe different paths or use input parameters to find the library while others know to load it from a certain path (next to the host, for example, or from a machine-wide location).</span></span>

<span data-ttu-id="dbd30-157">발견된 라이브러리는 `LoadLibraryEx`(Windows) 또는 `dlopen`(Linux/macOS)을 사용하여 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-157">Once found, the library is loaded with `LoadLibraryEx` (on Windows) or `dlopen` (on Linux/macOS).</span></span>

[!code-cpp[CoreClrHost#1](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithCoreClrHost/src/SampleHost.cpp#1)]

### <a name="step-2---get-net-core-hosting-functions"></a><span data-ttu-id="dbd30-158">2단계 - .NET Core 호스팅 함수 가져오기</span><span class="sxs-lookup"><span data-stu-id="dbd30-158">Step 2 - Get .NET Core hosting functions</span></span>

<span data-ttu-id="dbd30-159">CoreClrHost에는 .NET Core를 호스팅하는 데 유용한 중요 메서드가 몇 개 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-159">CoreClrHost has several important methods useful for hosting .NET Core:</span></span>

* <span data-ttu-id="dbd30-160">`coreclr_initialize`: .NET Core 런타임을 시작하고 기본(그리고 유일한) AppDomain을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-160">`coreclr_initialize`: Starts the .NET Core runtime and sets up the default (and only) AppDomain.</span></span>
* <span data-ttu-id="dbd30-161">`coreclr_execute_assembly`: 관리되는 어셈블리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-161">`coreclr_execute_assembly`: Executes a managed assembly.</span></span>
* <span data-ttu-id="dbd30-162">`coreclr_create_delegate`: 관리되는 메서드에 대한 함수 포인터를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-162">`coreclr_create_delegate`: Creates a function pointer to a managed method.</span></span>
* <span data-ttu-id="dbd30-163">`coreclr_shutdown`: .NET Core 런타임을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-163">`coreclr_shutdown`: Shuts down the .NET Core runtime.</span></span>
* <span data-ttu-id="dbd30-164">`coreclr_shutdown_2`: `coreclr_shutdown`과 유사하지만 관리 코드의 종료 코드도 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-164">`coreclr_shutdown_2`: Like `coreclr_shutdown`, but also retrieves the managed code's exit code.</span></span>

<span data-ttu-id="dbd30-165">CoreCLR 라이브러리를 로드한 후 다음 단계는 `GetProcAddress`(Windows) 또는 `dlsym`(Linux/macOS)을 사용하여 이러한 함수에 대한 참조를 가져오는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-165">After loading the CoreCLR library, the next step is to get references to these functions using `GetProcAddress` (on Windows) or `dlsym` (on Linux/macOS).</span></span>

[!code-cpp[CoreClrHost#2](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithCoreClrHost/src/SampleHost.cpp#2)]

### <a name="step-3---prepare-runtime-properties"></a><span data-ttu-id="dbd30-166">3단계 - 런타임 속성 준비</span><span class="sxs-lookup"><span data-stu-id="dbd30-166">Step 3 - Prepare runtime properties</span></span>

<span data-ttu-id="dbd30-167">런타임을 시작하기 전에 동작을 지정하는 일부 속성을 준비해야 합니다(특히 어셈블리 로더 관련).</span><span class="sxs-lookup"><span data-stu-id="dbd30-167">Before starting the runtime, it is necessary to prepare some properties to specify behavior (especially concerning the assembly loader).</span></span>

<span data-ttu-id="dbd30-168">일반적인 속성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-168">Common properties include:</span></span>

* <span data-ttu-id="dbd30-169">`TRUSTED_PLATFORM_ASSEMBLIES` 런타임이 기본적으로 확인할 수 있는 어셈블리 경로의 목록입니다(Windows에서 ‘;’으로 구분되고 Linux에서 ‘:’으로 구분됨).</span><span class="sxs-lookup"><span data-stu-id="dbd30-169">`TRUSTED_PLATFORM_ASSEMBLIES` This is a list of assembly paths (delimited by ';' on Windows and ':' on Linux) which the runtime will be able to resolve by default.</span></span> <span data-ttu-id="dbd30-170">일부 호스트에는 로드할 수 있는 어셈블리를 나열하는 하드 코딩된 매니페스트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-170">Some hosts have hard-coded manifests listing assemblies they can load.</span></span> <span data-ttu-id="dbd30-171">다른 호스트는 이 목록의 특정 위치(예: *coreclr.dll* 옆)에 라이브러리를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-171">Others will put any library in certain locations (next to *coreclr.dll*, for example) on this list.</span></span>
* <span data-ttu-id="dbd30-172">`APP_PATHS` TPA(신뢰할 수 있는 플랫폼 어셈블리) 목록에서 찾을 수 없는 경우 어셈블리에 대해 검색하는 경로 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-172">`APP_PATHS` This is a list of paths to probe in for an assembly if it can't be found in the trusted platform assemblies (TPA) list.</span></span> <span data-ttu-id="dbd30-173">호스트는 TPA 목록을 사용하여 로드되는 어셈블리를 더 세부적으로 제어할 수 있지만 호스트가 로드해야 하는 어셈블리를 결정하고 명시적으로 나열하는 것이 가장 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-173">Because the host has more control over which assemblies are loaded using the TPA list, it is a best practice for hosts to determine which assemblies they expect to load and list them explicitly.</span></span> <span data-ttu-id="dbd30-174">하지만 런타임 시 검색이 필요한 경우 이 속성으로 해당 시나리오를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-174">If probing at run time is needed, however, this property can enable that scenario.</span></span>
* <span data-ttu-id="dbd30-175">`APP_NI_PATHS` 이 목록은 네이티브 이미지에 대해 검색되는 경로를 제외하고, APP_PATHS와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-175">`APP_NI_PATHS` This list is similar to APP_PATHS except that it's meant to be paths that will be probed for native images.</span></span>
* <span data-ttu-id="dbd30-176">`NATIVE_DLL_SEARCH_DIRECTORIES` 이 속성은 p/invoke를 통해 호출되는 네이티브 라이브러리를 찾을 때 로더에서 검색해야 하는 경로 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-176">`NATIVE_DLL_SEARCH_DIRECTORIES` This property is a list of paths the loader should probe when looking for native libraries called via p/invoke.</span></span>
* <span data-ttu-id="dbd30-177">`PLATFORM_RESOURCE_ROOTS` 이 목록에는 (문화권별 하위 디렉터리에서) 리소스 위성 어셈블리에 대해 검색하는 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-177">`PLATFORM_RESOURCE_ROOTS` This list includes paths to probe in for resource satellite assemblies (in culture-specific subdirectories).</span></span>

<span data-ttu-id="dbd30-178">이 샘플 호스트에서는 현재 디렉터리의 모든 라이브러리를 나열하기만 하면 TPA 목록이 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-178">In this sample host, the TPA list is constructed by simply listing all libraries in the current directory:</span></span>

[!code-cpp[CoreClrHost#7](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithCoreClrHost/src/SampleHost.cpp#7)]

<span data-ttu-id="dbd30-179">간단한 샘플이기 때문에 `TRUSTED_PLATFORM_ASSEMBLIES` 속성만 있으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-179">Because the sample is simple, it only needs the `TRUSTED_PLATFORM_ASSEMBLIES` property:</span></span>

[!code-cpp[CoreClrHost#3](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithCoreClrHost/src/SampleHost.cpp#3)]

### <a name="step-4---start-the-runtime"></a><span data-ttu-id="dbd30-180">4단계 - 런타임 시작</span><span class="sxs-lookup"><span data-stu-id="dbd30-180">Step 4 - Start the runtime</span></span>

<span data-ttu-id="dbd30-181">`coreclrhost.h` API는 런타임을 시작하고 단일 호출을 사용하여 기본 AppDomain을 모두 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-181">`coreclrhost.h` APIs start the runtime and create the default AppDomain all with a single call.</span></span> <span data-ttu-id="dbd30-182">`coreclr_initialize` 함수는 이전에 설명한 기본 경로, 이름, 속성을 허용하고, `hostHandle` 매개 변수를 통해 호스트에 대한 핸들을 다시 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-182">The `coreclr_initialize` function takes a base path, name, and the properties described earlier and returns back a handle to the host via the `hostHandle` parameter.</span></span>

[!code-cpp[CoreClrHost#4](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithCoreClrHost/src/SampleHost.cpp#4)]

### <a name="step-5---run-managed-code"></a><span data-ttu-id="dbd30-183">5단계 - 관리 코드 실행</span><span class="sxs-lookup"><span data-stu-id="dbd30-183">Step 5 - Run managed code!</span></span>

<span data-ttu-id="dbd30-184">런타임이 시작되면 호스트가 관리 코드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-184">With the runtime started, the host can call managed code.</span></span> <span data-ttu-id="dbd30-185">이는 두 가지 방법으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-185">This can be done in a couple of different ways.</span></span> <span data-ttu-id="dbd30-186">이 자습서에 연결된 샘플 코드는 `coreclr_create_delegate` 함수를 사용하여 정적 관리 메서드에 대한 대리자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-186">The sample code linked to this tutorial uses the `coreclr_create_delegate` function to create a delegate to a static managed method.</span></span> <span data-ttu-id="dbd30-187">이 API는 [어셈블리 이름](../../standard/assembly/names.md), 네임스페이스로 한정된 형식 이름, 메서드 이름을 입력으로 허용하고, 메서드를 호출하는 데 사용할 수 있는 대리자를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-187">This API takes the [assembly name](../../standard/assembly/names.md), namespace-qualified type name, and method name as inputs and returns a delegate that can be used to invoke the method.</span></span>

[!code-cpp[CoreClrHost#5](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithCoreClrHost/src/SampleHost.cpp#5)]

<span data-ttu-id="dbd30-188">이 샘플에서 호스트는 이제 `managedDelegate`를 호출하여 `ManagedWorker.DoWork` 메서드를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-188">In this sample, the host can now call `managedDelegate` to run the `ManagedWorker.DoWork` method.</span></span>

<span data-ttu-id="dbd30-189">또는 `coreclr_execute_assembly` 함수를 사용하여 관리되는 실행 파일을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-189">Alternatively, the `coreclr_execute_assembly` function can be used to launch a managed executable.</span></span> <span data-ttu-id="dbd30-190">이 API는 어셈블리 경로 및 인수 배열을 입력매개 변수로 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-190">This API takes an assembly path and array of arguments as input parameters.</span></span> <span data-ttu-id="dbd30-191">해당 경로의 어셈블리를 로드하고 기본 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-191">It loads the assembly at that path and invokes its main method.</span></span>

```c++
int hr = executeAssembly(
        hostHandle,
        domainId,
        argumentCount,
        arguments,
        "HelloWorld.exe",
        (unsigned int*)&exitCode);
```

### <a name="step-6---shutdown-and-clean-up"></a><span data-ttu-id="dbd30-192">6단계 - 종료 및 정리</span><span class="sxs-lookup"><span data-stu-id="dbd30-192">Step 6 - Shutdown and clean up</span></span>

<span data-ttu-id="dbd30-193">마지막으로 호스트가 관리 코드 실행을 완료하면 `coreclr_shutdown` 또는 `coreclr_shutdown_2`를 사용하여 .NET Core 런타임이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-193">Finally, when the host is done running managed code, the .NET Core runtime is shut down with `coreclr_shutdown` or `coreclr_shutdown_2`.</span></span>

[!code-cpp[CoreClrHost#6](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithCoreClrHost/src/SampleHost.cpp#6)]

<span data-ttu-id="dbd30-194">CoreCLR은 다시 초기화 또는 언로드를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-194">CoreCLR does not support reinitialization or unloading.</span></span> <span data-ttu-id="dbd30-195">`coreclr_initialize`를 다시 호출하거나 CoreCLR 라이브러리를 언로드하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="dbd30-195">Do not call `coreclr_initialize` again or unload the CoreCLR library.</span></span>

## <a name="conclusion"></a><span data-ttu-id="dbd30-196">결론</span><span class="sxs-lookup"><span data-stu-id="dbd30-196">Conclusion</span></span>

<span data-ttu-id="dbd30-197">호스트가 빌드되면 명령줄에서 실행하고 호스트에서 예상하는 인수를 전달하여 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-197">Once your host is built, it can be tested by running it from the command line and passing any arguments the host expects.</span></span> <span data-ttu-id="dbd30-198">실행할 호스트에 대해 .NET Core 앱을 지정할 때 `dotnet build`로 생성된 .dll을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="dbd30-198">When specifying the .NET Core app for the host to run, be sure to use the .dll that is produced by `dotnet build`.</span></span> <span data-ttu-id="dbd30-199">자체 포함된 애플리케이션에 대해 `dotnet publish`로 생성된 실행 파일(.exe 파일)이 실제로 기본 .NET Core 호스트이며(앱이 주 시나리오의 명령줄에서 직접 실행될 수 있음), 사용자 코드는 동일한 이름의 DLL로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-199">Executables (.exe files) produced by `dotnet publish` for self-contained applications are actually the default .NET Core host (so that the app can be launched directly from the command line in mainline scenarios); user code is compiled into a dll of the same name.</span></span>

<span data-ttu-id="dbd30-200">처음에 작동되지 않으면, 호스트가 예상한 위치에서 *coreclr.dll* 을 사용할 수 있고, 필요한 프레임워크 라이브러리가 모두 TPA 목록에 있으며 CoreCLR의 비트 수(32비트 또는 64비트)가 호스트가 빌드된 방식과 일치하는지 다시 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-200">If things don't work initially, double-check that *coreclr.dll* is available in the location expected by the host, that all necessary Framework libraries are in the TPA list, and that CoreCLR's bitness (32-bit or 64-bit) matches how the host was built.</span></span>

<span data-ttu-id="dbd30-201">.NET Core 런타임 호스트는 일부 개발자만 필요로 하는 고급 시나리오이지만, 네이티브 프로세스에서 관리 코드를 실행해야 하거나 .NET Core 런타임의 동작에 대해 더 많은 제어권이 필요한 경우 아주 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd30-201">Hosting the .NET Core runtime is an advanced scenario that many developers won't require, but for those who need to launch managed code from a native process, or who need more control over the .NET Core runtime's behavior, it can be very useful.</span></span>
