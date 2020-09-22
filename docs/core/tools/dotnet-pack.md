---
title: dotnet pack 명령
description: dotnet pack 명령은 .NET Core 프로젝트에 대한 NuGet 패키지를 만듭니다.
ms.date: 04/28/2020
ms.openlocfilehash: 409b946d93cf73fec38941740a446c3ee3402490
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537833"
---
# <a name="dotnet-pack"></a>dotnet pack

**이 문서의 적용 대상:** ✔️ .NET Core 2.x SDK 이상 버전

## <a name="name"></a>이름

`dotnet pack` - 코드를 NuGet 패키지로 압축합니다.

## <a name="synopsis"></a>개요

```dotnetcli
dotnet pack [<PROJECT>|<SOLUTION>] [-c|--configuration <CONFIGURATION>]
    [--force] [--include-source] [--include-symbols] [--interactive]
    [--no-build] [--no-dependencies] [--no-restore] [--nologo]
    [-o|--output <OUTPUT_DIRECTORY>] [--runtime <RUNTIME_IDENTIFIER>]
    [-s|--serviceable] [-v|--verbosity <LEVEL>]
    [--version-suffix <VERSION_SUFFIX>]

dotnet pack -h|--help
```

## <a name="description"></a>설명

`dotnet pack` 명령은 프로젝트를 빌드하고 NuGet 패키지를 만듭니다. 이 명령의 결과가 NuGet 패키지(즉, *.nupkg* 파일)입니다.

디버그 기호를 포함하는 패키지를 만들려면 다음 두 가지 옵션을 사용할 수 있습니다.

- `--include-symbols` - 기호 패키지를 만듭니다.
- `--include-source` - 내부에 원본 파일이 포함된 `src` 폴더가 있는 기호 패키지를 만듭니다.

압축된 프로젝트의 NuGet 종속성은 *.nuspec* 파일에 추가되므로 패키지를 설치할 때 적절히 확인됩니다. 프로젝트 간 참조는 프로젝트 내에서 패키지되지 않습니다. 현재 프로젝트 간 종속성이 있는 경우 프로젝트당 패키지가 있어야 합니다.

`dotnet pack`은 기본적으로 프로젝트를 먼저 빌드합니다. 이렇게 하지 않으려면 `--no-build` 옵션을 전달합니다. 이 옵션은 코드가 이미 빌드된 CI(연속 통합) 빌드 시나리오에서 유용합니다.

> [!NOTE]
> 경우에 따라 암시적 빌드를 수행할 수 없습니다. 이는 빌드 대상과 압축 대상 간에 순환 종속성을 방지하기 위해 `GeneratePackageOnBuild`가 설정된 경우에 발생할 수 있습니다. 잠긴 파일 또는 기타 문제가 있는 경우에도 빌드가 실패할 수 있습니다.

압축 프로세스에 대한 `dotnet pack` 명령에 MSBuild 속성을 제공할 수 있습니다. 자세한 내용은 [NuGet 메타데이터 속성](csproj.md#nuget-metadata-properties) 및 [MSBuild 명령줄 참조](/visualstudio/msbuild/msbuild-command-line-reference)를 참조하세요. [예제](#examples) 섹션에서는 몇 가지 시나리오에 MSBuild -p 스위치를 사용하는 방법을 보여 줍니다.

웹 프로젝트는 기본적으로 패키지할 수 없습니다. 기본 동작을 재정의하려면 다음 속성을 *.csproj* 파일에 추가합니다.

```xml
<PropertyGroup>
   <IsPackable>true</IsPackable>
</PropertyGroup>
```

### <a name="implicit-restore"></a>암시적 복원

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a>인수

`PROJECT | SOLUTION`

  압축할 프로젝트 또는 솔루션입니다. [csproj 파일](csproj.md), vbproj 파일, fsproj 파일, 솔루션 파일 또는 디렉터리에 대한 경로입니다. 지정하지 않으면 이 명령은 현재 디렉터리에서 프로젝트 또는 솔루션 파일을 검색합니다.

## <a name="options"></a>옵션

- **`-c|--configuration <CONFIGURATION>`**

  빌드 구성을 정의합니다. 대부분의 프로젝트에 대한 기본값은 `Debug`이지만 프로젝트의 빌드 구성 설정을 재정의할 수 있습니다.

- **`--force`**

  마지막 복원이 성공한 경우에도 모든 종속성을 강제 확인합니다. 이 플래그를 지정하는 것은 *project.assets.json* 파일을 삭제하는 것과 같습니다.

- **`-h|--help`**

  명령에 대한 간단한 도움말을 출력합니다.

- **`--include-source`**

  출력 디렉터리에 일반 NuGet 패키지 외에 디버그 기호 NuGet 패키지를 포함합니다. 원본 파일은 기호 패키지 내 `src` 폴더에 있습니다.

- **`--include-symbols`**

  출력 디렉터리에 일반 NuGet 패키지 외에 디버그 기호 NuGet 패키지를 포함합니다.

- **`--interactive`**

  명령이 중지되고 사용자 입력 또는 작업을 대기할 수 있도록 허용합니다(예: 인증 완료). .NET Core 3.0 SDK 이후 사용할 수 있습니다.

- **`--no-build`**

  압축하기 전에 프로젝트를 빌드하지 않습니다. 또한 암시적으로 `--no-restore` 플래그를 설정합니다.

- **`--no-dependencies`**

  프로젝트 간 참조를 무시하고 루트 프로젝트만 복원합니다.

- **`--no-restore`**

  명령을 실행할 때 암시적 복원을 실행하지 않습니다.

- **`--nologo`**

  시작 배너 또는 저작권 메시지를 표시하지 않습니다. .NET Core 3.0 SDK 이후 사용할 수 있습니다.

- **`-o|--output <OUTPUT_DIRECTORY>`**

  지정된 디렉터리에 빌드된 패키지를 배치합니다.

- **`--runtime <RUNTIME_IDENTIFIER>`**

  패키지를 복원할 대상 런타임을 지정합니다. RID(런타임 식별자) 목록은 [RID 카탈로그](../rid-catalog.md)를 참조하세요.

- **`-s|--serviceable`**

  패키지에 서비스 가능 플래그를 설정합니다. 자세한 내용은 [.NET 블로그: .NET 4.5.1에서 .NET NuGet 라이브러리에 대한 Microsoft 보안 업데이트를 지원함](https://aka.ms/nupkgservicing)을 참조하세요.

- **`--version-suffix <VERSION_SUFFIX>`**

  프로젝트에서 `$(VersionSuffix)` MSBuild 속성에 대한 값을 정의합니다.

- **`-v|--verbosity <LEVEL>`**

  명령의 세부 정보 표시 수준을 설정합니다. 허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.

## <a name="examples"></a>예

- 현재 디렉터리에 있는 프로젝트를 압축합니다.

  ```dotnetcli
  dotnet pack
  ```

- `app1` 프로젝트를 압축합니다.

  ```dotnetcli
  dotnet pack ~/projects/app1/project.csproj
  ```

- 현재 디렉터리에 있는 프로젝트를 압축하고 결과 패키지를 `nupkgs` 폴더에 배치합니다.

  ```dotnetcli
  dotnet pack --output nupkgs
  ```

- 현재 디렉터리에 있는 프로젝트를 `nupkgs` 폴더로 압축하고 빌드 단계를 건너뜁니다.

  ```dotnetcli
  dotnet pack --no-build --output nupkgs
  ```

- *.csproj* 파일에서 프로젝트의 버전 접미사를 `<VersionSuffix>$(VersionSuffix)</VersionSuffix>`로 구성한 상태로 현재 프로젝트를 압축하고 결과 패키지 버전을 지정된 접미사로 업데이트합니다.

  ```dotnetcli
  dotnet pack --version-suffix "ci-1234"
  ```

- `PackageVersion` MSBuild 속성을 사용하여 패키지 버전을 `2.1.0`으로 설정합니다.

  ```dotnetcli
  dotnet pack -p:PackageVersion=2.1.0
  ```

- 특정 [대상 프레임워크](../../standard/frameworks.md)에 대한 프로젝트를 압축합니다.

  ```dotnetcli
  dotnet pack -p:TargetFrameworks=net45
  ```

- 프로젝트를 압축하고 복원 작업에 대한 특정 런타임(Windows 10)을 사용합니다.

  ```dotnetcli
  dotnet pack --runtime win10-x64
  ```

- *.nuspec* 파일을 사용하여 프로젝트를 압축합니다.

  ```dotnetcli
  dotnet pack ~/projects/app1/project.csproj -p:NuspecFile=~/projects/app1/project.nuspec -p:NuspecBasePath=~/projects/app1/nuget
  ```

  `NuspecFile`, `NuspecBasePath` 및 `NuspecProperties`를 사용하는 방법에 관한 자세한 내용은 다음 리소스를 참조하세요.
  
  - [.nuspec을 사용하여 압축](/nuget/reference/msbuild-targets#packing-using-a-nuspec)
  - [사용자 지정 패키지를 만들기 위한 고급 확장점](/nuget/reference/msbuild-targets#advanced-extension-points-to-create-customized-package)
  - [전역 속성](/visualstudio/msbuild/msbuild-properties?view=vs-2019#global-properties)
