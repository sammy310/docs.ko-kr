---
title: dotnet nuget push 명령
description: dotnet nuget push 명령은 서버에 패키지를 푸시하고 게시합니다.
author: karann-msft
ms.date: 12/04/2019
ms.openlocfilehash: a352120efa199b871e67eb8ba2442bd69a9fc4ed
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789877"
---
# <a name="dotnet-nuget-push"></a>dotnet nuget push

**이 문서의 적용 대상:**  ✔️ .NET Core 1.x SDK 이상 버전

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>이름

`dotnet nuget push` - 서버에 패키지를 푸시하고 게시합니다.

## <a name="synopsis"></a>개요

```dotnetcli
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [--interactive] [-k|--api-key] [-n|--no-symbols]
    [--no-service-endpoint] [-s|--source] [--skip-duplicate] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```

## <a name="description"></a>설명

`dotnet nuget push` 명령은 서버에 패키지를 푸시하고 게시합니다. push 명령은 시스템의 NuGet 구성 파일에 있는 서버 및 자격 증명 정보 또는 구성 파일 체인을 사용합니다. 구성 파일에 대한 자세한 내용은 [NuGet 동작 구성](/nuget/consume-packages/configuring-nuget-behavior)을 참조하세요. NuGet의 기본 구성은 *%AppData%\NuGet\NuGet.config*(Windows) 또는 *$HOME/.local/share*(Linux/macOS)를 로드한 다음 드라이브의 루트에서 시작되고 현재 디렉터리에서 끝나는 *nuget.config* 또는 *.nuget\nuget.config*를 로드하여 가져올 수 있습니다.

## <a name="arguments"></a>인수

* **`ROOT`**

  푸시되는 패키지에 대한 파일 경로를 지정합니다.

## <a name="options"></a>옵션

* **`-d|--disable-buffering`**

  메모리 사용량을 줄이려면 HTTP(S) 서버로 푸시할 때 버퍼링을 사용하지 않도록 설정합니다.

* **`--force-english-output`**

  고정 영어 기반 문화권을 사용하여 애플리케이션을 강제로 실행합니다.

* **`-h|--help`**

  명령에 대한 간단한 도움말을 출력합니다.

* **`--interactive`**

  명령 차단을 허용하고 인증 등의 작업에 대해 수동 작업을 요구합니다. .NET Core 2.2 SDK 이후 사용할 수 있는 옵션입니다.

* **`-k|--api-key <API_KEY>`**

  서버에 대한 API 키입니다.

* **`-n|--no-symbols`**

  기호를 푸시하지 않습니다(있는 경우).

* **`--no-service-endpoint`**

  소스 URL에 “api/v2/package”를 추가하지 마세요. .NET Core 2.1 SDK 이후 사용할 수 있는 옵션입니다.

* **`-s|--source <SOURCE>`**

  서버 URL을 지정합니다. 이 옵션은 NuGet 구성 파일에 `DefaultPushSource` 구성 값이 설정되어 있지 않을 때 필요합니다.

* **`--skip-duplicate`**

  여러 패키지를 HTTP(S) 서버로 푸시할 때 푸시를 계속할 수 있도록 409 충돌 응답을 경고로 처리합니다. .NET Core 3.1 SDK부터 사용할 수 있습니다.

* **`-sk|--symbol-api-key <API_KEY>`**

  기호 서버에 대한 API 키입니다.

* **`-ss|--symbol-source <SOURCE>`**

  기호 서버 URL을 지정합니다.

* **`-t|--timeout <TIMEOUT>`**

  서버에 푸시하기 위한 제한 시간(초)을 지정합니다. 기본값은 300 초(5 분)입니다. 0(0초)을 지정하면 기본값이 적용됩니다.

## <a name="examples"></a>예

* 기본 푸시 소스에 *foo.nupkg*를 푸시하여 API 키를 지정합니다.

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a
  ```

* 공식 NuGet 서버에 *foo.nupkg*를 푸시하여 API 키를 지정합니다.

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://api.nuget.org/v3/index.json
  ```
  
  * 사용자 지정 푸시 소스 `https://customsource`에 *foo.nupkg*를 푸시하여 API 키를 지정합니다.

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://customsource/
  ```

* 기본 푸시 소스 *foo.nupkg*를 푸시합니다.

  ```dotnetcli
  dotnet nuget push foo.nupkg
  ```

* 기본 기호 소스에 *foo.symbols.nupkg*를 푸시합니다.

  ```dotnetcli
  dotnet nuget push foo.symbols.nupkg
  ```

* 360초 시간 제한을 지정하여 기본 푸시 소스에 *foo.nupkg*를 푸시합니다.

  ```dotnetcli
  dotnet nuget push foo.nupkg --timeout 360
  ```

* 기본 푸시 소스에 현재 디렉터리에 있는 모든 *.nupkg* 파일을 푸시합니다.

  ```dotnetcli
  dotnet nuget push *.nupkg
  ```

  > [!NOTE]
  > 이 명령이 작동하지 않는 경우 이전 버전의 SDK(.NET Core 2.1 SDK 및 이전 버전)에 존재했던 버그 때문일 수 있습니다.
  > 이 문제를 해결하려면 SDK 버전을 업그레이드하거나 대신 `dotnet nuget push **/*.nupkg` 명령을 실행합니다.

* HTTP(S) 서버가 409 충돌 응답을 반환하더라도 모든 *.nupkg* 파일을 푸시합니다.

  ```dotnetcli
  dotnet nuget push *.nupkg --skip-duplicate
  ```
