---
title: dotnet 설치 스크립트
description: .NET Core SDK 및 공유 런타임을 설치하는 dotnet-install 스크립트에 대해 알아봅니다.
ms.date: 09/22/2020
ms.openlocfilehash: 35161edd2a4862e064373d75f1e19396983f3a64
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91078205"
---
# <a name="dotnet-install-scripts-reference"></a>dotnet-install 스크립트 참조

## <a name="name"></a>이름

`dotnet-install.ps1` | `dotnet-install.sh` - .NET Core SDK 및 공유 런타임을 설치하는 데 사용되는 스크립트입니다.

## <a name="synopsis"></a>개요

Windows:

```powershell
dotnet-install.ps1 [-Architecture <ARCHITECTURE>] [-AzureFeed]
    [-Channel <CHANNEL>] [-DryRun] [-FeedCredential]
    [-InstallDir <DIRECTORY>] [-JSonFile <JSONFILE>]
    [-NoCdn] [-NoPath] [-ProxyAddress] [-ProxyBypassList <LIST_OF_URLS>]
    [-ProxyUseDefaultCredentials] [-Runtime <RUNTIME>]
    [-SkipNonVersionedFiles] [-UncachedFeed] [-Verbose]
    [-Version <VERSION>]

Get-Help ./dotnet-install.ps1
```

Linux/macOS:

```bash
dotnet-install.sh  [--architecture <ARCHITECTURE>] [--azure-feed]
    [--channel <CHANNEL>] [--dry-run] [--feed-credential]
    [--install-dir <DIRECTORY>] [--jsonfile <JSONFILE>]
    [--no-cdn] [--no-path] [--runtime <RUNTIME>] [--runtime-id <RID>]
    [--skip-non-versioned-files] [--uncached-feed] [--verbose]
    [--version <VERSION>]

dotnet-install.sh --help
```

또한 bash 스크립트는 PowerShell 스위치를 읽으므로 Linux/macOS 시스템에서 스크립트와 함께 PowerShell 스위치를 사용할 수 있습니다.

## <a name="description"></a>설명

`dotnet-install` 스크립트는 .NET Core CLI 및 공유 런타임을 포함하는 .NET Core SDK의 비관리자 설치를 수행합니다. 다음과 같은 두 가지 스크립트가 있습니다.

* Windows에서 작동하는 PowerShell 스크립트
* Linux/macOS에서 작동하는 bash 스크립트

### <a name="purpose"></a>용도

 이 스크립트는 다음과 같은 CI(연속 통합) 시나리오에 사용하기 위한 것입니다.

* 사용자 조작 및 관리자 권한 없이 SDK를 설치해야 합니다.
* SDK 설치를 여러 CI 실행 간에 유지할 필요가 없습니다.

  일반적인 이벤트 시퀀스는 다음과 같습니다.
  * CI가 트리거됩니다.
  * CI에서 이러한 스크립트 중 하나를 사용하여 SDK를 설치합니다.
  * CI에서 작업을 완료하고 SDK 설치를 비롯해 임시 데이터를 지웁니다.

개발 환경을 설정하거나 앱을 실행하려면 이러한 스크립트가 아니라 설치 관리자를 사용합니다.

### <a name="recommended-version"></a>추천 버전

안정적인 버전의 스크립트를 사용하는 것이 좋습니다.

- Bash(Linux/macOS): <https://dot.net/v1/dotnet-install.sh>
- PowerShell(Windows): <https://dot.net/v1/dotnet-install.ps1>

### <a name="script-behavior"></a>스크립트 동작

두 스크립트의 동작은 동일합니다. 스크립트는 CLI 빌드 저장 위치에서 ZIP/tarball 파일을 다운로드하여 기본 위치나 `-InstallDir|--install-dir`로 지정한 위치에 설치를 계속 진행합니다.

기본적으로 설치 스크립트는 SDK를 다운로드하고 설치합니다. 공유 런타임만 가져오려는 경우 `-Runtime|--runtime` 인수를 지정합니다.

기본적으로 스크립트는 현재 세션에 대한 $PATH에 설치 위치를 추가합니다. `-NoPath|--no-path` 인수를 지정하여 이 기본 동작을 재정의합니다. 스크립트는 `DOTNET_ROOT` 환경 변수를 설정하지 않습니다.

스크립트를 실행하기 전에 필요한 모든 [종속성](../install/windows.md#dependencies)을 설치하세요.

`-Version|--version` 인수를 사용하여 특정 버전을 설치할 수 있습니다. 버전은 `2.1.0`과 같이 세 부분으로 구성된 버전 번호로 지정해야 합니다. 버전을 지정하지 않은 경우 스크립트는 `latest` 버전을 설치합니다.

설치 스크립트는 Windows에서 레지스트리를 업데이트하지 않습니다. 단지 압축된 이진 파일을 다운로드하여 폴더에 복사합니다. 레지스트리 키 값을 업데이트하려면 .NET Core 설치 관리자를 사용합니다.

## <a name="options"></a>옵션

- **`-Architecture|--architecture <ARCHITECTURE>`**

  설치할 .NET Core 바이너리의 아키텍처입니다. 가능한 값은 `<auto>`, `amd64`, `x64`, `x86`, `arm64` 및 `arm`입니다. 기본값은 현재 실행 중인 OS 아키텍처를 나타내는 `<auto>`입니다.

- **`-AzureFeed|--azure-feed`**

  설치 관리자에 대한 Azure 피드의 URL을 지정합니다. 이 값은 변경하지 않는 것이 좋습니다. 기본값은 `https://dotnetcli.azureedge.net/dotnet`입니다.

- **`-Channel|--channel <CHANNEL>`**

  설치에 대한 소스 채널을 지정합니다. 가능한 값은 다음과 같습니다.

  - `Current` - 최신 릴리스입니다.
  - `LTS` - 장기 지원 채널(지원되는 최신 릴리스)입니다.
  - 특정 릴리스를 나타내는 X.Y 형식의 두 부분으로 된 버전입니다(예: `2.1` 또는 `3.0`).
  - 예를 들어 분기 이름은 `release/3.1.1xx` 또는 `master`(야간 릴리스의 경우)입니다. 미리 보기 채널에서 버전을 설치하려면 이 옵션을 사용합니다. [설치 관리자 및 이진 파일](https://github.com/dotnet/core-sdk#installers-and-binaries)에 나열된 채널 이름을 사용합니다.

  기본값은 `LTS`입니다. .NET 지원 채널에 대한 자세한 내용은 [.NET 지원 정책](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 페이지를 참조하세요.

- **`-DryRun|--dry-run`**

  설정하면 스크립트에서 설치를 수행하지는 않지만, 대신 현재 요청된 버전의 .NET Core CLI를 일관되게 설치하기 위해 사용할 명령줄을 표시합니다. 예를 들어 `latest` 버전을 지정하면 빌드 스크립트에서 이 명령을 결정적으로 사용할 수 있도록 특정 버전에 대한 링크를 표시합니다. 또한 직접 설치하거나 다운로드하는 것을 선호하는 경우 이진 파일 위치를 표시합니다.

- **`-FeedCredential|--feed-credential`**

  Azure 피드에 추가할 쿼리 문자열로 사용됩니다. public이 아닌 Blob 스토리지 계정을 사용하도록 URL을 변경할 수 있습니다.

- **`--help`**

  스크립트에 대한 도움말을 출력합니다. Bash 스크립트에만 적용됩니다. PowerShell의 경우 `Get-Help ./dotnet-install.ps1`을 사용합니다.

- **`-InstallDir|--install-dir <DIRECTORY>`**

  설치 경로를 지정합니다. 디렉터리가 없을 경우 만듭니다. 기본값은 *%LocalAppData%\Microsoft\dotnet*(Windows) 또는 */usr/share/dotnet*(Linux/macOS)입니다. 이진 파일은 이 디렉터리에 바로 배치됩니다.

- **`-JSonFile|--jsonfile <JSONFILE>`**

  SDK 버전을 확인하는 데 사용되는 [global.json](global-json.md) 파일의 경로를 지정합니다. *global.json* 파일에 `sdk:version`의 값이 있어야 합니다.

- **`-NoCdn|--no-cdn`**

  [Azure CDN(Content Delivery Network)](/azure/cdn/cdn-overview)에서 다운로드할 수 없도록 설정하고 캐시되지 않은 피드를 바로 사용합니다.

- **`-NoPath|--no-path`**

  설정하면 설치 폴더를 현재 세션의 경로로 내보내지 않습니다. 기본적으로 스크립트는 경로를 수정하므로 설치 후 .NET Core CLI를 즉시 사용할 수 있습니다.

- **`-ProxyAddress`**

  설정된 경우 설치 관리자에서 웹 요청을 만들 때 프록시를 사용합니다. (Windows에만 유효함)

- **`-ProxyBypassList <LIST_OF_URLS>`**

  `ProxyAddress`를 사용하여 설정하는 경우 프록시를 우회하는 쉼표로 구분된 URL 목록을 제공합니다. (Windows에만 유효함)

- **`ProxyUseDefaultCredentials`**

  설정하면 설치 관리자가 프록시 주소를 사용할 때 현재 사용자의 자격 증명을 사용합니다. (Windows에만 유효함)

- **`-Runtime|--runtime <RUNTIME>`**

  전체 SDK가 아닌 공유 런타임만 설치합니다. 가능한 값은 다음과 같습니다.

  - `dotnet` - `Microsoft.NETCore.App` 공유 런타임입니다.
  - `aspnetcore` - `Microsoft.AspNetCore.App` 공유 런타임입니다.
  - `windowsdesktop` - `Microsoft.WindowsDesktop.App` 공유 런타임입니다.

- **`--runtime-id <RID>`**

  도구가 설치되는 [런타임 식별자](../rid-catalog.md)를 지정합니다. 휴대용 Linux에 `linux-x64`를 사용합니다. (Linux/macOS에만 유효함)

- **`-SharedRuntime|--shared-runtime`**

  > [!NOTE]
  > 이 매개 변수는 더 이상 사용되지 않으며 스크립트의 이후 버전에서 제거될 수 있습니다. 대신 `-Runtime|--runtime` 옵션을 사용하는 것이 좋습니다.

  전체 SDK가 아니라 공유 런타임 비트만 설치합니다. 이 옵션은 `-Runtime|--runtime dotnet`을 지정하는 것과 같습니다.

- **`-SkipNonVersionedFiles|--skip-non-versioned-files`**

  *dotnet.exe*와 같은 버전이 없는 파일이 있을 경우 해당 파일의 설치를 건너뜁니다.

- **`-UncachedFeed|--uncached-feed`**

  이 설치 관리자가 사용하는 캐시되지 않은 피드의 URL을 변경할 수 있습니다. 이 값은 변경하지 않는 것이 좋습니다.

- **`-Verbose|--verbose`**

  진단 정보를 표시합니다.

- **`-Version|--version <VERSION>`**

  특정 빌드 버전을 나타냅니다. 가능한 값은 다음과 같습니다.

  - `latest` - 채널의 최신 빌드입니다(`-Channel` 옵션과 함께 사용됨).
  - 특정 빌드 버전을 나타내는 X.Y.Z 형식의 세 부분으로 구성된 버전이며 `-Channel` 옵션을 대체합니다. 예를 들어 `2.0.0-preview2-006120`을 참조하십시오.

  지정하지 않으면 `-Version`은 기본값인 `latest`로 설정됩니다.

## <a name="examples"></a>예

- 기본 위치에 최신 LTS(장기 지원) 버전을 설치합니다.

  Windows:

  ```powershell
  ./dotnet-install.ps1 -Channel LTS
  ```

  macOS/Linux:

  ```bash
  ./dotnet-install.sh --channel LTS
  ```

- 3\.1 채널에서 지정된 위치에 최신 버전을 설치합니다.

  Windows:

  ```powershell
  ./dotnet-install.ps1 -Channel 3.1 -InstallDir C:\cli
  ```

  macOS/Linux:

  ```bash
  ./dotnet-install.sh --channel 3.1 --install-dir ~/cli
  ```

- 3\.0.0 버전의 공유 런타임을 설치합니다.

  Windows:

  ```powershell
  ./dotnet-install.ps1 -Runtime dotnet -Version 3.0.0
  ```

  macOS/Linux:

  ```bash
  ./dotnet-install.sh --runtime dotnet --version 3.0.0
  ```

- 스크립트를 얻어 회사 프록시 뒤에 2.1.2 버전을 설치합니다(Windows에만 해당).

  ```powershell
  Invoke-WebRequest 'https://dot.net/v1/dotnet-install.ps1' -Proxy $env:HTTP_PROXY -ProxyUseDefaultCredentials -OutFile 'dotnet-install.ps1';
  ./dotnet-install.ps1 -InstallDir '~/.dotnet' -Version '2.1.2' -ProxyAddress $env:HTTP_PROXY -ProxyUseDefaultCredentials;
  ```

- 스크립트 가져와서 .NET Core CLI one-liner 예제를 설치합니다.

  Windows:

  ```powershell
  # Run a separate PowerShell process because the script calls exit, so it will end the current PowerShell session.
  &powershell -NoProfile -ExecutionPolicy unrestricted -Command "[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; &([scriptblock]::Create((Invoke-WebRequest -UseBasicParsing 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"
  ```

  macOS/Linux:

  ```bash
  curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>
  ```

## <a name="see-also"></a>참조

- [.NET Core 릴리스](https://github.com/dotnet/core/releases)
- [.NET Core 런타임 및 SDK 다운로드 아카이브](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)
