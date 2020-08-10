---
title: .NET Core 도구
description: .NET Core 도구를 설치, 사용, 업데이트 및 제거하는 방법을 설명합니다. 전역 도구, 도구 경로 도구 및 로컬 도구를 다룹니다.
author: KathleenDollard
ms.date: 02/12/2020
ms.openlocfilehash: 75bdedcbc3ebe9c23477795415076d160ab9a642
ms.sourcegitcommit: 7499bdb428d63ed0e19e97f54d3d576c41598659
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/31/2020
ms.locfileid: "87455728"
---
# <a name="how-to-manage-net-core-tools"></a>.NET Core 도구를 관리하는 방법

**이 문서의 적용 대상:**  ✔️ .NET Core 2.1 SDK 이상 버전

.NET Core 도구는 콘솔 애플리케이션을 포함하는 특별한 NuGet 패키지입니다. 다음과 같은 방법으로 컴퓨터에 도구를 설치할 수 있습니다.

* 전역 도구로

  도구 이진 파일이 PATH 환경 변수에 추가된 기본 디렉터리에 설치됩니다. 해당 위치를 지정하지 않고 컴퓨터의 모든 디렉터리에서 도구를 호출할 수 있습니다. 한 버전의 도구가 컴퓨터의 모든 디렉터리에 사용됩니다.

* 사용자 지정 위치에서 전역 도구로(도구 경로 도구라고도 함)

  도구 이진 파일이 사용자가 지정하는 위치에 설치됩니다. 설치 디렉터리에서 또는 명령 이름으로 디렉터리를 제공하거나 PATH 환경 변수에 디렉터리를 추가하여 이 도구를 호출할 수 있습니다. 한 버전의 도구가 컴퓨터의 모든 디렉터리에 사용됩니다.

* 로컬 도구로(.NET Core SDK 3.0 이상에 적용됨)

  도구 이진 파일이 기본 디렉터리에 설치됩니다. 설치 디렉터리 또는 하위 디렉터리에서 도구를 호출합니다. 디렉터리마다 동일한 도구의 다른 버전을 사용할 수 있습니다.
  
  .NET CLI는 매니페스트 파일을 사용하여 디렉터리에 로컬로 설치되는 도구를 추적합니다. 매니페스트 파일을 소스 코드 리포지토리의 루트 디렉터리에 저장하면 참가자가 리포지토리를 복제하고 매니페스트 파일에 나열된 모든 도구를 설치하는 단일 .NET Core CLI 명령을 호출할 수 있습니다.

> [!IMPORTANT]
> .NET Core 도구는 완전 신뢰로 실행됩니다. 작성자를 신뢰하지 않는 한 .NET Core 도구를 설치하지 마세요.

## <a name="find-a-tool"></a>도구 찾기

현재 .NET Core에는 도구 검색 기능이 없습니다. 다음은 도구를 찾는 몇 가지 방법입니다.

* ".NET 도구" 패키지 유형 필터를 사용하여 [NuGet](https://www.nuget.org) 웹 사이트를 검색합니다. 자세한 내용은 [패키지 찾기 및 선택](/nuget/consume-packages/finding-and-choosing-packages)을 참조하세요.
* [natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools) GitHub 리포지토리에서 도구 목록을 확인합니다.
* [ToolGet](https://www.toolget.net/)을 사용하여 .NET 도구를 검색합니다.
* [dotnet/aspnetcore GitHub 리포지토리의 Tools 디렉터리](https://github.com/dotnet/aspnetcore/tree/master/src/Tools)에서 ASP.NET Core 팀이 만든 도구의 소스 코드를 참조합니다.
* [.NET Core dotnet 진단 도구](../diagnostics/index.md#net-core-dotnet-diagnostic-global-tools)에서 진단 도구에 대해 자세히 알아보세요.

## <a name="check-the-author-and-statistics"></a>작성자 및 통계 확인

.NET Core 도구는 완전 신뢰로 실행되고 전역 도구는 PATH 환경 변수에 추가되므로 매우 강력할 수 있습니다. 신뢰할 수 없는 사용자의 도구를 다운로드하지 마세요.

도구가 NuGet에서 호스팅되는 경우 도구를 검색하여 작성자 및 통계를 확인할 수 있습니다.

## <a name="install-a-global-tool"></a>전역 도구 설치

도구를 전역 도구로 설치하려면 다음 예제와 같이 [dotnet tool install](dotnet-tool-install.md)의 `-g` 또는 `--global` 옵션을 사용합니다.

```dotnetcli
dotnet tool install -g dotnetsay
```

출력은 다음 예제와 같이 도구 및 설치된 버전을 호출하는 데 사용되는 명령을 보여 줍니다.

```output
You can invoke the tool using the following command: dotnetsay
Tool 'dotnetsay' (version '2.1.4') was successfully installed.
```

도구 이진 파일의 기본 위치는 운영 체제에 따라 달라집니다.

| OS          | 경로                          |
|-------------|-------------------------------|
| Linux/macOS | `$HOME/.dotnet/tools`         |
| Windows     | `%USERPROFILE%\.dotnet\tools` |

이 위치는 SDK를 처음 실행할 때 사용자의 경로에 추가되므로 전역 도구는 도구 위치를 지정하지 않고 모든 디렉터리에서 호출할 수 있습니다.

도구 액세스는 컴퓨터 전역이 아닌 사용자별로 적용됩니다. 전역 도구는 도구를 설치한 사용자만 사용할 수 있습니다.

### <a name="install-a-global-tool-in-a-custom-location"></a>사용자 지정 위치에 전역 도구 설치

도구를 사용자 지정 위치에 전역 도구로 설치하려면 다음 예제와 같이 [dotnet tool install](dotnet-tool-install.md)의 `--tool-path` 옵션을 사용합니다.

Windows에서:

```dotnetcli
dotnet tool install dotnetsay --tool-path c:\dotnet-tools
```

Linux 또는 macOS에서:

```dotnetcli
dotnet tool install dotnetsay --tool-path ~/bin
```

.NET Core SDK는 이 위치를 PATH 환경 변수에 자동으로 추가하지 않습니다. [도구 경로 도구를 호출](#invoke-a-tool-path-tool)하려면 다음 방법 중 하나를 사용하여 명령을 사용할 수 있도록 해야 합니다.

* PATH 환경 변수에 설치 디렉터리를 추가합니다.
* 도구를 호출할 때 전체 경로를 지정합니다.
* 설치 디렉터리 내에서 도구를 호출합니다.

## <a name="install-a-local-tool"></a>로컬 도구 설치

**.NET Core 3.0 SDK 이상에 적용됩니다.**

로컬 액세스 전용(현재 디렉터리 및 하위 디렉터리용) 도구를 설치하려면 매니페스트 파일에 도구를 추가해야 합니다. 도구 매니페스트 파일을 만들려면 `dotnet new tool-manifest` 명령을 실행합니다.

```dotnetcli
dotnet new tool-manifest
```

이 명령은 *.config* 디렉터리 아래에 *dotnet-tools.json*이라는 매니페스트 파일을 만듭니다. 매니페스트 파일에 로컬 도구를 추가하려면 다음 예제와 같이 [dotnet tool install](dotnet-tool-install.md) 명령을 사용하고 `--global` 및 `--tool-path` 옵션을 **생략**합니다.

```dotnetcli
dotnet tool install dotnetsay
```

명령 출력은 다음 예제와 같이 새로 설치된 도구가 있는 매니페스트 파일을 보여 줍니다.

```console
You can invoke the tool from this directory using the following command:
dotnet tool run dotnetsay
Tool 'dotnetsay' (version '2.1.4') was successfully installed.
Entry is added to the manifest file /home/name/botsay/.config/dotnet-tools.json.
```

다음 예제에서는 두 개의 로컬 도구가 설치된 매니페스트 파일을 보여 줍니다.

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "botsay": {
      "version": "1.0.0",
      "commands": [
        "botsay"
      ]
    },
    "dotnetsay": {
      "version": "2.1.3",
      "commands": [
        "dotnetsay"
      ]
    }
  }
}
```

일반적으로 로컬 도구는 리포지토리의 루트 디렉터리에 추가합니다. 저장소에 매니페스트 파일을 체크 인한 후에는 리포지토리에서 코드를 체크 아웃하는 개발자가 최신 매니페스트 파일을 가져옵니다. 매니페스트 파일에 나열된 모든 도구를 설치하려면 `dotnet tool restore` 명령을 실행합니다.

```dotnetcli
dotnet tool restore
```

출력은 복원된 도구를 나타냅니다.

```console
Tool 'botsay' (version '1.0.0') was restored. Available commands: botsay
Tool 'dotnetsay' (version '2.1.3') was restored. Available commands: dotnetsay
Restore was successful.
```

## <a name="install-a-specific-tool-version"></a>특정 도구 버전 설치

시험판 버전 또는 특정 버전의 도구를 설치하려면 다음 예제와 같이 `--version` 옵션을 사용하여 버전 번호를 지정합니다.

```dotnetcli
dotnet tool install dotnetsay --version 2.1.3
```

## <a name="use-a-tool"></a>도구 사용

도구를 호출하는 데 사용하는 명령은 사용자가 설치하는 패키지의 이름과 다를 수 있습니다. 현재 컴퓨터에 현재 사용자에 대해 설치되어 있는 모든 도구를 표시하려면 [dotnet tool list](dotnet-tool-list.md) 명령을 사용합니다.

```dotnetcli
dotnet tool list
```

출력에는 다음 예제와 같이 각 도구의 버전 및 명령이 표시됩니다.

```console
Package Id      Version      Commands       Manifest
-------------------------------------------------------------------------------------------
botsay          1.0.0        botsay         /home/name/repository/.config/dotnet-tools.json
dotnetsay       2.1.3        dotnetsay      /home/name/repository/.config/dotnet-tools.json
```

이 예제에서는 목록에 로컬 도구가 표시됩니다. 전역 도구를 보려면 `--global` 옵션을 사용하고, 도구 경로 도구를 보려면 `--tool-path` 옵션을 사용합니다.

### <a name="invoke-a-global-tool"></a>전역 도구 호출

전역 도구의 경우 도구 명령을 단독으로 사용합니다. 예를 들어 명령이 `dotnetsay` 또는 `dotnet-doc`이면 명령을 호출하는 데 사용하는 것입니다.

```console
dotnetsay
dotnet-doc
```

명령이 접두사 `dotnet-`으로 시작하는 경우 도구를 호출하는 다른 방법은 `dotnet` 명령을 사용하고 도구 명령 접두사를 생략하는 것입니다. 예를 들어 명령이 `dotnet-doc`인 경우 다음 명령은 도구를 호출합니다.

```dotnetcli
dotnet doc
```

그러나 다음 시나리오에서는 `dotnet` 명령을 사용하여 전역 도구를 호출할 수 없습니다.

* 전역 도구와 로컬 도구는 접두사 `dotnet-`가 있는 동일한 명령을 사용합니다.
* 로컬 도구에 대한 범위에 있는 디렉터리에서 전역 도구를 호출하려고 합니다.

이 시나리오에서는 `dotnet doc` 및 `dotnet dotnet-doc`이 로컬 도구를 호출합니다. 전역 도구를 호출하려면 명령을 단독으로 사용합니다.

```dotnetcli
dotnet-doc
```

### <a name="invoke-a-tool-path-tool"></a>도구 경로 도구 호출

`tool-path` 옵션을 사용하여 설치된 전역 도구를 호출하려면 [이 문서의 앞부분](#install-a-global-tool-in-a-custom-location)에서 설명한 대로 명령을 사용할 수 있도록 해야 합니다.

### <a name="invoke-a-local-tool"></a>로컬 도구 호출

로컬 도구를 호출하려면 설치 디렉터리 내에서 `dotnet` 명령을 사용해야 합니다. 다음 예제와 같이 긴 형식(`dotnet tool run <COMMAND_NAME>`) 또는 짧은 형식(`dotnet <COMMAND_NAME>`)을 사용할 수 있습니다.

```dotnetcli
dotnet tool run dotnetsay
dotnet dotnetsay
```

명령에 접두사 `dotnet-`가 있으면 도구를 호출할 때 접두사를 포함하거나 생략할 수 있습니다. 예를 들어 명령이 `dotnet-doc`인 경우 다음 예제 중 하나는 로컬 도구를 호출합니다.

```dotnetcli
dotnet tool run dotnet-doc
dotnet dotnet-doc
dotnet doc
```

## <a name="update-a-tool"></a>도구 업데이트

도구 업데이트는 원래 버전을 제거하고 안정적인 최신 버전을 다시 설치하는 것입니다. 도구를 업데이트하려면 도구를 설치하는 데 사용한 것과 동일한 옵션을 지정하여 [dotnet tool update](dotnet-tool-update.md) 명령을 사용합니다.

```dotnetcli
dotnet tool update --global <packagename>
dotnet tool update --tool-path <packagename>
dotnet tool update <packagename>
```

로컬 도구의 경우 SDK는 현재 디렉터리와 부모 디렉터리를 검색하여 패키지 ID를 포함하는 첫 번째 매니페스트 파일을 찾습니다. 매니페스트 파일에 이러한 패키지 ID가 없는 경우 SDK는 가장 가까운 매니페스트 파일에 새 항목을 추가합니다.

## <a name="uninstall-a-tool"></a>도구 제거

도구를 설치하는 데 사용한 것과 동일한 옵션을 지정하여 [dotnet tool uninstall](dotnet-tool-uninstall.md) 명령을 사용하여 도구를 제거합니다.

```dotnetcli
dotnet tool uninstall --global <packagename>
dotnet tool uninstall --tool-path <packagename>
dotnet tool uninstall <packagename>
```

로컬 도구의 경우 SDK는 현재 디렉터리와 부모 디렉터리를 검색하여 패키지 ID를 포함하는 첫 번째 매니페스트 파일을 찾습니다.

## <a name="get-help-and-troubleshoot"></a>도움말 보기 및 문제 해결

사용 가능한 `dotnet tool` 명령 목록을 가져오려면 다음 명령을 입력합니다.

```dotnetcli
dotnet tool --help
```

도구 사용 지침을 얻으려면 다음 명령 중 하나를 입력하거나 도구의 웹 사이트를 참조하세요.

```dotnetcli
<command> --help
dotnet <command> --help
```

도구를 설치하거나 실행하지 못하는 경우 [.NET Core 도구 사용 문제 해결](troubleshoot-usage-issues.md)을 참조하세요.

## <a name="see-also"></a>참조

- [자습서: .NET Core CLI를 사용하여 .NET Core 도구 만들기](global-tools-how-to-create.md)
- [자습서: .NET Core CLI를 사용하여 .NET Core 전역 도구 설치 및 사용](global-tools-how-to-use.md)
- [자습서: .NET Core CLI를 사용하여 .NET Core 로컬 도구 설치 및 사용](local-tools-how-to-use.md)
