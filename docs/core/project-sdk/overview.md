---
title: .NET Core 프로젝트 SDK 개요
titleSuffix: ''
description: .NET Core 프로젝트 SDK에 대해 알아봅니다.
ms.date: 02/02/2020
ms.topic: conceptual
ms.openlocfilehash: 9db62ab7774e3dd71412fa346d78ae0c62a2f81f
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803043"
---
# <a name="net-core-project-sdks"></a>.NET Core 프로젝트 SDK

.NET Core 프로젝트는 SDK(소프트웨어 개발 키트)와 연결됩니다. 각 ‘프로젝트 SDK’는 코드를 컴파일, 압축 및 게시해야 하는 MSBuild [대상](/visualstudio/msbuild/msbuild-targets) 및 관련 [작업](/visualstudio/msbuild/msbuild-tasks) 집합입니다. 프로젝트 SDK를 참조하는 프로젝트를 ‘SDK 스타일 프로젝트’라고도 합니다.

## <a name="available-sdks"></a>사용 가능한 SDK

.NET Core에 사용할 수 있는 SDK는 다음과 같습니다.

| ID | 설명 | 리포지토리|
| - | - | - |
| `Microsoft.NET.Sdk` | .NET Core SDK | <https://github.com/dotnet/sdk> |
| `Microsoft.NET.Sdk.Web` | .NET Core [웹 SDK](/aspnet/core/razor-pages/web-sdk) | <https://github.com/aspnet/websdk> |
| `Microsoft.NET.Sdk.Razor` | .NET Core [Razor SDK](/aspnet/core/razor-pages/sdk) |
| `Microsoft.NET.Sdk.Worker` | .NET Core 작업자 서비스 SDK |
| `Microsoft.NET.Sdk.WindowsDesktop` | .NET Core WinForms 및 WPF SDK |

.NET Core SDK는 .NET Core의 기본 SDK입니다. 다른 SDK는 .NET Core SDK를 참조하며 다른 SDK와 연결된 프로젝트는 모든 .NET Core SDK 속성을 사용할 수 있습니다. 예를 들어 웹 SDK는 .NET Core SDK 및 Razor SDK에 종속됩니다.

NuGet을 통해 배포할 수 있는 고유한 SDK를 작성할 수도 있습니다.

## <a name="project-files"></a>프로젝트 파일

.NET Core 프로젝트는 [MSBuild](/visualstudio/msbuild/msbuild) 형식을 기반으로 합니다. *.csproj*(C# 프로젝트) 및 *.fsproj*(F# 프로젝트) 같은 확장명을 가진 프로젝트 파일은 XML 형식입니다. MSBuild 프로젝트 파일의 루트 요소는 [Project](/visualstudio/msbuild/project-element-msbuild) 요소입니다. `Project` 요소에는 사용할 SDK(및 버전)를 지정하는 선택적 `Sdk` 특성이 있습니다. .NET Core 도구를 사용하고 코드를 빌드하려면 `Sdk` 특성을 [사용 가능한 SDK](#available-sdks) 표의 ID 중 하나로 설정합니다.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
</Project>
```

NuGet에서 제공되는 SDK를 지정하려면 이름 끝에 버전을 포함하거나 *global.json* 파일에서 이름 및 버전을 지정합니다.

```xml
<Project Sdk="MSBuild.Sdk.Extras/2.0.54">
  ...
</Project>
```

SDK를 지정하는 또 다른 방법은 최상위 [Sdk](/visualstudio/msbuild/sdk-element-msbuild) 요소를 사용하는 것입니다.

```xml
<Project>
  <Sdk Name="Microsoft.NET.Sdk" />
  ...
</Project>
```

해당 방법 중 하나에서 SDK를 참조하면 .NET Core용 프로젝트 파일이 크게 간소화됩니다. 프로젝트를 평가하는 동안 MSBuild는 프로젝트 파일 맨 위에 `Sdk.props`의 암시적 가져오기를 추가하고 맨 아래에 `Sdk.targets`를 추가합니다.

```xml
<Project>
  <!-- Implicit top import -->
  <Import Project="Sdk.props" Sdk="Microsoft.NET.Sdk" />
  ...
  <!-- Implicit bottom import -->
  <Import Project="Sdk.targets" Sdk="Microsoft.NET.Sdk" />
</Project>
```

> [!TIP]
> Windows 머신에서 *Sdk.props* 및 *Sdk.targets* 파일은 *%ProgramFiles%\dotnet\sdk\\[버전]\Sdks\Microsoft.NET.Sdk\Sdk* 폴더에 있습니다.

### <a name="preprocess-the-project-file"></a>프로젝트 파일 전처리

`dotnet msbuild -preprocess` 명령을 사용하여 SDK 및 해당 대상이 포함된 후 MSBuild에서 보는 것처럼 완전히 확장된 프로젝트를 볼 수 있습니다. [`dotnet msbuild`](../tools/dotnet-msbuild.md) 명령의 [preprocess](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) 스위치는 가져온 파일, 해당 소스 및 실제로 프로젝트를 빌드하지 않는 빌드에 대한 기여를 표시합니다.

프로젝트에 대상 프레임워크가 여러 개 있는 경우 명령의 결과는 대상을 MSBuild 속성으로 지정하여 프레임워크 하나에만 초점을 맞춥니다. 예를 들어:

`dotnet msbuild -property:TargetFramework=netcoreapp2.0 -preprocess:output.xml`

### <a name="default-compilation-includes"></a>기본 컴파일 포함

컴파일 항목, 포함된 리소스 및 `None` 항목의 기본 포함 및 제외는 SDK에서 정의됩니다. SDK가 아닌 .NET Framework 프로젝트와 달리 기본값은 대부분의 일반적인 사용 사례를 처리하므로 프로젝트 파일에서 해당 항목을 지정할 필요가 없습니다. 그러면 프로젝트 파일이 크기가 줄어들고 더 쉽게 이해하고 필요에 따라 수동으로 편집할 수 있습니다.

다음 표에는 .NET Core SDK에 포함되거나 제외되는 요소 및 [GLOB](https://en.wikipedia.org/wiki/Glob_(programming))가 나와 있습니다.

| 요소           | GLOB 포함                              | GLOB 제외                                                  | GLOB 제거              |
|-------------------|-------------------------------------------|---------------------------------------------------------------|--------------------------|
| Compile           | \*\*/\*.cs(또는 기타 언어 확장) | \*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc  | N/A                      |
| EmbeddedResource  | \*\*/\*.resx                              | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | N/A                      |
| 없음              | \*\*/\*                                   | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | \*\*/\*.cs; \*\*/\*.resx |

> [!NOTE]
> `$(BaseOutputPath)` 및 `$(BaseIntermediateOutputPath)` MSBuild 속성으로 나타내는 `./bin` 및 `./obj` 폴더는 기본적으로 GLOB에서 제외됩니다. 제외는 `$(DefaultItemExcludes)` 속성으로 나타냅니다.

#### <a name="build-errors"></a>빌드 오류

프로젝트 파일에서 이러한 항목을 명시적으로 정의하는 경우 다음과 비슷한 "NETSDK1022" 빌드 오류가 발생할 수 있습니다.

  > 중복된 'Compile' 항목이 포함되었습니다. .NET SDK에는 기본적으로 프로젝트 디렉터리의 'Compile' 항목이 포함됩니다. 프로젝트 파일에서 이러한 항목을 제거하거나, 프로젝트 파일에서 이러한 항목을 명시적으로 포함하려면 'EnableDefaultCompileItems' 속성을 'false'로 설정할 수 있습니다.

  > 중복된 'EmbeddedResource' 항목이 포함되었습니다. .NET SDK에는 기본적으로 프로젝트 디렉터리의 'EmbeddedResource' 항목이 포함됩니다. 프로젝트 파일에서 해당 항목을 제거하거나, 프로젝트 파일에 해당 항목을 명시적으로 포함하려면 'EnableDefaultEmbeddedResourceItems' 속성을 'false'로 설정할 수 있습니다.

오류를 해결하려면 다음 중 하나를 수행합니다.

- 앞의 표에 나열된 암시적 `Compile`, `EmbeddedResource` 또는 `None` 항목과 일치하는 항목을 제거합니다.

- 모든 암시적 파일 포함을 사용하지 않으려면 `EnableDefaultItems` 속성을 `false`로 설정합니다.

  ```xml
  <PropertyGroup>
    <EnableDefaultItems>false</EnableDefaultItems>
  </PropertyGroup>
  ```

  앱과 함께 게시할 파일을 지정하려는 경우 해당 항목(예: `Content` 요소)에 알려진 MSBuild 메커니즘을 계속 사용할 수 있습니다.

- `EnableDefaultCompileItems`, `EnableDefaultEmbeddedResourceItems` 또는 `EnableDefaultNoneItems` 속성을 `false`로 설정하여 `Compile`, `EmbeddedResource` 또는 `None` GLOB만 사용하지 않도록 설정합니다.

  ```xml
  <PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
    <EnableDefaultEmbeddedResourceItems>false</EnableDefaultEmbeddedResourceItems>
    <EnableDefaultNoneItems>false</EnableDefaultNoneItems>
  </PropertyGroup>
  ```

  `Compile` GLOB만 사용하지 않도록 설정하는 경우 Visual Studio의 솔루션 탐색기는 \*.cs 항목을 `None` 항목으로 포함된 프로젝트의 일부로 계속 표시합니다. 암시적 `None` GLOB를 사용하지 않도록 설정하려면 `EnableDefaultNoneItems`도 `false`로 설정합니다.

## <a name="customize-the-build"></a>빌드 사용자 지정

다양한 방법으로 [빌드를 사용자 지정](/visualstudio/msbuild/customize-your-build)할 수 있습니다. [msbuild](/visualstudio/msbuild/msbuild-command-line-reference) 또는 [dotnet](../tools/index.md) 명령에 인수로 전달하여 속성을 재정의할 수 있습니다. 또한 프로젝트 파일 또는 *Directory.Build.props* 파일에 속성을 추가할 수 있습니다. .NET Core 프로젝트의 유용한 속성 목록을 보려면 [.NET Core SDK 프로젝트용 MSBuild 참조](msbuild-props.md)를 참조하세요.

### <a name="custom-targets"></a>사용자 지정 대상

.NET Core 프로젝트는 패키지를 사용하는 프로젝트에서 사용할 사용자 지정 MSBuild 대상 및 속성을 패키지할 수 있습니다. 다음을 수행하려는 경우 이 유형의 확장성을 사용합니다.

- 빌드 프로세스를 확장합니다.
- 생성된 파일과 같은 빌드 프로세스의 아티팩트에 액세스합니다.
- 빌드를 호출하는 데 사용된 구성을 검사합니다.

프로젝트의 *build* 폴더에 `<package_id>.targets` 또는 `<package_id>.props`(예: `Contoso.Utility.UsefulStuff.targets`) 형식의 파일을 배치하여 사용자 지정 빌드 대상 또는 속성을 추가합니다.

다음 XML은 [`dotnet pack`](../tools/dotnet-pack.md) 명령에 패키지할 항목을 알리는 *.csproj* 파일의 코드 조각입니다. `<ItemGroup Label="dotnet pack instructions">` 요소는 패키지 내부 *build* 폴더에 대상 파일을 배치합니다. `<Target Name="CollectRuntimeOutputs" BeforeTargets="_GetPackageFiles">` 요소는 *build* 폴더에 어셈블리 및 *.json* 파일을 배치합니다.

```xml
<Project Sdk="Microsoft.NET.Sdk">

  ...
  <ItemGroup Label="dotnet pack instructions">
    <Content Include="build\*.targets">
      <Pack>true</Pack>
      <PackagePath>build\</PackagePath>
    </Content>
  </ItemGroup>
  <Target Name="CollectRuntimeOutputs" BeforeTargets="_GetPackageFiles">
    <!-- Collect these items inside a target that runs after build but before packaging. -->
    <ItemGroup>
      <Content Include="$(OutputPath)\*.dll;$(OutputPath)\*.json">
        <Pack>true</Pack>
        <PackagePath>build\</PackagePath>
      </Content>
    </ItemGroup>
  </Target>
  ...
  
</Project>
```

프로젝트에서 사용자 지정 대상을 사용하려면 패키지 및 해당 버전을 가리키는 `PackageReference` 요소를 추가합니다. 도구와 달리 사용자 지정 대상 패키지는 사용하는 프로젝트의 종속성 종료 항목에 포함됩니다.

사용자 지정 대상을 사용하는 방법을 구성할 수 있습니다. MSBuild 대상이므로 지정된 대상에 종속되거나, 다른 대상 이후에 실행되거나, `dotnet msbuild -t:<target-name>` 명령을 사용하여 수동으로 호출될 수 있습니다. 그러나 더 나은 사용자 환경을 제공하려면 프로젝트별 도구 및 사용자 지정 대상을 결합할 수 있습니다. 이 시나리오에서 프로젝트별 도구는 필요한 모든 매개 변수를 허용하며 대상을 실행하는 필수 [`dotnet msbuild`](../tools/dotnet-msbuild.md) 호출로 변환합니다. 이러한 종류의 시너지 효과는 [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer) 프로젝트의 [MVP Summit 2016 Hackathon 샘플](https://github.com/dotnet/MVPSummitHackathon2016) 리포지토리에서 확인할 수 있습니다.

## <a name="see-also"></a>참조

- [.NET Core 설치](../install/index.yml)
- [MSBuild 프로젝트 SDK 사용 방법](/visualstudio/msbuild/how-to-use-project-sdk)
- [NuGet을 사용하여 사용자 지정 MSBuild 대상 및 속성 패키지](/nuget/create-packages/creating-a-package#include-msbuild-props-and-targets-in-a-package)
