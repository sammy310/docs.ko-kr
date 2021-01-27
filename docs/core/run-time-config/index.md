---
title: 런타임 구성 옵션
description: 런타임 구성 설정을 사용하여 .NET Core 애플리케이션을 구성하는 방법을 알아봅니다.
ms.date: 01/21/2020
ms.openlocfilehash: 5e9f292476cf953c3e63bb8e89268f7cc06b3bfc
ms.sourcegitcommit: 2b878d7011306b215dbf3d5dc9c1e78355a6dcd5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2021
ms.locfileid: "98757852"
---
# <a name="net-core-run-time-configuration-settings"></a><span data-ttu-id="c8dcb-103">.NET Core 런타임 구성 설정</span><span class="sxs-lookup"><span data-stu-id="c8dcb-103">.NET Core run-time configuration settings</span></span>

<span data-ttu-id="c8dcb-104">.NET Core에서는 구성 파일 및 환경 변수를 사용하여 런타임에 .NET Core 애플리케이션의 동작을 구성할 수 있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcb-104">.NET Core supports the use of configuration files and environment variables to configure the behavior of .NET Core applications at run time.</span></span> <span data-ttu-id="c8dcb-105">런타임 구성은 다음과 같은 경우에 유용한 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcb-105">Run-time configuration is an attractive option if:</span></span>

- <span data-ttu-id="c8dcb-106">애플리케이션의 소스 코드를 소유하거나 제어하지 않으므로 프로그래밍 방식으로 해당 소스 코드를 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcb-106">You don't own or control the source code for an application and therefore are unable to configure it programmatically.</span></span>

- <span data-ttu-id="c8dcb-107">애플리케이션의 여러 인스턴스가 단일 시스템에서 동시에 실행되며 최적의 성능을 위해 각 인스턴스를 구성하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcb-107">Multiple instances of your application run at the same time on a single system, and you want to configure each for optimum performance.</span></span>

> [!NOTE]
> <span data-ttu-id="c8dcb-108">이 설명서는 진행 중인 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcb-108">This documentation is a work in progress.</span></span> <span data-ttu-id="c8dcb-109">여기에 제공된 정보가 불완전하거나 부정확한 경우에는 [이슈를 열어](https://github.com/dotnet/docs/issues) 그에 대해 알려주시거나 [끌어오기 요청을 제출](https://github.com/dotnet/docs/pulls)하여 이슈를 해결하세요.</span><span class="sxs-lookup"><span data-stu-id="c8dcb-109">If you notice that the information presented here is either incomplete or inaccurate, either [open an issue](https://github.com/dotnet/docs/issues) to let us know about it, or [submit a pull request](https://github.com/dotnet/docs/pulls) to address the issue.</span></span> <span data-ttu-id="c8dcb-110">dotnet/docs 리포지토리의 끌어오기 요청 제출에 대한 자세한 내용은 [기여자 가이드](/contribute/dotnet/dotnet-contribute)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c8dcb-110">For information about submitting pull requests for the dotnet/docs repository, see the [contributor's guide](/contribute/dotnet/dotnet-contribute).</span></span>

<span data-ttu-id="c8dcb-111">.NET Core는 런타임에 애플리케이션 동작을 구성하기 위해 다음과 같은 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcb-111">.NET Core provides the following mechanisms for configuring application behavior at run time:</span></span>

- <span data-ttu-id="c8dcb-112">[runtimeconfig.json 파일](#runtimeconfigjson)</span><span class="sxs-lookup"><span data-stu-id="c8dcb-112">The [runtimeconfig.json file](#runtimeconfigjson)</span></span>

- [<span data-ttu-id="c8dcb-113">MSBuild 속성</span><span class="sxs-lookup"><span data-stu-id="c8dcb-113">MSBuild properties</span></span>](#msbuild-properties)

- [<span data-ttu-id="c8dcb-114">환경 변수</span><span class="sxs-lookup"><span data-stu-id="c8dcb-114">Environment variables</span></span>](#environment-variables)

> [!TIP]
> <span data-ttu-id="c8dcb-115">환경 변수를 사용하여 런타임 옵션을 구성하면 모든 .NET Core 앱에 설정이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcb-115">Configuring a run-time option by using an environment variable applies the setting to all .NET Core apps.</span></span> <span data-ttu-id="c8dcb-116">*runtimeconfig.json* 또는 프로젝트 파일에서 런타임 옵션을 구성하면 해당 애플리케이션에만 설정이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcb-116">Configuring a run-time option in the *runtimeconfig.json* or project file applies the setting to that application only.</span></span>

<span data-ttu-id="c8dcb-117">일부 구성 값은 <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> 메서드를 호출하여 프로그래밍 방식으로 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcb-117">Some configuration values can also be set programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="c8dcb-118">설명서의 이 섹션에 있는 문서는 [디버깅](debugging-profiling.md) 및 [가비지 수집](garbage-collector.md) 등의 범주별로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcb-118">The articles in this section of the documentation are organized by category, for example, [debugging](debugging-profiling.md) and [garbage collection](garbage-collector.md).</span></span> <span data-ttu-id="c8dcb-119">해당하는 경우 .NET Framework 프로젝트의 *runtimeconfig.json* 파일, MSBuild 속성, 환경 변수 그리고 상호 참조의 경우 *app.config* 파일에 대한 구성 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcb-119">Where applicable, configuration options are shown for *runtimeconfig.json* files, MSBuild properties, environment variables, and, for cross-reference, *app.config* files for .NET Framework projects.</span></span>

## <a name="runtimeconfigjson"></a><span data-ttu-id="c8dcb-120">runtimeconfig.json</span><span class="sxs-lookup"><span data-stu-id="c8dcb-120">runtimeconfig.json</span></span>

<span data-ttu-id="c8dcb-121">프로젝트가 [빌드](../tools/dotnet-build.md)되면 *[앱 이름].runtimeconfig.json* 파일이 출력 디렉터리에 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcb-121">When a project is [built](../tools/dotnet-build.md), an *[appname].runtimeconfig.json* file is generated in the output directory.</span></span> <span data-ttu-id="c8dcb-122">*runtimeconfig.template.json* 파일이 프로젝트 파일과 같은 폴더에 있으면 포함된 모든 구성 옵션이 *[앱 이름].runtimeconfig.json* 파일에 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcb-122">If a *runtimeconfig.template.json* file exists in the same folder as the project file, any configuration options it contains are inserted into the *[appname].runtimeconfig.json* file.</span></span> <span data-ttu-id="c8dcb-123">앱을 직접 빌드하는 경우 *runtimeconfig.template.json* 파일에 구성 옵션을 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcb-123">If you're building the app yourself, put any configuration options in the *runtimeconfig.template.json* file.</span></span> <span data-ttu-id="c8dcb-124">앱을 실행만 하는 경우에는 *[앱 이름].runtimeconfig.json* 파일에 직접 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcb-124">If you're just running the app, insert them directly into the *[appname].runtimeconfig.json* file.</span></span>

> [!NOTE]
> <span data-ttu-id="c8dcb-125">그러면 *[앱 이름].runtimeconfig.json* 파일이 다음 번 빌드에서 덮어쓰입니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcb-125">The *[appname].runtimeconfig.json* file will get overwritten on subsequent builds.</span></span>

<span data-ttu-id="c8dcb-126">*runtimeconfig.json* 파일의 **configProperties** 섹션에 런타임 구성 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcb-126">Specify run-time configuration options in the **configProperties** section of the *runtimeconfig.json* files.</span></span> <span data-ttu-id="c8dcb-127">이 섹션은 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcb-127">This section has the form:</span></span>

```json
"configProperties": {
  "config-property-name1": "config-value1",
  "config-property-name2": "config-value2"
}
```

### <a name="example-appnameruntimeconfigjson-file"></a><span data-ttu-id="c8dcb-128">예: [앱 이름].runtimeconfig.template.json 파일</span><span class="sxs-lookup"><span data-stu-id="c8dcb-128">Example [appname].runtimeconfig.json file</span></span>

<span data-ttu-id="c8dcb-129">출력 JSON 파일에 옵션을 배치하는 경우 `runtimeOptions` 속성 아래에 중첩합니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcb-129">If you're placing the options in the output JSON file, nest them under the `runtimeOptions` property.</span></span>

```json
{
  "runtimeOptions": {
    "tfm": "netcoreapp3.1",
    "framework": {
      "name": "Microsoft.NETCore.App",
      "version": "3.1.0"
    },
    "configProperties": {
      "System.GC.Concurrent": false,
      "System.Threading.ThreadPool.MinThreads": 4,
      "System.Threading.ThreadPool.MaxThreads": 25
    }
  }
}
```

### <a name="example-runtimeconfigtemplatejson-file"></a><span data-ttu-id="c8dcb-130">예: runtimeconfig.template.json 파일</span><span class="sxs-lookup"><span data-stu-id="c8dcb-130">Example runtimeconfig.template.json file</span></span>

<span data-ttu-id="c8dcb-131">템플릿 JSON 파일에 옵션을 배치하는 경우 `runtimeOptions` 속성을 생략합니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcb-131">If you're placing the options in the template JSON file, omit the `runtimeOptions` property.</span></span>

```json
{
  "configProperties": {
    "System.GC.Concurrent": false,
    "System.Threading.ThreadPool.MinThreads": "4",
    "System.Threading.ThreadPool.MaxThreads": "25"
  }
}
```

## <a name="msbuild-properties"></a><span data-ttu-id="c8dcb-132">MSBuild 속성</span><span class="sxs-lookup"><span data-stu-id="c8dcb-132">MSBuild properties</span></span>

<span data-ttu-id="c8dcb-133">일부 런타임 구성 옵션은 *.csproj* 의 MSBuild 속성 또는 SDK 스타일 .NET Core 프로젝트의 *.vbproj* 파일을 사용하여 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcb-133">Some run-time configuration options can be set using MSBuild properties in the *.csproj* or *.vbproj* file of SDK-style .NET Core projects.</span></span> <span data-ttu-id="c8dcb-134">MSBuild 속성은 *runtimeconfig.template.json* 파일에 설정된 옵션보다 우선적으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcb-134">MSBuild properties take precedence over options set in the *runtimeconfig.template.json* file.</span></span>

<span data-ttu-id="c8dcb-135">런타임 동작을 구성하기 위한 MSBuild 속성이 포함된 SDK 스타일 프로젝트 파일의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcb-135">Here is an example SDK-style project file with MSBuild properties for configuring run-time behavior:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
    <ThreadPoolMaxThreads>25</ThreadPoolMaxThreads>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="c8dcb-136">런타임 동작을 구성하기 위한 MSBuild 속성은 각 영역에 대한 개별 문서(예: [가비지 수집](garbage-collector.md))에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcb-136">MSBuild properties for configuring run-time behavior are noted in the individual articles for each area, for example, [garbage collection](garbage-collector.md).</span></span> <span data-ttu-id="c8dcb-137">SDK 스타일 프로젝트에 대한 MSBuild 속성 참조의 [런타임 구성](../project-sdk/msbuild-props.md#run-time-configuration-properties) 섹션에도 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcb-137">They are also listed in the [Run-time configuration](../project-sdk/msbuild-props.md#run-time-configuration-properties) section of the MSBuild properties reference for SDK-style projects.</span></span>

## <a name="environment-variables"></a><span data-ttu-id="c8dcb-138">환경 변수</span><span class="sxs-lookup"><span data-stu-id="c8dcb-138">Environment variables</span></span>

<span data-ttu-id="c8dcb-139">환경 변수를 사용하여 일부 런타임 구성 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcb-139">Environment variables can be used to supply some run-time configuration information.</span></span> <span data-ttu-id="c8dcb-140">환경 변수를 사용하여 런타임 옵션을 구성하면 모든 .NET Core 앱에 설정이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcb-140">Configuring a run-time option by using an environment variable applies the setting to all .NET Core apps.</span></span> <span data-ttu-id="c8dcb-141">환경 변수로 지정된 구성 노브는 일반적으로 **COMPlus_** 접두사가 붙어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcb-141">Configuration knobs specified as environment variables generally have the prefix **COMPlus_**.</span></span>

<span data-ttu-id="c8dcb-142">Windows 제어판, 명령줄 또는 Windows 및 Unix 기반 시스템에서 <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> 메서드를 호출하여 프로그래밍 방식으로 환경 변수를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcb-142">You can define environment variables from the Windows Control Panel, at the command line, or programmatically by calling the <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> method on both Windows and Unix-based systems.</span></span>

<span data-ttu-id="c8dcb-143">다음 예제는 명령줄에서 환경 변수를 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcb-143">The following examples show how to set an environment variable at the command line:</span></span>

```shell
# Windows
set COMPlus_GCRetainVM=1

# Powershell
$env:COMPlus_GCRetainVM="1"

# Unix
export COMPlus_GCRetainVM=1
```
