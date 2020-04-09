---
title: dotnet publish 명령
description: dotnet publish 명령은 .NET Core 프로젝트 또는 솔루션을 디렉터리에 게시합니다.
ms.date: 02/24/2020
ms.openlocfilehash: 0e18220443f3713c86c257fcf401b98ddd716ebc
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588276"
---
# <a name="dotnet-publish"></a>dotnet publish

**이 문서의 적용 대상:**  ✔️ .NET Core 2.1 SDK 이상 버전

## <a name="name"></a>이름

`dotnet publish` - 호스팅 시스템에 배포하기 위해 애플리케이션 및 해당 종속성을 폴더에 게시합니다.

## <a name="synopsis"></a>개요

```dotnetcli
dotnet publish [<PROJECT>|<SOLUTION>] [-c|--configuration]
    [-f|--framework] [--force] [--interactive] [--manifest]
    [--no-build] [--no-dependencies] [--no-restore] [--nologo]
    [-o|--output] [-r|--runtime] [--self-contained]
    [--no-self-contained] [-v|--verbosity] [--version-suffix]

dotnet publish [-h|--help]
```

## <a name="description"></a>설명

`dotnet publish`는 애플리케이션을 컴파일하고 프로젝트 파일에 지정된 종속성을 읽은 다음 결과 파일 집합을 디렉터리에 게시합니다. 출력에는 다음과 같은 자산이 포함됩니다.

- *dll* 확장과 함께 어셈블리의 IL(중간 언어) 코드
- 프로젝트의 종속성을 모두 포함하는 *.deps.json* 파일
- 런타임에 대한 기타 구성 옵션(예: 가비지 수집 유형)과 애플리케이션에서 예상하는 공유 런타임을 지정하는 *.runtimeconfig.json* 파일
- 애플리케이션의 종속성은 NuGet 캐시에서 출력 폴더로 복사됩니다.

`dotnet publish` 명령의 출력이 실행을 위해 호스팅 시스템(예: 서버, PC, Mac, 랩톱)에 배포할 준비가 되었습니다. 이는 배포를 위해 애플리케이션을 준비하는 데 공식적으로 지원되는 유일한 방법입니다. 프로젝트에서 지정하는 배포 유형에 따라 호스팅 시스템에 .NET Core 공유 런타임이 설치되어 있을 수도 있고 그렇지 않을 수도 있습니다. 자세한 내용은 [.NET Core CLI를 사용하여 .NET Core 앱 게시](../deploying/deploy-with-cli.md)를 참조하세요.

### <a name="msbuild"></a>MSBuild

`dotnet publish` 명령은 `Publish` 대상을 불러오는 MSBuild를 호출합니다. `dotnet publish` 및 MSBuild에 전달된 모든 매개 변수. `-c` 및 `-o` 매개 변수는 각각 MSBuild의 `Configuration` 및 `OutputPath` 속성에 매핑됩니다.

`dotnet publish` 명령은 속성 설정에 대한 `-p` 및 로거를 정의하는 `-l` 같은 MSBuild 옵션을 수락합니다. 예를 들어 `-p:<NAME>=<VALUE>` 형식을 사용하여 MSBuild 속성을 설정할 수 있습니다. *.pubxml* 파일을 참조하여 게시 관련 속성을 설정할 수도 있습니다. 예를 들면 다음과 같습니다.

```dotnetcli
dotnet publish -p:PublishProfile=Properties\PublishProfiles\FolderProfile.pubxml
```

자세한 내용은 다음 자료를 참조하세요.

- [MSBuild 명령줄 참조](/visualstudio/msbuild/msbuild-command-line-reference)
- [ASP.NET Core 앱 배포용 Visual Studio 게시 프로필(.pubxml)](/aspnet/core/host-and-deploy/visual-studio-publish-profiles)
- [dotnet msbuild](dotnet-msbuild.md)

## <a name="arguments"></a>인수

- **`PROJECT|SOLUTION`**

  게시할 프로젝트 또는 솔루션입니다.
  
  * `PROJECT`는 [C#](csproj.md), F# 또는 Visual Basic 프로젝트 파일의 경로 및 파일 이름이거나 C#, F# 또는 Visual Basic 프로젝트 파일을 포함하는 디렉터리의 경로입니다. 디렉터리를 지정하지 않으면 현재 디렉터리로 기본 설정됩니다.

  * `SOLUTION`은 솔루션 파일 ( *.sln* 확장명)의 경로 및 파일 이름이거나 솔루션 파일을 포함하는 디렉터리의 경로입니다. 디렉터리를 지정하지 않으면 현재 디렉터리로 기본 설정됩니다. .NET Core 3.0 SDK 이후 사용할 수 있습니다.

## <a name="options"></a>옵션

- **`-c|--configuration <CONFIGURATION>`**

  빌드 구성을 정의합니다. 대부분의 프로젝트에 대한 기본값은 `Debug`이지만 프로젝트의 빌드 구성 설정을 재정의할 수 있습니다.

- **`-f|--framework <FRAMEWORK>`**

  지정한 [대상 프레임워크](../../standard/frameworks.md)에 대한 애플리케이션을 게시합니다. 프로젝트 파일에 대상 프레임워크를 지정해야 합니다.

- **`--force`**

  마지막 복원이 성공한 경우에도 모든 종속성을 강제 확인합니다. 이 플래그를 지정하는 것은 *project.assets.json* 파일을 삭제하는 것과 같습니다.

- **`-h|--help`**

  명령에 대한 간단한 도움말을 출력합니다.

- **`--interactive`**

  명령이 중지되고 사용자 입력 또는 작업을 대기할 수 있도록 허용합니다. 예를 들어 인증을 완료합니다. .NET Core 3.0 SDK 이후 사용할 수 있습니다.

- **`--manifest <PATH_TO_MANIFEST_FILE>`**

  앱을 통해 게시된 패키지 집합을 잘라내는 데 사용할 하나 이상의 [대상 매니페스트](../deploying/runtime-store.md)를 지정합니다. 매니페스트 파일은 [`dotnet store` 명령](dotnet-store.md) 출력의 일부입니다. 여러 매니페스트를 지정하려면 각 매니페스트에 대해 `--manifest` 옵션을 추가합니다.

- **`--no-build`**

  게시하기 전에 프로젝트를 빌드하지 않습니다. 또한 암시적으로 `--no-restore` 플래그를 설정합니다.

- **`--no-dependencies`**

  프로젝트 간 참조를 무시하고 루트 프로젝트만 복원합니다.

- **`--nologo`**

  시작 배너 또는 저작권 메시지를 표시하지 않습니다. .NET Core 3.0 SDK 이후 사용할 수 있습니다.

- **`--no-restore`**

  명령을 실행할 때 암시적 복원을 실행하지 않습니다.

- **`-o|--output <OUTPUT_DIRECTORY>`**

  출력 디렉터리의 경로를 지정합니다.
  
  지정하지 않으면 런타임 종속 실행 파일과 플랫폼 간 이진 파일에 대해 *[project_file_folder]./bin/[configuration]/[framework]/publish/* 로 기본 설정되고 자체 포함 실행 파일에 대해 *[project_file_folder]/bin/[configuration]/[framework]/[runtime]/publish/* 로 기본 설정됩니다.

  - .NET Core 3.x SDK 이상
  
    프로젝트를 게시할 때 상대 경로를 지정하는 경우 생성되는 출력 디렉터리는 프로젝트 파일 위치가 아니라 현재 작업 디렉터리에 대해 상대적입니다.

    솔루션을 게시할 때 상대 경로를 지정하는 경우 모든 프로젝트에 대한 모든 출력은 현재 작업 디렉터리에 대해 상대적인 지정 폴더로 이동합니다. 게시 출력을 각 프로젝트의 별도 폴더로 이동하려면 `--output` 옵션 대신 msbuild `PublishDir` 속성을 사용하여 상대 경로를 지정합니다. 예를 들어 `dotnet publish -p:PublishDir=.\publish`는 각 프로젝트의 게시 출력을 프로젝트 파일이 포함된 폴더 아래에 있는 `publish` 폴더로 보냅니다.

  - .NET Core 2.x SDK
  
    프로젝트를 게시할 때 상대 경로를 지정하는 경우 생성되는 출력 디렉터리는 현재 작업 디렉터리가 아니라 프로젝트 파일 위치에 대해 상대적입니다.

    솔루션을 게시할 때 상대 경로를 지정하는 경우 각 프로젝트의 출력은 프로젝트 파일 위치에 대해 상대적인 별도의 폴더로 이동합니다. 솔루션을 게시할 때 절대 경로를 지정하는 경우 모든 프로젝트에 대한 모든 게시 출력은 지정된 폴더로 이동합니다.

- **`--self-contained [true|false]`**

  대상 컴퓨터에 런타임을 설치할 필요가 없도록 애플리케이션을 통해 .NET Core 런타임을 게시합니다. 런타임 식별자가 지정되고 프로젝트가 라이브러리 프로젝트가 아니라 실행 가능 프로젝트인 경우 기본값은 `true`입니다. 자세한 내용은 [.NET Core application publishing](../deploying/index.md)(.NET Core 애플리케이션 게시) 및 [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md)(.NET Core CLI를 사용하여 .NET Core 앱 게시)를 참조하세요.

  `true` 또는 `false`를 지정하지 않고 이 옵션을 사용하는 경우 기본값은 `true`입니다. 이 경우 솔루션 또는 프로젝트 인수를 `--self-contained` 바로 뒤에 배치하지 마세요. 이 위치에 `true` 또는 `false`가 필요하기 때문입니다.

- **`--no-self-contained`**

  `--self-contained false`과 동일합니다. .NET Core 3.0 SDK 이후 사용할 수 있습니다.

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  지정된 런타임에 대한 애플리케이션을 게시합니다. RID(런타임 식별자) 목록은 [RID 카탈로그](../rid-catalog.md)를 참조하세요. 자세한 내용은 [.NET Core application publishing](../deploying/index.md)(.NET Core 애플리케이션 게시) 및 [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md)(.NET Core CLI를 사용하여 .NET Core 앱 게시)를 참조하세요.

- **`-v|--verbosity <LEVEL>`**

  명령의 세부 정보 표시 수준을 설정합니다. 허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다. 기본값은 `minimal`여야 합니다.

- **`--version-suffix <VERSION_SUFFIX>`**

  프로젝트 파일의 버전 필드에서 별표(`*`)를 대신할 버전 접미사를 정의합니다.

## <a name="examples"></a>예

- 현재 디렉터리에 있는 프로젝트에 대해 [런타임 종속 플랫폼 간 이진 파일](../deploying/index.md#produce-a-cross-platform-binary)을 만듭니다.

  ```dotnetcli
  dotnet publish
  ```

  .NET Core 3.0 SDK부터, 이 예제는 현재 플랫폼에 대해 [런타임 종속 실행 파일](../deploying/index.md#publish-runtime-dependent)도 만듭니다.

- 현재 디렉터리에 있는 프로젝트에 대해 특정 런타임에 대한 [자체 포함 실행 파일](../deploying/index.md#publish-self-contained)을 만듭니다.

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64
  ```

  RID가 프로젝트 파일 안에 있어야 합니다.

- 현재 디렉터리에 있는 프로젝트에 대해 특정 플랫폼에 대한 [런타임 종속 실행 파일](../deploying/index.md#publish-runtime-dependent)을 만듭니다.

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64 --self-contained false
  ```

  RID가 프로젝트 파일 안에 있어야 합니다. 이 예제는 .NET Core 3.0 SDK 이상 버전에 적용됩니다.

- 현재 디렉터리에 있는 프로젝트를 특정 런타임 및 대상 프레임워크에 대해 게시합니다.

  ```dotnetcli
  dotnet publish --framework netcoreapp3.1 --runtime osx.10.11-x64
  ```

- 지정된 프로젝트 파일을 게시합니다.

  ```dotnetcli
  dotnet publish ~/projects/app1/app1.csproj
  ```

- 현재 애플리케이션을 게시하되 복원 작업 중에 프로젝트 간(P2P) 참조는 복원하지 않고 루트 프로젝트만 복원합니다.

  ```dotnetcli
  dotnet publish --no-dependencies
  ```

## <a name="see-also"></a>참조

- [.NET Core application publishing overview](../deploying/index.md)(.NET Core 애플리케이션 게시 개요)
- [.NET Core CLI를 사용하여 .NET Core 앱 게시](../deploying/deploy-with-cli.md)
- [대상 프레임워크](../../standard/frameworks.md)
- [RID(런타임 식별자) 카탈로그](../rid-catalog.md)
- [macOS Catalina 공증 관련 사항](../install/macos-notarization-issues.md)
- [Directory structure of a published application](/aspnet/core/hosting/directory-structure)(게시된 애플리케이션의 디렉터리 구조)
- [MSBuild 명령줄 참조](/visualstudio/msbuild/msbuild-command-line-reference)
- [ASP.NET Core 앱 배포용 Visual Studio 게시 프로필(.pubxml)](/aspnet/core/host-and-deploy/visual-studio-publish-profiles)
- [dotnet msbuild](dotnet-msbuild.md)
