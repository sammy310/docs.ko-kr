---
title: .NET Core CLI
titleSuffix: ''
description: .NET Core CLI 및 해당 기능에 대한 개요입니다.
ms.date: 08/14/2017
ms.openlocfilehash: b0a8e0dd8cf77bb6f7567c27e9972f62515ec0f2
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920486"
---
# <a name="net-core-cli-overview"></a>.NET Core CLI 개요

.NET Core CLI(명령줄 인터페이스)는 .NET Core 애플리케이션의 개발, 빌드, 실행 및 게시에 사용되는 플랫폼 간 도구 체인입니다.

.NET Core CLI는 [.NET Core SDK](../sdk.md)에 포함되어 있습니다. .NET Core SDK를 설치하는 방법에 대한 자세한 내용은 [.NET Core SDK 설치](../install/sdk.md)를 참조하세요.

## <a name="cli-commands"></a>CLI 명령

다음은 기본적으로 설치되는 명령입니다.

<!-- markdownlint-disable MD025 -->

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

**기본 명령**

- [new](dotnet-new.md)
- [restore](dotnet-restore.md)
- [build](dotnet-build.md)
- [publish](dotnet-publish.md)
- [run](dotnet-run.md)
- [test](dotnet-test.md)
- [vstest](dotnet-vstest.md)
- [pack](dotnet-pack.md)
- [migrate](dotnet-migrate.md)
- [clean](dotnet-clean.md)
- [sln](dotnet-sln.md)
- [help](dotnet-help.md)
- [store](dotnet-store.md)

**프로젝트 수정 명령**

- [add package](dotnet-add-package.md)
- [add reference](dotnet-add-reference.md)
- [remove package](dotnet-remove-package.md)
- [remove reference](dotnet-remove-reference.md)
- [list reference](dotnet-list-reference.md)

**고급 명령**

- [nuget delete](dotnet-nuget-delete.md)
- [nuget locals](dotnet-nuget-locals.md)
- [nuget push](dotnet-nuget-push.md)
- [msbuild](dotnet-msbuild.md)
- [dotnet install script](dotnet-install-script.md)

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

**기본 명령**

- [new](dotnet-new.md)
- [restore](dotnet-restore.md)
- [build](dotnet-build.md)
- [publish](dotnet-publish.md)
- [run](dotnet-run.md)
- [test](dotnet-test.md)
- [vstest](dotnet-vstest.md)
- [pack](dotnet-pack.md)
- [migrate](dotnet-migrate.md)
- [clean](dotnet-clean.md)
- [sln](dotnet-sln.md)

**프로젝트 수정 명령**

- [add package](dotnet-add-package.md)
- [add reference](dotnet-add-reference.md)
- [remove package](dotnet-remove-package.md)
- [remove reference](dotnet-remove-reference.md)
- [list reference](dotnet-list-reference.md)

**고급 명령**

- [nuget delete](dotnet-nuget-delete.md)
- [nuget locals](dotnet-nuget-locals.md)
- [nuget push](dotnet-nuget-push.md)
- [msbuild](dotnet-msbuild.md)
- [dotnet install script](dotnet-install-script.md)

---

CLI에는 프로젝트에 맞게 추가 도구를 지정할 수 있는 확장성 모델이 있습니다. 자세한 내용은 [.NET Core CLI 확장성 모델](extensibility.md) 항목을 참조하세요.

## <a name="command-structure"></a>명령 구조

CLI 명령 구조는 [드라이버("dotnet")](#driver), [명령](#command), 경우에 따라 [arguments](#arguments) 및 [options](#options) 명령으로 구성됩니다. *my_app* 디렉터리에서 실행될 때 다음 명령이 표시하는 것처럼 새 콘솔 앱 생성 및 명령줄에서 실행 등의 대부분의 CLI 작업에서 이 패턴을 볼 수 있습니다.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

```dotnetcli
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

```dotnetcli
dotnet new console
dotnet restore
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

---

### <a name="driver"></a>드라이버

이 드라이버는 [dotnet](dotnet.md)으로 이름이 지정되며 [프레임워크 종속 앱](../deploying/index.md)을 실행하거나 명령을 실행합니다. 

예를 들어 프레임워크 종속 앱을 실행하려면 드라이버 다음에 앱을 지정합니다(예: `dotnet /path/to/my_app.dll`). 앱의 DLL이 있는 폴더에서 명령을 실행할 때는 `dotnet my_app.dll`을 실행하기만 하면 됩니다. 특정 버전의 .NET Core 런타임을 사용하려면 `--fx-version <VERSION>` 옵션을 사용합니다([dotnet 명령](dotnet.md) 참조).

드라이버에 명령을 제공하면 `dotnet.exe`가 CLI 명령 실행 프로세스를 시작합니다. 예:

```dotnetcli
dotnet build
```

먼저 드라이버는 사용할 SDK 버전을 확인합니다. ['global.json'](global-json.md)이 없는 경우 사용 가능한 최신 버전의 SDK가 사용됩니다. 이는 머신의 최신 버전에 따라 미리 보기 또는 안정적인 버전일 수 있습니다.  SDK 버전이 확인되면 명령을 실행합니다.

### <a name="command"></a>명령

이 명령이 작업을 수행합니다. 예를 들어 `dotnet build`는 코드를 빌드합니다. `dotnet publish`는 코드를 게시합니다. 명령은 `dotnet {command}` 규칙을 사용하여 콘솔 애플리케이션으로 구현됩니다.

### <a name="arguments"></a>인수

명령줄에서 전달하는 인수는 호출되는 명령에 대한 인수입니다. 예를 들어 `dotnet publish my_app.csproj`를 실행하면 `my_app.csproj` 인수는 게시할 프로젝트를 나타내고 `publish` 명령에 전달됩니다.

### <a name="options"></a>옵션

명령줄에서 전달하는 옵션은 호출되는 명령에 대한 옵션입니다. 예를 들어 `dotnet publish --output /build_output`을 실행하면 `--output` 옵션 및 해당 값이 `publish` 명령에 전달됩니다.

## <a name="migration-from-projectjson"></a>project.json에서 마이그레이션

Preview 2 도구를 사용하여 *project.json* 기반 프로젝트를 생성하는 경우 [dotnet migrate](dotnet-migrate.md) 항목에서 릴리스 도구와 함께 사용할 MSBuild/ *.csproj*로 프로젝트를 마이그레이션하기 위한 정보를 참조하세요. Preview 2 도구 릴리스 이전에 만든 .NET Core 프로젝트의 경우 [DNX에서.NET Core CLI(project.json)로 마이그레이션](../migration/from-dnx.md)의 지침에 따라 프로젝트를 수동으로 업데이트한 후 `dotnet migrate`를 사용하거나 프로젝트를 직접 업그레이드합니다.

## <a name="see-also"></a>참조

- [dotnet/sdk GitHub 리포지토리](https://github.com/dotnet/sdk/)
- [.NET Core 설치 가이드](https://aka.ms/dotnetcoregs)
