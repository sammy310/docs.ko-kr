---
title: dotnet build 명령
description: dotnet build 명령은 프로젝트와 모든 종속성을 빌드합니다.
ms.date: 02/14/2020
ms.openlocfilehash: 6f33b449301f40949ff5dfe4077564344a9de8ec
ms.sourcegitcommit: c8c3e1c63a00b7d27f76f5e50ee6469e6bdc8987
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87251168"
---
# <a name="dotnet-build"></a>dotnet build

**이 문서의 적용 대상:** ✔️ .NET Core 2.x SDK 이상 버전

## <a name="name"></a>이름

`dotnet build` - 프로젝트 및 모든 종속성을 빌드합니다.

## <a name="synopsis"></a>개요

```dotnetcli
dotnet build [<PROJECT>|<SOLUTION>] [-c|--configuration <CONFIGURATION>]
    [-f|--framework <FRAMEWORK>] [--force] [--interactive] [--no-dependencies]
    [--no-incremental] [--no-restore] [--nologo] [-o|--output <OUTPUT_DIRECTORY>]
    [-r|--runtime <RUNTIME_IDENTIFIER>] [--source <SOURCE>]
    [-v|--verbosity <LEVEL>] [--version-suffix <VERSION_SUFFIX>]

dotnet build -h|--help
```

## <a name="description"></a>설명

`dotnet build` 명령은 이진 파일 집합으로 프로젝트와 해당 종속성을 빌드합니다. 이진 파일에는 확장명이 *.dll*인 IL(중간 언어) 파일의 프로젝트 코드가 포함됩니다.  프로젝트 형식 및 설정에 따라 다음과 같은 다른 파일이 포함될 수도 있습니다.

- 프로젝트 형식이 .NET Core 3.0 이상을 대상으로 하는 실행 파일인 경우 애플리케이션을 실행하는 데 사용할 수 있는 실행 파일
- 확장명이 *.pdb*인 디버깅에 사용되는 기호 파일
- 애플리케이션 또는 라이브러리의 종속성을 나열하는 *.deps.json* 파일
- 애플리케이션의 공유 런타임 및 해당 버전을 지정하는 *.runtimeconfig.json* 파일
- 프로젝트 참조 또는 NuGet 패키지 참조를 통해 프로젝트가 종속된 다른 라이브러리

.NET Core 3.0 이전 버전을 대상으로 하는 실행 가능 프로젝트의 경우 NuGet의 라이브러리 종속성은 일반적으로 출력 폴더에 복사되지 않습니다.  런타임에 NuGet 전역 패키지 폴더에서 확인됩니다. 따라서 `dotnet build`의 제품을 실행하기 위해 다른 컴퓨터로 전송할 준비가 되지 않았습니다. 배포할 수 있는 애플리케이션 버전을 만들려면 [dotnet publish](dotnet-publish.md) 명령 등을 사용하여 애플리케이션을 게시해야 합니다. 자세한 내용은 [.NET Core 애플리케이션 배포](../deploying/index.md)를 참조하세요.

.NET Core 3.0 이상을 대상으로 하는 실행 가능 프로젝트의 경우 라이브러리 종속성이 출력 폴더에 복사됩니다. 따라서 웹 프로젝트 등에 다른 게시 특정 논리가 없는 경우 빌드 출력을 배포할 수 있습니다.

### <a name="implicit-restore"></a>암시적 복원

빌드하려면 애플리케이션의 종속성을 나열하는 *project.assets.json* 파일이 필요합니다. [`dotnet restore`](dotnet-restore.md)가 실행되면 파일이 만들어집니다. 자산 파일이 없으면 도구로 참조 어셈블리를 확인할 수 없으므로 오류가 발생합니다.

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

### <a name="executable-or-library-output"></a>실행 파일 또는 라이브러리 출력

프로젝트가 실행 가능한지 아닌지 여부는 프로젝트 파일의 `<OutputType>` 속성으로 확인할 수 있습니다. 다음 예제에서는 실행 코드를 생성하는 프로젝트를 보여 줍니다.

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

라이브러리를 생성하려면 `<OutputType>` 속성을 생략하거나 속성 값을 `Library`로 변경합니다. 라이브러리의 IL DLL은 진입점을 포함하지 않으며 실행할 수 없습니다.

### <a name="msbuild"></a>MSBuild

`dotnet build`는 MSBuild를 사용하여 프로젝트를 빌드하므로 병렬 및 증분 빌드를 모두 지원합니다. 자세한 내용은 [증분 빌드](/visualstudio/msbuild/incremental-builds)를 참조하세요.

해당 옵션 외에도, `dotnet build` 명령은 속성 설정에 대한 `-p` 또는 로거를 정의하는 `-l`처럼 MSBuild 옵션도 수락합니다. 이러한 옵션에 대한 자세한 내용은 [MSBuild 명령줄 참조](/visualstudio/msbuild/msbuild-command-line-reference)를 확인하세요. 또는 [dotnet msbuild](dotnet-msbuild.md) 명령을 사용할 수도 있습니다.

`dotnet build` 실행은 `dotnet msbuild -restore` 실행과 같지만 출력의 기본 세부 정보 표시가 다릅니다.

## <a name="arguments"></a>인수

`PROJECT | SOLUTION`

빌드할 프로젝트 또는 솔루션 파일입니다. 프로젝트 또는 솔루션 파일을 지정하지 않으면 MSBuild는 현재 작업 디렉터리에서 *proj* 또는 *sln*으로 끝나는 파일 확장명이 있는 파일을 검색하고 해당 파일을 사용합니다.

## <a name="options"></a>옵션

- **`-c|--configuration <CONFIGURATION>`**

  빌드 구성을 정의합니다. 대부분의 프로젝트에 대한 기본값은 `Debug`이지만 프로젝트의 빌드 구성 설정을 재정의할 수 있습니다.

- **`-f|--framework <FRAMEWORK>`**

  특정 [프레임워크](../../standard/frameworks.md)에 대해 컴파일합니다. 프레임워크는 [프로젝트 파일](csproj.md)에 정의해야 합니다.

- **`--force`**

  마지막 복원이 성공한 경우에도 모든 종속성을 강제 확인합니다. 이 플래그를 지정하는 것은 *project.assets.json* 파일을 삭제하는 것과 같습니다.

- **`-h|--help`**

  명령에 대한 간단한 도움말을 출력합니다.

- **`--interactive`**

  명령이 중지되고 사용자 입력 또는 작업을 대기할 수 있도록 허용합니다. 예를 들어 인증을 완료합니다. .NET Core 3.0 SDK 이후 사용할 수 있습니다.

- **`--no-dependencies`**

  프로젝트 간(P2P) 참조를 무시하고 지정된 루트 프로젝트만 빌드합니다.

- **`--no-incremental`**

  빌드를 증분 빌드에 안전하지 않은 것으로 표시합니다. 이 플래그로 증분 컴파일이 해제되고 프로젝트 종속성 그래프를 강제로 완전히 다시 빌드합니다.

- **`--no-restore`**

  빌드하는 동안 암시적 복원을 실행하지 않습니다.

- **`--nologo`**

  시작 배너 또는 저작권 메시지를 표시하지 않습니다. .NET Core 3.0 SDK 이후 사용할 수 있습니다.

- **`-o|--output <OUTPUT_DIRECTORY>`**

  빌드된 이진 파일을 배치할 디렉터리입니다. 지정하지 않으면 기본 경로는 `./bin/<configuration>/<framework>/`입니다.  `TargetFrameworks` 속성을 통해 여러 개의 대상 프레임워크가 지정된 프로젝트의 경우 이 옵션을 지정할 때 `--framework`도 정의해야 합니다.

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  대상 런타임을 지정합니다. RID(런타임 식별자) 목록은 [RID 카탈로그](../rid-catalog.md)를 참조하세요.

- **`--source <SOURCE>`**

  복원 작업 중에 사용할 NuGet 패키지 소스의 URI입니다.

- **`-v|--verbosity <LEVEL>`**

  MSBuild의 자세한 정도 수준을 설정합니다. 허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다. 기본값은 `minimal`입니다.

- **`--version-suffix <VERSION_SUFFIX>`**

  프로젝트를 빌드할 때 사용할 `$(VersionSuffix)` 속성의 값을 설정합니다. `$(Version)` 속성이 설정되지 않은 경우에만 작동합니다. 그런 다음, `$(Version)`이 대시로 구분하여 `$(VersionSuffix)`와 결합된 `$(VersionPrefix)`로 설정됩니다.

## <a name="examples"></a>예

- 프로젝트 및 해당 종속성을 빌드합니다.

  ```dotnetcli
  dotnet build
  ```

- 릴리스 구성을 사용하여 프로젝트 및 해당 종속성을 빌드합니다.

  ```dotnetcli
  dotnet build --configuration Release
  ```

- 특정 런타임(이 예제의 경우 Ubuntu 18.04)에 대한 프로젝트 및 해당 종속성을 빌드합니다.

  ```dotnetcli
  dotnet build --runtime ubuntu.18.04-x64
  ```

- 프로젝트를 빌드하고 복원 작업 중 지정된 NuGet 패키지 소스를 사용합니다(.NET Core 2.0 SDK 이상 버전).

  ```dotnetcli
  dotnet build --source c:\packages\mypackages
  ```

- `-p`[MSBuild 옵션](#msbuild)을 사용하여 프로젝트를 빌드하고 버전 1.2.3.4를 빌드 매개 변수로 설정합니다.

  ```dotnetcli
  dotnet build -p:Version=1.2.3.4
  ```
