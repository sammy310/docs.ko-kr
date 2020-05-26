---
title: 런타임 구성 옵션
description: 런타임 구성 설정을 사용하여 .NET Core 애플리케이션을 구성하는 방법을 알아봅니다.
ms.date: 01/21/2020
ms.openlocfilehash: 68690689fd4f936e3af76ab647f0b58d8ec6ca27
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761956"
---
# <a name="net-core-run-time-configuration-settings"></a>.NET Core 런타임 구성 설정

.NET Core에서는 구성 파일 및 환경 변수를 사용하여 런타임에 .NET Core 애플리케이션의 동작을 구성할 수 있도록 지원합니다. 런타임 구성은 다음과 같은 경우에 유용한 옵션입니다.

- 애플리케이션의 소스 코드를 소유하거나 제어하지 않으므로 프로그래밍 방식으로 해당 소스 코드를 구성할 수 없습니다.

- 애플리케이션의 여러 인스턴스가 단일 시스템에서 동시에 실행되며 최적의 성능을 위해 각 인스턴스를 구성하려고 합니다.

> [!NOTE]
> 이 설명서는 진행 중인 작업입니다. 여기에 제공된 정보가 불완전하거나 부정확한 경우에는 [이슈를 열어](https://github.com/dotnet/docs/issues) 그에 대해 알려주시거나 [끌어오기 요청을 제출](https://github.com/dotnet/docs/pulls)하여 이슈를 해결하세요. dotnet/docs 리포지토리의 끌어오기 요청 제출에 대한 자세한 내용은 [기여자 가이드](https://docs.microsoft.com/contribute/dotnet/dotnet-contribute)를 참조하세요.

.NET Core는 런타임에 애플리케이션 동작을 구성하기 위해 다음과 같은 메커니즘을 제공합니다.

- [runtimeconfig.json 파일](#runtimeconfigjson)

- [MSBuild 속성](#msbuild-properties)

- [환경 변수](#environment-variables)

> [!TIP]
> 환경 변수를 사용하여 런타임 옵션을 구성하면 모든 .NET Core 앱에 설정이 적용됩니다. *runtimeconfig.json* 또는 프로젝트 파일에서 런타임 옵션을 구성하면 해당 애플리케이션에만 설정이 적용됩니다.

일부 구성 값은 <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> 메서드를 호출하여 프로그래밍 방식으로 설정할 수도 있습니다.

설명서의 이 섹션에 있는 문서는 [디버깅](debugging-profiling.md) 및 [가비지 수집](garbage-collector.md) 등의 범주별로 구성되어 있습니다. 해당하는 경우 .NET Framework 프로젝트의 *runtimeconfig.json* 파일, MSBuild 속성, 환경 변수 그리고 상호 참조의 경우 *app.config* 파일에 대한 구성 옵션이 표시됩니다.

## <a name="runtimeconfigjson"></a>runtimeconfig.json

프로젝트가 [빌드](../tools/dotnet-build.md)되면 *[앱 이름].runtimeconfig.json* 파일이 출력 디렉터리에 생성됩니다. *runtimeconfig.template.json* 파일이 프로젝트 파일과 동일한 폴더에 있으면 포함된 구성 옵션이 *[앱 이름].runtimeconfig.json* 파일로 병합됩니다. 앱을 직접 빌드하는 경우 *runtimeconfig.template.json* 파일에 구성 옵션을 배치합니다. 앱을 실행만 하는 경우에는 *[앱 이름].runtimeconfig.json* 파일에 직접 삽입합니다.

> [!NOTE]
> 그러면 *[앱 이름].runtimeconfig.json* 파일이 다음 번 빌드에서 덮어쓰입니다.

*runtimeconfig.json* 파일의 **configProperties** 섹션에 런타임 구성 옵션을 지정합니다. 이 섹션은 형식은 다음과 같습니다.

```json
"configProperties": {
  "config-property-name1": "config-value1",
  "config-property-name2": "config-value2"
}
```

### <a name="example-appnameruntimeconfigjson-file"></a>예: [앱 이름].runtimeconfig.template.json 파일

출력 JSON 파일에 옵션을 배치하는 경우 `runtimeOptions` 속성 아래에 중첩합니다.

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

### <a name="example-runtimeconfigtemplatejson-file"></a>예: runtimeconfig.template.json 파일

템플릿 JSON 파일에 옵션을 배치하는 경우 `runtimeOptions` 속성을 생략합니다.

```json
{
  "configProperties": {
    "System.GC.Concurrent": false,
    "System.Threading.ThreadPool.MinThreads": "4",
    "System.Threading.ThreadPool.MaxThreads": "25"
  }
}
```

## <a name="msbuild-properties"></a>MSBuild 속성

일부 런타임 구성 옵션은 *.csproj*의 MSBuild 속성 또는 SDK 스타일 .NET Core 프로젝트의 *.vbproj* 파일을 사용하여 설정할 수 있습니다. MSBuild 속성은 *runtimeconfig.template.json* 파일에 설정된 옵션보다 우선적으로 적용됩니다. 이 속성도 빌드 시 *[앱 이름].runtimeconfig.json* 파일에서 설정한 옵션을 덮어씁니다.

런타임 동작을 구성하기 위한 MSBuild 속성이 포함된 SDK 스타일 프로젝트 파일의 예는 다음과 같습니다.

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

런타임 동작을 구성하기 위한 MSBuild 속성은 각 영역에 대한 개별 문서(예: [가비지 수집](garbage-collector.md))에 설명되어 있습니다. SDK 스타일 프로젝트에 대한 MSBuild 속성 참조의 [런타임 구성](../project-sdk/msbuild-props.md#run-time-configuration-properties) 섹션에도 나열됩니다.

## <a name="environment-variables"></a>환경 변수

환경 변수를 사용하여 일부 런타임 구성 정보를 제공할 수 있습니다. 환경 변수를 사용하여 런타임 옵션을 구성하면 모든 .NET Core 앱에 설정이 적용됩니다. 환경 변수로 지정된 구성 노브는 일반적으로 **COMPlus_** 접두사가 붙어 있습니다.

Windows 제어판, 명령줄 또는 Windows 및 Unix 기반 시스템에서 <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> 메서드를 호출하여 프로그래밍 방식으로 환경 변수를 정의할 수 있습니다.

다음 예제는 명령줄에서 환경 변수를 설정하는 방법을 보여 줍니다.

```shell
# Windows
set COMPlus_GCRetainVM=1

# Powershell
$env:COMPlus_GCRetainVM="1"

# Unix
export COMPlus_GCRetainVM=1
```
