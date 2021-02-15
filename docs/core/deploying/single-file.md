---
title: 단일 파일 애플리케이션
description: 단일 파일 애플리케이션이란 무엇이고, 이 애플리케이션 배포 모델 사용을 왜 고려해야 하는지를 알아봅니다.
author: lakshanf
ms.author: lakshanf
ms.date: 12/17/2020
ms.openlocfilehash: fb768fa6fe390fbe8390e441f4eb71c3172ad395
ms.sourcegitcommit: f2ab02d9a780819ca2e5310bbcf5cfe5b7993041
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2021
ms.locfileid: "99505428"
---
# <a name="single-file-deployment-and-executable"></a><span data-ttu-id="3ce2a-103">단일 파일 배포 및 실행 파일</span><span class="sxs-lookup"><span data-stu-id="3ce2a-103">Single file deployment and executable</span></span>

<span data-ttu-id="3ce2a-104">모든 애플리케이션 종속 파일을 하나의 이진 파일로 묶으면 애플리케이션 개발자가 애플리케이션을 단일 파일로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-104">Bundling all application-dependent files into a single binary provides an application developer with the attractive option to deploy and distribute the application as a single file.</span></span> <span data-ttu-id="3ce2a-105">이 배포 모델은 .NET Core 3.0부터 사용할 수 있었으며 .NET 5.0에서 향상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-105">This deployment model has been available since .NET Core 3.0 and has been enhanced in .NET 5.0.</span></span> <span data-ttu-id="3ce2a-106">이전의 .NET Core 3.0에서는 사용자가 단일 파일 앱을 실행할 때 .NET Core 호스트에서 먼저 모든 파일을 임시 디렉터리로 추출한 후 애플리케이션을 실행했습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-106">Previously in .NET Core 3.0, when a user runs your single-file app, .NET Core host first extracts all files to a temporary directory before running the application.</span></span> <span data-ttu-id="3ce2a-107">.NET 5.0에서는 앱에서 파일을 추출할 필요 없이 코드를 직접 실행하여 이 환경을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-107">.NET 5.0 improves this experience by directly running the code without the need to extract the files from the app.</span></span>

<span data-ttu-id="3ce2a-108">단일 파일 배포는 [프레임워크 종속 배포 모델](index.md#publish-framework-dependent)과 [자체 포함 애플리케이션](index.md#publish-self-contained)에 모두 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-108">Single File deployment is available for both the [framework-dependent deployment model](index.md#publish-framework-dependent) and [self-contained applications](index.md#publish-self-contained).</span></span> <span data-ttu-id="3ce2a-109">자체 포함 애플리케이션의 단일 파일 크기는 런타임 및 프레임워크 라이브러리를 포함하므로 커집니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-109">The size of the single file in a self-contained application will be large since it will include the runtime and the framework libraries.</span></span> <span data-ttu-id="3ce2a-110">단일 파일 배포 옵션을 [ReadyToRun](ready-to-run.md) 및 [Trim(.NET 5.0의 실험적 기능)](trim-self-contained.md) 게시 옵션과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-110">The single file deployment option can be combined with [ReadyToRun](ready-to-run.md) and [Trim (an experimental feature in .NET 5.0)](trim-self-contained.md) publish options.</span></span>

## <a name="api-incompatibility"></a><span data-ttu-id="3ce2a-111">API 비호환성</span><span class="sxs-lookup"><span data-stu-id="3ce2a-111">API incompatibility</span></span>

<span data-ttu-id="3ce2a-112">일부 API는 단일 파일 배포와 호환되지 않으며, 이러한 API를 사용하는 애플리케이션은 수정이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-112">Some APIs are not compatible with single-file deployment and applications may require modification if they use these APIs.</span></span> <span data-ttu-id="3ce2a-113">사용 중인 타사 프레임워크나 패키지에도 이러한 API 중 하나가 사용될 수 있으며, 이 경우 수정이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-113">If you use a third-party framework or package, it's possible that they may also use one of these APIs and need modification.</span></span> <span data-ttu-id="3ce2a-114">문제의 가장 일반적인 원인은 애플리케이션과 함께 제공되는 파일 또는 DLL의 파일 경로에 대한 종속성입니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-114">The most common cause of problems is dependence on file paths for files or DLLs shipped with the application.</span></span>

<span data-ttu-id="3ce2a-115">아래 표에는 단일 파일 사용을 위한 관련 런타임 라이브러리 API 세부 정보가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-115">The table below has the relevant runtime library API details for single-file use.</span></span>

| <span data-ttu-id="3ce2a-116">API</span><span class="sxs-lookup"><span data-stu-id="3ce2a-116">API</span></span>                            | <span data-ttu-id="3ce2a-117">참고</span><span class="sxs-lookup"><span data-stu-id="3ce2a-117">Note</span></span>                                                                   |
|--------------------------------|------------------------------------------------------------------------|
| `Assembly.Location`            | <span data-ttu-id="3ce2a-118">빈 문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-118">Returns an empty string.</span></span>                                               |
| `Module.FullyQualifiedName`    | <span data-ttu-id="3ce2a-119">`<Unknown>` 값이 포함된 문자열을 반환하거나 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-119">Returns a string with the value of `<Unknown>` or throws an exception.</span></span> |
| `Module.Name`                  | <span data-ttu-id="3ce2a-120">`<Unknown>` 값이 포함된 문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-120">Returns a string with the value of `<Unknown>`.</span></span>                        |
| `Assembly.GetFile`             | <span data-ttu-id="3ce2a-121"><xref:System.IO.IOException>을 버립니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-121">Throws <xref:System.IO.IOException>.</span></span>                                   |
| `Assembly.GetFiles`            | <span data-ttu-id="3ce2a-122"><xref:System.IO.IOException>을 버립니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-122">Throws <xref:System.IO.IOException>.</span></span>                                   |
| `Assembly.CodeBase`            | <span data-ttu-id="3ce2a-123"><xref:System.PlatformNotSupportedException>을 버립니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-123">Throws <xref:System.PlatformNotSupportedException>.</span></span>                    |
| `Assembly.EscapedCodeBase`     | <span data-ttu-id="3ce2a-124"><xref:System.PlatformNotSupportedException>을 버립니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-124">Throws <xref:System.PlatformNotSupportedException>.</span></span>                    |
| `AssemblyName.CodeBase`        | <span data-ttu-id="3ce2a-125">`null`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-125">Returns `null`.</span></span>                                                        |
| `AssemblyName.EscapedCodeBase` | <span data-ttu-id="3ce2a-126">`null`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-126">Returns `null`.</span></span>                                                        |

<span data-ttu-id="3ce2a-127">일반적인 시나리오를 해결하기 위한 몇 가지 권장 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-127">We have some recommendations for fixing common scenarios:</span></span>

* <span data-ttu-id="3ce2a-128">실행 파일 옆의 파일에 액세스하려면 <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType>을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-128">To access files next to the executable, use <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType>.</span></span>

* <span data-ttu-id="3ce2a-129">실행 파일의 파일 이름을 찾으려면 <xref:System.Environment.GetCommandLineArgs?displayProperty=nameWithType>의 첫 번째 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-129">To find the file name of the executable, use the first element of <xref:System.Environment.GetCommandLineArgs?displayProperty=nameWithType>.</span></span>

* <span data-ttu-id="3ce2a-130">느슨한 파일이 제공되는 것을 완전히 방지하려면 [포함 리소스](../../framework/resources/creating-resource-files-for-desktop-apps.md)를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-130">To avoid shipping loose files entirely, consider using [embedded resources](../../framework/resources/creating-resource-files-for-desktop-apps.md).</span></span>

## <a name="attaching-a-debugger"></a><span data-ttu-id="3ce2a-131">디버거 연결</span><span class="sxs-lookup"><span data-stu-id="3ce2a-131">Attaching a debugger</span></span>

<span data-ttu-id="3ce2a-132">Linux에서 자체 포함 단일 파일 프로세스나 디버그 크래시 덤프에 연결할 수 있는 유일한 디버거는 [LLDB를 포함한 SOS](../diagnostics/dotnet-sos.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-132">On Linux, the only debugger which can attach to self-contained single-file processes or debug crash dumps is [SOS with LLDB](../diagnostics/dotnet-sos.md).</span></span>

<span data-ttu-id="3ce2a-133">Windows와 Mac에서는 Visual Studio 및 VS Code를 사용하여 크래시 덤프를 디버그할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-133">On Windows and Mac, Visual Studio and VS Code can be used to debug crash dumps.</span></span> <span data-ttu-id="3ce2a-134">실행 중인 자체 포함 단일 파일 실행 파일에 연결하려면 추가 파일 _mscordbi.{dll,so}_ 가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-134">Attaching to a running self-contained single-file executable requires an extra file: _mscordbi.{dll,so}_.</span></span>

<span data-ttu-id="3ce2a-135">이 파일이 없으면 Visual Studio에서 “프로세스에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-135">Without this file Visual Studio may produce the error "Unable to attach to the process.</span></span> <span data-ttu-id="3ce2a-136">디버그 구성 요소가 설치되지 않았습니다.” 오류가 발생할 수 있고,</span><span class="sxs-lookup"><span data-stu-id="3ce2a-136">A debug component is not installed."</span></span> <span data-ttu-id="3ce2a-137">VS Code에서는 “프로세스에 연결하지 못했습니다: 알 수 없는 오류: 0x80131c3c” 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-137">and VS Code may produce the error "Failed to attach to process: Unknown Error: 0x80131c3c."</span></span>

<span data-ttu-id="3ce2a-138">이러한 오류를 해결하려면 실행 파일 옆에 _mscordbi_ 를 복사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-138">To fix these errors, _mscordbi_ needs to be copied next to the executable.</span></span> <span data-ttu-id="3ce2a-139">_mscordbi_ 는 기본적으로 애플리케이션의 런타임 ID를 사용하여 하위 디렉터리에 `publish`됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-139">_mscordbi_ is `publish`ed by default in the subdirectory with the application's runtime ID.</span></span> <span data-ttu-id="3ce2a-140">따라서 예를 들어 `-r win-x64` 매개 변수를 사용하여 Windows용 `dotnet` CLI로 자체 포함 단일 파일 실행 파일을 게시하는 경우 실행 파일은 _bin/Debug/net5.0/win-x64/publish_ 에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-140">So, for example, if one were to publish a self-contained single-file executable using the `dotnet` CLI for Windows using the parameters `-r win-x64`, the executable would be placed in _bin/Debug/net5.0/win-x64/publish_.</span></span> <span data-ttu-id="3ce2a-141">_mscordbi.dll_ 복사본은 _bin/Debug/net5.0/win-x64_ 에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-141">A copy of _mscordbi.dll_ would be present in _bin/Debug/net5.0/win-x64_.</span></span>

## <a name="other-considerations"></a><span data-ttu-id="3ce2a-142">기타 고려 사항</span><span class="sxs-lookup"><span data-stu-id="3ce2a-142">Other considerations</span></span>

<span data-ttu-id="3ce2a-143">단일 파일은 기본적으로 네이티브 라이브러리를 묶지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-143">Single-file doesn't bundle native libraries by default.</span></span> <span data-ttu-id="3ce2a-144">Linux에서는 런타임을 번들로 사전 링크하며, 애플리케이션 네이티브 라이브러리만 단일 파일 앱과 동일한 디렉터리에 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-144">On Linux, we prelink the runtime into the bundle and only application native libraries are deployed to the same directory as the single-file app.</span></span> <span data-ttu-id="3ce2a-145">Windows에서는 호스팅 코드만 사전 링크하며, 런타임 및 애플리케이션 네이티브 라이브러리가 모두 단일 파일 앱과 동일한 디렉터리에 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-145">On Windows, we prelink only the hosting code and both the runtime and application native libraries are deployed to the same directory as the single-file app.</span></span> <span data-ttu-id="3ce2a-146">그러면 네이티브 파일을 단일 파일에서 제외해야 하는 좋은 디버깅 환경이 보장됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-146">This is to ensure a good debugging experience, which requires native files to be excluded from the single file.</span></span> <span data-ttu-id="3ce2a-147">`IncludeNativeLibrariesForSelfExtract` 플래그를 설정하면 네이티브 라이브러리가 단일 파일 번들에 포함되지만 단일 파일 애플리케이션을 실행할 때 클라이언트 머신의 임시 디렉터리에 파일이 추출됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-147">There is an option to set a flag, `IncludeNativeLibrariesForSelfExtract`, to include native libraries in the single file bundle, but these files will be extracted to a temporary directory in the client machine when the single file application is run.</span></span>

<span data-ttu-id="3ce2a-148">`IncludeAllContentForSelfExtract`를 지정하면 실행 파일을 실행하기 전에 모든 파일이 추출됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-148">Specifying `IncludeAllContentForSelfExtract` will extract all files before running the executable.</span></span> <span data-ttu-id="3ce2a-149">이렇게 하면 원래 .NET Core 단일 파일 배포 동작이 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-149">This preserves the original .NET Core single-file deployment behavior.</span></span>

<span data-ttu-id="3ce2a-150">단일 파일 애플리케이션에는 관련된 모든 PDB 파일이 함께 포함되며, 기본적으로 함께 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-150">Single-file application will have all related PDB files alongside it and will not be bundled by default.</span></span> <span data-ttu-id="3ce2a-151">빌드하는 프로젝트의 어셈블리 내부에 PDB를 포함하려면 [아래](#include-pdb-files-inside-the-bundle) 설명된 대로 `DebugType`을 `embedded`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-151">If you want to include PDBs inside the assembly for projects you build, set the `DebugType` to `embedded` as described [below](#include-pdb-files-inside-the-bundle) in detail.</span></span>

<span data-ttu-id="3ce2a-152">관리형 C++ 구성 요소는 단일 파일 배포에 적합하지 않으므로 단일 파일과 호환되도록 C# 또는 다른 비관리형 C++ 언어로 애플리케이션을 작성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-152">Managed C++ components aren't well suited for single-file deployment and we recommend that you write applications in C# or another non-managed C++ language to be single-file compatible.</span></span>

## <a name="exclude-files-from-being-embedded"></a><span data-ttu-id="3ce2a-153">파일이 포함되지 않도록 제외</span><span class="sxs-lookup"><span data-stu-id="3ce2a-153">Exclude files from being embedded</span></span>

<span data-ttu-id="3ce2a-154">다음 메타데이터를 설정하면 특정 파일이 단일 파일에 포함되지 않도록 명시적으로 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-154">Certain files can be explicitly excluded from being embedded in the single-file by setting following metadata:</span></span>

```xml
<ExcludeFromSingleFile>true</ExcludeFromSingleFile>
```

<span data-ttu-id="3ce2a-155">예를 들어 일부 파일을 게시 디렉터리에 저장하지만 단일 파일에 묶이지 않도록 하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-155">For example, to place some files in the publish directory but not bundle them in the single-file:</span></span>

```xml
<ItemGroup>
  <Content Update="Plugin.dll">
    <CopyToPublishDirectory>PreserveNewest</CopyToPublishDirectory>
    <ExcludeFromSingleFile>true</ExcludeFromSingleFile>
  </Content>
</ItemGroup>
```

## <a name="include-pdb-files-inside-the-bundle"></a><span data-ttu-id="3ce2a-156">번들 내에 PDB 파일 포함</span><span class="sxs-lookup"><span data-stu-id="3ce2a-156">Include PDB files inside the bundle</span></span>

<span data-ttu-id="3ce2a-157">어셈블리의 PDB 파일은 아래 설정을 사용하여 어셈블리 자체(`.dll`)에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-157">The PDB file for an assembly can be embedded into the assembly itself (the `.dll`) using the setting below.</span></span> <span data-ttu-id="3ce2a-158">기호는 어셈블리의 일부이므로 단일 파일 애플리케이션의 일부가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-158">Since the symbols are part of the assembly, they will be part of the single-file application as well:</span></span>

```xml
<DebugType>embedded</DebugType>
```

<span data-ttu-id="3ce2a-159">예를 들어 어셈블리의 프로젝트 파일에 다음 속성을 추가하여 해당 어셈블리에 PDB 파일을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-159">For example, add the following property to the project file of an assembly to embed the PDB file to that assembly:</span></span>

```xml
<PropertyGroup>
  <DebugType>embedded</DebugType>
</PropertyGroup>
```

## <a name="publish-a-single-file-app---sample-project-file"></a><span data-ttu-id="3ce2a-160">단일 파일 앱 게시 - 샘플 프로젝트 파일</span><span class="sxs-lookup"><span data-stu-id="3ce2a-160">Publish a single file app - sample project file</span></span>

<span data-ttu-id="3ce2a-161">다음은 단일 파일 게시를 지정하는 샘플 프로젝트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-161">Here's a sample project file that specifies single-file publishing:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
    <PublishSingleFile>true</PublishSingleFile>
    <SelfContained>true</SelfContained>
    <RuntimeIdentifier>win-x64</RuntimeIdentifier>
    <PublishTrimmed>true</PublishTrimmed>
    <PublishReadyToRun>true</PublishReadyToRun>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="3ce2a-162">위 속성에는 다음과 같은 함수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-162">These properties have the following functions:</span></span>

* <span data-ttu-id="3ce2a-163">`PublishSingleFile` - 단일 파일 게시를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-163">`PublishSingleFile` - Enables single-file publishing.</span></span>
* <span data-ttu-id="3ce2a-164">`SelfContained` - 앱이 자체 포함인지, 프레임워크 종속인지를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-164">`SelfContained` - Determines whether the app will be self-contained or framework-dependent.</span></span>
* <span data-ttu-id="3ce2a-165">`RuntimeIdentifier` - 대상으로 할 [OS 및 CPU 종류](../rid-catalog.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-165">`RuntimeIdentifier` - Specifies the [OS and CPU type](../rid-catalog.md) you are targeting.</span></span>
* <span data-ttu-id="3ce2a-166">`PublishTrimmed` - 자체 포함 앱에만 지원되는 [어셈블리 트리밍](trim-self-contained.md)을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-166">`PublishTrimmed` - Enables use of [assembly trimming](trim-self-contained.md), which is only supported for self-contained apps.</span></span>
* <span data-ttu-id="3ce2a-167">`PublishReadyToRun` - [AOT(Ahead-Of-Time) 컴파일](ready-to-run.md)을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-167">`PublishReadyToRun` - Enables [ahead-of-time (AOT) compilation](ready-to-run.md).</span></span>

<span data-ttu-id="3ce2a-168">**참고:**</span><span class="sxs-lookup"><span data-stu-id="3ce2a-168">**Notes:**</span></span>

* <span data-ttu-id="3ce2a-169">앱은 OS 및 아키텍처별로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-169">Apps are OS and architecture-specific.</span></span> <span data-ttu-id="3ce2a-170">Linux x64, Linux ARM64, Windows x64 등과 같은 각 구성에 대해 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-170">You need to publish for each configuration, such as Linux x64, Linux ARM64, Windows x64, and so forth.</span></span>
* <span data-ttu-id="3ce2a-171">*\*.runtimeconfig.json* 과 같은 구성 파일은 단일 파일에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-171">Configuration files, such as *\*.runtimeconfig.json*, are included in the single file.</span></span> <span data-ttu-id="3ce2a-172">추가 구성 파일이 필요한 경우 단일 파일 옆에 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-172">If an additional configuration file is needed, you can place it beside the single file.</span></span>

## <a name="publish-a-single-file-app---cli"></a><span data-ttu-id="3ce2a-173">단일 파일 앱 게시 - CLI</span><span class="sxs-lookup"><span data-stu-id="3ce2a-173">Publish a single file app - CLI</span></span>

<span data-ttu-id="3ce2a-174">[dotnet publish](../tools/dotnet-publish.md) 명령을 사용하여 단일 파일 애플리케이션을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-174">Publish a single file application using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span> <span data-ttu-id="3ce2a-175">앱을 게시할 때 다음 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-175">When you publish your app, set the following properties:</span></span>

- <span data-ttu-id="3ce2a-176">특정 런타임에 대해 게시: `-r win-x64`</span><span class="sxs-lookup"><span data-stu-id="3ce2a-176">Publish for a specific runtime: `-r win-x64`</span></span>
- <span data-ttu-id="3ce2a-177">단일 파일로 게시: `-p:PublishSingleFile=true`</span><span class="sxs-lookup"><span data-stu-id="3ce2a-177">Publish as a single-file: `-p:PublishSingleFile=true`</span></span>

<span data-ttu-id="3ce2a-178">다음 예제에서는 Windows용 앱을 자체 포함 단일 파일 애플리케이션으로 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-178">The following example publishes an app for Windows as a self-contained single file application.</span></span>

```dotnetcli
dotnet publish -r win-x64 -p:PublishSingleFile=true --self-contained true
```

<span data-ttu-id="3ce2a-179">다음 예제에서는 Linux용 앱을 프레임워크 종속 단일 파일 애플리케이션으로 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-179">The following example publishes an app for Linux as a framework dependent single file application.</span></span>

```dotnetcli
dotnet publish -r linux-x64 -p:PublishSingleFile=true --self-contained false
```

<span data-ttu-id="3ce2a-180">자세한 내용은 [.NET Core CLI를 사용하여 .NET Core 앱 게시](deploy-with-cli.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-180">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="publish-a-single-file-app---visual-studio"></a><span data-ttu-id="3ce2a-181">단일 파일 앱 게시 - Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3ce2a-181">Publish a single file app - Visual Studio</span></span>

<span data-ttu-id="3ce2a-182">Visual Studio는 애플리케이션의 게시 방식을 제어하는 재사용 가능한 게시 프로필을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-182">Visual Studio creates reusable publishing profiles that control how your application is published.</span></span>

01. <span data-ttu-id="3ce2a-183">**솔루션 탐색기** 창에서 게시할 프로젝트를 마우스 오른쪽 단추로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-183">On the **Solution Explorer** pane, right-click on the project you want to publish.</span></span> <span data-ttu-id="3ce2a-184">**게시** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-184">Select **Publish**.</span></span>

    :::image type="content" source="media/single-file/visual-studio-solution-explorer.png" alt-text="오른쪽 클릭 메뉴에서 게시 옵션이 강조 표시된 솔루션 탐색기.":::

    <span data-ttu-id="3ce2a-186">기존 게시 프로필이 없는 경우 지침에 따라 게시 프로필을 만들고 **폴더** 대상 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-186">If you don't already have a publishing profile, follow the instructions to create one and choose the **Folder** target-type.</span></span>

01. <span data-ttu-id="3ce2a-187">**편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-187">Choose **Edit**.</span></span>

    :::image type="content" source="media/single-file/visual-studio-publish-edit-settings.png" alt-text="편집 단추가 있는 Visual Studio 게시 프로필.":::

01. <span data-ttu-id="3ce2a-189">**프로필 설정** 대화 상자에서 다음 옵션을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-189">In the **Profile settings** dialog, set the following options:</span></span>

    - <span data-ttu-id="3ce2a-190">**배포 모드** 를 **자체 포함** 또는 **프레임워크 종속** 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-190">Set **Deployment mode** to **Self-contained** or **Framework-dependent**.</span></span>
    - <span data-ttu-id="3ce2a-191">**대상 런타임** 을 게시할 플랫폼으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-191">Set **Target runtime** to the platform you want to publish to.</span></span> <span data-ttu-id="3ce2a-192">(**이식 가능** 이외의 항목이어야 합니다.)</span><span class="sxs-lookup"><span data-stu-id="3ce2a-192">(Must be something other than **Portable**.)</span></span>
    - <span data-ttu-id="3ce2a-193">**단일 파일 생성** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-193">Select **Produce single file**.</span></span>

    <span data-ttu-id="3ce2a-194">**저장** 을 선택하여 설정을 저장하고 **게시** 대화 상자로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-194">Choose **Save** to save the settings and return to the **Publish** dialog.</span></span>

    :::image type="content" source="media/single-file/visual-studio-publish-single-file-properties.png" alt-text="배포 모드, 대상 런타임, 단일 파일 옵션이 강조 표시된 프로필 설정 대화 상자":::

01. <span data-ttu-id="3ce2a-196">**게시** 를 선택하여 앱을 단일 파일로 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-196">Choose **Publish** to publish your app as a single file.</span></span>

<span data-ttu-id="3ce2a-197">자세한 내용은 [Visual Studio를 사용하여 .NET Core 앱 게시](deploy-with-vs.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-197">For more information, see [Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>

## <a name="publish-a-single-file-app---visual-studio-for-mac"></a><span data-ttu-id="3ce2a-198">단일 파일 앱 게시 - Mac용 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3ce2a-198">Publish a single file app - Visual Studio for Mac</span></span>

<span data-ttu-id="3ce2a-199">Mac용 Visual Studio에서는 앱을 단일 파일로 게시하는 옵션을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-199">Visual Studio for Mac doesn't provide options to publish your app as a single file.</span></span> <span data-ttu-id="3ce2a-200">[단일 파일 앱 게시 - CLI](#publish-a-single-file-app---cli) 섹션의 지침에 따라 수동으로 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-200">You'll need to publish manually by following the instructions from the [Publish a single file app - CLI](#publish-a-single-file-app---cli) section.</span></span> <span data-ttu-id="3ce2a-201">자세한 내용은 [.NET Core CLI를 사용하여 .NET Core 앱 게시](deploy-with-cli.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3ce2a-201">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3ce2a-202">참조</span><span class="sxs-lookup"><span data-stu-id="3ce2a-202">See also</span></span>

- <span data-ttu-id="3ce2a-203">[.NET Core 애플리케이션 배포](index.md).</span><span class="sxs-lookup"><span data-stu-id="3ce2a-203">[.NET Core application deployment](index.md).</span></span>
- <span data-ttu-id="3ce2a-204">[.NET Core CLI를 사용하여 .NET Core 앱 게시](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="3ce2a-204">[Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>
- <span data-ttu-id="3ce2a-205">[Visual Studio를 사용하여 .NET Core 앱 게시](deploy-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="3ce2a-205">[Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>
- <span data-ttu-id="3ce2a-206">[`dotnet publish` 명령](../tools/dotnet-publish.md)</span><span class="sxs-lookup"><span data-stu-id="3ce2a-206">[`dotnet publish` command](../tools/dotnet-publish.md).</span></span>
